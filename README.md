# Submittable (submittable)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Submittable is a submission management, grants, and applications platform used by foundations, nonprofits, corporations, and governments to collect, review, and manage forms, applications, submissions, and awards. It exposes a real, documented **public REST API (v4)** at `https://submittable-api.submittable.com` with read-and-write access to account data — submissions and their form-field entries, projects and forms, submitters (users), labels, review team members and assignments, funds and payment distributions, and message attachments.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/submittable/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/submittable/refs/heads/main/apis.yml)

## Access Model

The Submittable API is **real and documented, but account-gated**:

- **You need a Submittable account.** API access is enabled per account under **More > Integrations > API Access**, which issues an access token.
- **Authentication is HTTP Basic Auth.** The access token is sent as the **password** portion of the Basic Authentication header on every call.
- **Current version is v4** (`/v4`), with legacy **v3** (`/v3`) still reachable. In v4, submission and label identifiers are **GUIDs**, list endpoints page with **continuation tokens**, and the old v3 `requests`/`responses` endpoints are consolidated into v4 **entries**.
- **Rate limits:** roughly **10 transactions/second** and **10,000 transactions/hour**.
- The interactive v4 reference is served as a JavaScript single-page app. Live probing confirms the surface exists — `GET https://submittable-api.submittable.com/v4/submissions` returns **HTTP 401** without credentials.

Because the reference is account-gated and Submittable does not publish a machine-readable OpenAPI, the OpenAPI in this repo is **honestly modeled** from the documented resource groups. Paths for submissions, entries, projects, organizations/team, and submissions/team/assignment are drawn from Submittable's public docs; the remaining paths are modeled to reflect the named resource groups and are marked **endpointsModeled** in `review.yml`.

## Tags

- Submission Management
- Grants Management
- Applications
- Forms
- Nonprofit
- Corporate Social Responsibility
- Workflow

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Submittable Submissions API

List, retrieve, and update submissions — the applications and entries people send to your projects. Filter by project, status, label, or date; page with continuation tokens; read status, labels, assignments, and history.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Entries API

Read the form-field entries (answers) captured on submissions. In v4 the legacy v3 requests/responses endpoints are consolidated into the entries endpoints.

- **Human URL:** [https://submittable.help/en/articles/8563401-api-version-reference](https://submittable.help/en/articles/8563401-api-version-reference)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Projects and Forms API

List, create, duplicate, and modify projects (the forms people apply through) and manage form types.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Users (Submitters) API

Retrieve submitter information — the people who create accounts and send submissions to your projects.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Teams and Reviews API

Administer organization team members and assign submissions to reviewers for evaluation.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Labels API

Create and organize labels (tags) used to categorize and filter submissions.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

### Submittable Funds and Payments API

Manage funds (budgets and grant distributions) and retrieve payment records filterable by period.

- **Human URL:** [https://submittable-api.submittable.com/docs/v4/index.html](https://submittable-api.submittable.com/docs/v4/index.html)
- **Base URL:** `https://submittable-api.submittable.com/v4`

## Artifacts

- [OpenAPI](openapi/submittable-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/submittable.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/submittable.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Plans](plans/submittable-plans-pricing.yml)
- [Rate Limits](rate-limits/submittable-rate-limits.yml)
- [Fin Ops](finops/submittable-finops.yml)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/submittable)
- [Website](https://www.submittable.com)
- [Documentation](https://submittable-api.submittable.com/docs/v4/index.html)
- [Support Documentation](https://submittable.help/en/collections/1728753-integrations-api)
- [Pricing](https://www.submittable.com/pricing/)

## Pricing

Submittable pricing is **quote-based** (contact sales). It is organized around bundleable products — Grant and Application Management and a Corporate Social Responsibility (CSR) platform — plus an **Enterprise** offering. No public per-seat list price is published; API access is included with the platform (not billed as a separate metered product) and governed by the transaction rate limits above.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
