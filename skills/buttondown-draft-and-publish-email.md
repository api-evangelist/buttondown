---
name: buttondown-draft-and-publish-email
description: >-
  Compose a Buttondown email as a draft, target it at an audience, publish or schedule it, and read
  back its delivery analytics — using the publish endpoint rather than hand-patching status.
api: openapi/buttondown-emails-api-openapi.yml
operations:
  - create_email
  - update_email
  - retrieve_email
  - send_draft
  - publish_email
  - retrieve_email_analytics
  - list_segments
generated: '2026-08-13'
method: generated
source: openapi/_original/buttondown-openapi.json + https://docs.buttondown.com/api-emails-introduction
---

# Draft, target, publish

Base URL: `https://api.buttondown.com/v1`. Auth: `Authorization: Token <api-key>`.
Set `X-API-Version: 2026-04-01` explicitly so behavior does not drift when the newsletter's pinned
version changes underneath you.

## 1. Create the draft

`create_email` — `POST /emails` with `{"subject": "...", "body": "...", "status": "draft"}`.

Two guards will bite:

- **Frontmatter.** A body starting with a `---` delimiter is rejected with `400`
  `body_contains_frontmatter` — it is almost always a bug in the integration. If it is genuinely
  intended, pass `X-Buttondown-Live-Dangerously: true`.
- **Idempotency.** Send `X-Idempotency-Key`. A retried create without one produces a second draft.

Other codes to branch on: `subject_invalid`, `body_invalid`, `slug_invalid`, `email_duplicate`,
`email_not_confirmed`, `publish_date_invalid`, `publish_date_missing`, `tag_invalid`,
`sending_requires_confirmation`.

## 2. Target the audience

Two ways, and the difference matters:

- Set `filters` directly on the email (a `FilterGroup` of tag and metadata conditions).
- Apply a saved **segment**: `list_segments` (`GET /segments`) then copy its filters onto the email.

An email's audience is a **snapshot**. Applying a segment copies its filters at that moment — later
edits to the segment never change an email you have already sent or scheduled.

## 3. Preview before you send

`send_draft` — `POST /emails/{id}/send-draft` sends the draft to yourself for review. For a whole-
newsletter dress rehearsal, enable test mode (Settings → Danger Zone): every send is redirected to
the author with a `[TEST MODE]` subject prefix. Note test mode is newsletter-wide and cannot be
scoped to one email.

## 4. Publish

`publish_email` — `POST /emails/{id}/publish`.

- Empty body `{}` publishes immediately.
- Include `publish_date` to schedule.
- Accepts the same payload as `update_email`, so other fields can be adjusted in the same call.

Do **not** publish by hand-patching `status` and `publish_date` via `update_email`; that was the
pre-2026-06-30 workaround and the publish endpoint is the supported path.

## 5. Read results

- `retrieve_email` — `GET /emails/{id}` for current status.
- `retrieve_email_analytics` — `GET /emails/{id}/analytics` for opens, clicks and failure breakdowns.
- For per-recipient detail, read the event store: `GET /events` filtered by `event_type` in
  `delivered`, `opened`, `clicked`, `bounced`, `complained`, `rejected`, `replied`, `unsubscribed`.
  Since 2026-06-23 event IDs carry the `ext_evt_` prefix and metadata is normalized to
  `code`, `url`, `ip_address`, `os`, `browser`.

## 6. Pagination when listing

`list_emails` and every other list endpoint use page-number pagination: pass `page`, read
`count`/`next`/`previous`/`results`, and follow `next` until it is `null`. A `Link` header with
`rel="next"`/`rel="prev"` is also returned.
