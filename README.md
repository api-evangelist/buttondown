# Buttondown

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Buttondown is an independent, bootstrapped email newsletter platform for writers, creators and developers, offering a Markdown and rich-text editor, subscriber management with tags, segments and metadata, automations, RSS-to-email, surveys, comments, paid subscriptions via Stripe with no revenue share, custom sending and hosting domains, and hosted archives. Its public REST API covers 133 operations across 29 resource areas — subscribers, emails, tags, segments, automations, webhooks, imports, exports, surveys, forms, images, snippets, prices and more — described by a live OpenAPI 3.1 document, backed by an 82-event webhook catalog, a date-based version train, idempotency keys, and a first-party CLI for syncing newsletter content to a local folder.

**Areas:** Analytics · Automation · Email · Markdown · Newsletters · Paid Subscriptions · Software-as-a-Service · Subscribers · Webhook · Segmentation · Developer Tools · Marketing

## Buttondown on APIs.io

Everything profiled for Buttondown is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/buttondown/](https://apis.io/providers/buttondown/)** — or go straight to one of the APIs or properties below.

### APIs (31)

- [Buttondown Accounts API](https://apis.io/apis/buttondown/buttondown-accounts-api/) — The Accounts API from Buttondown — 1 operation(s) covering the authenticated account and its plan/feature state.
- [Buttondown Advertising Units API](https://apis.io/apis/buttondown/buttondown-advertising-units-api/) — The Advertising Units API from Buttondown — 6 operation(s) covering newsletter sponsorship inventory — advertising units and the slots sold against them.
- [Buttondown API Requests API](https://apis.io/apis/buttondown/buttondown-api-requests-api/) — The API Requests API from Buttondown — 2 operation(s) covering the account's own API request log, including retained response bodies for idempotent requests.
- [Buttondown Attachments API](https://apis.io/apis/buttondown/buttondown-attachments-api/) — The Attachments API from Buttondown — 4 operation(s) covering files attached to emails and inbox replies.
- [Buttondown Automations API](https://apis.io/apis/buttondown/buttondown-automations-api/) — The Automations API from Buttondown — 7 operation(s) covering triggered and scheduled email sequences, their actions, timing and analytics.
- [Buttondown Books API](https://apis.io/apis/buttondown/buttondown-books-api/) — The Books API from Buttondown — 5 operation(s) covering the Bookshop.org book catalog embedded in newsletters.
- [Buttondown Bulk Actions API](https://apis.io/apis/buttondown/buttondown-bulk-actions-api/) — The Bulk Actions API from Buttondown — 2 operation(s) covering asynchronous mass operations over existing records.
- [Buttondown Comments API](https://apis.io/apis/buttondown/buttondown-comments-api/) — The Comments API from Buttondown — 5 operation(s) covering subscriber comments on emails, and their moderation state.
- [Buttondown Coupons API](https://apis.io/apis/buttondown/buttondown-coupons-api/) — The Coupons API from Buttondown — 1 operation(s) covering Stripe coupons available to a paid newsletter.
- [Buttondown Emails API](https://apis.io/apis/buttondown/buttondown-emails-api/) — The Emails API from Buttondown — 11 operation(s) covering drafting, scheduling, publishing, rendering and analyzing newsletter emails.
- [Buttondown Events API](https://apis.io/apis/buttondown/buttondown-events-api/) — The Events API from Buttondown — 2 operation(s) covering the unified event store that also powers webhooks.
- [Buttondown Exports API](https://apis.io/apis/buttondown/buttondown-exports-api/) — The Exports API from Buttondown — 3 operation(s) covering data exports of subscribers, emails and events.
- [Buttondown External Feeds API](https://apis.io/apis/buttondown/buttondown-external-feeds-api/) — The External Feeds API from Buttondown — 7 operation(s) covering RSS-to-email feeds, their polling cadence and the items they produce.
- [Buttondown Forms API](https://apis.io/apis/buttondown/buttondown-forms-api/) — The Forms API from Buttondown — 5 operation(s) covering hosted and embeddable subscription forms.
- [Buttondown Images API](https://apis.io/apis/buttondown/buttondown-images-api/) — The Images API from Buttondown — 4 operation(s) covering images hosted for use in emails and archives.
- [Buttondown Imports API](https://apis.io/apis/buttondown/buttondown-imports-api/) — The Imports API from Buttondown — 5 operation(s) covering bulk subscriber imports — the supported path for adding subscribers at volume.
- [Buttondown Newsletters API](https://apis.io/apis/buttondown/buttondown-newsletters-api/) — The Newsletters API from Buttondown — 7 operation(s) covering newsletter settings, branding, locale, and custom sending/hosting domain verification.
- [Buttondown Notes API](https://apis.io/apis/buttondown/buttondown-notes-api/) — The Notes API from Buttondown — 3 operation(s) covering internal notes attached to subscribers and team members.
- [Buttondown Ping API](https://apis.io/apis/buttondown/buttondown-ping-api/) — The Ping API from Buttondown — 1 operation(s) covering a connectivity and credential health check.
- [Buttondown Prices API](https://apis.io/apis/buttondown/buttondown-prices-api/) — The Prices API from Buttondown — 3 operation(s) covering paid-subscription pricing and products.
- [Buttondown Public API](https://apis.io/apis/buttondown/buttondown-public-api/) — The Public API from Buttondown — 1 operation(s) covering the unauthenticated public archive search.
- [Buttondown Segments API](https://apis.io/apis/buttondown/buttondown-segments-api/) — The Segments API from Buttondown — 5 operation(s) covering saved, reusable audiences built from tag and metadata filters.
- [Buttondown Snippets API](https://apis.io/apis/buttondown/buttondown-snippets-api/) — The Snippets API from Buttondown — 5 operation(s) covering reusable content snippets referenced from emails.
- [Buttondown Subscribers API](https://apis.io/apis/buttondown/buttondown-subscribers-api/) — The Subscribers API from Buttondown — 12 operation(s) covering subscriber lifecycle — creation, updates, tags, referrals, automations and Stripe subscriptions.
- [Buttondown Survey Responses API](https://apis.io/apis/buttondown/buttondown-survey-responses-api/) — The Survey Responses API from Buttondown — 3 operation(s) covering responses collected from newsletter surveys.
- [Buttondown Surveys API](https://apis.io/apis/buttondown/buttondown-surveys-api/) — The Surveys API from Buttondown — 5 operation(s) covering surveys embedded in emails and on the archive.
- [Buttondown Tags API](https://apis.io/apis/buttondown/buttondown-tags-api/) — The Tags API from Buttondown — 6 operation(s) covering subscriber tags and their analytics.
- [Buttondown Users API](https://apis.io/apis/buttondown/buttondown-users-api/) — The Users API from Buttondown — 5 operation(s) covering team members on the account and their permissions.
- [Buttondown Webhooks API](https://apis.io/apis/buttondown/buttondown-webhooks-api/) — The Webhooks API from Buttondown — 7 operation(s) covering webhook registration, delivery attempts, and test fires.
- [Buttondown Newsletter Platform](https://apis.io/apis/buttondown/newsletter-platform/) — The Buttondown hosted newsletter platform provides a markdown-based composition experience, subscriber management, delivery infrastructure, analytics,…
- [Buttondown Buttondown API](https://apis.io/apis/buttondown/buttondown-buttondown-api-api/) — The Buttondown API API from Buttondown — 0 operation(s) for buttondown api.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Buttondown Webhooks](https://apis.io/asyncapis/buttondown/buttondown-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [buttondown-mcp.yml](https://apis.io/servers/buttondown/buttondown-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Buttondown Agentic Access](https://apis.io/agentic-access/buttondown/buttondown-agentic-access/)

#### Examples (2)

Example requests and responses.

- [Buttondown Enums](https://apis.io/examples/buttondown/buttondown-enums/)
- [Buttondown Fixtures](https://apis.io/examples/buttondown/buttondown-fixtures/)

#### Collections (30)

Postman and Open Collection request collections.

- [Buttondown API](https://apis.io/collections/buttondown/open-buttondown/)
- [Buttondown Accounts API](https://apis.io/collections/buttondown/open-buttondown-accounts-api/)
- [Buttondown Advertising Units API](https://apis.io/collections/buttondown/open-buttondown-advertising-units-api/)
- [Buttondown API Requests API](https://apis.io/collections/buttondown/open-buttondown-api-requests-api/)
- [Buttondown Attachments API](https://apis.io/collections/buttondown/open-buttondown-attachments-api/)
- [Buttondown Automations API](https://apis.io/collections/buttondown/open-buttondown-automations-api/)
- [Buttondown Books API](https://apis.io/collections/buttondown/open-buttondown-books-api/)
- [Buttondown Bulk Actions API](https://apis.io/collections/buttondown/open-buttondown-bulk-actions-api/)
- [Buttondown Comments API](https://apis.io/collections/buttondown/open-buttondown-comments-api/)
- [Buttondown Coupons API](https://apis.io/collections/buttondown/open-buttondown-coupons-api/)
- [Buttondown Emails API](https://apis.io/collections/buttondown/open-buttondown-emails-api/)
- [Buttondown Events API](https://apis.io/collections/buttondown/open-buttondown-events-api/)
- [Buttondown Exports API](https://apis.io/collections/buttondown/open-buttondown-exports-api/)
- [Buttondown External Feeds API](https://apis.io/collections/buttondown/open-buttondown-external-feeds-api/)
- [Buttondown Forms API](https://apis.io/collections/buttondown/open-buttondown-forms-api/)
- [Buttondown Images API](https://apis.io/collections/buttondown/open-buttondown-images-api/)
- [Buttondown Imports API](https://apis.io/collections/buttondown/open-buttondown-imports-api/)
- [Buttondown Newsletters API](https://apis.io/collections/buttondown/open-buttondown-newsletters-api/)
- [Buttondown Notes API](https://apis.io/collections/buttondown/open-buttondown-notes-api/)
- [Buttondown Ping API](https://apis.io/collections/buttondown/open-buttondown-ping-api/)
- [Buttondown Prices API](https://apis.io/collections/buttondown/open-buttondown-prices-api/)
- [Buttondown public API](https://apis.io/collections/buttondown/open-buttondown-public-api/)
- [Buttondown Segments API](https://apis.io/collections/buttondown/open-buttondown-segments-api/)
- [Buttondown Snippets API](https://apis.io/collections/buttondown/open-buttondown-snippets-api/)
- [Buttondown Subscribers API](https://apis.io/collections/buttondown/open-buttondown-subscribers-api/)
- …and 5 more published on APIs.io

#### Overlays (29)

OpenAPI overlays, including conversational phrasing for each operation.

- [Buttondown Accounts Overlay](https://apis.io/overlays/buttondown/buttondown-accounts-overlay/)
- [Buttondown Advertising Units Overlay](https://apis.io/overlays/buttondown/buttondown-advertising-units-overlay/)
- [Buttondown Api Requests Overlay](https://apis.io/overlays/buttondown/buttondown-api-requests-overlay/)
- [Buttondown Attachments Overlay](https://apis.io/overlays/buttondown/buttondown-attachments-overlay/)
- [Buttondown Automations Overlay](https://apis.io/overlays/buttondown/buttondown-automations-overlay/)
- [Buttondown Books Overlay](https://apis.io/overlays/buttondown/buttondown-books-overlay/)
- [Buttondown Bulk Actions Overlay](https://apis.io/overlays/buttondown/buttondown-bulk-actions-overlay/)
- [Buttondown Comments Overlay](https://apis.io/overlays/buttondown/buttondown-comments-overlay/)
- [Buttondown Coupons Overlay](https://apis.io/overlays/buttondown/buttondown-coupons-overlay/)
- [Buttondown Emails Overlay](https://apis.io/overlays/buttondown/buttondown-emails-overlay/)
- [Buttondown Events Overlay](https://apis.io/overlays/buttondown/buttondown-events-overlay/)
- [Buttondown Exports Overlay](https://apis.io/overlays/buttondown/buttondown-exports-overlay/)
- [Buttondown External Feeds Overlay](https://apis.io/overlays/buttondown/buttondown-external-feeds-overlay/)
- [Buttondown Forms Overlay](https://apis.io/overlays/buttondown/buttondown-forms-overlay/)
- [Buttondown Images Overlay](https://apis.io/overlays/buttondown/buttondown-images-overlay/)
- [Buttondown Imports Overlay](https://apis.io/overlays/buttondown/buttondown-imports-overlay/)
- [Buttondown Newsletters Overlay](https://apis.io/overlays/buttondown/buttondown-newsletters-overlay/)
- [Buttondown Notes Overlay](https://apis.io/overlays/buttondown/buttondown-notes-overlay/)
- [Buttondown Ping Overlay](https://apis.io/overlays/buttondown/buttondown-ping-overlay/)
- [Buttondown Prices Overlay](https://apis.io/overlays/buttondown/buttondown-prices-overlay/)
- [Buttondown Public Overlay](https://apis.io/overlays/buttondown/buttondown-public-overlay/)
- [Buttondown Segments Overlay](https://apis.io/overlays/buttondown/buttondown-segments-overlay/)
- [Buttondown Snippets Overlay](https://apis.io/overlays/buttondown/buttondown-snippets-overlay/)
- [Buttondown Subscribers Overlay](https://apis.io/overlays/buttondown/buttondown-subscribers-overlay/)
- [Buttondown Survey Responses Overlay](https://apis.io/overlays/buttondown/buttondown-survey-responses-overlay/)
- …and 4 more published on APIs.io

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Buttondown Authentication](https://apis.io/security/buttondown/buttondown-authentication/)
- [Buttondown Domain Security](https://apis.io/security/buttondown/buttondown-domain-security/)
- [Buttondown Vulnerability Disclosure](https://apis.io/security/buttondown/buttondown-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Buttondown Plans Pricing](https://apis.io/plans/buttondown/buttondown-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Buttondown Rate Limits](https://apis.io/rate-limits/buttondown/buttondown-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Buttondown Finops](https://apis.io/finops/buttondown/buttondown-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://buttondown.com/)
- [Documentation](https://docs.buttondown.com/)
- [Getting started](https://docs.buttondown.com/quickstart)
- [API reference](https://docs.buttondown.com/api-introduction)
- [Pricing](https://buttondown.com/pricing)
- [Sign up](https://buttondown.com/register)
- [Support](https://buttondown.com/support)
- [Blog](https://buttondown.com/blog)
- [Security](https://buttondown.com/blog/security)
- [Terms of service](https://buttondown.com/legal/terms)
- [Privacy policy](https://buttondown.com/legal/privacy)
- [GitHub](https://github.com/buttondown)
- [Status](https://status.buttondown.com)

## API Evangelist rating

**Kin Score 62.9** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 64.4 |
| Contract governance | 4.5 |
| Operational transparency | 92.1 |
| Developer ergonomics | 73.2 |
| Access clarity | 65.8 |

**Agent readiness 42.3** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 25.8** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/buttondown/](https://apis.io/providers/buttondown/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Buttondown: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/buttondown/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
