# funeralOne (funeralone)

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
