# American Gene Technologies

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

American Gene Technologies International Inc. (AGT) is a privately held gene and cell therapy
company founded in 2007 and headquartered at 9713 Key West Avenue, 5th Floor, Rockville, Maryland —
a 27,000 sq ft laboratory and office across from the National Cancer Institute campus, housing a
Vector Production Facility and a Translational Science Laboratory. AGT operates a proprietary
lentiviral gene-delivery platform and develops cell and gene therapies for HIV, phenylketonuria
(PKU) and solid tumors (gamma-delta T cell immuno-oncology).

## Is there an API?

**AGT publishes no product API, no developer portal and no API documentation, and runs no developer
program.** That was verified, not assumed. Probed on 2026-08-06 and all 404 / non-resolving:

`/openapi.json` · `/swagger.json` · `/api-docs` · `/docs` · `/graphql` · `/llms.txt` ·
`/.well-known/security.txt` · `/.well-known/openid-configuration` ·
`/.well-known/oauth-authorization-server` · `/.well-known/oauth-protected-resource` ·
`/.well-known/api-catalog` · `/.well-known/ai-plugin.json` · `/.well-known/agent-card.json` ·
`/.well-known/agent.json` · `/wp-json/mcp` — and no `api.`, `docs.`, `developer(s).`, `status.`,
`trust.` or `security.` subdomain resolves. No GitHub organization, no package on npm or PyPI, no
Postman workspace, no CLI, no SDK.

## What this profile catalogues

One real, live, machine-readable surface: the **WordPress REST content API** at
`https://www.americangene.com/wp-json` — 576 routes across 23 namespaces, of which **68 read
operations** were verified to return data anonymously. It is a platform default (WordPress core and
its plugins), not something AGT markets — but the content in it is first-party, because the site
build registered AGT-specific custom post types with `show_in_rest`:

| Collection | Path | Items (2026-08-06) |
|---|---|---|
| Blog posts | `/wp/v2/blog` | 106 |
| In the news | `/wp/v2/in-the-news` | 75 |
| News releases | `/wp/v2/news-releases` | 64 |
| Patents | `/wp/v2/patent` | 53 |
| Newsletters | `/wp/v2/agt-newsletters` | 18 |
| Advisory board | `/wp/v2/agt_advisors` | 7 |
| Videos | `/wp/v2/videos` | 5 |
| Gene therapy reference entries | `/wp/v2/gene_therapies` | 4 |
| Young Minds explainers | `/wp/v2/young_minds` | 4 |
| Milestones | `/wp/v2/milestones` | 1 |
| Corporate pages | `/wp/v2/pages` | 72 |
| Media library | `/wp/v2/media` | 2,997 |
| Search index | `/wp/v2/search` | 409 |

Two traps worth knowing: the core `/wp/v2/posts` collection is **empty** (the blog lives on the
custom `blog` type), and `/wp/v2/gene_therapies` lists **approved third-party** therapies
(Zolgensma, Yescarta, Kymriah, Zynteglo) published as educational context — not AGT's own pipeline.

## Artifacts

| Path | What it is |
|---|---|
| `openapi/` | OpenAPI 3.1 — 68 operations, 19 tags. **Derived by API Evangelist**, not published by AGT, from the `/wp-json/` route index plus each route's own `OPTIONS` self-description (which supplies every parameter and item schema verbatim). Raw source kept in `openapi/_source/`. |
| `overlays/` | OpenAPI Overlay 1.0.0 — the API Evangelist annotation layer on top of the derived spec. |
| `conventions/` | Pagination, sparse fieldsets, embedding, `context`, HAL-style `_links`, caching, CORS, versioning. |
| `errors/` | Five problem types, each triggered and captured live. WordPress `{code, message, data.status}` envelope — **not** RFC 9457. |
| `data-model/` | 15 entities, 15 taxonomies, relationships, live item counts. |
| `authentication/` | Application Passwords (HTTP Basic) is advertised but required by nothing modelled here. |
| `lifecycle/` | No versioning policy, no deprecation policy, no Sunset header, no SLA, no status page — recorded honestly. |
| `conformance/` | What this surface does and does not conform to. No compliance program is published. |
| `examples/` | Real captured request/response pairs, including every error. |
| `well-known/` | The `/.well-known/` probe results — all 404. An honest zero. |
| `security/` | Live TLS/DNS probe: TLS 1.3, no HSTS, no DNSSEC, no CAA, SPF present, DMARC `p=quarantine`. |
| `agentic-access/` | Recommended `x-agentic-access` contracts. All 68 operations classify as safe reads. |
| `skills/` | Three packaged Agent Skills, every step grounded in a real `operationId`. |
| `mcp/` | **Candidate only.** No MCP server exists — `/wp-json/mcp` returns `rest_no_route`. |
| `llms/` | Generated `llms.txt` (AGT publishes none). |

No `a2a/` artifact exists, and that is deliberate: no agent card was found at either well-known
path, and an agent card is the one artifact this pipeline will never author on a provider's behalf.

- https://www.americangene.com/
- https://forgeglobal.com/american-gene-technologies-international_stock/
