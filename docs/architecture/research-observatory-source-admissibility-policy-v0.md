# Research Observatory source-use and admissibility policy v0

Status: **RD1-F candidate deliverable — DRAFT for independent review; NOT adopted policy**
Owning issue: [TIBER-Ops #24](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24)
Frontier: `RD1-F — source-use and admissibility policy`
Work item: `research_observatory_rd1_f_source_admissibility_v0`
Authority: [scope approval](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5040660662) and [activation](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5040664503) of the exact proposal [#24 comment 5034511886](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5034511886), SHA-256 `31b3245cd770aff0f154e18a2df51877703cbfc6d881b8aaf0ec5f5fc3ee2e56`
Predecessor: accepted RD1 audit `docs/architecture/research-observatory-readiness-inventory-v0.md`, blob `149e60f3f2634021f743d83fe7ee02b396c58577`, document SHA-256 `a5104706260b83888d4a94e0623ded78d165d611dbe1de8893a939503e1dbe77`, merge commit `c443f281f184301edd8dc70eeb218cbc5b777edf`
Drafted: 2026-07-22 UTC
Terminal result: **`source_use_admissibility_policy_ready_for_operator_decision`**

> This document is a **policy proposal**, not legal advice, not adopted policy, and not permission to acquire, retain, transform, publish, or redistribute any data. Every classification below is an operator-policy candidate. A source becomes usable only through the separate operator adoption and later feasibility/acquisition controls applicable to its disposition. Unknown or conflicting rights fail closed.

## 1. What this document decides, and what it does not

RD1 (`source_temporal_audit_requires_followup`) established that TIBER can *reach* a large body of football data but has not established the rights to *use* most of it, nor the point-in-time evidence to use it faithfully. RD1 named seven follow-ups. This document is the decision artifact for follow-ups **1** (a source-use policy by source family and intended use) and **2** (a narrow admissible-source decision), and it makes the review-gate portion of follow-up **7** explicit (which questions cannot be closed without qualified rights/licensing input).

It does **not** resolve: archive feasibility, point-in-time availability, a replacement injury source, receiver-alignment/tracking acquisition, correction/cutoff policy, snapshot architecture, question generation, or any research/model/forecast/product run. Those remain parked (§9).

**Central distinction carried from RD1:** *technical accessibility is not permitted use.* Public availability, an open-source loader, a repository-level licence, or possession of a URL is never, by itself, authority for acquisition, retention, model use, publication, or redistribution.

## 2. Method and evidence discipline

Under the approved RD1-F scope, this discovery:

- evaluated **only** the closed source universe frozen by RD1 (§4 of the proposal; §3 below). No new provider or dataset was searched.
- **read only primary licence, terms, and documentation pages already cited by RD1**, to detect material change. Retrieval date recorded below.
- did **not** download, sample, retain, hash, transform, or inspect any source **data** asset. Reading terms/licences is not source-corpus acquisition.
- fails closed on unknown or conflicting rights, and routes conflicts to qualified review rather than silently admitting them.

### 2.1 Fresh re-verification log (2026-07-22 UTC)

| Primary page re-read | RD1 citation | Result 2026-07-22 |
| --- | --- | --- |
| nflverse-data `LICENSE.md` | [link](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md) | CC BY 4.0 confirmed; attribution + indicate-modifications + retain-licence obligations. **No material change.** |
| `nflreadr` Terms of Use | [link](https://github.com/nflverse/nflreadr#terms-of-use) | "NFL data accessed by this package belong to their respective owners, and are governed by their terms of use"; MIT covers code only. **No material change.** |
| NFL Terms of Service | [link](https://www.nfl.com/legal/terms/) | Individual non-commercial/informational use only; "Systematic retrieval of data or other content … to create or compile … a collection, compilation, database, or directory, is prohibited absent … express prior written consent." **No material change.** |
| FTN charting (`load_ftn_charting`) | [link](https://nflreadr.nflverse.com/reference/load_ftn_charting.html) | CC BY-SA 4.0; required attribution "FTN Data via nflverse"; share-alike. **No material change.** |
| Genius Sports distribution | [link](https://www.nfl.com/news/nfl-extends-strategic-partnership-with-genius-sports) | Exclusive distributor of real-time official play-by-play and proprietary Next Gen Stats through 2027-28. **No material change.** |
| Sports Reference data-use policy | [link](https://www.sports-reference.com/data_use.html) | **HTTP 403 — could not re-verify.** Fail closed: RD1's finding is carried unchanged; PFR-derived snap counts remain excluded pending express review. |

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
10. nflverse participation data
11. NFL Game Books
12. NFL public injury-report surfaces
13. NFL public statistics and correction surfaces
14. NFL Pro / public Next Gen Stats surfaces
15. Genius Sports (potential licensed path)
16. Big Data Bowl releases
17. `nflreadr` / `nflreadpy` (access tooling only)

## 4. Classification legend

**Intended-use axes** (evaluated separately for every family; a permission on one axis never implies another):

- **Machine acquisition** — automated/programmatic retrieval of the asset.
- **Exact-byte retention** — keeping the retrieved bytes as a TIBER object.
- **Internal research use** — internal analysis, not exposed outside TIBER.
- **Model / analytical use** — use in analytical or agent/model pipelines; **explicitly states whether records would be transferred to a hosted third-party model.**
- **Transformation & derived-artifact retention** — building and keeping derived artifacts.
- **Public findings / derived-output publication** — publishing aggregate findings or derived outputs.
- **Raw-data redistribution** — redistributing the underlying records.

**Per-cell classification** (exactly one):

```text
operator_policy_candidate_permitted
operator_policy_candidate_permitted_with_obligations
operator_policy_candidate_not_permitted
unresolved_fail_closed
not_applicable
```

**Per-family disposition** (exactly one):

```text
candidate_for_later_feasibility_review
manual_reference_only
excluded
held_for_qualified_review
```

## 5. Source-family policy rows

### 5.1 nflverse play-by-play

- **Provider / upstream owner:** nflverse (compilation) over NFL-owned underlying game data.
- **Primary evidence (retrieval 2026-07-22):** nflverse-data CC BY 4.0 `LICENSE.md`; `nflreadr` Terms of Use reserving underlying NFL-data ownership; RD1 §5.1.
- **Rights posture:** two layers. nflverse's compilation is affirmatively CC BY 4.0 (fresh-verified). The underlying NFL data ownership is expressly reserved by `nflreadr` and is **unresolved**; a repository-level licence does not override upstream-owner terms.

| Intended use | Classification |
| --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations (CC BY 4.0 attribution) |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations |
| Internal research use | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use | Internal analytical use: permitted_with_obligations. **Transfer of records to a hosted third-party model: `unresolved_fail_closed`** (implicates unresolved upstream terms). |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations (indicate modifications; derivative cannot launder upstream obligations) |
| Public findings / derived-output publication | Aggregate findings with attribution: permitted_with_obligations. Publication amounting to raw-data republication: see redistribution. |
| Raw-data redistribution | `unresolved_fail_closed` (CC BY 4.0 would permit at the compilation layer, but conflicts with reserved upstream NFL-owner terms). |

- **Obligations:** CC BY 4.0 attribution to nflverse; indicate modifications; retain licence notice; retain full RD1 §8 provenance.
- **Operator / qualified review required:** **Yes** — the CC BY 4.0-vs-upstream-owner relationship (RD1 follow-up #1/#7).
- **Temporal caveats (RD1):** rolling release filenames overwritten; dated archives are periodic and overwrite-capable; current URLs are not historical revisions. Point-in-time availability is a later step.
- **Disposition:** `held_for_qualified_review`. *Contingent path:* would become `candidate_for_later_feasibility_review` for an internal-use-only, attribution-bound profile if qualified review confirms the CC BY 4.0 compilation grant governs internal retained analytical use.

### 5.2 nflverse weekly player/team statistics

Derivative of play-by-play; **identical rights posture, obligations, review requirement, and disposition as §5.1.**

- **Additional temporal caveat (RD1):** historical values can also change with calculation-code changes; RDS metadata may retain nflfastR version/timestamp, CSV loses it.
- **Disposition:** `held_for_qualified_review` (contingent path as §5.1).

### 5.3 nflverse games and schedules

- **Rights posture:** as §5.1 (CC BY 4.0 compilation + unresolved upstream). Per RD1, the row must be split: **stable game identity** (ids, teams, kickoff) vs **mutable schedule/result fields** (times, scores, market fields refreshing every ~5 minutes).
- **Intended-use cells:** as §5.1 (acquisition/retention/internal/transformation/findings = permitted_with_obligations; hosted-model transfer and raw redistribution = `unresolved_fail_closed`).
- **Temporal caveats (RD1):** mutable fields have no revision identity; each archive date needs an asset/digest check.
- **Operator / qualified review required:** Yes (as §5.1).
- **Disposition:** `held_for_qualified_review`. *Contingent path:* stable game-identity fields are the strongest candidate for a later feasibility review; mutable schedule/result fields remain fail-closed until revision identity is established.

### 5.4 nflverse weekly rosters

- **Rights posture:** as §5.1; RD1 notes upstream is "NFL API"; retain `NFL via nflverse` provenance and resolve rights.
- **Intended-use cells:** as §5.1.
- **Temporal caveats (RD1):** current season rebuilt daily ~07:00 UTC; football `week` is not availability time; no documented correction/finalization contract.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`.

### 5.5 nflverse depth charts

- **Rights posture:** as §5.1; RD1 explicitly did not resolve source-specific upstream rights.
- **Intended-use cells:** as §5.1.
- **Temporal caveats (RD1):** daily ~07:00 UTC; from 2025 appended with timestamps (improves ordering, does not freeze the rolling asset); earlier weekly rows do not prove knowability time.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`.

### 5.6 nflverse historical injuries

- **Rights posture:** as §5.1, over NFL club injury-report data. The current-season lane is separately **blocked**: RD1 (fresh-confirmed) records the nflverse injury source ended after 2024 — no 2025 data, no ETA.
- **Intended-use cells:** Machine acquisition of a current recurring feed = `not_applicable` (no current provider). Historical 2009–2024 acquisition/retention/internal/transformation/findings = `unresolved_fail_closed` pending both the upstream-rights resolution (as §5.1) and confirmation these do not inherit NFL injury-surface restrictions. Hosted-model transfer and raw redistribution = `unresolved_fail_closed`.
- **Temporal caveats (RD1):** `date_modified` helps but does not replace publication/retrieval evidence; no current feed.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`; recurring injury-conditioned research remains **blocked for lack of a current source** (RD1 follow-up #4, parked).

### 5.7 nflverse / PFR snap counts

- **Rights posture:** carries an **additional** restriction beyond §5.1: PFR-derived data implicates the [Sports Reference data-use policy](https://www.sports-reference.com/data_use.html), which a repository-level CC label does not cure. Fresh re-verification returned **HTTP 403** (2026-07-22) → fail closed; RD1's finding stands.
- **Intended-use cells:** Machine acquisition / retention / model use / transformation / publication / redistribution = `unresolved_fail_closed`. Internal research use = `unresolved_fail_closed`.
- **Operator / qualified review required:** Yes — an **express** review resolving the Sports Reference policy conflict is a precondition.
- **Disposition:** `excluded` (binding rule: PFR snap counts remain excluded unless an express review resolves the Sports Reference conflict).

### 5.8 nflverse weekly NGS aggregates

- **Rights posture:** as §5.1 (CC BY 4.0 compilation + unresolved NFL/NGS upstream).
- **Intended-use cells:** as §5.1.
- **Temporal caveats (RD1):** current season rebuilt nightly; no public revision history; **missing-not-at-random** (players below provider thresholds are absent, not zero); no raw x-y coordinates.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`. Any admitted use must preserve the absent-vs-zero distinction (RD1 admission rule 7: no semantic substitution).

### 5.9 nflverse FTN charting

- **Provider / upstream owner:** FTN Data (own charting product), distributed via nflverse.
- **Primary evidence (retrieval 2026-07-22):** **CC BY-SA 4.0**; required attribution "FTN Data via nflverse"; share-alike. Fresh-verified. This is an affirmative, explicit grant — materially cleaner than the §5.1 families, with no separate reserved NFL-ownership layer over FTN's own charting.

| Intended use | Classification |
| --- | --- |
| Machine acquisition | operator_policy_candidate_permitted_with_obligations |
| Exact-byte retention | operator_policy_candidate_permitted_with_obligations |
| Internal research use | operator_policy_candidate_permitted_with_obligations |
| Model / analytical use | Internal analytical/model use: permitted_with_obligations. Transfer to a hosted third-party model: permitted_with_obligations **provided any published adaptation carries share-alike** (see review flag). |
| Transformation & derived-artifact retention | operator_policy_candidate_permitted_with_obligations — an **adapted database/derivative may be subject to CC BY-SA share-alike**. |
| Public findings / derived-output publication | operator_policy_candidate_permitted_with_obligations — published adaptations of the data must be licensed **CC BY-SA 4.0** with attribution; the precise scope of share-alike attachment to a governed TIBER derivative is a qualified-review flag. |
| Raw-data redistribution | operator_policy_candidate_permitted_with_obligations — permitted **only** under CC BY-SA 4.0 with attribution. |

- **Obligations:** attribution "FTN Data via nflverse"; **share-alike** on adaptations; identify adapted-database obligations; do not treat as ordinary permissive input.
- **Operator / qualified review required:** an **operator policy decision** on whether TIBER will accept CC BY-SA share-alike on any *published/redistributed* adaptation; a **qualified-review flag** on the exact scope of share-alike attachment to governed derivatives. **Internal-use candidacy does not depend on this**, because internal use is not distribution and does not trigger share-alike.
- **Temporal caveats (RD1):** 2022 onward; charted within ~48h but provider-dependent; rolling asset can be replaced; **not** a receiver-width or all-route-denominator solution. Archive completeness must be verified later.
- **Disposition:** **`candidate_for_later_feasibility_review`** — narrow candidate for **internal analytical use** under attribution + share-alike, with publication/redistribution gated on the share-alike decisions above.

### 5.10 nflverse participation data

- **Rights posture:** CC BY-SA 4.0 labeled, but **era-mixed underlying source** — attribution differs by era. Per the binding rule, the family is **split**:
  - **2023 onward (FTN-sourced):** posture as §5.9 (CC BY-SA, FTN attribution). Candidate path available.
  - **2016–2022 (NFL NGS-sourced):** the underlying-ownership question of §5.1 applies over the CC BY-SA label; **`unresolved_fail_closed`** for redistribution and hosted-model transfer; `held_for_qualified_review`.
- **Intended-use cells:** FTN-era slice as §5.9; NGS-era slice as §5.1/§5.8.
- **Temporal caveats (RD1):** from 2023, FTN supplies data **only after the postseason** — not an in-season weekly feed; does not expose receiver-width coordinates.
- **Operator / qualified review required:** Yes (share-alike decision for the FTN slice; upstream-ownership review for the NGS slice).
- **Disposition:** **split** — FTN-era (2023+) slice: `candidate_for_later_feasibility_review` (internal use, obligations as §5.9; **postseason-only, unsuitable as a live weekly backbone**). NGS-era (≤2022) slice: `held_for_qualified_review`.

### 5.11 NFL Game Books

- **Provider / upstream owner:** NFL (owned public PDFs).
- **Primary evidence (retrieval 2026-07-22):** [NFL Terms](https://www.nfl.com/legal/terms/) — systematic retrieval to build a collection/database prohibited absent express written consent; individual informational use only. Fresh-verified.
- **Intended-use cells:** Machine acquisition / exact-byte retention / model use / transformation-retention / publication / redistribution = `operator_policy_candidate_not_permitted` under current terms. Internal research use as an **automated retained corpus** = `not_permitted`; manual human reference = permitted outside this policy's data-acquisition scope.
- **Operator / qualified review required:** only new authoritative permission or qualified review could narrow this.
- **Temporal caveats (RD1):** no documented revision ID, replacement time, or superseded-PDF archive.
- **Disposition:** `manual_reference_only`.

### 5.12 NFL public injury-report surfaces

- **Rights posture:** NFL-owned public surfaces; same NFL Terms as §5.11.
- **Intended-use cells:** automated acquisition/retention/model/redistribution = `operator_policy_candidate_not_permitted`; not an automated snapshot source.
- **Temporal caveats (RD1):** no row-level publication timestamp, revision ID, or complete filing history; filing deadlines are not timestamps.
- **Disposition:** `manual_reference_only`.

### 5.13 NFL public statistics and correction surfaces

- **Rights posture:** NFL-owned; same NFL Terms as §5.11.
- **Intended-use cells:** automated acquisition/retention/model/redistribution = `operator_policy_candidate_not_permitted`.
- **Temporal caveats (RD1):** correction dates do not establish a complete prior snapshot; time zone, revision identity, and completeness guarantees are absent.
- **Disposition:** `manual_reference_only` (manual corroboration only).

### 5.14 NFL Pro / public Next Gen Stats surfaces

- **Rights posture:** consumer access is not a machine-use, export, or retention licence; NFL Terms as §5.11.
- **Intended-use cells:** automated acquisition/retention/model/transformation/publication/redistribution = `operator_policy_candidate_not_permitted`.
- **Temporal caveats (RD1):** no documented historical revision stream, metric-version contract, or raw coordinate export.
- **Disposition:** `manual_reference_only` (reference-only).

### 5.15 Genius Sports (potential licensed path)

- **Provider / upstream owner:** Genius Sports as the NFL's exclusive distributor of official real-time play-by-play and proprietary NGS through 2027-28 (fresh-verified).
- **Intended-use cells:** all axes = `unresolved_fail_closed` — no licence terms, cost, latency, correction, archive, retention, derived-work, publication, or open-source rights are known. Nothing may be inferred from the public announcement.
- **Operator / qualified review required:** Yes — commercial licensing negotiation and qualified rights/licensing review.
- **Disposition:** `held_for_qualified_review` (potential licensed path; not evaluated for acquisition here — contacting/pricing/procuring is a parked follow-up, §9).

### 5.16 Big Data Bowl releases

- **Provider / upstream owner:** NFL, via competition-specific releases.
- **Intended-use cells:** all axes = `unresolved_fail_closed` pending a **per-release** terms audit; each competition's exact terms govern retention and production reuse and were not audited here.
- **Operator / qualified review required:** Yes, per dataset.
- **Temporal caveats (RD1):** dataset/task-specific; not a recurring weekly feed.
- **Disposition:** `held_for_qualified_review` (dataset-specific research candidate only; separate per-release audit required before any retention).

### 5.17 `nflreadr` / `nflreadpy` (access tooling)

- **Rights posture:** MIT-licensed access clients. The software licence covers the **code**, not the underlying data (fresh-verified via `nflreadr` Terms of Use).
- **Intended-use cells:** as a **source of data rights** — `not_applicable` on every axis. As tooling, the MIT licence permits use of the client software; the client's commit/version, loader arguments, and cache mode must be recorded in provenance (RD1 §8).
- **Disposition:** `excluded` **as a data source** (it conveys no data rights); permitted purely as access tooling. This is a labeling disposition, not an admission of any data.

## 6. Summary matrix

| # | Source family | Disposition | Gating question |
| --- | --- | --- | --- |
| 1 | nflverse play-by-play | held_for_qualified_review | CC BY 4.0 vs reserved upstream NFL-owner terms |
| 2 | nflverse weekly stats | held_for_qualified_review | as #1 |
| 3 | nflverse games/schedules | held_for_qualified_review | as #1; split stable-id vs mutable fields |
| 4 | nflverse weekly rosters | held_for_qualified_review | as #1 |
| 5 | nflverse depth charts | held_for_qualified_review | as #1 |
| 6 | nflverse historical injuries | held_for_qualified_review | as #1 + no current feed (recurring lane blocked) |
| 7 | nflverse / PFR snap counts | **excluded** | Sports Reference data-use conflict (re-verify 403 → fail closed) |
| 8 | nflverse weekly NGS aggregates | held_for_qualified_review | as #1; preserve absent-vs-zero |
| 9 | nflverse FTN charting | **candidate_for_later_feasibility_review** | operator acceptance of CC BY-SA share-alike (internal use unaffected) |
| 10 | nflverse participation | split: FTN-era **candidate**; NGS-era held | share-alike (FTN slice) / upstream ownership (NGS slice) |
| 11 | NFL Game Books | manual_reference_only | NFL Terms bar systematic retrieval |
| 12 | NFL injury surfaces | manual_reference_only | as #11 |
| 13 | NFL stats/correction surfaces | manual_reference_only | as #11 |
| 14 | NFL Pro / public NGS surfaces | manual_reference_only | as #11 |
| 15 | Genius Sports | held_for_qualified_review | unknown licence terms/cost/rights |
| 16 | Big Data Bowl | held_for_qualified_review | per-release terms audit |
| 17 | nflreadr / nflreadpy | excluded (as data source) | none — tooling only, no data rights |

## 7. Narrow candidate source set (RD1 follow-up #2)

The narrowest source set responsibly eligible for a **later archive-feasibility decision**, under this proposal, is:

1. **nflverse FTN charting** (2022+), for internal analytical use under CC BY-SA attribution + share-alike; publication/redistribution gated on the operator's share-alike decision.
2. **nflverse participation — FTN-era slice (2023+)** only, same basis, with the temporal caveat that it is **postseason-only and unsuitable as a live weekly backbone**.

This set is deliberately narrow. The nflverse statistical **backbone** (play-by-play, weekly stats, schedules, rosters, depth charts, NGS aggregates) is **not** in the candidate set: each is `held_for_qualified_review` on the single CC BY 4.0-vs-upstream question, and each would become a candidate for internal-use only if that question is resolved. PFR snap counts and all NFL-owned public surfaces are outside the set by rule.

**Naming a family a candidate is not permission to acquire it.** It marks it as eligible to enter the *next* (archive-feasibility) gate, which itself precedes any acquisition, retention, or adoption decision.

## 8. Consequences for the initial Research Observatory question envelope (completion criterion #7)

- With the statistical backbone held for qualified review, the initial envelope **cannot yet admit a recurring cutoff-bound source corpus**. The realistic near-term admissible material is FTN-charted play-level labels (internal use, share-alike), which supports selected play-level questions but **not** the volume/efficiency backbone, and **not** a live weekly cadence (participation is postseason-only).
- **Injury-conditioned** questions remain **blocked** for lack of a current source (RD1 follow-up #4).
- **Receiver-width / all-route** questions remain **not testable** from this universe; formation labels must not be substituted for alignment coordinates (RD1 admission rule 7).
- **Raw player-tracking** questions require the Genius Sports licensed path or a separately cleared competition dataset — both `held_for_qualified_review`.
- Retrospective analysis over **already-governed TIBER artifacts** is a separate matter from this source-corpus policy and is neither approved nor broadened here (see §10).

## 9. Parked follow-ups (not resolved or activated here)

Asset-level archive feasibility and point-in-time availability; inspection of archive assets/dates/digests; historical week/cohort selection; injury-provider replacement/procurement; receiver-alignment/tracking/licensed-feed acquisition; contacting/pricing/procuring/evaluating any licensed feed (incl. Genius Sports, Big Data Bowl); capture-timing/correction/cutoff policy; snapshot architecture/storage/manifests/builders; question generation/routing; research execution, modeling, forecasting, scheduling, promotion; any public or recurring source corpus. Discoveries in these areas must be parked, not absorbed into RD1-F.

## 10. Interpretation rules applied (proposal §7)

- Unknown or conflicting rights → fail closed (nflverse upstream question; Genius; Big Data Bowl; Sports Reference 403).
- A repository-level licence does not override upstream-owner terms (nflverse CC BY 4.0 does not settle NFL-owner reservation).
- An access-client software licence does not license the underlying data (nflreadr/nflreadpy MIT).
- Internal analysis, model use, retained derivatives, public findings, and raw redistribution are decided **separately** on every family.
- Public access does not imply machine-access, retention, model-use, or redistribution rights (all NFL-owned surfaces).
- PFR snap counts remain excluded pending express review.
- NFL-owned public surfaces remain manual-reference-only pending new authoritative permission or qualified review.
- CC BY-SA material (FTN charting; FTN-era participation) has its attribution, adaptation, database, and share-alike obligations identified, not treated as permissive.
- A TIBER derivative cannot receive broader permissions than the underlying evidence supports; transformation does not launder obligations.
- A positive outcome is reached with a deliberately narrow set while ambiguous families are excluded, manual-only, or held.
- Rights that differ by era/provider/field are split (schedules; participation) rather than hidden under a broad label.
- No disposition here establishes historical point-in-time availability — that is the later archive-feasibility step.

## 11. Completion criteria check (proposal §8)

1. Every family has a populated row — **yes** (§5, 17 families).
2. Every non-fail-closed claim cites primary evidence — **yes** (§2.1 + §5 links, retrieval-dated).
3. Raw data / derived artifacts / public findings / model use not conflated — **yes** (per-axis cells).
4. Attribution / share-alike / retention / redistribution obligations explicit — **yes** (§5.9–5.10, §5.1 family).
5. Unresolved conflicts excluded or routed to qualified review, never silently admitted — **yes** (§6).
6. Narrow candidate set named, incl. empty-set option — **yes**, non-empty but narrow (§7).
7. Consequences for the question envelope stated — **yes** (§8).
8. Traceability to RD1 follow-ups 1, 2, and review-gate of 7 — **yes** (§12).
9. No existing TIBER artifact retroactively approved/broadened — **affirmed** (§10, §8 final bullet); this policy governs external source admissibility only and changes nothing about already-governed artifacts.
10. Candidate document + terminal token receive fresh-context independent review — **requested at the #24 checkpoint; pending.**
11. Executing agent stops for Joseph's separate terminal-acceptance, merge, policy-adoption, and next-frontier decisions — **yes** (this draft PR is not self-merged).

## 12. Requirements traceability

| RD1 follow-up | Addressed by |
| --- | --- |
| #1 — signed source-use policy by family and intended use | §5 per-family rows; §10 interpretation rules |
| #2 — narrow admissible source set | §7 candidate set (FTN charting; FTN-era participation) |
| #7 (review-gate portion) — where qualified review is required | §5 review flags; §6 gating-question column; §13 terminal rationale |

Follow-ups #3 (archive feasibility), #4 (injury source), #5 (alignment/tracking), and #6 (correction/cutoff policy) remain **parked** (§9).

## 13. Terminal result

```text
source_use_admissibility_policy_ready_for_operator_decision
```

**Rationale.** An independently-reviewable, operator-legible policy proposal now exists. A **narrow, complete** candidate policy is honestly available for an operator decision: admit — for a later archive-feasibility gate — FTN charting and the FTN-era participation slice, for internal analytical use under attribution and share-alike, with publication/redistribution gated on an operator share-alike decision; hold the nflverse statistical backbone for qualified review on the single CC BY 4.0-vs-upstream question; exclude PFR snap counts; keep all NFL-owned public surfaces manual-reference-only; hold Genius Sports and Big Data Bowl for qualified/per-release review. The held rows are dispensable to this narrow policy, so a complete decision does not depend on qualified input — satisfying the positive terminal rather than `..._requires_qualified_review`.

This token means **only** that a reviewed policy proposal exists. It does **not** approve the policy, admit any source, activate archive feasibility, or authorize acquisition, retention, model use, publication, or redistribution. The candidate set is a proposal for the operator's separate adoption decision.

## 14. Hard stop boundary

This document does not activate RD2, #24's three-run pilot, or #35 F1–F5. It authorizes no source acquisition, data download/sampling/retention/hashing/transformation/inspection, registry change, deployment, publication, scheduling, model run, Forecast influence, or production behavior. It is a docs-only candidate on one non-main branch in one draft PR. Execution stops here for fresh-context independent review and Joseph's separate decisions.
