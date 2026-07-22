# Research Observatory source-use and admissibility policy v0

Status: **RD1-F candidate deliverable — DRAFT for independent review; NOT adopted policy**
Owning issue: [TIBER-Ops #24](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24)
Frontier: `RD1-F — source-use and admissibility policy`
Work item: `research_observatory_rd1_f_source_admissibility_v0`
Authority: [scope approval](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5040660662) and signed [activation](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5040664503) of the exact proposal [#24 comment 5034511886](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5034511886), SHA-256 `31b3245cd770aff0f154e18a2df51877703cbfc6d881b8aaf0ec5f5fc3ee2e56`
Predecessor: accepted RD1 audit `docs/architecture/research-observatory-readiness-inventory-v0.md`, blob `149e60f3f2634021f743d83fe7ee02b396c58577`, document SHA-256 `a5104706260b83888d4a94e0623ded78d165d611dbe1de8893a939503e1dbe77`, merge commit `c443f281f184301edd8dc70eeb218cbc5b777edf`
Drafted: 2026-07-22 UTC (rev. 3 after second independent review)
Terminal result: **`source_use_admissibility_policy_ready_for_operator_decision`** (provisional; pending fresh-context independent review of this head)

> This document is a **policy proposal**, not legal advice, not adopted policy, and not permission to acquire, retain, transform, publish, or redistribute any data. Every classification below is an operator-policy candidate. A source becomes usable only through the separate operator adoption and later feasibility/acquisition controls applicable to its disposition. Unknown or conflicting rights fail closed.

## 1. What this document decides, and what it does not

RD1 (`source_temporal_audit_requires_followup`) established that TIBER can *reach* a large body of football data but has not established the rights to *use* most of it, nor the point-in-time evidence to use it faithfully. RD1 named seven follow-ups. This document is the decision artifact for follow-ups **1** (a source-use policy by source family and intended use) and **2** (a narrow admissible-source decision), and it makes the review-gate portion of follow-up **7** explicit (which questions cannot be closed without qualified rights/licensing input).

It does **not** resolve: archive feasibility, point-in-time availability, a replacement injury source, receiver-alignment/tracking acquisition, correction/cutoff policy, snapshot architecture, question generation, or any research/model/forecast/product run. Those remain parked (§9).

**Central distinction carried from RD1:** *technical accessibility is not permitted use.* Public availability, an open-source loader, a repository-level licence, or possession of a URL is never, by itself, authority for acquisition, retention, model use, publication, or redistribution.

## 2. Method and evidence discipline

Under the approved RD1-F scope, this discovery:

- evaluated **only** the closed source universe frozen by RD1 (§4 of the proposal; §3 below). No new provider or dataset was searched.
- **read only primary licence, terms, and documentation pages already cited by RD1**, to detect material change. Retrieval date recorded below and per row in §5.
- did **not** download, sample, retain, hash, transform, or inspect any source **data** asset. Reading terms/licences is not source-corpus acquisition.
- fails closed on unknown or conflicting rights, and routes conflicts to qualified review rather than silently admitting them.

### 2.1 Fresh re-verification log (2026-07-22 UTC)

Rights-determinative primary pages:

| Primary page re-read | RD1 citation | Result 2026-07-22 |
| --- | --- | --- |
| nflverse-data `LICENSE.md` | [link](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) | CC BY 4.0 confirmed; attribution + indicate-modifications + retain-licence obligations. **No material change.** |
| `nflreadr` Terms of Use | [link](https://github.com/nflverse/nflreadr#terms-of-use) | "NFL data accessed by this package belong to their respective owners, and are governed by their terms of use"; MIT covers code only. **No material change.** |
| NFL Terms of Service | [link](https://www.nfl.com/legal/terms/) | Individual non-commercial/informational use only; "Systematic retrieval of data or other content … to create or compile … a collection, compilation, database, or directory, is prohibited absent … express prior written consent." **No material change.** |
| FTN charting (`load_ftn_charting`) | [link](https://nflreadr.nflverse.com/reference/load_ftn_charting.html) | CC BY-SA 4.0; required attribution "FTN Data via nflverse"; share-alike. **No material change.** |
| Participation (`load_participation`) | [link](https://nflreadr.nflverse.com/reference/load_participation.html) | CC BY-SA 4.0; attribution "FTN Data via nflverse" (2023+) vs "NFL NextGenStats via nflverse" (≤2022); "prior to 2023 is from NFL NGS … from 2023 onwards is courtesy of FTN"; "from 2023 onwards is provided after all post-season games are completed." **No material change.** |
| Genius Sports distribution | [link](https://www.nfl.com/news/nfl-extends-strategic-partnership-with-genius-sports) | Exclusive distributor of real-time official play-by-play and proprietary Next Gen Stats through 2027-28. **No material change.** |
| Sports Reference data-use policy | [link](https://www.sports-reference.com/data_use.html) | **HTTP 403 — could not re-verify.** Fail closed: RD1's finding is carried unchanged; PFR-derived snap counts remain excluded pending express review. |

Source-specific loader/documentation pages (already cited by RD1) were re-read per family on 2026-07-22 and their links and retrieval dates are recorded in each §5 row: `load_pbp`, `load_schedules`, `load_rosters_weekly`, `load_depth_charts`, `load_injuries`, `load_nextgen_stats`, and the [official Big Data Bowl page](https://operations.nfl.com/programs-initiatives/innovation/big-data-bowl). These documentation pages carry coverage/grain/cadence, not a licence; the licence and owner-reservation live in the two nflverse rights pages above. **No material change** in coverage/grain was observed except one **parked source-identity delta** for depth charts (§5.5, §9).

No re-read contradicted an accepted RD1 finding, changed the frozen source universe, or required a broader source or rights interpretation. No RD1 correction is triggered.

## 3. Closed source universe

Evaluated families (frozen by RD1; expansion is a parked discovery needing separate scope authority):

1. nflverse play-by-play
2. nflverse weekly player/team statistics
3. nflverse games and schedules
4. nflverse weekly rosters
5. nflverse depth charts
6. nflverse historical injuries
7. nflverse / PFR snap counts
8. nflverse weekly NGS aggregates
9. nflverse FTN charting
10. nflverse participation data (split into 10a FTN-era 2023+ and 10b NGS-era ≤2022)
11. NFL Game Books
12. NFL public injury-report surfaces
13. NFL public statistics and correction surfaces
14. NFL Pro / public Next Gen Stats surfaces
15. Genius Sports (potential licensed path)
16. Big Data Bowl releases
17. `nflreadr` / `nflreadpy` (access tooling only)

## 4. Classification legend

**Intended-use axes** (evaluated separately for every family; a permission on one axis never implies another):

1. **Machine acquisition** — automated/programmatic retrieval of the asset.
2. **Exact-byte retention** — keeping the retrieved bytes as a TIBER object.
3. **Internal research use** — internal analysis, not exposed outside TIBER.
4. **Model / analytical use** — use in analytical or agent/model pipelines. Shown for two data-handling cases where they differ: **local/internal** and **transfer of records to a hosted third-party model.**
5. **Transformation & derived-artifact retention** — building and keeping derived artifacts.
6. **Public findings / derived-output publication** — publishing aggregate findings or derived outputs.
7. **Raw-data redistribution** — redistributing the underlying records.

**Per-cell classification** — exactly one of:

```text
operator_policy_candidate_permitted
operator_policy_candidate_permitted_with_obligations
operator_policy_candidate_not_permitted
unresolved_fail_closed
not_applicable
```

**Two result columns where a repository licence sits over an unresolved upstream layer.** For the nflverse statistical families, a **CC BY 4.0 compilation-layer** column records what nflverse's own repository grant would support — this is **contingent evidence, not present permission** — and a **Net authority** column records the operative result once the unresolved upstream reservation is accounted for. Where there is no separately reserved upstream layer (e.g. FTN's own CC BY-SA product), a single **Net authority** column is used. The operative classification is always the Net-authority column.

**Per-family evidence contract.** Every one of the 18 rendered rows (17 families; participation split 10a/10b) records the same template: provider and upstream owner — or a clearly identified attributed source when ownership is unproven; direct primary evidence links with retrieval date; the complete seven-axis intended-use matrix; explicit obligations (including *not applicable while fail-closed* where the net authority is fail-closed); operator/qualified-review requirement; inherited temporal/revision caveats; and exactly one disposition.

**Per-family disposition** — exactly one of:

```text
candidate_for_later_feasibility_review
manual_reference_only
excluded
held_for_qualified_review
```

## 5. Source-family policy rows

### 5.1 nflverse play-by-play

- **Provider / upstream owner:** nflverse (compilation) over NFL-owned underlying game data.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (retrieved 2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) reserving underlying NFL-data ownership (2026-07-22); loader documentation [`load_pbp`](https://nflreadr.nflverse.com/reference/load_pbp.html) (2026-07-22, 1999+, play grain, no formal on-page correction schedule); [nflverse update schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) and [dated archives](https://github.com/nflverse/nflverse-data-archives/releases) per RD1 §5.1.
- **Rights posture:** two layers. nflverse's compilation is affirmatively CC BY 4.0 (fresh-verified) — **contingent evidence only**. The underlying NFL-data ownership is expressly reserved by `nflreadr` and is **unresolved**; a repository-level licence does not override upstream-owner terms. Because the unresolved layer gates every use, the **net authority is uniformly fail-closed**.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed.* If qualified review clears the family, CC BY 4.0 attribution to nflverse, indicate-modifications, retain-licence-notice, and full RD1 §8 provenance would attach; TIBER internal provenance is required regardless as operator policy.
- **Operator / qualified review required:** **Yes** — the CC BY 4.0-vs-upstream-owner relationship (RD1 follow-up #1/#7).
- **Temporal caveats (RD1):** rolling release filenames overwritten; dated archives periodic and overwrite-capable; current URLs are not historical revisions. Point-in-time availability is a later step.
- **Disposition:** `held_for_qualified_review`. *Contingent path:* if qualified review confirms the CC BY 4.0 compilation grant governs an internal-use-only, attribution-bound profile, the net cells for acquisition/retention/internal-use/transformation would become `operator_policy_candidate_permitted_with_obligations` and the family could enter a later archive-feasibility gate.

### 5.2 nflverse weekly player/team statistics

- **Provider / upstream owner:** nflverse (compilation) over NFL-owned underlying game data; these are player-week/team-week derivatives of play-by-play.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); parent loader [`load_pbp`](https://nflreadr.nflverse.com/reference/load_pbp.html) (2026-07-22) and [nflverse update schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) per RD1 §5.1.
- **Rights posture:** as §5.1 — CC BY 4.0 compilation is contingent evidence; underlying NFL-owner reservation unresolved; net authority fail-closed.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed* (CC BY 4.0 attribution would attach if cleared; TIBER internal provenance required regardless).
- **Operator / qualified review required:** Yes (as §5.1).
- **Temporal caveats (RD1):** shares play-by-play correction exposure; historical values can also change with calculation-code changes; RDS metadata may retain nflfastR version/timestamp, CSV loses it; stable release filenames overwritten.
- **Disposition:** `held_for_qualified_review` (contingent path as §5.1).

### 5.3 nflverse games and schedules

- **Provider / attributed source:** nflverse compilation; the schedules file is maintained within nflverse (`nfldata`, Lee Sharpe) over NFL-owned game facts. Underlying game data is NFL-owned.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); loader [`load_schedules`](https://nflreadr.nflverse.com/reference/load_schedules.html) (2026-07-22, game grain, past/future rows); [official schedule refresh note](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) per RD1 §5.1.
- **Rights posture:** as §5.1; net authority fail-closed. **Within this row**, RD1's distinction is preserved: **stable game identity** (ids, teams, kickoff) versus **mutable schedule/result fields** (times, scores, market fields). This is a within-row field distinction, not a subrow split.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed* (CC BY 4.0 attribution would attach if cleared; TIBER internal provenance required regardless).
- **Operator / qualified review required:** Yes.
- **Temporal caveats (RD1):** the combined file refreshes every ~5 minutes; mutable fields have no revision identity; each archive date needs an asset/digest check.
- **Disposition:** `held_for_qualified_review`. *Contingent path:* the stable game-identity fields are the strongest candidate for a later feasibility review; mutable schedule/result fields remain fail-closed until revision identity is established.

### 5.4 nflverse weekly rosters

- **Provider / upstream owner:** nflverse compilation; RD1 identified the upstream as an "NFL API" (retain `NFL via nflverse` provenance); the loader page does not restate the provider. Underlying data NFL-owned.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); loader [`load_rosters_weekly`](https://nflreadr.nflverse.com/reference/load_rosters_weekly.html) (2026-07-22, 2002+, player/team/week grain); RD1 §5.1.
- **Rights posture:** as §5.1; net authority fail-closed.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed* (CC BY 4.0 attribution would attach if cleared; TIBER internal provenance required regardless).
- **Operator / qualified review required:** Yes.
- **Temporal caveats (RD1):** current season rebuilt daily ~07:00 UTC; football `week` is not availability time; no documented correction/finalization contract.
- **Disposition:** `held_for_qualified_review`.

### 5.5 nflverse depth charts

- **Provider / upstream owner:** **source-specific upstream unresolved.** RD1 did not resolve the depth-chart upstream, and this row does **not** inherit §5.1's NFL-owner premise. The [`load_depth_charts`](https://nflreadr.nflverse.com/reference/load_depth_charts.html) page (retrieved 2026-07-22) does not identify a provider.
- **Parked source-identity delta (independent review):** the second independent review flagged that the nflreadr 1.5.0 changelog reports the depth-chart source changed from **NFL Data Exchange to ESPN**. This is **parked** (§9): it lies outside RD1-F's already-cited-page boundary, so it is not absorbed here. ESPN terms are **not** inspected or classified, the family is **not** admitted, and the frozen source universe is **not** expanded. Upstream rights remain unresolved and the net authority remains fail-closed regardless of provider identity.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22, contingent compilation-layer evidence only); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); loader [`load_depth_charts`](https://nflreadr.nflverse.com/reference/load_depth_charts.html) (2026-07-22, 2001+, team/player/week grain).

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed.*
- **Operator / qualified review required:** Yes — including resolution of the parked upstream source identity (NFL Data Exchange vs ESPN) before any classification of the actual provider's terms.
- **Temporal caveats (RD1):** daily ~07:00 UTC; from 2025 appended with timestamps (improves ordering, does not freeze the rolling asset); earlier weekly rows do not prove knowability time.
- **Disposition:** `held_for_qualified_review`.

### 5.6 nflverse historical injuries

- **Provider / attributed source:** nflverse compilation; the loader documents the data as "collected from an API for weekly injury report data" (specific upstream unresolved), over NFL club injury-report data. RD1 (fresh-confirmed via the nflverse update schedule) records the source **ended after 2024** — no 2025 data, no ETA.
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); loader [`load_injuries`](https://nflreadr.nflverse.com/reference/load_injuries.html) (2026-07-22, 2009+, weekly report grain with `date_modified`); [nflverse update schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) (source-ended finding) per RD1 §5.1.
- **Rights posture:** as §5.1; net authority fail-closed. The matrix below is for **historical 2009–2024** records; a current recurring feed is `not_applicable` (no provider) and the recurring lane is **blocked**.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition (historical 2009–2024) | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed.*
- **Operator / qualified review required:** Yes. Also inherits the NFL injury-surface question (net remains fail-closed regardless).
- **Temporal caveats (RD1):** `date_modified` helps but does not replace publication/retrieval evidence; no current feed.
- **Disposition:** `held_for_qualified_review`; recurring injury-conditioned research remains **blocked for lack of a current source** (RD1 follow-up #4, parked). Current recurring feed acquisition: `not_applicable`.

### 5.7 nflverse / PFR snap counts

- **Provider / upstream owner:** Pro Football Reference (Sports Reference) via nflverse.
- **Primary evidence:** [Sports Reference data-use policy](https://www.sports-reference.com/data_use.html) — **HTTP 403, could not re-verify** (2026-07-22) → fail closed; RD1's finding stands. A repository-level CC label does not cure the Sports Reference model-use conflict. Loader context: PFR game/player snap counts 2012+ per RD1 §5.1.
- **Rights posture:** additional third-party restriction beyond the nflverse layer; net authority fail-closed on every axis.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | unresolved_fail_closed |
| Exact-byte retention | unresolved_fail_closed |
| Internal research use | unresolved_fail_closed |
| Model / analytical use — local/internal | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | unresolved_fail_closed |
| Public findings / derived-output publication | unresolved_fail_closed |
| Raw-data redistribution | unresolved_fail_closed |

- **Obligations:** *not applicable while fail-closed / excluded.*
- **Operator / qualified review required:** Yes — an **express** review resolving the Sports Reference policy conflict is a precondition.
- **Temporal caveats (RD1):** the pipeline may not revisit already-scraped games; no correction service level is documented; only periodic observations appear in the dated archive releases (per-date/asset verification required).
- **Disposition:** `excluded` (binding rule: PFR snap counts remain excluded unless an express review resolves the Sports Reference conflict).

### 5.8 nflverse weekly NGS aggregates

- **Provider / upstream owner:** nflverse compilation over **NFL Next Gen Stats** (upstream `nextgenstats.nfl.com`).
- **Primary evidence:** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) (2026-07-22); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (2026-07-22); loader [`load_nextgen_stats`](https://nflreadr.nflverse.com/reference/load_nextgen_stats.html) (2026-07-22, 2016+, player-week aggregates, "updates every night", threshold note "NGS will only provide data for players above a minimum number of pass/rush/rec attempts").
- **Rights posture:** as §5.1 (CC BY 4.0 compilation over NFL/NGS upstream); net authority fail-closed.

| Intended-use axis | CC BY 4.0 compilation layer (contingent evidence) | Net authority |
| --- | --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Internal research use | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed.*
- **Operator / qualified review required:** Yes.
- **Temporal caveats (RD1):** current season rebuilt nightly; no public revision history; **missing-not-at-random** (players below provider thresholds are absent, not zero); no raw x-y coordinates.
- **Disposition:** `held_for_qualified_review`. Any admitted use must preserve the absent-vs-zero distinction (RD1 admission rule 7: no semantic substitution).

### 5.9 nflverse FTN charting

- **Provider / upstream owner:** FTN Data (own charting product), distributed via nflverse.
- **Primary evidence:** [`load_ftn_charting`](https://nflreadr.nflverse.com/reference/load_ftn_charting.html) (retrieved 2026-07-22) — **CC BY-SA 4.0**; required attribution "FTN Data via nflverse"; share-alike. Fresh-verified. **No additional upstream reservation was identified in the cited source-specific documentation** for FTN's own charting.
- **Rights posture:** affirmative CC BY-SA 4.0 grant; single Net-authority column.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations |
| Internal research use | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations |

- **Obligations — TIBER policy vs CC legal triggers are distinct:**
  - **TIBER operator policy (always on):** internal provenance and attribution are always required for any retained record — this is the obligation that makes the internal cells `operator_policy_candidate_permitted_with_obligations`. It is a TIBER provenance obligation, **not** a legal-ShareAlike attachment.
  - **CC BY attribution (legal):** attaches when the licensed material is **Shared** (distributed/publicly made available).
  - **CC BY-SA ShareAlike (legal):** attaches when **Adapted Material is Shared**, with the licence's database-specific conditions (adapted-database/sui-generis) preserved.
  - **Private/internal analytical use does not itself trigger legal ShareAlike.**
- **Hosted third-party model transfer** is `unresolved_fail_closed`. The **CC copyright-rights layer is affirmative** (CC BY-SA contains no special AI/model prohibition); the unresolved layer is the **unreviewed hosted-model provider's terms and data handling** — retention, training, sublicensing, disclosure, and related controls — which must be reviewed before records are transferred.
- **Operator / qualified review required:** an **operator policy decision** on whether TIBER will accept CC BY-SA ShareAlike on any *published/redistributed* adaptation; a **qualified-review flag** on the exact scope of ShareAlike/database conditions attaching to a governed TIBER derivative when Shared; and a provider-terms/data-handling review before any hosted-model transfer. Internal-use candidacy does not depend on these.
- **Temporal caveats (RD1):** 2022 onward; charted within ~48h but provider-dependent; rolling asset can be replaced; **not** a receiver-width or all-route-denominator solution. Archive completeness must be verified later.
- **Disposition:** **`candidate_for_later_feasibility_review`** — narrow candidate for **local/internal analytical use** under TIBER provenance + attribution, with hosted-model transfer fail-closed and publication/redistribution gated on the ShareAlike decisions above.

### 5.10a nflverse participation — FTN-era slice (2023 onward)

- **Provider / upstream owner:** FTN Data via nflverse (2023+).
- **Primary evidence:** [`load_participation`](https://nflreadr.nflverse.com/reference/load_participation.html) (retrieved 2026-07-22) — CC BY-SA 4.0; attribution "FTN Data via nflverse" for 2023+; "Participation data from 2023 onwards is courtesy of FTN"; "provided after all post-season games are completed."
- **Rights posture:** as §5.9 (FTN CC BY-SA); no additional upstream reservation identified in the cited source-specific documentation for the FTN-sourced slice.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations |
| Internal research use | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use — local/internal | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations |

- **Obligations:** as §5.9 — TIBER provenance/attribution always on for internal use (not legal ShareAlike); CC BY attribution on Sharing; CC BY-SA ShareAlike + database conditions when Adapted Material is Shared; internal analytical use does not trigger legal ShareAlike.
- **Hosted third-party model transfer:** `unresolved_fail_closed` for the same reason as §5.9 (affirmative CC layer; unresolved model-provider terms/data-handling).
- **Separability condition:** this slice may advance **only if it can be acquired without also retaining unresolved NGS-era (≤2022) records** (§5.10b). If the loader/asset cannot yield the 2023+ FTN slice in isolation, this slice fails closed until it can.
- **Temporal caveats (RD1 + primary):** postseason-only (not an in-season weekly feed); does not expose receiver-width coordinates.
- **Operator / qualified review required:** ShareAlike decision and hosted-model provider-terms review as §5.9.
- **Disposition:** **`candidate_for_later_feasibility_review`** — local/internal analytical use, subject to the separability condition and the ShareAlike/hosted-model gates.

### 5.10b nflverse participation — NGS-era slice (2022 and earlier)

- **Provider / upstream owner:** NFL Next Gen Stats via nflverse (≤2022).
- **Primary evidence:** [`load_participation`](https://nflreadr.nflverse.com/reference/load_participation.html) (retrieved 2026-07-22) — attribution "NFL NextGenStats via nflverse"; "Participation data prior to 2023 is from NFL NGS." The CC BY-SA label sits over an **NFL/NGS upstream layer** that is unresolved as in §5.1/§5.8; the label is contingent evidence, not present permission.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | unresolved_fail_closed |
| Exact-byte retention | unresolved_fail_closed |
| Internal research use | unresolved_fail_closed |
| Model / analytical use — local/internal | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | unresolved_fail_closed |
| Public findings / derived-output publication | unresolved_fail_closed |
| Raw-data redistribution | unresolved_fail_closed |

- **Obligations:** *not applicable while net authority is fail-closed.*
- **Operator / qualified review required:** Yes — NGS upstream-ownership review (as §5.1/§5.8).
- **Temporal caveats (RD1):** NFL NGS through 2022; does not expose receiver-width coordinates.
- **Disposition:** `held_for_qualified_review`.

### 5.11 NFL Game Books

- **Provider / upstream owner:** NFL (owned public PDFs).
- **Primary evidence:** [NFL Terms](https://www.nfl.com/legal/terms/) (retrieved 2026-07-22) — systematic retrieval to build a collection/database prohibited absent express written consent; individual informational use only. Fresh-verified.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_not_permitted |
| Exact-byte retention | operator_policy_candidate_not_permitted |
| Internal research use (automated retained corpus) | operator_policy_candidate_not_permitted |
| Model / analytical use — local/internal | operator_policy_candidate_not_permitted |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_not_permitted |
| Transformation & derived-artifact retention | operator_policy_candidate_not_permitted |
| Public findings / derived-output publication | operator_policy_candidate_not_permitted |
| Raw-data redistribution | operator_policy_candidate_not_permitted |

- **Obligations:** none available to satisfy under current terms (the disposition is a no-corpus posture, not a grant).
- **`manual_reference_only` means:** TIBER's **conservative no-corpus posture** — an operator may consult an individual public PDF as a human, but this is **not** an affirmative grant to incorporate manual observations into TIBER artifacts, datasets, model inputs, or outputs.
- **Operator / qualified review required:** only new authoritative permission or qualified review could narrow this.
- **Temporal caveats (RD1):** no documented revision ID, replacement time, or superseded-PDF archive.
- **Disposition:** `manual_reference_only`.

### 5.12 NFL public injury-report surfaces

- **Provider / upstream owner:** NFL-owned public surfaces.
- **Primary evidence:** [NFL Terms](https://www.nfl.com/legal/terms/) (retrieved 2026-07-22) as §5.11.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_not_permitted |
| Exact-byte retention | operator_policy_candidate_not_permitted |
| Internal research use (automated retained corpus) | operator_policy_candidate_not_permitted |
| Model / analytical use — local/internal | operator_policy_candidate_not_permitted |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_not_permitted |
| Transformation & derived-artifact retention | operator_policy_candidate_not_permitted |
| Public findings / derived-output publication | operator_policy_candidate_not_permitted |
| Raw-data redistribution | operator_policy_candidate_not_permitted |

- **Obligations:** none available to satisfy under current terms.
- **`manual_reference_only` means:** TIBER's conservative no-corpus posture (as §5.11); not a grant to incorporate manual observations into TIBER artifacts or outputs.
- **Operator / qualified review required:** new authoritative permission or qualified review.
- **Temporal caveats (RD1):** no row-level publication timestamp, revision ID, or complete filing history; filing deadlines are not timestamps.
- **Disposition:** `manual_reference_only`.

### 5.13 NFL public statistics and correction surfaces

- **Provider / upstream owner:** NFL-owned.
- **Primary evidence:** [NFL Terms](https://www.nfl.com/legal/terms/) (retrieved 2026-07-22) as §5.11.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_not_permitted |
| Exact-byte retention | operator_policy_candidate_not_permitted |
| Internal research use (automated retained corpus) | operator_policy_candidate_not_permitted |
| Model / analytical use — local/internal | operator_policy_candidate_not_permitted |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_not_permitted |
| Transformation & derived-artifact retention | operator_policy_candidate_not_permitted |
| Public findings / derived-output publication | operator_policy_candidate_not_permitted |
| Raw-data redistribution | operator_policy_candidate_not_permitted |

- **Obligations:** none available to satisfy under current terms.
- **`manual_reference_only` means:** TIBER's conservative no-corpus posture (as §5.11); manual corroboration only, not a grant to incorporate into TIBER artifacts or outputs.
- **Operator / qualified review required:** new authoritative permission or qualified review.
- **Temporal caveats (RD1):** correction dates do not establish a complete prior snapshot; time zone, revision identity, and completeness guarantees are absent.
- **Disposition:** `manual_reference_only`.

### 5.14 NFL Pro / public Next Gen Stats surfaces

- **Provider / upstream owner:** NFL-owned; consumer access is not a machine-use, export, or retention licence.
- **Primary evidence:** [NFL Terms](https://www.nfl.com/legal/terms/) (retrieved 2026-07-22) as §5.11.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | operator_policy_candidate_not_permitted |
| Exact-byte retention | operator_policy_candidate_not_permitted |
| Internal research use (automated retained corpus) | operator_policy_candidate_not_permitted |
| Model / analytical use — local/internal | operator_policy_candidate_not_permitted |
| Model / analytical use — hosted third-party model transfer | operator_policy_candidate_not_permitted |
| Transformation & derived-artifact retention | operator_policy_candidate_not_permitted |
| Public findings / derived-output publication | operator_policy_candidate_not_permitted |
| Raw-data redistribution | operator_policy_candidate_not_permitted |

- **Obligations:** none available to satisfy under current terms.
- **`manual_reference_only` means:** TIBER's conservative no-corpus posture (as §5.11); reference-only, not a grant to incorporate into TIBER artifacts or outputs.
- **Operator / qualified review required:** new authoritative permission or qualified review.
- **Temporal caveats (RD1):** no documented historical revision stream, metric-version contract, or raw coordinate export.
- **Disposition:** `manual_reference_only`.

### 5.15 Genius Sports (potential licensed path)

- **Provider / upstream owner:** Genius Sports as the NFL's exclusive distributor of official real-time play-by-play and proprietary NGS through 2027-28.
- **Primary evidence:** [Genius Sports distribution announcement](https://www.nfl.com/news/nfl-extends-strategic-partnership-with-genius-sports) (retrieved 2026-07-22). No licence terms are known; nothing may be inferred from the public announcement.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | unresolved_fail_closed |
| Exact-byte retention | unresolved_fail_closed |
| Internal research use | unresolved_fail_closed |
| Model / analytical use — local/internal | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | unresolved_fail_closed |
| Public findings / derived-output publication | unresolved_fail_closed |
| Raw-data redistribution | unresolved_fail_closed |

- **Obligations:** *not applicable while fail-closed* (any obligations would come from a negotiated licence).
- **Operator / qualified review required:** Yes — commercial licensing negotiation and qualified rights/licensing review.
- **Temporal caveats (RD1):** a contract would need to define latency, corrections, archive, and version behavior.
- **Disposition:** `held_for_qualified_review` (potential licensed path; contacting/pricing/procuring is a parked follow-up, §9).

### 5.16 Big Data Bowl releases

- **Provider / upstream owner:** NFL, via competition-specific releases (AWS/Kaggle-hosted).
- **Primary evidence:** [official NFL Big Data Bowl page](https://operations.nfl.com/programs-initiatives/innovation/big-data-bowl) (retrieved 2026-07-22, confirmed official; annual competition using NFL data and Next Gen Stats tracking; **no dataset licensing/reuse terms stated on the page** — per-competition terms live on Kaggle and were not audited). Each competition's exact terms govern retention and production reuse.

| Intended-use axis | Net authority |
| --- | --- |
| Machine acquisition | unresolved_fail_closed |
| Exact-byte retention | unresolved_fail_closed |
| Internal research use | unresolved_fail_closed |
| Model / analytical use — local/internal | unresolved_fail_closed |
| Model / analytical use — hosted third-party model transfer | unresolved_fail_closed |
| Transformation & derived-artifact retention | unresolved_fail_closed |
| Public findings / derived-output publication | unresolved_fail_closed |
| Raw-data redistribution | unresolved_fail_closed |

- **Obligations:** *not applicable while fail-closed* (obligations would come from the per-release competition terms, not audited here).
- **Operator / qualified review required:** Yes, per dataset/release. This row does **not** audit release-specific terms.
- **Temporal caveats (RD1):** dataset/task-specific; not a recurring weekly feed.
- **Disposition:** `held_for_qualified_review` (dataset-specific research candidate only; separate per-release audit required before any retention).

### 5.17 `nflreadr` / `nflreadpy` (access tooling)

- **Rights posture:** MIT-licensed access clients. The software licence covers the **code**, not the underlying data.
- **Primary evidence:** [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) (retrieved 2026-07-22, MIT covers code; NFL data belong to owners); [`nflreadpy`](https://github.com/nflverse/nflreadpy) (MIT access client) per RD1 §5.1.

| Intended-use axis | Net authority (as a source of *data* rights) |
| --- | --- |
| Machine acquisition | not_applicable |
| Exact-byte retention | not_applicable |
| Internal research use | not_applicable |
| Model / analytical use — local/internal | not_applicable |
| Model / analytical use — hosted third-party model transfer | not_applicable |
| Transformation & derived-artifact retention | not_applicable |
| Public findings / derived-output publication | not_applicable |
| Raw-data redistribution | not_applicable |

- **Obligations:** as tooling, MIT permits use of the client software; the client's commit/version, loader arguments, and cache mode must be recorded in provenance (RD1 §8). Conveys no data rights.
- **Operator / qualified review required:** not for the tool itself; the underlying data's rights are decided in the data-family rows above.
- **Temporal caveats:** loader/cache version must be captured in provenance for reproducibility.
- **Disposition:** `excluded` **as a data source** (it conveys no data rights). This is a labeling disposition, not an admission of any data.

## 6. Summary matrix

| # | Source family | Disposition | Gating question |
| --- | --- | --- | --- |
| 1 | nflverse play-by-play | held_for_qualified_review | CC BY 4.0 vs reserved upstream NFL-owner terms (net fail-closed) |
| 2 | nflverse weekly stats | held_for_qualified_review | as #1 |
| 3 | nflverse games/schedules | held_for_qualified_review | as #1; stable vs mutable fields distinguished within the row |
| 4 | nflverse weekly rosters | held_for_qualified_review | as #1 |
| 5 | nflverse depth charts | held_for_qualified_review | source-specific upstream unresolved (parked NFL Data Exchange→ESPN delta); net fail-closed |
| 6 | nflverse historical injuries | held_for_qualified_review | as #1 + no current feed (recurring lane blocked) |
| 7 | nflverse / PFR snap counts | **excluded** | Sports Reference data-use conflict (re-verify 403 → fail closed) |
| 8 | nflverse weekly NGS aggregates | held_for_qualified_review | as #1; preserve absent-vs-zero |
| 9 | nflverse FTN charting | **candidate_for_later_feasibility_review** | operator acceptance of CC BY-SA ShareAlike on Sharing; hosted-model transfer fail-closed on provider terms; internal use unaffected |
| 10a | nflverse participation — FTN-era 2023+ | **candidate_for_later_feasibility_review** | as #9 + separable from NGS-era records; postseason-only |
| 10b | nflverse participation — NGS-era ≤2022 | held_for_qualified_review | NGS upstream ownership (net fail-closed) |
| 11 | NFL Game Books | manual_reference_only | NFL Terms bar systematic retrieval (no-corpus posture) |
| 12 | NFL injury surfaces | manual_reference_only | as #11 |
| 13 | NFL stats/correction surfaces | manual_reference_only | as #11 |
| 14 | NFL Pro / public NGS surfaces | manual_reference_only | as #11 |
| 15 | Genius Sports | held_for_qualified_review | unknown licence terms/cost/rights |
| 16 | Big Data Bowl | held_for_qualified_review | per-release terms audit |
| 17 | nflreadr / nflreadpy | excluded (as data source) | none — tooling only, no data rights |

## 7. Narrow candidate source set (RD1 follow-up #2)

The narrowest source set responsibly eligible for a **later archive-feasibility decision**, under this proposal, is:

1. **nflverse FTN charting** (2022+, §5.9), for **local/internal** analytical use under TIBER provenance + attribution; hosted-model transfer fail-closed on provider terms; publication/redistribution gated on the operator's CC BY-SA ShareAlike decision.
2. **nflverse participation — FTN-era slice (2023+, §5.10a)** only, same basis, **subject to the separability condition** (acquirable without retaining unresolved NGS-era records) and the caveat that it is **postseason-only and unsuitable as a live weekly backbone**.

This set is deliberately narrow. The nflverse statistical **backbone** (play-by-play, weekly stats, schedules, rosters, depth charts, NGS aggregates) and the **NGS-era participation slice** are **`held_for_qualified_review`** with **net-authority fail-closed** on the CC BY 4.0/CC BY-SA-vs-upstream question; each would become a candidate for internal use only if that question is resolved. PFR snap counts are **excluded** and all NFL-owned public surfaces are **manual-reference-only** by rule.

**Naming a family a candidate is not permission to acquire it.** It marks it as eligible to enter the *next* (archive-feasibility) gate, which itself precedes any acquisition, retention, or adoption decision.

## 8. Consequences for the initial Research Observatory question envelope (completion criterion #7)

- With the statistical backbone net-authority fail-closed and held for qualified review, the initial envelope **cannot yet admit a recurring cutoff-bound source corpus**. The realistic near-term admissible material is FTN-charted play-level labels (local/internal use), which supports selected play-level questions but **not** the volume/efficiency backbone, and **not** a live weekly cadence (participation is postseason-only).
- **Injury-conditioned** questions remain **blocked** for lack of a current source (RD1 follow-up #4).
- **Receiver-width / all-route** questions remain **not testable** from this universe; formation labels must not be substituted for alignment coordinates (RD1 admission rule 7).
- **Raw player-tracking** questions require the Genius Sports licensed path or a separately cleared competition dataset — both `held_for_qualified_review`.
- Retrospective analysis over **already-governed TIBER artifacts** is a separate matter from this source-corpus policy and is neither approved nor broadened here (see §10).

## 9. Parked follow-ups and deltas (not resolved or activated here)

- **Depth-chart source-identity delta (independent review):** nflreadr 1.5.0 changelog reports the depth-chart source changed from NFL Data Exchange to ESPN. Parked — outside RD1-F's already-cited-page boundary; ESPN terms not inspected/classified; family not admitted; universe not expanded (§5.5).
- **Standing parked follow-ups:** asset-level archive feasibility and point-in-time availability; inspection of archive assets/dates/digests; historical week/cohort selection; injury-provider replacement/procurement; receiver-alignment/tracking/licensed-feed acquisition; contacting/pricing/procuring/evaluating any licensed feed (incl. Genius Sports, Big Data Bowl); capture-timing/correction/cutoff policy; snapshot architecture/storage/manifests/builders; question generation/routing; research execution, modeling, forecasting, scheduling, promotion; any public or recurring source corpus.

Discoveries in these areas must be recorded and parked, not absorbed into RD1-F.

## 10. Interpretation rules applied (proposal §7)

- Unknown or conflicting rights → fail closed. The nflverse upstream question renders the backbone **net-authority fail-closed** despite contingent CC BY 4.0 compilation-layer evidence; Genius, Big Data Bowl, and the Sports Reference 403 likewise fail closed.
- A repository-level licence does not override upstream-owner terms — CC BY 4.0 / CC BY-SA labels are preserved as **contingent evidence, not present permission** where an upstream layer is unresolved.
- An access-client software licence does not license the underlying data (nflreadr/nflreadpy MIT).
- Internal analysis, model use, retained derivatives, public findings, and raw redistribution are decided **separately** on every family; hosted third-party model transfer is called out separately from local/internal use, and its blocker is the unreviewed model-provider terms/data-handling, not a CC AI prohibition.
- TIBER internal provenance/attribution obligations are distinguished from CC legal triggers: CC attribution attaches on Sharing, CC BY-SA ShareAlike attaches when Adapted Material is Shared, and neither is triggered by purely internal analytical use.
- Public access does not imply machine-access, retention, model-use, or redistribution rights (all NFL-owned surfaces `operator_policy_candidate_not_permitted`); `manual_reference_only` is a conservative no-corpus posture, not an affirmative grant to incorporate manual observations into TIBER artifacts or outputs.
- PFR snap counts remain excluded pending express review.
- A TIBER derivative cannot receive broader permissions than the underlying evidence supports; transformation does not launder obligations.
- A positive outcome is reached with a deliberately narrow set while ambiguous families are excluded, manual-only, or held.
- Rights that differ by era/provider/field are handled honestly: **schedules distinguishes stable vs mutable fields within a single row; participation is the family actually split into subrows (10a FTN-era / 10b NGS-era)**.
- No disposition here establishes historical point-in-time availability — that is the later archive-feasibility step.

## 11. Completion criteria check (proposal §8)

1. Every family has a fully populated row — **yes** (§5; 18 rows against the §4 evidence-contract template, participation split 10a/10b; all seven axes with exact enums per cell).
2. Every non-fail-closed claim cites primary evidence — **yes**; per-row direct primary links with retrieval dates are now present in all 18 rows (not "as §5.1"), incl. `load_participation` for the FTN-era candidate.
3. Raw data / derived artifacts / public findings / model use not conflated — **yes** (per-axis cells; hosted-transfer separated with its distinct blocker).
4. Attribution / ShareAlike / retention / redistribution obligations explicit — **yes**; TIBER provenance obligations are distinguished from CC legal triggers (§5.9, §5.10a), and obligations are marked *not applicable while fail-closed* elsewhere.
5. Unresolved conflicts excluded or routed to qualified review, never silently admitted — **yes**; the backbone and NGS-era slice are net-authority fail-closed (§5, §6).
6. Narrow candidate set named, incl. empty-set option — **yes**, non-empty but narrow (§7).
7. Consequences for the question envelope stated — **yes** (§8).
8. Traceability to RD1 follow-ups 1, 2, and review-gate of 7 — **yes** (§12).
9. No existing TIBER artifact retroactively approved/broadened — **affirmed** (§10, §8 final bullet); this policy governs external source admissibility only.
10. Candidate document + terminal token receive fresh-context independent review — **rev. 1 and rev. 2 reviewed (CHANGES REQUIRED); this rev. 3 head is submitted for fresh-context re-review.**
11. Executing agent stops for Joseph's separate terminal-acceptance, merge, policy-adoption, and next-frontier decisions — **yes** (draft PR; not self-merged).

## 12. Requirements traceability

| RD1 follow-up | Addressed by |
| --- | --- |
| #1 — signed source-use policy by family and intended use | §5 per-family rows (full evidence contract); §10 interpretation rules |
| #2 — narrow admissible source set | §7 candidate set (FTN charting; FTN-era participation 10a) |
| #7 (review-gate portion) — where qualified review is required | §5 review flags; §6 gating-question column; §13 terminal rationale |

Follow-ups #3 (archive feasibility), #4 (injury source), #5 (alignment/tracking), and #6 (correction/cutoff policy) remain **parked** (§9).

## 13. Terminal result

```text
source_use_admissibility_policy_ready_for_operator_decision
```

**Rationale.** An independently-reviewable, operator-legible policy proposal now exists. A **narrow, complete** candidate policy is honestly available for an operator decision: admit — for a later archive-feasibility gate — FTN charting and the FTN-era participation slice, for local/internal analytical use under TIBER provenance + attribution, with hosted-model transfer fail-closed on provider terms and publication/redistribution gated on an operator CC BY-SA ShareAlike decision; hold the nflverse statistical backbone and the NGS-era participation slice for qualified review with net authority fail-closed on the CC BY 4.0/CC BY-SA-vs-upstream question; exclude PFR snap counts; keep all NFL-owned public surfaces manual-reference-only; hold Genius Sports and Big Data Bowl for qualified/per-release review. The held rows are dispensable to this narrow policy, so a complete decision does not depend on qualified input — satisfying the positive terminal rather than `..._requires_qualified_review`. The token is **provisional pending fresh-context independent review of this head**.

This token means **only** that a reviewed policy proposal exists. It does **not** approve the policy, admit any source, activate archive feasibility, or authorize acquisition, retention, model use, publication, or redistribution. The candidate set is a proposal for the operator's separate adoption decision.

## 14. Hard stop boundary

This document does not activate RD2, #24's three-run pilot, or #35 F1–F5. It authorizes no source acquisition, data download/sampling/retention/hashing/transformation/inspection, registry change, deployment, publication, scheduling, model run, Forecast influence, or production behavior. It is a docs-only candidate on one non-main branch in one draft PR. Execution stops here for fresh-context independent review and Joseph's separate decisions.
