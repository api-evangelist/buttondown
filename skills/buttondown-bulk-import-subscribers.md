---
name: buttondown-bulk-import-subscribers
description: >-
  Migrate or bulk-load subscribers into Buttondown using the imports endpoint instead of looping
  create_subscriber, and poll the import to completion.
api: openapi/buttondown-imports-api-openapi.yml
operations:
  - create_import
  - retrieve_import
  - list_imports
  - update_import
  - create_bulk_action
  - retrieve_bulk_action
generated: '2026-08-13'
method: generated
source: openapi/_original/buttondown-openapi.json + https://docs.buttondown.com/api-rate-limits
---

# Bulk-load subscribers

Base URL: `https://api.buttondown.com/v1`. Auth: `Authorization: Token <api-key>`.

## Why not loop create_subscriber

`create_subscriber` is capped at **100 per day per newsletter**. Exceeding it returns a `400` — not a
`429` — whose body points at `POST /imports`. Any migration or backfill above a hundred addresses must
use the import path from the start; there is no retry that gets you around the cap.

## 1. Create the import

`create_import` — `POST /imports`. Supply the subscriber payload along with the import `type` and
`source`. `create_import` is one of the few write endpoints whose documented failure modes are
file-shaped: `invalid_file_type`, `malformed_csv`, `import_failure`.

Send `X-Idempotency-Key`. A retried import without one is a second import of the same list.

## 2. Poll to completion

`retrieve_import` — `GET /imports/{id}`. Read `status` (an `ImportStatus`) and `results` (an
`ImportResult` summarizing what landed and what was rejected). Poll, do not assume — an import is
asynchronous.

`list_imports` — `GET /imports` — enumerates past imports; it paginates like every list endpoint
(`page` query param, `count`/`next`/`previous`/`results` envelope).

## 3. Watch the completion events

Rather than polling, subscribe a webhook to the import- and export-adjacent events and react on
arrival. The event store is also readable at `GET /events`, so a poller and a webhook consumer see
the same records.

## 4. Bulk operations on subscribers already in the list

For mass changes to existing subscribers — not loading new ones — use `create_bulk_action`
(`POST /bulk_actions`) and poll `retrieve_bulk_action` (`GET /bulk_actions/{id}`) for
`BulkActionStatus`. Same asynchronous shape as imports.

## 5. Rate limits still apply

The global limit of **600 requests/minute** governs the polling loop too. Read `X-RateLimit-Remaining`
and `X-RateLimit-Reset` on each response; on `429`, sleep for `Retry-After` seconds. Poll on an
interval, not in a tight loop.
