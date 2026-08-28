# TIBER Agent-Compatible Publication, Licensing, and Discovery Profile v0

## Status and authority boundary

- **Owning issue:** [TIBER-Ops #72](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/72).
- **Architecture lineage:** [TIBER-Ops #11](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/11),
  [#64](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64), and
  [#67](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/67).
- **First canary lineage:** [TIBER-Teamstate #90](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/issues/90)
  and merged [PR #91](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/pull/91).
- **Audit baseline:** TIBER-Ops main at
  [11b35f368f35351b4f609f9973b69c03076e9581](https://github.com/Prometheus-Frameworks/TIBER-Ops/commit/11b35f368f35351b4f609f9973b69c03076e9581),
  inspected 2026-08-28.
- **This document is:** a proposal for review, a rights inventory, and a phased decision packet.
- **This document is not:** a license grant, legal advice, a publication approval, a crawler
  directive, an API authorization, a deployment, or an implementation-lane rotation.
- **No rights change:** naming MIT, CC BY 4.0, RSL, or any candidate profile below does not apply
  that license or permission to any repository or artifact. Rights change only through separately
  approved license files, notices, terms, and per-artifact manifests.
- **No runtime change:** Teamstate publication remains disabled. This document does not change
  service metadata, routes, robots policy, a sitemap, RSL, or any report bytes.
- **Lane note:** ML / modeling remains the sole active implementation lane. This docs-only
  audit/spec does not activate product, governance, publication, or agent-access implementation.

This is a technical and product-governance recommendation, not a legal opinion. Before TIBER
licenses a valuable dataset, adopts custom AI terms, or republishes source-derived material whose
rights are uncertain, the operator should obtain qualified legal review.

Current operational posture at this document's baseline:

    policy_status: proposal_only
    teamstate_artifact_publication_enabled: false
    unclassified_material_default_rights: permissions_not_granted_or_assumed
    eligible_agent_public_artifacts: []

---

## 1. Decision summary

TIBER should become deliberately agent-compatible, but it should not express that intent through
one blanket license or one crawler file.

The recommended v0 design is a layered profile:

1. **TIBER-authored code:** nominate MIT as the default candidate, aligned with the existing
   TIBER-Research license. Adoption is per repository and requires a separate decision.
2. **TIBER-authored documentation and methodology:** nominate CC BY 4.0 as the default public
   knowledge candidate. It permits reuse, adaptation, commercial use, text and data mining, and
   AI use subject to attribution and its other terms.
3. **Public report prose, visual explanation, and TIBER-owned structured outputs:** use the
   open-knowledge profile only after a field-level source-rights matrix proves that TIBER can
   grant the stated rights. Do not apply a blanket data license before that proof exists.
4. **Third-party, source-restricted, paid, private, candidate, fixture, or operator-local
   material:** exclude it from the open profile. Transformation, aggregation, or storage by TIBER
   does not create sublicensing authority.
5. **Agent-use classes:** decide search, AI indexing, AI input, and AI training independently in
   policy and machine-readable metadata.
6. **Recommended open profile:** for wholly TIBER-authored, rights-cleared public knowledge,
   permit all four classes under CC BY 4.0 with a clear attribution and citation target.
7. **Training-reserved alternative:** if TIBER wants to allow agent retrieval and answers but
   reserve training, do not combine CC BY 4.0 with an added training prohibition. That requires
   separately drafted, lawyer-reviewed terms and must not be described as open content or open
   data.
8. **Discovery:** use canonical public HTML, linked JSON, methodology and rights pages,
   Schema.org metadata, a sitemap, crawler-specific robots directives, and RSL as coordinated
   signals. Optional llms.txt guidance may help navigation but is not a license or access control.
9. **First canary:** the historical 2024 Teamstate report is technically shaped for a controlled
   pilot, but remains blocked on exact source-rights evidence, an adopted per-artifact license
   profile, exact-byte operator approval, and separately authorized discovery implementation.

The central rule is:

> An artifact is agent-compatible only when it is eligible to publish, rights-cleared for the
> declared uses, covered by an explicit license or a documented and verified public-domain /
> no-exclusive-right basis, machine-readable, attributable, discoverable, and served through a
> governed public boundary.

No single one of those conditions implies the others.

---

## 2. Five controls that must remain separate

| Control | Question answered | Example mechanism | What it does not prove |
| --- | --- | --- | --- |
| Publication eligibility | May TIBER expose this exact artifact as governed public truth? | Provenance, coverage, freshness, methodology, validator, exact operator approval | That TIBER owns or may sublicense every field |
| Source and legal rights | What may TIBER and downstream users legally do? | Source contracts, copyright/database rights, license files, notices, per-artifact terms | That crawlers will visit or agents will cite |
| Crawl and indexing policy | Which automated fetchers should retrieve which public paths? | robots.txt, crawler-specific user-agent rules, RSL discovery | Access control, authentication, or a copyright license |
| API/tool authorization | Who may call a service and under what operational limits? | Authentication, scopes, rate limits, API terms, MCP capability policy | Publication approval or redistribution rights |
| Discovery and citation | Can a search engine or agent find, understand, and attribute the artifact? | Canonical URLs, server-rendered HTML, JSON-LD, sitemap, linked JSON, citation metadata | Ranking, legal permission, or factual correctness |

A public GitHub repository is readable, but absent a license downstream users generally retain only
the permissions supplied by copyright law and GitHub's service terms. GitHub's own guidance states
that without a license, default copyright applies:
[Licensing a repository](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

robots.txt is a voluntary crawler instruction, not an authentication boundary. Sensitive or
unapproved content must never be placed on a public route and then “protected” only with robots
rules.

---

## 3. Agent-use vocabulary

TIBER should use four granular RSL 1.0 tokens selected for this profile as its vendor-neutral
policy vocabulary while keeping the underlying legal grant explicit. RSL spells its AI tokens
with hyphens; TIBER's JSON examples use snake_case keys and must publish an explicit mapping rather
than silently changing the standard's vocabulary:

| Use class | TIBER meaning | Typical operation |
| --- | --- | --- |
| search | General-purpose search crawling, indexing, and result display | A search engine indexes the canonical Teamstate page |
| ai-index | Building a persistent AI-oriented retrieval index or embedding store | A provider embeds the report for later retrieval |
| ai-input | Supplying content to an AI system for inference-time grounding, answers, summaries, user-requested analysis, or transient evaluation that does not update weights or become a retained training corpus | An operator asks an agent a football question and it cites TIBER |
| ai-train | Pre-training, fine-tuning, distillation, embedding-model tuning, synthetic training-corpus construction, or another use that updates model weights or supplies a retained training corpus | A model provider includes the artifact in a training corpus |

If an evaluation retains the content or its transformations for later weight updates, ai-train
governs even if the first pass was described as evaluation. If it builds a persistent retrieval
index, ai-index also governs.

The selected vocabulary is pinned to [RSL 1.0](https://rslstandard.org/rsl) and must be checked with
the official RSL validator. A later RSL version requires an explicit TIBER profile revision; it is
not adopted automatically. TIBER deliberately avoids RSL's broader all and ai-all shortcuts here
because they would collapse decisions that this profile keeps independent.

These four decisions must be stored independently. “AI allowed” and “AI prohibited” are too
ambiguous for TIBER's governance model.

### 3.1 Recommended policy profiles

| Profile | Publication default | search | ai_index | ai_input | ai_train | Legal posture | Intended use |
| --- | --- | --- | --- | --- | --- | --- | --- |
| tiber-open-knowledge-v0 | Eligible only after every publication gate passes | Permit | Permit | Permit | Permit | CC BY 4.0 candidate, only for TIBER-authored and fully rights-cleared material | Default recommendation for public methodology and eligible public knowledge |
| tiber-agent-access-v0 | Withhold until custom terms and every publication gate pass | Permit | Permit | Permit | Reserve | Requires lawyer-reviewed custom terms; not drafted and not usable yet | Future sensitive material where agent answers are welcome but weight training is not |
| tiber-source-restricted-v0 | Withhold by default | Source-controlled or unknown | Source-controlled or unknown | Source-controlled or unknown | Source-controlled or unknown | Source terms or ownership do not support an open grant | Paid, proprietary, unknown-rights, or otherwise restricted material |
| tiber-private-v0 | Withhold | No public grant | No public grant | No public grant | No public grant | No public grant | Operator-private, candidate, fixture, internal, security-sensitive, or unpublished material |

“Permit” is only a recommendation until a real legal instrument is adopted. A crawler allow rule
alone is not that instrument.

### 3.2 Why the open profile permits training

CC BY 4.0 allows sharing and adaptation for any purpose, including commercial purposes, subject to
attribution and the license terms. Creative Commons also explains that its 4.0 licenses permit
text and data mining where permission is required. See the
[CC BY 4.0 deed](https://creativecommons.org/licenses/by/4.0/) and
[Creative Commons FAQ](https://creativecommons.org/faq/).

TIBER must not publish under CC BY 4.0 and then use RSL, robots.txt, or terms of use to impose a
new downstream “no AI training” restriction on the same licensed material. CC BY 4.0 does not
permit added restrictions that prevent recipients from exercising the licensed rights.

If the operator wants a training-reserved posture, the correct path is the future
tiber-agent-access-v0 profile with reviewed custom terms. That choice sacrifices the simplicity,
interoperability, and recognized openness of CC BY and should be made deliberately.

A later crawler-policy change also cannot revoke copies already received under an irrevocable
open license, assuming recipients remain compliant with its terms.

---

## 4. Current license and rights inventory

This is an engineering inventory of discoverable license signals, not a chain-of-title opinion.
“Not found” means the inspected repository did not expose the specified signal at the audit
baseline; it does not prove that no contributor, dependency, source contract, nested directory, or
external agreement carries relevant rights.

<!-- LICENSE_INVENTORY_START -->
| Repository | Discoverable explicit license signal | Current implication for this profile |
| --- | --- | --- |
| [TIBER-Ops](https://github.com/Prometheus-Frameworks/TIBER-Ops/tree/11b35f368f35351b4f609f9973b69c03076e9581) | No license/notice file or package metadata found; GitHub detects no license | Public readability does not supply a general reuse grant; no outbound license signal was found in the inspected architecture-doc tree |
| [TIBER-Data](https://github.com/Prometheus-Frameworks/TIBER-Data/tree/6762665fefdbc81963f3d0a5708078de6cfba981) | No license/notice file found; [package.json](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/6762665fefdbc81963f3d0a5708078de6cfba981/package.json) and [pyproject.toml](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/6762665fefdbc81963f3d0a5708078de6cfba981/pyproject.toml) omit a license; GitHub detects none | Highest-risk layer: no outbound data-license or per-artifact rights-manifest signal was found for the public raw/silver/gold/promoted data; upstream rights remain unresolved |
| [TIBER-Teamstate](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/tree/61485d1309484bad300378ef5d9aaa67365d3d62) | [package.json](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/blob/61485d1309484bad300378ef5d9aaa67365d3d62/package.json) says MIT; no full license text or NOTICE; GitHub detects none | MIT intent for the package does not establish rights for TIBER-Data inputs or the candidate public report |
| [TIBER-Fantasy](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/tree/b2ae15f2174bc8e244c847ad1cc400665df5f9ab) | [package.json](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/b2ae15f2174bc8e244c847ad1cc400665df5f9ab/package.json) and [README](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/b2ae15f2174bc8e244c847ad1cc400665df5f9ab/README.md) say MIT; no full license text; GitHub detects none | Incomplete code-license intent; operational legal analysis and attribution UI are not outbound licenses, and third-party data cannot inherit MIT |
| [TIBER-Research](https://github.com/Prometheus-Frameworks/TIBER-Research/tree/6a0671253fa7322b653b640109d2f74c3a0b9f8e) | Complete root [MIT license](https://github.com/Prometheus-Frameworks/TIBER-Research/blob/6a0671253fa7322b653b640109d2f74c3a0b9f8e/LICENSE), detected by GitHub | Green for material the licensor controls; external-source rights remain separately gated |
| [TIBER-Forecast](https://github.com/Prometheus-Frameworks/TIBER-Forecast/tree/e295e3de745b676df571348cb8541fb5e35e3a02) | No license/notice file found; [package.json](https://github.com/Prometheus-Frameworks/TIBER-Forecast/blob/e295e3de745b676df571348cb8541fb5e35e3a02/package.json) omits a license; GitHub detects none | No outbound code/output license signal was found in the inspected tree; permissions must not be assumed |
| [TIBER-FORGE](https://github.com/Prometheus-Frameworks/TIBER-FORGE/tree/31ef98393b6c86576442d79cd8996cac530b2fad) | No license/notice file found; [package.json](https://github.com/Prometheus-Frameworks/TIBER-FORGE/blob/31ef98393b6c86576442d79cd8996cac530b2fad/package.json) omits a license; GitHub detects none | No outbound code/output license signal was found in the inspected tree; derived-grade rights remain unresolved |
| [TIBER-Rookies](https://github.com/Prometheus-Frameworks/TIBER-Rookies/tree/a6f8555e79f3fc562a6c5f533acee583eeb12a3a) | No outbound license/notice file found; package metadata omits a license; GitHub detects none | Its [source-hygiene policy](https://github.com/Prometheus-Frameworks/TIBER-Rookies/blob/a6f8555e79f3fc562a6c5f533acee583eeb12a3a/docs/legal/external-source-hygiene-policy.md) is useful governance, but not an outbound grant; no outbound code license signal was found in the inspected tree |
| [TIBER-Strategy](https://github.com/Prometheus-Frameworks/TIBER-Strategy/tree/03c840765af7f64a797a4bc8b0cba6bb8dce0d6f) | [package.json](https://github.com/Prometheus-Frameworks/TIBER-Strategy/blob/03c840765af7f64a797a4bc8b0cba6bb8dce0d6f/package.json) is marked private: true and says MIT; no full license text; GitHub detects none | Incomplete code-license intent; ontology/content scope is ambiguous |
| [TIBER-Harness](https://github.com/Prometheus-Frameworks/TIBER-Harness/tree/eac4b0968ff4645582743421fc8bb2f6a1c2aa8b) | [package.json](https://github.com/Prometheus-Frameworks/TIBER-Harness/blob/eac4b0968ff4645582743421fc8bb2f6a1c2aa8b/package.json) is marked private: true and says MIT; [README](https://github.com/Prometheus-Frameworks/TIBER-Harness/blob/eac4b0968ff4645582743421fc8bb2f6a1c2aa8b/README.md) says MIT; no full license text; GitHub detects none | Incomplete code-license intent; fixtures and evaluation outputs have no separate content license |
<!-- LICENSE_INVENTORY_END -->

Four additional related public model repositories inspected at immutable snapshots —
[Age-curve-intelligence-model](https://github.com/Prometheus-Frameworks/Age-curve-intelligence-model/tree/998b28644be7d36efb235ce1df62113dd8f0350c),
[ARC](https://github.com/Prometheus-Frameworks/ARC/tree/b36fda874e699886a6184cb0340717a94724d6d7),
[Role-and-opportunity-model](https://github.com/Prometheus-Frameworks/Role-and-opportunity-model/tree/6435d8d3c2c4e53dc45ab57a05a2716e2b47598d),
and [Signal-Validation-Model](https://github.com/Prometheus-Frameworks/Signal-Validation-Model/tree/0ba3d4bc3d9696aca8059052a9ff948046f0e2e1)
— also expose no license file or package-level license declaration.

Cross-cutting result: only TIBER-Research has a complete, GitHub-detected license. Four inspected
TIBER repositories express MIT intent without the license text, while no explicit outbound license
signal was found in five inspected core TIBER trees. No inspected tree exposed a dedicated
data/content license, public-artifact rights manifest, RSL policy, NOTICE, or explicit agent-use
grant. These are findings about the inspected trees, not proof that no external agreement exists.
TIBER-Fantasy does expose a permissive
[robots.txt](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/b2ae15f2174bc8e244c847ad1cc400665df5f9ab/public/robots.txt),
but that is crawler signaling rather than a copyright or data license.

Before adoption, the inventory must be deepened within each inspected/active repository to include:

- root and nested LICENSE, LICENCE, COPYING, NOTICE, and rights files;
- package metadata license fields;
- vendored code and generated artifacts;
- contributor ownership or inbound-license assumptions;
- upstream dataset licenses, contracts, and attribution duties;
- database-right implications in relevant jurisdictions;
- trademarks and brand assets; and
- deployment-specific terms for public services.

The absence of a root license is a blocker for claiming that a repository is open source. It is
not, by itself, a blocker for TIBER to continue private development or publish an exact artifact
under separately verified rights.

---

## 5. Layered license recommendation

One repository can contain multiple legal layers. TIBER should state which instrument applies to
which paths or artifact components.

| Layer | Candidate | Scope condition | Exclusions and notes |
| --- | --- | --- | --- |
| TIBER-authored source code | MIT | TIBER controls the necessary contributor rights; adopted per repository | Dependencies retain their own licenses; no data or trademark grant |
| TIBER-authored public docs and methodology | CC BY 4.0 | Exact paths are named in a rights notice and TIBER owns the content | Does not cover code, third-party excerpts, logos, or source data |
| TIBER-authored public report prose and presentation | CC BY 4.0 | Exact report version is approved and every embedded element is rights-cleared | Upstream attribution and no-endorsement rules must remain visible |
| Structured report facts and derived fields | Per-artifact determination; CC BY 4.0 only when grantable | Field-level source-rights matrix is complete and applicable copyright/database rights can be licensed | Facts may be uncopyrightable in some places, but contracts, compilation rights, and database rights can still constrain extraction or reuse |
| Schemas and interface examples | MIT candidate with the code layer, or an explicit separate interoperable grant | Exact paths named | Do not leave schemas legally ambiguous |
| Trademarks, names, logos, and visual identity | No grant by default | Separate brand policy if later needed | Attribution may name TIBER, but cannot imply endorsement |
| Third-party content or source-restricted data | Source terms control | Only uses affirmatively supported by evidence | Never relicensed by transformation, aggregation, or repository placement |
| Private, candidate, fixture, operator-seeded, security-sensitive, or unpublished material | No public license | Remains outside public layer | Crawler directives are not a substitute for keeping it private |
| Modeled, forecast, or experimental outputs | Outside public-knowledge v0 | Requires its own eligibility and claims policy | Existing #11 boundary remains in force |

The [U.S. Copyright Office](https://www.copyright.gov/help/faq/faq-protect.html) explains that
facts themselves are not protected by copyright, while the EU's
[database-protection framework](https://eur-lex.europa.eu/EN/legal-content/summary/legal-protection-databases.html)
can protect qualifying database investment. Those principles do not erase source contracts,
confidentiality, compilation copyright, or other jurisdictions' rules; they are reasons to review
the exact source and use rather than label every “derived fact” safe.

### 5.1 Adoption mechanism

A later license-adoption change should include, at minimum:

- the full legal license text at the relevant repository root or public-artifact boundary;
- a RIGHTS.md or equivalent path map stating which license applies to code, docs, data, generated
  outputs, examples, and brand assets;
- SPDX identifiers in package metadata where appropriate;
- per-artifact license and source-rights manifests;
- carried-through upstream notices;
- a contribution/inbound-rights decision; and
- an effective date and immutable commit reference.

No rights should be inferred from this architecture document.

---

## 6. Source-rights and sublicensing matrix

Every public artifact family must have a reviewable, private evidence matrix before it can select
an open profile. Rows must be addressable to the exact output they authorize; a source-only list
cannot prove that each public field is covered. A useful minimum schema is:

| Field | Required meaning |
| --- | --- |
| artifact_family and artifact_version | Exact report family and immutable version under review |
| source_id | Stable internal identifier |
| source_provider and source_url | Who supplied the source and where its controlling terms can be inspected |
| acquired_by and acquired_at | Retrieval path and evidence timestamp |
| controlling_terms | Exact license, contract, API terms, public-domain basis, or other authority |
| rights_holder | Known rightsholder or unknown |
| output_fields_or_components | Exact JSON fields, HTML components, prose, methodology, schema, or other outputs to which this row applies |
| material_class | Raw, computed, aggregate, TIBER-authored expression, third-party expression, schema, or other explicit class |
| tiber_rights_basis | Authorship, assignment, inbound license, source permission, public-domain basis, or unknown |
| raw_storage | Whether TIBER may retain source bytes |
| internal_analysis | Whether TIBER may process the source internally |
| public_display | Whether exact source material may be shown |
| raw_redistribution | Whether source rows or bytes may be redistributed |
| derived_redistribution | Whether and under what conditions derived fields may be published |
| search | Allowed, prohibited, unknown, or not applicable |
| ai_index | Allowed, prohibited, unknown, or not applicable |
| ai_input | Allowed, prohibited, unknown, or not applicable |
| ai_train | Allowed, prohibited, unknown, or not applicable |
| attribution | Required names, notices, links, placement, and persistence |
| database_rights | Applicable grant, reservation, jurisdiction, or unknown |
| confidentiality and access limits | Paywall, account, rate, territory, term, or other restrictions |
| transformations | Exact derivations used and whether they preserve protected expression or a substantial database extraction |
| reconstruction_or_substitution_risk | Whether the output can reconstruct, substitute for, or expose a protected source |
| privacy_brand_and_personality_limits | Applicable personal-data, name/image, logo, trademark, or endorsement constraints |
| evidence | Immutable terms snapshot, contract reference, receipt, or legal-review record |
| reviewed_by and reviewed_at | Accountable human review and freshness date |
| disposition | approved, blocked, or requires_review |

Allowed values must fail closed:

- Unknown is never treated as allowed.
- Internal analysis permission is never treated as redistribution permission.
- Access to an API is never treated as ownership.
- A derived value is never presumed safe merely because its formula is original.
- A fact's possible lack of copyright protection in one jurisdiction does not override contract
  terms, compilation copyright, confidentiality, or database rights.
- Attribution is not a cure for missing permission.
- TIBER cannot grant downstream rights broader than the rights it holds.

This is the anti-rights-laundering invariant.

### 6.1 Private evidence ledger and public summary

The matrix above is a private governance artifact. It may contain contracts, receipts, reviewer
identity, account details, internal paths, or legal analysis that must not be published.

Each public artifact instead receives a disclosure-safe source-rights summary containing only:

- the artifact family/version and public output fields/components covered;
- a public source/provider name only when disclosure is permitted;
- the final permission state for publication, search, AI indexing, AI input, and AI training;
- required public attribution and notices;
- review status, review date, and expiry date; and
- opaque private-ledger ID and SHA-256 for approval/audit binding.

The public summary must never include private contract text, receipts, credentials, confidential
source URLs, internal filesystem paths, or reviewer personal data. The exact-action approval binds
the private ledger hash; the public rights manifest links only to the disclosure-safe summary.

---

## 7. Per-artifact rights manifest

Every public HTML and JSON representation should link to the same immutable rights manifest. The
illustrative contract below is not active and grants no rights:

    {
      "schema": "tiber_public_rights_manifest_v0",
      "manifest_id": "teamstate_public_offensive_environment_2024_v1.r1.rights.r1",
      "artifact_family": "teamstate_public_offensive_environment_2024_v1",
      "report_version_id": "teamstate_public_offensive_environment_2024_v1.r1",
      "canonical_url": "https://<public-host>/nfl/2024/offensive-environments",
      "representations": [
        {
          "kind": "html",
          "media_type": "text/html",
          "version_url": "https://<public-host>/<immutable-html-version-path>",
          "sha256": "<exact HTML bytes hash>"
        },
        {
          "kind": "json",
          "media_type": "application/json",
          "version_url": "https://<public-host>/<immutable-json-version-path>",
          "sha256": "<exact JSON bytes hash>"
        },
        {
          "kind": "methodology",
          "media_type": "text/html",
          "version_url": "https://<public-host>/<immutable-methodology-version-path>",
          "sha256": "<exact methodology bytes hash>"
        }
      ],
      "profile": "tiber-open-knowledge-v0",
      "license": {
        "spdx": "CC-BY-4.0",
        "url": "https://creativecommons.org/licenses/by/4.0/",
        "licensor": {
          "legal_name": "<approved legal licensor; decision required>",
          "identifier": "<stable legal-entity identifier or null>",
          "copyright_notice": "<approved notice>"
        },
        "applies_to": [
          "tiber_authored_methodology",
          "tiber_authored_report_text",
          "rights_cleared_structured_output"
        ]
      },
      "permissions": {
        "search": "permitted",
        "ai_index": "permitted",
        "ai_input": "permitted",
        "ai_train": "permitted"
      },
      "attribution": {
        "creator": "TIBER",
        "publisher": "TIBER",
        "title": "2024 NFL Offensive Environments",
        "version": "teamstate_public_offensive_environment_2024_v1.r1",
        "canonical_url": "https://<public-host>/nfl/2024/offensive-environments",
        "methodology_url": "https://<public-host>/methodology/teamstate-public-offensive-environment-2024-v1"
      },
      "source_rights": {
        "status": "verified",
        "public_summary": {
          "media_type": "application/json",
          "version_url": "https://<public-host>/<immutable-public-source-rights-summary-path>",
          "sha256": "<exact public source-rights summary hash>"
        },
        "private_evidence_ledger_id": "<opaque internal ledger identifier>",
        "private_evidence_ledger_sha256": "<exact private ledger hash>",
        "verified_at": "<ISO-8601 timestamp>",
        "review_expires_at": "<ISO-8601 timestamp or null>"
      },
      "machine_signals": {
        "rsl": {
          "version": "1.0",
          "version_url": "https://<public-host>/<immutable-rsl-policy-path>",
          "sha256": "<exact RSL policy bytes hash>"
        },
        "crawler_profile": {
          "id": "tiber-open-knowledge-crawlers-v0",
          "version_url": "https://<public-host>/<immutable-crawler-profile-path>",
          "sha256": "<exact crawler-profile bytes hash>",
          "expected_robots_txt_sha256": "<exact deployed robots.txt bytes hash>"
        }
      },
      "exclusions": [
        "third_party_material_not_expressly_listed",
        "trademarks_and_logos",
        "private_candidate_fixture_and_operator_local_material"
      ],
      "effective_at": "<ISO-8601 timestamp>",
      "supersedes": null
    }

The rights manifest's own bytes cannot safely self-hash without a canonical omission rule. The
external exact-action approval must bind rights_manifest_sha256 separately, plus every
representations[].sha256 value, the public source-rights summary hash, the private evidence-ledger
hash, and each machine-signal hash. JSON and HTML remain separately named and bound, preserving
the approval contract already implemented by Teamstate PR #91; the additional bindings extend a
later rights/discovery approval rather than weakening that contract.

Validator requirements:

1. The manifest must identify every public representation's exact bytes, media type, and immutable
   URL, not only a mutable route or one generic artifact hash.
2. The HTML, JSON, methodology, and manifest must agree on title, version, canonical URL, license,
   temporal scope, and attribution.
3. Every licensed output field or component must map to a verified private source-rights row or a
   TIBER-authorship record and to a disclosure-safe public summary entry.
4. Unknown, expired, contradictory, missing, or broader-than-source permissions fail closed.
5. The declared RSL permissions must not contradict the legal license.
6. A later manifest may govern later versions, but cannot silently rewrite the rights attached to
   an immutable prior version.
7. Machine-readable metadata must never claim that a license covers excluded third-party material.
8. RSL ownership, authority, non-infringement, or privacy-consent warranties — or the separate RSL
   attestation — must not be emitted for mixed-source material unless documentary evidence supports
   each representation.
9. A site-wide wildcard grant must not cover a domain that also serves private, candidate,
   third-party, or differently licensed material.
10. The approval must independently bind every representation, the public summary, the private
    evidence ledger, RSL/crawler policy, expected robots bytes, and the rights manifest itself.

---

## 8. Attribution and citation contract

Agent compatibility is useful to TIBER only if a human can understand where an answer came from.
Attribution should be easy for agents to preserve.

### 8.1 Visible human attribution

Every public report page should visibly include:

- TIBER as creator/publisher;
- the approved legal licensor/rightsholder identity and copyright notice, which may differ from
  the TIBER public brand;
- the report title and immutable version;
- data-through, source-snapshot, and generated-at dates;
- the canonical URL;
- the methodology URL and version;
- the applicable license and rights-manifest URL;
- required upstream attribution;
- a change/supersession notice; and
- a statement that attribution does not imply TIBER or an upstream source endorses the user's
  analysis.

### 8.2 Machine-readable citation payload

The HTML and JSON should expose equivalent fields:

- creator and publisher;
- legal licensor/rightsholder identity and copyright notice;
- name and description;
- canonical_url and version_url;
- report_version_id and schema_version;
- license and rights_manifest_url;
- methodology_url and methodology_version;
- dateModified, data_through, source_snapshot_at, and generated_at;
- isBasedOn/source-artifact references that are safe to expose;
- content hashes;
- citation_text; and
- upstream attribution entries.

Recommended citation hint:

> TIBER, “2024 NFL Offensive Environments,”
> teamstate_public_offensive_environment_2024_v1.r1, data through the 2024 regular season,
> canonical URL, CC BY 4.0.

This is a machine-friendly suggestion, not an attempt to override the “reasonable manner”
attribution flexibility in CC BY 4.0.

Attribution is not permission and cannot cure missing source rights. Nor can TIBER guarantee that
every open-web agent will cite correctly. Where an answer communicates only facts that are not
subject to the applied license, the license's attribution condition may not be triggered; a
broader universal citation obligation would require applicable contract terms. TIBER should still
make accurate citation the easiest path through visible and machine-readable metadata.

Use [Schema.org Dataset](https://schema.org/Dataset) or the more precise applicable Schema.org
type. Structured metadata must match visible page content. Google's
[Dataset structured-data guidance](https://developers.google.com/search/docs/appearance/structured-data/dataset)
is a useful implementation reference but does not guarantee search appearance.

---

## 9. Discovery profile

A rights-cleared artifact should still be treated as undiscoverable until its public surface meets
all of these requirements:

- stable, unauthenticated, HTTPS canonical URL;
- immutable version URL plus one current canonical alias;
- essential answer and attribution in server-rendered or static HTML;
- linked, content-negotiated, or otherwise obvious machine-readable JSON;
- descriptive title and meta description;
- canonical link tag;
- public methodology and rights pages;
- visible timestamps, scope, provenance, coverage, warnings, and supersession state;
- Schema.org metadata matching visible content;
- inclusion in a scoped XML sitemap;
- useful internal links from a durable TIBER index page;
- explicit no-index posture for health, admin, internal, candidate, fixture, approval, or staging
  routes;
- crawler-specific robots policy aligned with the chosen profile;
- RSL discovery and permissions aligned with the legal license;
- optional llms.txt navigation guidance that links only to already-public canonical resources; and
- monitoring for availability, manifest drift, stale rights reviews, crawler errors, and accidental
  index exposure.

Google's [sitemap guidance](https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview)
explains sitemap discovery. A sitemap helps discovery; it does not guarantee crawling or ranking.

The llms.txt proposal may offer a concise map for some agents, but it is not a web standard,
license, robots directive, authentication method, or guarantee that an agent will read it. See the
[proposal repository](https://github.com/AnswerDotAI/llms-txt).

### 9.1 OpenAI crawler mapping

OpenAI's official [crawler documentation](https://developers.openai.com/api/docs/bots) distinguishes:

- OAI-SearchBot, used to surface sites in ChatGPT search;
- GPTBot, which may be used to crawl content for foundation-model training; and
- ChatGPT-User, used for user-initiated actions rather than automatic web crawling.

The controls for OAI-SearchBot and GPTBot are independent. This supports TIBER's separation of
search from training. ChatGPT-User requests are user-initiated, so robots rules must not be treated
as an access-control boundary or the only enforcement mechanism.

Bot names and RSL use classes do not map one-to-one. Because ChatGPT search can generate an answer
from retrieved material, a TIBER profile that admits OAI-SearchBot should support both search and
ai-input rather than assuming the crawler name describes every downstream use.

Proposal-only crawler matrix — this is not a deployed robots policy:

| Bot or requester | Mapped use class | Open-knowledge posture | Training-reserved posture | Enforcement and scope note |
| --- | --- | --- | --- | --- |
| OAI-SearchBot | search plus downstream ai-input | Allow only on approved public paths | Allow only on approved public paths whose custom terms permit both uses | robots is crawler signaling; legal profile must cover answer generation |
| GPTBot | ai-train | Allow only on approved public paths because the open profile permits training | Disallow on all training-reserved paths | Separate user-agent rule; custom legal terms remain necessary and stronger access controls may be required |
| ChatGPT-User | User-initiated ai-input; ai-index also applies if a persistent retrieval store is built | Serve the same approved public representations | Serve only content public under the custom profile or through real authenticated authorization | User-initiated requests may not follow robots; robots is not access control |
| Recognized conventional search crawler | search; add ai-input if the provider uses content in generated answers | Allow only on approved public paths | Allow only after the provider's documented uses are mapped and permitted | Maintain dated, provider-specific evidence |
| Unknown or mixed-purpose crawler | Unmapped until reviewed | Default public-server behavior may allow access to open-profile paths, whose license permits all four uses; record as unmapped | Fail closed: disallow until every material use is mapped and permitted | Never infer purpose from a bot name; protect non-public content with real access control or no route |

“Allow” and “disallow” above describe the candidate crawler posture after activation. They do not
grant or revoke legal rights and do not authorize implementation in this PR.

An unknown crawler is always unmapped. It fails closed for every profile that does not already
permit all four use classes; the fully open profile is the narrow exception because its adopted
legal grant would already permit those uses on the approved public artifact.

The same category-based policy should be mapped to each vendor's current documented crawler names
during implementation. Do not assume one vendor's user-agent taxonomy applies to another.

[RFC 9309](https://www.rfc-editor.org/rfc/rfc9309.html) standardizes the Robots Exclusion
Protocol and explicitly warns that it is not a replacement for valid security measures. TIBER must
use real access controls or, preferably for unpublished artifacts, no public route at all.

### 9.2 Direct agent access later

REST, OpenAPI, MCP, or a ChatGPT app can make TIBER easier to invoke, but they do not replace the
public rights and publication gate. Any future tool must:

- expose only artifacts already eligible for that audience;
- return provenance, coverage, dates, license, rights-manifest, and citation metadata with the
  answer;
- separate public reads from authenticated/operator-scoped reads;
- preserve deterministic validation and rejection explanations;
- grant no repository, publication, or promotion authority by default; and
- use the same source-rights decision as the web surface.

The current MCP specification's
[resource model](https://modelcontextprotocol.io/specification/2026-07-28/server/resources) and the
[OpenAPI Specification](https://spec.openapis.org/oas/v3.2.0.html) are future interface references,
not implementation authorization.

---

## 10. Fail-closed agent-publication gate

An exact artifact may enter the public agent layer only if every gate passes:

1. **Provenance:** explicitly governed real data; never inferred from a path or successful build.
2. **Claims:** the report's question, observed/derived/modelled status, limitations, and excluded
   lanes are explicit.
3. **Coverage and freshness:** complete against declared scope, with separated data-through,
   source-snapshot, generated-at, and rights-review timestamps.
4. **Methodology:** every public field has a versioned deterministic derivation.
5. **Source rights:** every field/component has a current allowed disposition for public display
   and the chosen downstream uses.
6. **TIBER authority:** TIBER controls the rights it proposes to license; contributor and brand
   exclusions are resolved.
7. **Rights-instrument coherence:** the applicable license or documented public-domain /
   no-exclusive-right basis, per-artifact manifest, RSL, visible notices, API terms, and crawler
   posture do not contradict one another; contracts and database rights are still checked.
8. **Artifact identity:** JSON, HTML, methodology, manifest, and approval bind to immutable versions
   and content hashes.
9. **Security:** no credentials, private/operator context, candidate data, fixtures, internal paths,
   approval records, or source-restricted bytes leak.
10. **Human approval:** a valid exact-action operator approval names the version, hashes, license
    profile, crawler profile, and activation action.
11. **Serving state:** deployment changes occur only in a separately authorized implementation lane.
12. **Post-publication controls:** monitoring, takedown/withdrawal procedure, supersession, and
    incident ownership exist.

Any false, unknown, expired, or missing gate yields withhold. The system must not downgrade an
authoritative complete report into a silently partial public answer.

### 10.1 Immutability, withdrawal, and tombstones

“Immutable version” means that TIBER never serves different report bytes under the same version
identity. It does not promise perpetual public availability when law, safety, privacy, source
rights, or a material governance failure requires withdrawal.

If an immutable version must be withdrawn:

- do not replace its HTML or JSON with corrected or different report bytes under the old identity;
- replace the public version route with an explicit tombstone or withdrawal status, preferably an
  appropriate HTTP status plus a machine-readable status resource;
- record withdrawal date, non-confidential reason class, successor/correction if one exists, and
  accountable approval;
- preserve exact prior hashes, bytes, rights evidence, and audit history privately where lawful;
- remove the version from active sitemaps/index promotion and update the canonical alias safely;
  and
- do not claim that withdrawal or a later robots/RSL change revokes compliant copies already
  received under an irrevocable license.

This rule reconciles exact-byte identity with necessary takedown authority: report bytes never
mutate silently, while availability may end transparently.

---

## 11. Historical Teamstate report as the first canary

The implemented candidate is:

    teamstate_public_offensive_environment_2024_v1

Current evidence:

- TIBER-Teamstate PR #91 implemented the report, validator, immutable-version behavior, and
  fail-closed publication path.
- The production approval source contains no approval for the candidate version/content.
- Live service metadata remains:

      {
        "public_reports": [],
        "artifact_publication_enabled": false
      }

That is the correct state and remains unchanged.

### 11.1 Why it is a useful canary

- It has a narrow, historical, observed question rather than a live prediction or advice claim.
- It already has strong provenance, coverage, methodology, identity, and validation concepts.
- Its frozen bytes can be reviewed before any public activation.
- It can test citation, rights metadata, crawler behavior, and agent retrieval without exposing
  every TIBER artifact through the public-knowledge layer.

### 11.2 Why it is not yet publishable

The prior technical implementation does not answer these rights questions:

- What exact upstream sources and controlling terms support every public field?
- May TIBER display and redistribute the derived structured output?
- May TIBER grant search, AI indexing, AI input, and AI training rights?
- Which upstream attributions and notices must persist?
- Does TIBER control the report prose, methodology, schemas, and contributor rights?
- Which exact legal profile applies to the immutable JSON and HTML bytes?
- Does the crawler profile match that legal choice?

Until those are answered with evidence, the canary remains blocked regardless of its technical
quality.

### 11.3 Required decisions before activation

A later operator packet must name:

1. the exact report version and JSON/HTML/content hashes;
2. the completed private field-addressable source-rights ledger, its detached hash, and the
   disclosure-safe public source-rights summary;
3. the license profile and exact legal text;
4. the search, AI-index, AI-input, and AI-training permissions;
5. required upstream and TIBER attribution;
6. the rights-manifest bytes and hash;
7. the implementation commit for public rights/discovery metadata;
8. the crawler/RSL/sitemap posture;
9. monitoring, rollback, and takedown ownership; and
10. the exact publication state transition.

A general “make TIBER agent-friendly” instruction is not publication approval.

The 2024 historical report is a governance and systems canary, not a complete 2026 search strategy.
After it proves the pathway, TIBER still needs current, useful football questions and a repeatable
freshness/publication cadence to earn discovery traffic.

---

## 12. Profile stages toward implementation

These profile stages are local to this licensing/discovery proposal. They do not renumber or
replace the Phase 3 report implementation and Phase 4 discovery work defined by TIBER-Ops #11 and
TIBER-Teamstate. Every stage below requires its own scoped authority. None is activated here.

### Profile Stage 0 — this proposal

- Complete the license and rights-signal inventory.
- Define the profiles, manifest, source-rights matrix, crawler mapping, attribution, and gate.
- Open a draft TIBER-Ops PR.
- End with no license, runtime, or publication change.

### Profile Stage 1 — operator and legal decisions

- Choose code and documentation licenses.
- Decide whether the default public-knowledge profile permits AI training.
- Decide whether a training-reserved custom profile is worth drafting.
- Confirm contributor/inbound rights and trademark posture.
- Identify the legal licensor/rightsholder and approved copyright notice separately from the
  TIBER public brand.
- Approve the source-rights matrix schema.
- Choose whether the Teamstate report should continue as the first canary.

Terminal condition: exact adopted policy choices, not yet a live publication.

### Profile Stage 2 — license and rights-contract adoption

Separately scoped changes in each owning repository:

- add approved license text and path-specific rights notices;
- add package metadata where appropriate;
- implement the rights-manifest schema and validator contract;
- complete the canary's private field-addressable rights-evidence ledger and disclosure-safe public
  source-rights summary;
- bind upstream notices;
- keep Teamstate publication disabled.

Terminal condition: coherent legal and machine-readable contract, no public report activation.

### Profile Stage 3 — discovery implementation with publication still disabled

After an explicit implementation-lane decision:

- implement public methodology and rights resources;
- implement canonical and version metadata;
- implement Schema.org markup;
- implement scoped sitemap, robots, RSL, and optional llms.txt;
- add fail-closed tests for contradictory or missing rights;
- verify staging without exposing candidate/source-restricted content.

Terminal condition: implementation reviewed and deployable, publication still disabled.

### Profile Stage 4 — exact canary publication decision

- freeze and hash the final artifact, manifest, notices, and discovery policy;
- run technical, rights, security, and agent-retrieval review;
- record an exact operator approval;
- activate only the approved report/version;
- verify live metadata, routes, crawler exposure, citation, rollback, and monitoring.

Terminal condition: one governed public canary, or a documented no-go.

### Profile Stage 5 — usefulness and currentness

- measure successful retrieval, citations, crawl health, stale-result risk, and user usefulness;
- define a repeatable current-season artifact family and freshness SLA;
- expand only when source rights and operational quality remain proven.

### Profile Stage 6 — direct agent interfaces

- evaluate a public read-only API, OpenAPI document, MCP resources/tools, or ChatGPT app;
- preserve audience scopes and the same publication/right gates;
- keep promotion, repository mutation, and operator authority out of public-agent capabilities.

---

## 13. Acceptance criteria check

- [x] The proposal is explicitly non-granting and non-implementing.
- [x] Public visibility, legal permission, crawl policy, API authorization, and discovery are
      separate controls.
- [x] Search, AI indexing, AI input, and AI training receive independent policy states.
- [x] The open profile and training-reserved alternative do not contradict CC BY 4.0.
- [x] RSL is a machine-readable expression layer, not a substitute for legal rights.
- [x] robots.txt is not treated as access control.
- [x] llms.txt is optional navigation guidance, not a license or crawler control.
- [x] The layered code, docs, report, data, third-party, private, brand, and model-output treatment
      is defined.
- [x] A source-rights and sublicensing matrix is defined.
- [x] Rights laundering fails closed.
- [x] A per-artifact rights-manifest candidate is defined.
- [x] Human and machine-readable attribution/citation are defined.
- [x] Canonical URLs, sitemap, structured data, crawler mapping, and future direct-agent interfaces
      are scoped.
- [x] The Teamstate report is evaluated without authorizing publication.
- [x] Later work is phased behind explicit operator and lane decisions.
- [x] No license file, crawler rule, route, deployment, report approval, or publication state is
      changed by this document.

## Non-goals

This profile does not acquire third-party data; bypass a paywall, technical control, API term, or
source restriction; expose raw source material; authorize training by implication; promise search
ranking or vendor support; publish fixtures, candidates, private context, or experimental outputs;
build an API or MCP server; grant repository authority; provide legal advice; rotate the active
implementation lane; merge itself; or activate the Teamstate report.

## Final machine-readable decision

    requires_operator_license_and_publication_decisions
