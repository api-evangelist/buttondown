---
name: buttondown-subscribe-and-tag
description: >-
  Add a subscriber to a Buttondown newsletter safely, handle the case where the address already
  exists, and apply tags for later segmentation — without creating duplicates or tripping the
  daily subscriber-creation cap.
api: openapi/buttondown-subscribers-api-openapi.yml
operations:
  - create_subscriber
  - retrieve_subscriber
  - update_subscriber
  - list_tags
  - create_tag
generated: '2026-08-13'
method: generated
source: openapi/_original/buttondown-openapi.json + https://docs.buttondown.com/api-subscribers-introduction
---

# Subscribe someone and tag them

Base URL: `https://api.buttondown.com/v1`.
Auth: `Authorization: Token <api-key>` — note the trailing space after `Token`.

## 1. Decide the collision behavior before you call

`create_subscriber` (`POST /subscribers`) takes an `X-Buttondown-Collision-Behavior` header. Pick it
deliberately; the default will fail on a repeat signup.

| Value | Behavior |
|---|---|
| `no_op` (default) | Returns `400` if a subscriber with that address already exists. |
| `overwrite` | Replaces the existing subscriber's data. **Cannot** change terminal types (`unsubscribed`, `blocked`, `complained`, `undeliverable`) — those return `400` `subscriber_suppressed`. |
| `add` | Merges into the existing subscriber, and resubscribes an `unsubscribed` subscriber as `regular`. |

For a signup form, `add` is almost always what you want.

## 2. Send an idempotency key

Set `X-Idempotency-Key` to a fresh UUID on every create. A retry with the same key returns the
original response instead of creating a second subscriber. Without it, a network retry is a
duplicate.

## 3. Create the subscriber

`create_subscriber` — `POST /subscribers` with `{"email_address": "...", "type": "regular", "tags": [...]}`.

Expect `201` with the `Subscriber` object.

## 4. Handle the errors you will actually get

Errors come back as `{code, detail, metadata}`. Read `code`, not `detail`.

- `email_invalid`, `email_empty` — the address is malformed. `metadata.field` names it.
- `email_already_exists` / `subscriber_already_exists` — re-run with `add`, or `PATCH` instead. Since
  2026-06-05 the `metadata` carries the existing `subscriber_id`; use it rather than searching.
- `subscriber_suppressed` — terminal type; `overwrite` cannot resurrect it. Use `update_subscriber`
  with `{"type": "regular"}` if resubscribing is intended.
- `email_blocked`, `ip_address_spammy`, `newsletter_not_accepting_subscribers` — do not retry.
- `tag_invalid` — see step 5.
- `422` with a `detail[]` array — schema validation. Each entry has `type`, `loc`, `msg`. Fix the
  field at `loc` and resend; do not retry unchanged.

## 5. Tags require the tags add-on

Passing a not-yet-existing tag name in `tags` implicitly creates it — but since 2026-07-24 that
requires a plan including tags, and returns `403` `feature_disabled` otherwise. Referencing tags that
already exist is unaffected.

Safe order: `list_tags` first; create anything missing with `create_tag`; then reference existing
tags on the subscriber. Handle `403 feature_disabled` from `create_tag` by degrading to untagged
rather than failing the signup.

## 6. Respect the rate limits

- Global: **600 requests/minute**. Read `X-RateLimit-Remaining` and `X-RateLimit-Reset` from every
  response and back off before you hit zero. On `429`, honor `Retry-After`.
- `create_subscriber` specifically: **100 per day**. Exceeding it returns `400` (not `429`) pointing
  at `POST /imports`. If you are adding subscribers in bulk, use `create_import` from the start —
  see `buttondown-bulk-import-subscribers`.

## 7. Verify

`retrieve_subscriber` — `GET /subscribers/{id_or_email}`. This endpoint accepts either the TypeID or
the email address, so you can confirm without having stored the ID.
