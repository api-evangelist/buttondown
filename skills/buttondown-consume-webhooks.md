---
name: buttondown-consume-webhooks
description: >-
  Register a Buttondown webhook, verify its HMAC signature, process the event payload, and recover
  from a disabled endpoint — plus how to backfill from the event store when deliveries were missed.
api: openapi/buttondown-webhooks-api-openapi.yml
operations:
  - create_webhook
  - list_webhooks
  - retrieve_webhook
  - update_webhook
  - delete_webhook
  - test_webhook
  - retrieve_webhook_attempts
  - list_events
  - get_event
generated: '2026-08-13'
method: generated
source: >-
  openapi/_original/buttondown-openapi.json (webhooks block + Webhook schema),
  https://docs.buttondown.com/events-and-webhooks-introduction
---

# Receive and verify Buttondown events

Base URL: `https://api.buttondown.com/v1`. Auth: `Authorization: Token <api-key>`.

## 1. Register the webhook

`create_webhook` — `POST /webhooks` with `{"url": "https://…", "event_types": [...], "description": "..."}`.

`event_types` is an array of `ExternalEventType` values. There are **82** of them across 18 families —
`subscriber.*` (the largest), `email.*`, `survey.*`, `form.*`, `export.*`, `date.*`, plus integration
families `stripe.*`, `shopify.*`, `bigcommerce.*`, `patreon.*` and `memberful.*`. Subscribe to only
the ones you handle; the full catalog with per-event descriptions is in
`asyncapi/buttondown-webhooks.yml`.

Configure a **signing key** when you create the webhook. Without one, deliveries arrive unsigned and
you have no way to prove they came from Buttondown.

## 2. Verify the signature

Each signed delivery carries:

```
X-Buttondown-Signature: sha256=<hmac>
```

The HMAC is SHA-256 over the **raw request body**, keyed with the webhook's signing key. Compute it
over the bytes you received before any JSON parsing, and compare in constant time. Reject on
mismatch.

## 3. Handle the payload

```json
{
  "id": "ext_evt_00000000000000000000000000",
  "event_type": "subscriber.created",
  "data": { }
}
```

- `id` is the event's TypeID — use it to deduplicate.
- `event_type` selects your handler.
- `data` shape varies by event type. On accounts with more than one newsletter it also carries a
  `newsletter` ID; branch on it, because one endpoint receives events for every newsletter the
  account owns.

## 4. Acknowledge correctly

Return **any 2xx** status. Do the work asynchronously and acknowledge fast.

**Five consecutive non-2xx responses disable the webhook.** This is the failure mode that silently
stops an integration: the endpoint 500s during a deploy, five events land, and deliveries stop.
Monitor for it — `retrieve_webhook` (`GET /webhooks/{id}`) returns a `WebhookStatus`, and
`retrieve_webhook_attempts` (`GET /webhooks/{id}/attempts`) returns the delivery log with the
responses your endpoint gave.

## 5. Test before you rely on it

`test_webhook` — `POST /webhooks/{id}/test` fires a synthetic delivery so you can verify signature
checking and routing without waiting for a real event.

## 6. Backfill what you missed

Webhooks and the REST event store are the **same** records since 2026-06-23. If your endpoint was
down, replay from `list_events` (`GET /events`) rather than asking for redelivery, and dedupe on the
event `id`. Note the migration consequences: IDs use the `ext_evt_` prefix (previously `em_evt_`), the
`event_type` filter accepts only `bounced`, `clicked`, `complained`, `delivered`, `opened`,
`rejected`, `replied` and `unsubscribed`, and metadata is normalized to `code`, `url`, `ip_address`,
`os` and `browser` — plus `from`, `subject`, `html` and `text` on `replied`.
