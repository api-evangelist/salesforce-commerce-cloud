# Salesforce Commerce Cloud (salesforce-commerce-cloud)

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

Salesforce Commerce Cloud (formerly Demandware) is an enterprise commerce platform supporting B2C and B2B storefronts, order management, product content, and headless commerce experiences. Commerce Cloud exposes two REST API products: the legacy Open Commerce API (OCAPI) and the modern Salesforce Commerce API (SCAPI), a unified RAML-defined API family built for headless commerce. SCAPI uses OAuth 2.0 via Salesforce Account Manager and groups APIs into Shopper, Data, and Admin tiers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/salesforce-commerce-cloud/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/salesforce-commerce-cloud/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Commerce
- E-Commerce
- Headless Commerce
- Salesforce
- B2C Commerce
- B2B Commerce
- Demandware

## Timestamps

- **Created:** 2026-05-11
- **Modified:** 2026-05-19

## APIs

### Salesforce Commerce API (SCAPI)

Modern REST API family for B2C Commerce Cloud built on a unified RAML specification, organized into Shopper, Data, and Admin APIs for headless commerce. Authentication uses OAuth 2.0 via Salesforce Account Manager (SLAS for shopper flows). Custom APIs allow developers to publish their own endpoints under the SCAPI framework using an OAS 3.0 schema contract.

- **Human URL:** [https://developer.salesforce.com/docs/commerce/commerce-api/overview](https://developer.salesforce.com/docs/commerce/commerce-api/overview)
- **Base URL:** `https://<short-code>.api.commercecloud.salesforce.com`

#### Tags

- SCAPI
- Headless Commerce
- Shopper API
- Data API
- Admin API
- OAuth 2.0

#### Properties

- [Documentation](https://developer.salesforce.com/docs/commerce/commerce-api/overview)
- [A P I  References](https://developer.salesforce.com/docs/commerce/commerce-api/references)
- [A P I  Explorer](https://api-explorer.commercecloud.salesforce.com)
- [Why  Use  S C A P I](https://developer.salesforce.com/docs/commerce/commerce-api/guide/why-use-scapi.html)
- [Custom  A P Is](https://developer.salesforce.com/docs/commerce/commerce-api/guide/custom-apis.html)
- [Postman Collection](collections/salesforce-commerce-cloud.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/salesforce-commerce-cloud.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Commerce API (OCAPI)

Legacy REST API for B2C Commerce Cloud, organized into Shop API, Data API, and Meta API. Authentication uses OAuth 2.0 via Salesforce Account Manager. OCAPI is deprecated for new projects in favor of SCAPI but remains supported on existing instances.

- **Human URL:** [https://developer.salesforce.com/docs/commerce/b2c-commerce/references](https://developer.salesforce.com/docs/commerce/b2c-commerce/references)
- **Base URL:** `https://<instance>.demandware.net/s/-/dw/data/v23_2`

#### Tags

- OCAPI
- Shop API
- Data API
- Meta API
- Legacy

#### Properties

- [Documentation](https://developer.salesforce.com/docs/commerce/b2c-commerce/references)
- [A P I  Explorer](https://developer.salesforce.com/docs/commerce/b2c-commerce/references/b2c-commerce-ocapi/apiexplorer.html)
- [Usage  Guide](https://developer.salesforce.com/docs/commerce/b2c-commerce/references/b2c-commerce-ocapi/apiusage.html)
- [Postman Collection](collections/salesforce-commerce-cloud.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/salesforce-commerce-cloud.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/commercecloud-demandware)
- [Website](https://www.salesforce.com/products/commerce-cloud/)
- [Documentation](https://developer.salesforce.com/docs/commerce)
- [A P I  Documentation](https://developer.salesforce.com/docs/commerce/commerce-api/overview)
- [A P I  Explorer](https://api-explorer.commercecloud.salesforce.com)
- [Postman  Collection](https://www.postman.com/salesforce-developers/salesforce-developers/documentation/1qkzgik/salesforce-commerce-b2c)
- [Pricing](https://www.salesforce.com/products/commerce-cloud/pricing/)
- [Sign Up](https://developer.salesforce.com/signup)
- [Trailhead](https://trailhead.salesforce.com/content/learn/modules/b2c-integration-approaches/b2c-explore-ocapi)
- [GitHub Organization](https://github.com/SalesforceCommerceCloud)
- [Support](https://help.salesforce.com/s/)
- [Agent Skill](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
