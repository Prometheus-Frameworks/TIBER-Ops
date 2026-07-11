# TIBER Public Knowledge and Agent-Discovery Architecture v0

## Status

- **Owning issue:** [TIBER-Ops #11](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/11)
  — the canonical cross-repository parent for the public knowledge and agent-discovery lane.
- **Operator decision incorporated:** [Direction A](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/11#issuecomment-4940087322)
  — use the governed 2024 full-league Teamstate source as the first controlled public-report
  pilot, scoped as a historical report.
- **Technical evidence incorporated:** [TIBER-Teamstate PR #80](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/pull/80)
  — merged Teamstate-side readiness audit for the 2024 offensive-environment source.
- **This document is:** architecture, governance, and implementation-planning only.
- **This document is not:** an implementation, a published report, a route, or an enabled
  artifact. It does not modify TIBER-Teamstate, publish any football artifact, implement
  aggregation, add routes, or enable artifact publication. No football artifact is published by
  this document.
- **Lane note:** per [`docs/operating-map.md`](../operating-map.md), the currently active
  implementation lane is ML/modeling (Point-prediction-model #60). This document is **audit /
  spec** work — it produces findings and a plan, it does not implement — and does not itself
  activate a new implementation lane. Promoting Phase 2 (contract design, §12) or Phase 3
  (implementation, §12) to the active lane is a separate weekly-board decision, not a consequence
  of merging this document. Phase 2 itself contains no publication code — see §13.

---

## 1. Current-state inventory and the Teamstate deployment milestone

TIBER now has substantial internal structure: repository ownership boundaries, governed and
promoted artifacts, provenance and source-status semantics, observed-versus-inferred
distinctions, deterministic validators, fail-closed promotion rules, explicit unknown/provisional
states, and multiple downstream-readable contracts. Most of that value is still trapped inside
repositories, generated artifacts, documentation, issue history, and operator context. TIBER does
not yet have a consistent public knowledge layer through which a human or agent can ask a normal
football question and retrieve a current, explainable, source-bounded answer.

**Correction and lineage.** The original public-knowledge architecture issue was accidentally
opened in TIBER-Teamstate rather than TIBER-Ops:

- TIBER-Teamstate #77 — the original (misfiled) architecture issue. **Closed, retained as
  historical context only.**
- TIBER-Teamstate #78 — Add minimal Railway-compatible HTTP serving scaffold. **Completed.**
- TIBER-Teamstate PR #79 — merged implementation of the Railway-compatible serving scaffold.
  **Completed.**

TIBER-Ops #11 is the canonical cross-repository parent for this lane going forward.

**Teamstate deployment milestone — completed.** Live service:

```text
https://tiber-teamstate-production.up.railway.app
```

Verified routes:

```text
GET /
GET /healthz
GET /service-metadata.json
```

Current machine-readable service state:

```json
{
  "service": "tiber-teamstate",
  "status": "deployment_scaffold",
  "public_reports": [],
  "artifact_publication_enabled": false
}
```

This is the correct current posture: the service is publicly reachable, but no football artifact
has been authorized for publication. Nothing in this document changes that state. It stays this
way until a report contract (Phase 2), its validator implementation (Phase 3), and an explicit
publication authorization all exist (§12).

---

## 2. Public knowledge layer boundary

Document a distinct public publication layer above the internal repositories:

```text
TIBER-Data
    ↓ governed canonical evidence

TIBER-Teamstate / FORGE / Forecast / Rookies
    ↓ governed domain derivations

TIBER Public Knowledge Layer
    ├── human-readable reports
    ├── machine-readable JSON
    ├── stable canonical URLs
    ├── methodology pages
    ├── provenance and coverage metadata
    ├── crawler and indexing controls
    └── eventual API, MCP, or agent-tool interfaces
```

The public layer must **not** directly mirror every repository artifact. Only artifacts that pass
the publication eligibility gate (§3), have a documented derivation/methodology, and have been
explicitly authorized reach the public layer. A repository producing an artifact is necessary but
never sufficient for that artifact to become public.

---

## 3. Publication eligibility matrix

For every provenance/lifecycle state below: whether publication is forbidden, allowed only with
warnings, what coverage is required, requires a source cutoff, requires source artifact
IDs/hashes, requires methodology documentation, requires human approval, allows search indexing,
and how the service fails closed when a requirement is not met.

**Coverage is scope-relative, not universally full-league.** A governed public report may
legitimately declare a narrower scope than "all 32 NFL teams" — one team, one player, one position
population, one game, or any other bounded population. The invariant is **complete coverage of the
report's declared scope**, not full-league coverage as a blanket requirement. Every report must
carry:

- `declared_scope` / `expected_entities` — what population the report claims to cover, stated
  explicitly (e.g. "all 32 NFL teams," "team DET only," "all starting QBs, 2024 season");
- actual coverage measured against that declared scope, not against some other, larger population;
- an explicit flag for whether the report claims full-league (or otherwise "complete industry")
  coverage, since that is a stronger claim than "complete coverage of a narrow declared scope" and
  readers/agents need to know which claim is being made;
- withholding whenever actual coverage does not satisfy the declared claim, at **any** declared
  scope — a one-team report that is missing that team's data fails closed exactly like a
  league-wide report missing teams would.

For **this specific Direction A report**, the declared scope is all 32 NFL teams and the complete
2024 regular season, so 32/32 teams and 544/544 team-game rows remain mandatory for it — that
requirement is a consequence of this report's own declared scope, not of a universal full-league
rule.

| State | Publication | Coverage requirement | Source cutoff required | Source artifact IDs/hashes required | Methodology doc required | Human approval required | Search indexing allowed | Fail-closed behavior |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `governed_real_data` | **Allowed** | Yes — complete coverage of the report's own `declared_scope`/`expected_entities`; a report claiming full-league coverage must actually have it (32/32 teams for this pilot), but a narrower honestly-declared scope is equally valid if it is complete against itself | Yes | Yes | Yes | Yes (initial publication + any methodology change) | Yes | If any required field is missing/malformed, or actual coverage does not satisfy `declared_scope`, treat as ineligible and withhold — never partially publish |
| `partial_real_data` | **Forbidden as authoritative; may appear only as explicitly labeled partial-coverage evidence, never as satisfying its own declared scope** | By definition does not satisfy its own declared scope — the gap must be stated explicitly, not implied | Yes | Yes | Yes | Yes | No (not indexed as if it were a complete report) | Withhold from any report route whose contract claims complete coverage; a partial-coverage page, if it exists at all, must self-label as partial (and state the declared scope it falls short of) in both HTML and JSON |
| `candidate` | **Forbidden** | — | — | — | — | — | No | Fail closed on `provenanceStatus` alone — path, filename, or validation success must never be used to infer eligibility (this mirrors the boundary TIBER-Teamstate's own candidate/governed adapters already enforce) |
| `fixture_scaffold` | **Forbidden as authoritative content.** May exist only as an internally-labeled dev/demo artifact, never served on a public report route | — | — | — | — | — | No | Any artifact whose `provenanceStatus` is `fixture_scaffold` must be rejected by the publication validator, regardless of how complete or convenient it looks |
| `sample` | **Forbidden** | — | — | — | — | — | No | Same as `fixture_scaffold` |
| `operator_seeded` | **Forbidden as authoritative; may be shown only with an explicit, prominent "operator-seeded, not validated" label if surfaced at all** | — | — | — | — | Yes, and re-approval required before any status upgrade | No | Never silently promoted; a status change requires an explicit governance action, not a data refresh |
| `public_data_pending` | **Forbidden** | — | — | — | — | — | No | Treated identically to `unknown_provenance` until the pending status resolves explicitly |
| `unknown_provenance` | **Forbidden** | — | — | — | — | — | No | Hardest fail-closed case: absence of a provenance marker is not a passing state, it is a rejection |
| `deprecated` / `superseded` | **Forbidden as the canonical current report.** May remain reachable only via its immutable versioned identity (§6) as an explicitly marked historical/superseded page that links to its successor at the canonical alias | Reflects whatever `declared_scope` and coverage it had when it was current | Reflects its original cutoff | Yes (preserved for audit trail) | Yes (preserved) | No new approval needed to keep it archived; approval is needed to keep serving it as current | No (excluded from primary indexing; a superseded marker/canonical redirect points crawlers to the current report) | A report that becomes superseded must flip to this state before or atomically with the new report's publication — never a window where both look current |
| Model-generated / modeled / experimental outputs (forecasts, projections, scenario outputs) | **Forbidden from this lane.** Public knowledge layer v0 publishes governed *observed* derivations only; modeled/forecast outputs are out of scope until a separately authorized lane defines their own eligibility rules | — | — | — | — | — | No | Any field whose value is modeled/projected rather than observed must be absent from the response, not present-with-a-disclaimer |

Fixture, sample, candidate, operator-seeded, pending, and unknown-provenance material must never
silently appear as authoritative TIBER truth. The only state eligible for full public authoritative
publication in this v0 architecture is `governed_real_data`, evaluated field-by-field, not
artifact-wide (§4 shows why artifact-level `governed_real_data` status does not automatically make
every field in that artifact publication-ready), and scope-by-scope, not by an assumed full-league
default (this section).

---

## 4. Teamstate 2024 artifact-readiness audit (incorporating PR #80)

The Teamstate-side technical audit for this lane is done and merged:
[TIBER-Teamstate PR #80](https://github.com/Prometheus-Frameworks/TIBER-Teamstate/pull/80),
auditing `data/governed/team_week_raw_v0_2024_real_source_candidate.json` against Direction A.
Findings incorporated into this architecture:

- **The governed 2024 source is valid at team-week grain.** `provenanceStatus:
  "governed_real_data"`, `governance.governanceStatus: "governed"`,
  `governance.governanceSource: "explicit_marker"` — all independently verified against the
  committed artifact, not assumed from the operator comment.
- **Coverage: 32 teams / 544 played team-game rows.** `metadata.coverage.isFullLeague: true`,
  `missingTeams: []`, weeks 1–18, `expectedTeamGameRows === actualTeamGameRows === 544`.
- **The source and its consumption boundary are deterministic** — a committed, sha256-pinned
  mirror read through `teamWeekRawV0GovernedAdapter`, which is null-aware and fail-closed. This
  determinism claim is scoped to the *input and boundary*, not to any report: no report derivation
  exists yet, so "the report is deterministically regenerable" cannot be claimed until one does.
- **No field is automatically season-publication-ready.** Field availability at team-week grain
  (19 non-withheld fields, all present with 0 nulls except the null-aware `redZoneTdRate`) is a
  different question from season-level publication eligibility. Every one of those 19 fields needs
  an explicit, documented aggregation decision before a season value can be published:
  - counts (`pointsFor`, `offensivePlays`, `neutralPlays`, `drives`, `redZoneTrips`,
    `sacksAllowed`, `turnovers`) need an explicit season-total vs. per-game presentation decision;
  - rate/pace fields (`secondsPerPlay`, `epaPerPlay`, `successRate`, `explosivePlayRate`,
    `passRate`, `rushRate`, `neutralPassRate`) need play- or neutral-play-weighted aggregation, not
    an unweighted mean of weekly rates;
  - `pointsPerDrive` needs drive-weighted aggregation;
  - `redZoneTdRate` needs `redZoneTrips`-weighted aggregation with null preservation for
    legitimate zero-red-zone-trip weeks, not simple exclusion-then-average;
  - `passEpaPerPlay`/`rushEpaPerPlay` need exact pass-/rush-play denominators that are not
    explicit fields in the source row — deriving them by multiplying a rate by total plays would
    introduce unacknowledged approximation and must not be assumed silently;
  - `pointsAgainst` needs an explicit scope rationale for inclusion in an *offensive*-environment
    report at all, not automatic inclusion because it happens to be available.
- **`pressureRateAllowed` and the 8 fantasy split fields are withheld**, matching the operator
  comment's required exclusions exactly: `pressureRateAllowed` is `deferred` (544/544 null,
  unavailable, never zero-filled) and the fantasy split fields are 544/544 null / absent in
  practice.
- **Two artifacts are confirmed ineligible substitutes and must not be used:**
  `data/processed/2026_team_offensive_environment_v0.json` in TIBER-Teamstate is a **2026,
  operator-seeded, qualitative-label** artifact unrelated to the 2024 governed team-week data
  despite the similarly worded name; and the Forecast Run 2 handoff packet
  (`team_week_raw_v0_2024_forecast_run2.full.json`) is scoped and enveloped for Forecast's gate
  evaluation, not for public consumption, and must not be exposed directly as the public report.

**Net effect on this architecture:** the data layer is ready; the derivation layer is not. §13
scopes the issue that closes that gap.

---

## 5. First bounded public question

Per Direction A, the first public question is scoped as a **historical** report, not current-season
or forecast truth:

> How did all 32 NFL offensive environments compare during the 2024 regular season, based on
> governed observed team-week data?

Rationale (from the operator decision): the governed 2024 source already exists; coverage is all
32 teams and 544 played team-game rows; provenance, cutoff, coverage, and null semantics are
explicit; the report can be regenerated deterministically at the source layer; and this lets TIBER
prove the complete publication pathway before starting another upstream current-data project.

**Unsupported lanes explicitly excluded** from this first report (per the operator comment and
confirmed by §4): current or future-week expectations, market priors, coaching forecasts, QB
stability, pressure rate, fantasy-position split fields, and any field not supported by the
governed 2024 source and a documented Teamstate derivation. The report must be clearly labeled as
a historical 2024 regular-season comparison, not a current or predictive statement.

---

## 6. Human-readable report contract (proposed)

### Route identity

A public report needs **two** distinct route/identity concepts, not one mutable canonical route,
so that a later methodology revision can never make an earlier report's response silently change
or disappear:

- a **canonical alias** — e.g. `/nfl/2024/offensive-environments` — that always resolves to
  whatever report is currently `current` (§8's supersession status) for that declared scope; and
- an **immutable versioned identity** — a report/artifact identity (route or ID, exact syntax left
  to the Teamstate contract issue, §13) that, once published, keeps returning that exact version's
  content forever, even after the canonical alias moves on to a superseded successor.

Without both, "superseded reports remain reachable" (§3, §8) is a stated guarantee with no way to
implement it: if methodology v2 replaces v1 at the same mutable URL, v1's content is either
silently overwritten or lost. The versioned identity is what a citation, an agent tool, or a
search index can point to permanently; the canonical alias is what a human question resolves to
today.

Candidate canonical alias:

```text
/nfl/2024/offensive-environments
```

Required page elements:

- report title, stated as a historical comparison (e.g. "2024 NFL Offensive Environments —
  Regular-Season Comparison");
- season scope (2024 regular season, weeks 1–18) — explicitly not current-season;
- the three distinct temporal facts (§8): when the underlying football events occurred
  (`data_through`/`coverage_cutoff`), when the upstream source bytes were retrieved
  (`source_snapshot_at`), and when this report was derived (`generated_at`) — not collapsed into
  one ambiguous "cutoff" timestamp;
- coverage summary against the report's declared scope (§3) — for this report, 32/32 teams,
  544/544 team-game rows, full regular-season calendar;
- provenance status (`governed_real_data`) and governance reference;
- methodology version, linking to the season-aggregation methodology document that §13 will
  produce (this document does not itself define that methodology — see §4's finding that no
  aggregation decision is made yet);
- source artifact references (artifact ID, sha256, upstream lineage/validation report paths);
- supported environment lanes (the fields the eventual contract actually publishes, once §13's
  aggregation decisions are made) and which lanes are explicitly excluded and why
  (`pressureRateAllowed`, fantasy splits, any current/future/model-derived lane);
- per-team observed supporting signals and deterministic derivations;
- uncertainty and missing-data warnings (e.g. null-aware handling of zero-red-zone-trip weeks);
- supersession status (whether this report has been superseded by a later version) and, if
  superseded, a link to its successor at the canonical alias;
- the immutable versioned identity for this exact report version, distinct from the canonical
  alias;
- a link to the machine-readable representation (§7);
- clear language describing what the report does not claim — it is a historical, observed,
  governed-source comparison, not a projection, ranking recommendation, or advice surface.

The page must answer the recognizable football question in §5, not merely display internal
contract fields.

---

## 7. Machine-readable report contract (proposed, illustrative)

Candidate route:

```text
/nfl/2024/offensive-environments.json
```

Illustrative shape — **not final**; the actual field list depends on the season-aggregation
methodology decisions §13 scopes, and must publish only fields with a documented, justified
derivation, excluding the withheld fields in §4. Note the three separated temporal fields (§6, §8)
and the versioned-identity fields (§6) — none of these collapse into a single ambiguous timestamp
or a single mutable URL:

```json
{
  "artifact": "public_team_offensive_environment_report_v1",
  "schema_version": "1.0.0",
  "report_version_id": "teamstate_public_offensive_environment_2024_v1.r1",
  "canonical_url": "/nfl/2024/offensive-environments",
  "version_url": "/nfl/2024/offensive-environments/v1",
  "season": 2024,
  "scope": "regular_season_historical",
  "declared_scope": "all_32_nfl_teams_2024_regular_season",
  "generated_at": "ISO-8601 timestamp — when this report was derived",
  "data_through": "ISO-8601 date — latest football event/date included (2024 regular season)",
  "source_snapshot_at": "ISO-8601 timestamp — when the upstream source bytes were retrieved",
  "coverage": {
    "team_count": 32,
    "expected_team_count": 32,
    "is_full_league": true,
    "team_game_row_count": 544
  },
  "provenance_status": "governed_real_data",
  "methodology_version": "teamstate_public_offensive_environment_2024_v1",
  "source_artifacts": [],
  "warnings": [],
  "supersession_status": "current",
  "teams": [
    {
      "team": "DET",
      "supported_lanes": {},
      "observed_signals": [],
      "derived_signals": [],
      "warnings": []
    }
  ]
}
```

This shape is illustrative only, inherited from issue #11's original sketch and narrowed to the
historical-2024 scope. The final contract must include only fields supported by a documented
Teamstate derivation (§13) — it must not simply enumerate every field §4 found "source available."

---

## 8. Required metadata

Every public report (human- and machine-readable) must carry:

- **Provenance:** the governing `provenanceStatus` and its governance markers
  (`governanceStatus`, `governanceSource`), consistent with §3's eligibility matrix — no report
  publishes without these.
- **Coverage:** `declared_scope`/`expected_entities` (what population the report claims to cover),
  actual coverage measured against that declared scope (entity count vs. expected, row count vs.
  expected), and an explicit `is_full_league` flag distinct from "complete against declared scope"
  — a report can satisfy the latter while declaring a scope narrower than full-league (§3). For
  weekly/partial scopes (not used in the v0 historical report), week coverage as well.
- **Temporal metadata (three distinct facts, never collapsed into one "cutoff" field):**
  - `data_through` / `coverage_cutoff` — the latest football event/date the report's data
    actually includes (e.g. end of the 2024 regular season);
  - `source_snapshot_at` — when the upstream source bytes were retrieved (the governed source
    already carries a retrieval/snapshot timestamp at the TIBER-Data layer; the public report must
    preserve it, not discard it);
  - `generated_at` — when this public report itself was derived from the governed source.

    These can differ substantially (a report generated today can still have `data_through` fixed
    at the end of the 2024 season), and conflating them would misstate either how current the
    football facts are or how current the report's generation is.
- **Methodology:** a versioned methodology identifier that resolves to a published derivation
  document — the aggregation/weighting/normalization decisions from §4/§13, not an internal
  implementation detail left undocumented.
- **Warnings:** explicit, structured warnings for any null-aware or partial field (e.g. weeks
  excluded from a `redZoneTdRate` season average), never silent.
- **Supersession:** a status field distinguishing `current` from `superseded`, with superseded
  reports pointing to their successor. This is only implementable given §6's two-identity
  requirement: the immutable versioned identity keeps returning the superseded version's exact
  content, while the canonical alias moves forward to point at the new current version — a single
  mutable URL cannot satisfy both "superseded reports remain reachable" and "the canonical route
  always shows the current report."

---

## 9. Ownership boundaries

**TIBER-Data owns:** canonical raw and derived source inputs; team identity; source metadata;
retrieval timestamps; provenance; temporal validity; legal and source-safe ingestion; governed
source artifacts.

**TIBER-Teamstate owns:** deterministic team-environment derivations; environment contracts;
explanation language; coverage and warning propagation; report generation; Teamstate public
routes; Teamstate methodology (including the season-aggregation methodology §13 scopes).

**TIBER-Ops owns:** cross-repository publication architecture (this document); publication
eligibility policy (§3); rollout order; public-surface governance; agent-discovery strategy;
reusable standards; cross-repo readiness decisions (§14). Per TIBER-Ops's own charter, this repo
is docs-only — it defines policy, it does not implement it.

**TIBER-Fantasy owns:** future user-facing product composition; fantasy-specific interpretation
surfaces; roster-aware experiences; advice boundaries. Fantasy is explicitly not part of this v0
public-knowledge pilot.

No repository should invent upstream truth that belongs to another repository.

---

## 10. Fail-closed publication behavior

The public knowledge layer must default to **not publishing** whenever a requirement is unmet,
mirroring the fail-closed pattern TIBER-Teamstate's own governed adapter already implements
(governance accepted only from explicit upstream markers; nulls never zero-filled or estimated;
path/filename/validation-success never substituted for a real eligibility check):

- Missing, malformed, or non-explicit provenance/governance markers → **withhold**, do not publish
  with a best-effort label.
- Actual coverage that does not satisfy the report's own `declared_scope`/`expected_entities`
  (§3) — missing teams, missing weeks, missing whatever population the report declares — →
  **withhold** or explicitly re-scope the claim to match actual coverage (e.g. relabel as
  partial), never publish the declared-scope claim anyway. This applies at any declared scope, not
  only full-league ones: a one-team report missing that team's data fails closed exactly like a
  league-wide report missing teams would.
- A field lacking a documented aggregation/derivation decision (§4) → **omit that field**, do not
  publish an unweighted or approximated value silently.
- A report route with no corresponding contract + validator → the route does not exist; do not
  serve a partial or draft response.
- `service-metadata.json`'s `artifact_publication_enabled` stays `false` and `public_reports`
  stays `[]` until a specific report has a contract, a validator, and explicit publication
  authorization — the presence of usable data is not sufficient authorization by itself.

---

## 11. Discoverability requirements (defined, not implemented)

Minimum requirements for search engines and AI search systems to eventually discover the public
report — **none of these are implemented by this document**:

- public unauthenticated access;
- stable canonical URLs;
- server-rendered or static essential content;
- descriptive page titles;
- meta descriptions;
- canonical link tags;
- `robots.txt`;
- XML sitemap;
- useful internal links;
- public methodology pages;
- structured data matching visible content;
- crawlable machine-readable report links;
- no indexing of health, internal, candidate, fixture, or administrative routes;
- explicit handling for deprecated or superseded reports (§8's supersession status feeding
  canonical/redirect behavior).

The architecture distinguishes, in increasing order of intentionality: **publicly reachable**
(true today — the Railway scaffold is live) → **crawlable** → **indexed** → **likely to rank** →
**directly callable through an API** → **deliberately connected through a future agent tool**. The
current service is only at the first stage. Moving to later stages requires the phases in §12, not
this document.

---

### Future direct-agent access (documented, not implemented)

Documented for later progression, not implemented:

- versioned REST endpoints;
- downloadable schemas;
- read-only MCP server;
- ChatGPT or other assistant integration;
- tools such as `get_team_environment`, `get_offensive_environment_report`,
  `compare_team_environments`, `get_environment_movement`, `get_report_provenance`.

Direct agent access must remain downstream of the same publication eligibility gate (§3) used by
the public website. An agent must not gain access to candidate or internal artifacts merely
because it is using a direct tool instead of web search.

---

## 12. Phased implementation plan

- **Phase 0 — completed.** Teamstate Railway-compatible HTTP scaffold; stable live URL; health
  endpoint; service metadata; artifact publication disabled.
- **Phase 1 — this document (and TIBER-Teamstate PR #80 feeding it).** Publication architecture;
  eligibility matrix; Teamstate artifact-readiness audit; first public-question selection;
  human-readable contract sketch; machine-readable contract sketch; ownership boundaries;
  discoverability requirements.
- **Phase 2 — next Teamstate issue (scoped in §13, not yet opened). Contract design only, no
  publication code.** The season-aggregation methodology; the final HTML and JSON schemas;
  publication invariants; a validator **specification** and fail-closed acceptance test cases
  (not validator code); route identities (§6's canonical-alias/immutable-version requirement); and
  implementation acceptance criteria that Phase 3 must satisfy. Nothing in Phase 2 is deployed or made publishable.
- **Phase 3 — implementation (a separate, later issue, not authorized by this document).**
  Derivation code, validator code, the HTML and JSON routes, and any `service-metadata.json`
  changes, all built to the Phase 2 contract's acceptance criteria. Publication stays disabled
  (`artifact_publication_enabled: false`) until this implementation passes review and receives its
  own explicit authorization — passing Phase 2 does not pre-authorize Phase 3's output for
  publication.
- **Phase 4.** Methodology page; canonical URLs; crawler policy; sitemap; indexing controls; report
  supersession handling. Discoverability/indexing implementation is later work, not part of Phase
  2 or Phase 3.
- **Phase 5.** Repeatable weekly or seasonal publication process; freshness monitoring;
  publication validation; operator approval workflow.
- **Phase 6.** Evaluate public API or MCP access; expand the pattern to the next TIBER repository
  only after Teamstate proves the pathway.

---

## 13. Scope of the next Teamstate contract-design issue

Not opened by this document — deliberately deferred until this architecture decision is merged, per
explicit operator instruction. When opened, its scope is **Phase 2 only (§12): contract design,
zero publication code.** Deliverables are documents, schemas, and test cases — no derivation code,
no validator code, no routes, no `service-metadata.json` changes:

**Define the `teamstate_public_offensive_environment_2024_v1` report contract:**

1. A documented, field-by-field team-season aggregation methodology over
   `teamWeekRawV0GovernedAdapter` output, resolving each open decision PR #80 identified:
   - season-total vs. per-game presentation for `pointsFor`, `offensivePlays`, `neutralPlays`,
     `drives`, `redZoneTrips`, `sacksAllowed`, `turnovers`;
   - the play/neutral-play/drive weighting for `secondsPerPlay`, `epaPerPlay`, `successRate`,
     `explosivePlayRate`, `passRate`, `rushRate`, `neutralPassRate`, `pointsPerDrive`;
   - `redZoneTrips`-weighted, null-preserving aggregation for `redZoneTdRate`;
   - an explicit, non-approximated denominator sourcing decision for `passEpaPerPlay` and
     `rushEpaPerPlay`;
   - an explicit scope rationale for including or excluding `pointsAgainst`;
   - the `declared_scope`/`expected_entities` statement for this report (§3) — all 32 NFL teams,
     complete 2024 regular season — and the coverage check against it.
2. Confirmation that `pressureRateAllowed` and the 8 fantasy split fields stay withheld.
3. The human-readable page contract (§6, finalized), including the canonical-alias and
   immutable-versioned-identity requirement.
4. The machine-readable JSON contract (§7, finalized), including the split temporal metadata
   (`data_through`/`coverage_cutoff`, `source_snapshot_at`, `generated_at`) and versioned identity.
5. A **validator specification and fail-closed acceptance matrix** per §10 — the documented rules
   and test cases an implementation must satisfy (e.g. "given rows missing team X, the validator
   must reject publication with reason Y") — not a working validator. Writing the validator is
   Phase 3.

Implementation — derivation code, validator code, the HTML/JSON routes, and any
`service-metadata.json` changes — is explicitly **Phase 3, a separate later issue**, not
authorized by the contract-design issue and not to be scoped into it. Publication stays disabled
until Phase 3's implementation passes review and receives its own explicit authorization.

---

## 14. Acceptance criteria check

- [x] TIBER-Ops is established as the canonical parent for the public knowledge and
      agent-discovery lane (§0, §1).
- [x] Teamstate #77 is documented as the historical misfiled architecture issue (§1).
- [x] Teamstate #78 and PR #79 are documented as the completed deployment bridge (§1).
- [x] The live Railway URL is recorded (§1).
- [x] Current service metadata is recorded with artifact publication disabled (§1).
- [x] Internal artifacts are clearly separated from public knowledge outputs (§2).
- [x] A publication eligibility matrix is defined (§3).
- [x] Fixture, sample, candidate, operator-seeded, pending, and unknown-provenance states cannot
      silently publish as authority (§3, §10).
- [x] Current Teamstate artifacts are audited for public readiness (§4, via PR #80).
- [x] One bounded public football question is selected (§5).
- [x] Unsupported lanes are explicitly excluded (§5, §4).
- [x] A human-readable report contract is defined (§6).
- [x] A machine-readable report contract is defined (§7).
- [x] Provenance, cutoff, coverage, methodology, warnings, and supersession requirements are
      specified (§8).
- [x] Repository ownership is explicit (§9).
- [x] Crawler, sitemap, canonical URL, metadata, and indexing requirements are documented (§11).
- [x] No football artifact is published in this issue.
- [x] No MCP server or full public API is implemented (§11).
- [x] The report identifies the next bounded Teamstate **contract-design** issue (§13) — explicitly
      not an implementation issue; implementation is a separate, later Phase 3 (§12).
- [x] The report ends with one machine-readable decision (below).

## Non-goals (unchanged from issue #11)

Rebuilding the Teamstate deployment scaffold; reopening Teamstate #77; publishing every existing
Teamstate artifact; exposing repository directories directly; making fixture or provisional data
public to make the service look complete; creating fantasy rankings, start/sit advice, trade
advice, or betting recommendations; building a full TIBER public API; building an MCP server;
expanding immediately into every TIBER repository; optimizing search ranking before publication
safety and report quality exist; styling the current deployment scaffold as a finished product;
treating public reachability as equivalent to governed publication readiness.

## Final machine-readable decision

```text
may_open_teamstate_public_report_contract_issue
```

The governed 2024 source and its consumption boundary are ready (§4). The gap is entirely the
undocumented season-aggregation methodology, not the data. The next step is opening the
Teamstate contract-design issue scoped in §13 — not implementation, and not `do_not_proceed`, since
nothing found here blocks the pathway; and not `requires_upstream_data_or_governance_work`, since
no upstream (TIBER-Data) gap was found.
