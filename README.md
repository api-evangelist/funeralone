# funeralOne (funeralone)

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

funeralOne is a funeral-home technology company whose **f1Connect** platform delivers funeral-home websites, memorial/tribute pages, **Life Tributes** tribute videos, memorial webcasting, and e-commerce for independent funeral homes. funeralOne publishes a real but **partner-gated** integration API at `https://api.funeralone.com` (docs at [api.funeralone.com/docs](https://api.funeralone.com/docs/)) that lets funeral-management / case-management systems push deceased, obituary, service-event, tribute-video, and family-administration data into a funeral home's f1Connect account, where it automatically populates the memorial website and Life Tributes.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/funeralone/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/funeralone/refs/heads/main/apis.yml)

## Access Model (important)

This API is **not self-serve**. Access is provisioned per integration partner:

- Authentication is **HTTP Basic**: the funeralOne-issued **API key** is the username, with a blank/dummy password.
- Each funeral-home customer is identified by an immutable **AccountExternalId** that funeralOne associates with your API key.
- Onboarding involves requesting an API key, supplying a test AccountExternalId, getting a test f1Connect account set up, submitting test cases, and having funeralOne associate customer accounts with your key.
- There is **no separately published API price** - the API is an integration benefit of the f1Connect platform, which is sold to funeral homes on a per-home subscription (commonly reported around **$245-$495/month plus per-case fees**) with add-on products (Life Tributes, webcasting, e-commerce).

Only the **Cases** resource is publicly documented. The broader website, e-commerce, and webcasting products are delivered through the f1Connect platform UI rather than a public API, so this catalog models **one honest API** (the Cases API) rather than fabricating separate Obituaries / Websites / Orders APIs that funeralOne does not document.

## Tags

- Funeral Homes
- Deathcare
- Obituaries
- Tribute Videos
- Memorial Websites
- Life Tributes
- Case Management
- Partner API

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### funeralOne Cases API

Partner integration surface for pushing funeral-case data into a funeral home's f1Connect account. A **Case** carries the deceased's identity and obituary, an optional Base64 photo, serving-location and family-address details, cemetery coordinates, a typed **Events** array (Visitation, Service, Shiva, Cemetery), **ExternalVideoUrls** (Tribute and Webcast videos, e.g. `videos.lifetributes.com`), and **FamilyAdmins** email invitations. Creating or updating a case automatically surfaces the deceased in the memorial website and Life Tributes.

- **Human URL:** [https://api.funeralone.com/docs/](https://api.funeralone.com/docs/)
- **Base URL:** `https://api.funeralone.com`

#### Endpoints

- `POST /cases` — create or update a case
- `GET /cases/AccountExternalId/{AccountExternalId}` — retrieve all cases for an account
- `GET /cases/AccountExternalId/{AccountExternalId}/CaseExternalId/{CaseExternalId}` — retrieve a specific case

#### Properties

- [Documentation](https://api.funeralone.com/docs/)
- [API Reference](https://api.funeralone.com/docs/)
- [OpenAPI](openapi/funeralone-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/funeralone.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

The OpenAPI models the three confirmed endpoints and reconstructs the Case object's fields from the developer documentation; funeralOne does not publish an official machine-readable spec, so field types and enum values are honestly inferred.

## Common Properties

- [Website](https://www.funeralone.com)
- [LinkedIn](https://www.linkedin.com/company/funeralone)
- [Documentation](https://api.funeralone.com/docs/)
- [Support](https://support.funeralone.com)
- [Plans](plans/funeralone-plans-pricing.yml)
- [Rate Limits](rate-limits/funeralone-rate-limits.yml)
- [Fin Ops](finops/funeralone-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
