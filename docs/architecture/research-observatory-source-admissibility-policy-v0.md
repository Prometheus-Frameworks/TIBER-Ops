# Research Observatory source-use and admissibility policy v0

Status: **RD1-F candidate deliverable — DRAFT for independent review; NOT adopted policy**
Owning issue: [TIBER-Ops #24](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24)
Frontier: `RD1-F — source-use and admissibility policy`
Work item: `research_observatory_rd1_f_source_admissibility_v0`
Authority: [scope approval](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5040660662) and signed [activation](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5040664503) of the exact proposal [#24 comment 5034511886](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24#issuecomment-5034511886), SHA-256 `31b3245cd770aff0f154e18a2df51877703cbfc6d881b8aaf0ec5f5fc3ee2e56`
Predecessor: accepted RD1 audit `docs/architecture/research-observatory-readiness-inventory-v0.md`, blob `149e60f3f2634021f743d83fe7ee02b396c58577`, document SHA-256 `a5104706260b83888d4a94e0623ded78d165d611dbe1de8893a939503e1dbe77`, merge commit `c443f281f184301edd8dc70eeb218cbc5b777edf`
Drafted: 2026-07-22 UTC (rev. 2 after independent review)
Terminal result: **`source_use_admissibility_policy_ready_for_operator_decision`** (provisional; pending fresh-context independent review of this head)

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
| Participation (`load_participation`) | [link](https://nflreadr.nflverse.com/reference/load_participation.html) | CC BY-SA 4.0; attribution "FTN Data via nflverse" (2023+) vs "NFL NextGenStats via nflverse" (≤2022); "prior to 2023 is from NFL NGS … from 2023 onwards is courtesy of FTN"; "from 2023 onwards is provided after all post-season games are completed." **No material change.** |
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

**Two result columns where a repository licence sits over an unresolved upstream-owner layer.** For the nflverse statistical families, a **CC BY 4.0 compilation-layer** column records what nflverse's own repository grant would support — this is **contingent evidence, not present permission** — and a **Net authority** column records the operative result once the unresolved upstream NFL-owner reservation is accounted for. Where there is no separately reserved upstream layer (e.g. FTN's own CC BY-SA product), a single **Net authority** column is used. The operative classification is always the Net-authority column.

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
- **Primary evidence (retrieval 2026-07-22):** [nflverse-data CC BY 4.0 `LICENSE.md`](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md); [`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use) reserving underlying NFL-data ownership; RD1 §5.1.
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

- **Obligations (if ever cleared):** CC BY 4.0 attribution to nflverse; indicate modifications; retain licence notice; retain full RD1 §8 provenance.
- **Operator / qualified review required:** **Yes** — the CC BY 4.0-vs-upstream-owner relationship (RD1 follow-up #1/#7).
- **Temporal caveats (RD1):** rolling release filenames overwritten; dated archives periodic and overwrite-capable; current URLs are not historical revisions. Point-in-time availability is a later step.
- **Disposition:** `held_for_qualified_review`. *Contingent path:* if qualified review confirms the CC BY 4.0 compilation grant governs an internal-use-only, attribution-bound profile, the net cells for acquisition/retention/internal-use/transformation would become `operator_policy_candidate_permitted_with_obligations` and the family could enter a later archive-feasibility gate.

### 5.2 nflverse weekly player/team statistics

- **Provider / upstream owner / primary evidence:** as §5.1 (derivative of play-by-play).
- **Additional temporal caveat (RD1):** historical values can also change with calculation-code changes; RDS metadata may retain nflfastR version/timestamp, CSV loses it.

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

- **Operator / qualified review required:** Yes (as §5.1).
- **Disposition:** `held_for_qualified_review` (contingent path as §5.1).

### 5.3 nflverse games and schedules

- **Provider / upstream owner / primary evidence:** as §5.1. Per RD1 the family splits into **stable game identity** (ids, teams, kickoff) vs **mutable schedule/result fields** (times, scores, market fields refreshing every ~5 minutes).

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

- **Temporal caveats (RD1):** mutable fields have no revision identity; each archive date needs an asset/digest check.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`. *Contingent path:* the stable game-identity fields are the strongest candidate for a later feasibility review; mutable schedule/result fields remain fail-closed until revision identity is established.

### 5.4 nflverse weekly rosters

- **Provider / upstream owner / primary evidence:** as §5.1; RD1 notes upstream is an "NFL API"; retain `NFL via nflverse` provenance.

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

- **Temporal caveats (RD1):** current season rebuilt daily ~07:00 UTC; football `week` is not availability time; no documented correction/finalization contract.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`.

### 5.5 nflverse depth charts

- **Provider / upstream owner / primary evidence:** as §5.1; RD1 explicitly did not resolve source-specific upstream rights.

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

- **Temporal caveats (RD1):** daily ~07:00 UTC; from 2025 appended with timestamps (improves ordering, does not freeze the rolling asset); earlier weekly rows do not prove knowability time.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`.

### 5.6 nflverse historical injuries

- **Provider / upstream owner / primary evidence:** as §5.1, over NFL club injury-report data. RD1 (fresh-confirmed) records the nflverse injury source **ended after 2024** — no 2025 data, no ETA. The matrix below is for **historical 2009–2024** records; a current recurring feed is `not_applicable` (no provider) and the recurring lane is **blocked**.

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

- **Temporal caveats (RD1):** `date_modified` helps but does not replace publication/retrieval evidence; no current feed.
- **Operator / qualified review required:** Yes. Also inherits the NFL injury-surface question (net remains fail-closed regardless).
- **Disposition:** `held_for_qualified_review`; recurring injury-conditioned research remains **blocked for lack of a current source** (RD1 follow-up #4, parked). Current recurring feed acquisition: `not_applicable`.

### 5.7 nflverse / PFR snap counts

- **Provider / upstream owner:** Pro Football Reference (Sports Reference) via nflverse.
- **Primary evidence (retrieval 2026-07-22):** [Sports Reference data-use policy](https://www.sports-reference.com/data_use.html) — **HTTP 403, could not re-verify** → fail closed; RD1's finding stands. A repository-level CC label does not cure the Sports Reference model-use conflict.

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

- **Operator / qualified review required:** Yes — an **express** review resolving the Sports Reference policy conflict is a precondition.
- **Disposition:** `excluded` (binding rule: PFR snap counts remain excluded unless an express review resolves the Sports Reference conflict).

### 5.8 nflverse weekly NGS aggregates

- **Provider / upstream owner / primary evidence:** as §5.1 (CC BY 4.0 compilation over NFL/NGS upstream).

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

- **Temporal caveats (RD1):** current season rebuilt nightly; no public revision history; **missing-not-at-random** (players below provider thresholds are absent, not zero); no raw x-y coordinates.
- **Operator / qualified review required:** Yes.
- **Disposition:** `held_for_qualified_review`. Any admitted use must preserve the absent-vs-zero distinction (RD1 admission rule 7: no semantic substitution).

### 5.9 nflverse FTN charting

- **Provider / upstream owner:** FTN Data (own charting product), distributed via nflverse.
- **Primary evidence (retrieval 2026-07-22):** [`load_ftn_charting`](https://nflreadr.nflverse.com/reference/load_ftn_charting.html) — **CC BY-SA 4.0**; required attribution "FTN Data via nflverse"; share-alike. Fresh-verified. This is an affirmative, explicit grant; **no additional upstream reservation was identified in the cited source-specific documentation** for FTN's own charting.

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

- **Hosted third-party model transfer** is `unresolved_fail_closed` pending a provider-specific data-handling review (whether transferring FTN records to a hosted third-party model is consistent with the licence and provider expectations).
- **Obligations:** attribution "FTN Data via nflverse"; **CC BY-SA ShareAlike** and adapted-database obligations. **ShareAlike is a legal trigger that attaches only when an adaptation is publicly shared/distributed** — it is distinct from TIBER's always-on internal provenance policy, which applies regardless and does not by itself satisfy or invoke ShareAlike. Internal analytical use does not distribute and does not trigger ShareAlike.
- **Operator / qualified review required:** an **operator policy decision** on whether TIBER will accept CC BY-SA ShareAlike on any *published/redistributed* adaptation; a **qualified-review flag** on the exact scope of ShareAlike attachment to a governed TIBER derivative. Internal-use candidacy does not depend on these.
- **Temporal caveats (RD1):** 2022 onward; charted within ~48h but provider-dependent; rolling asset can be replaced; **not** a receiver-width or all-route-denominator solution. Archive completeness must be verified later.
- **Disposition:** **`candidate_for_later_feasibility_review`** — narrow candidate for **local/internal analytical use** under attribution + ShareAlike, with hosted-model transfer, publication, and redistribution gated as above.

### 5.10a nflverse participation — FTN-era slice (2023 onward)

- **Provider / upstream owner:** FTN Data via nflverse (2023+).
- **Primary evidence (retrieval 2026-07-22):** [`load_participation`](https://nflreadr.nflverse.com/reference/load_participation.html) — CC BY-SA 4.0; attribution "FTN Data via nflverse" for 2023+; "Participation data from 2023 onwards is courtesy of FTN"; "provided after all post-season games are completed."
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

- **Obligations:** attribution "FTN Data via nflverse"; CC BY-SA ShareAlike (public-distribution trigger, as §5.9); provenance policy is separate from ShareAlike.
- **Separability condition:** this slice may advance **only if it can be acquired without also retaining unresolved NGS-era (≤2022) records** (§5.10b). If the loader/asset cannot yield the 2023+ FTN slice in isolation, this slice fails closed until it can.
- **Temporal caveats (RD1 + primary):** postseason-only (not an in-season weekly feed); does not expose receiver-width coordinates.
- **Operator / qualified review required:** ShareAlike decision as §5.9.
- **Disposition:** **`candidate_for_later_feasibility_review`** — local/internal analytical use, subject to the separability condition and the ShareAlike gate on publication/redistribution.

### 5.10b nflverse participation — NGS-era slice (2022 and earlier)

- **Provider / upstream owner:** NFL Next Gen Stats via nflverse (≤2022).
- **Primary evidence (retrieval 2026-07-22):** [`load_participation`](https://nflreadr.nflverse.com/reference/load_participation.html) — attribution "NFL NextGenStats via nflverse"; "Participation data prior to 2023 is from NFL NGS." The CC BY-SA label sits over an **NFL/NGS upstream layer** that is unresolved as in §5.1/§5.8; the label is contingent evidence, not present permission.

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

- **Operator / qualified review required:** Yes — NGS upstream-ownership review (as §5.1/§5.8).
- **Disposition:** `held_for_qualified_review`.

### 5.11 NFL Game Books

- **Provider / upstream owner:** NFL (owned public PDFs).
- **Primary evidence (retrieval 2026-07-22):** [NFL Terms](https://www.nfl.com/legal/terms/) — systematic retrieval to build a collection/database prohibited absent express written consent; individual informational use only. Fresh-verified.

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

- Manual human reference of an individual PDF is permitted **outside** this policy's data-acquisition axes and does not create a retained corpus.
- **Temporal caveats (RD1):** no documented revision ID, replacement time, or superseded-PDF archive.
- **Disposition:** `manual_reference_only`.

### 5.12 NFL public injury-report surfaces

- **Provider / upstream owner / primary evidence:** NFL-owned public surfaces; [NFL Terms](https://www.nfl.com/legal/terms/) as §5.11.

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

- **Temporal caveats (RD1):** no row-level publication timestamp, revision ID, or complete filing history; filing deadlines are not timestamps.
- **Disposition:** `manual_reference_only`.

### 5.13 NFL public statistics and correction surfaces

- **Provider / upstream owner / primary evidence:** NFL-owned; [NFL Terms](https://www.nfl.com/legal/terms/) as §5.11.

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

- **Temporal caveats (RD1):** correction dates do not establish a complete prior snapshot; time zone, revision identity, and completeness guarantees are absent.
- **Disposition:** `manual_reference_only` (manual corroboration only).

### 5.14 NFL Pro / public Next Gen Stats surfaces

- **Provider / upstream owner / primary evidence:** NFL-owned; consumer access is not a machine-use, export, or retention licence; [NFL Terms](https://www.nfl.com/legal/terms/) as §5.11.

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

- **Temporal caveats (RD1):** no documented historical revision stream, metric-version contract, or raw coordinate export.
- **Disposition:** `manual_reference_only` (reference-only).

### 5.15 Genius Sports (potential licensed path)

- **Provider / upstream owner:** Genius Sports as the NFL's exclusive distributor of official real-time play-by-play and proprietary NGS through 2027-28 ([announcement](https://www.nfl.com/news/nfl-extends-strategic-partnership-with-genius-sports), fresh-verified). No licence terms are known; nothing may be inferred from the public announcement.

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

- **Operator / qualified review required:** Yes — commercial licensing negotiation and qualified rights/licensing review.
- **Disposition:** `held_for_qualified_review` (potential licensed path; contacting/pricing/procuring is a parked follow-up, §9).

### 5.16 Big Data Bowl releases

- **Provider / upstream owner:** NFL, via competition-specific releases. Each competition's exact terms govern retention and production reuse and were not audited here.

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

- **Operator / qualified review required:** Yes, per dataset.
- **Temporal caveats (RD1):** dataset/task-specific; not a recurring weekly feed.
- **Disposition:** `held_for_qualified_review` (dataset-specific research candidate only; separate per-release audit required before any retention).

### 5.17 `nflreadr` / `nflreadpy` (access tooling)

- **Rights posture:** MIT-licensed access clients. The software licence covers the **code**, not the underlying data ([`nflreadr` Terms of Use](https://github.com/nflverse/nflreadr#terms-of-use), fresh-verified).

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

- As **tooling**, the MIT licence permits use of the client software; the client's commit/version, loader arguments, and cache mode must be recorded in provenance (RD1 §8).
- **Disposition:** `excluded` **as a data source** (it conveys no data rights). This is a labeling disposition, not an admission of any data.

## 6. Summary matrix

| # | Source family | Disposition | Gating question |
| --- | --- | --- | --- |
| 1 | nflverse play-by-play | held_for_qualified_review | CC BY 4.0 vs reserved upstream NFL-owner terms (net fail-closed) |
| 2 | nflverse weekly stats | held_for_qualified_review | as #1 |
| 3 | nflverse games/schedules | held_for_qualified_review | as #1; split stable-id vs mutable fields |
| 4 | nflverse weekly rosters | held_for_qualified_review | as #1 |
| 5 | nflverse depth charts | held_for_qualified_review | as #1 |
| 6 | nflverse historical injuries | held_for_qualified_review | as #1 + no current feed (recurring lane blocked) |
| 7 | nflverse / PFR snap counts | **excluded** | Sports Reference data-use conflict (re-verify 403 → fail closed) |
| 8 | nflverse weekly NGS aggregates | held_for_qualified_review | as #1; preserve absent-vs-zero |
| 9 | nflverse FTN charting | **candidate_for_later_feasibility_review** | operator acceptance of CC BY-SA ShareAlike on publication; hosted-model transfer fail-closed; internal use unaffected |
| 10a | nflverse participation — FTN-era 2023+ | **candidate_for_later_feasibility_review** | as #9 + separable from NGS-era records; postseason-only |
| 10b | nflverse participation — NGS-era ≤2022 | held_for_qualified_review | NGS upstream ownership (net fail-closed) |
| 11 | NFL Game Books | manual_reference_only | NFL Terms bar systematic retrieval |
| 12 | NFL injury surfaces | manual_reference_only | as #11 |
| 13 | NFL stats/correction surfaces | manual_reference_only | as #11 |
| 14 | NFL Pro / public NGS surfaces | manual_reference_only | as #11 |
| 15 | Genius Sports | held_for_qualified_review | unknown licence terms/cost/rights |
| 16 | Big Data Bowl | held_for_qualified_review | per-release terms audit |
| 17 | nflreadr / nflreadpy | excluded (as data source) | none — tooling only, no data rights |

## 7. Narrow candidate source set (RD1 follow-up #2)

The narrowest source set responsibly eligible for a **later archive-feasibility decision**, under this proposal, is:

1. **nflverse FTN charting** (2022+, §5.9), for **local/internal** analytical use under CC BY-SA attribution; hosted-model transfer fail-closed; publication/redistribution gated on the operator's ShareAlike decision.
2. **nflverse participation — FTN-era slice (2023+, §5.10a)** only, same basis, **subject to the separability condition** (acquirable without retaining unresolved NGS-era records) and the caveat that it is **postseason-only and unsuitable as a live weekly backbone**.

This set is deliberately narrow. The nflverse statistical **backbone** (play-by-play, weekly stats, schedules, rosters, depth charts, NGS aggregates) and the **NGS-era participation slice** are **`held_for_qualified_review`** with **net-authority fail-closed** on the CC BY 4.0/CC BY-SA-vs-upstream question; each would become a candidate for internal use only if that question is resolved. PFR snap counts are **excluded** and all NFL-owned public surfaces are **manual-reference-only** by rule.

**Naming a family a candidate is not permission to acquire it.** It marks it as eligible to enter the *next* (archive-feasibility) gate, which itself precedes any acquisition, retention, or adoption decision.

## 8. Consequences for the initial Research Observatory question envelope (completion criterion #7)

- With the statistical backbone net-authority fail-closed and held for qualified review, the initial envelope **cannot yet admit a recurring cutoff-bound source corpus**. The realistic near-term admissible material is FTN-charted play-level labels (local/internal use, ShareAlike), which supports selected play-level questions but **not** the volume/efficiency backbone, and **not** a live weekly cadence (participation is postseason-only).
- **Injury-conditioned** questions remain **blocked** for lack of a current source (RD1 follow-up #4).
- **Receiver-width / all-route** questions remain **not testable** from this universe; formation labels must not be substituted for alignment coordinates (RD1 admission rule 7).
- **Raw player-tracking** questions require the Genius Sports licensed path or a separately cleared competition dataset — both `held_for_qualified_review`.
- Retrospective analysis over **already-governed TIBER artifacts** is a separate matter from this source-corpus policy and is neither approved nor broadened here (see §10).

## 9. Parked follow-ups (not resolved or activated here)

Asset-level archive feasibility and point-in-time availability; inspection of archive assets/dates/digests; historical week/cohort selection; injury-provider replacement/procurement; receiver-alignment/tracking/licensed-feed acquisition; contacting/pricing/procuring/evaluating any licensed feed (incl. Genius Sports, Big Data Bowl); capture-timing/correction/cutoff policy; snapshot architecture/storage/manifests/builders; question generation/routing; research execution, modeling, forecasting, scheduling, promotion; any public or recurring source corpus. Discoveries in these areas must be parked, not absorbed into RD1-F.

## 10. Interpretation rules applied (proposal §7)

- Unknown or conflicting rights → fail closed. The nflverse upstream-owner question renders the backbone **net-authority fail-closed** despite contingent CC BY 4.0 compilation-layer evidence; Genius, Big Data Bowl, and the Sports Reference 403 likewise fail closed.
- A repository-level licence does not override upstream-owner terms — CC BY 4.0 / CC BY-SA labels are preserved as **contingent evidence, not present permission** where an upstream layer is unresolved.
- An access-client software licence does not license the underlying data (nflreadr/nflreadpy MIT).
- Internal analysis, model use, retained derivatives, public findings, and raw redistribution are decided **separately** on every family; hosted third-party model transfer is called out separately from local/internal use.
- Public access does not imply machine-access, retention, model-use, or redistribution rights (all NFL-owned surfaces `operator_policy_candidate_not_permitted`).
- PFR snap counts remain excluded pending express review.
- NFL-owned public surfaces remain manual-reference-only pending new authoritative permission or qualified review.
- CC BY-SA material (FTN charting; FTN-era participation) has its attribution, adaptation, database, and ShareAlike obligations identified, not treated as permissive; ShareAlike's public-distribution trigger is distinguished from TIBER's always-on provenance policy.
- A TIBER derivative cannot receive broader permissions than the underlying evidence supports; transformation does not launder obligations.
- A positive outcome is reached with a deliberately narrow set while ambiguous families are excluded, manual-only, or held.
- Rights that differ by era/provider/field are split into subrows (schedules; participation 10a/10b) rather than hidden under a broad label.
- No disposition here establishes historical point-in-time availability — that is the later archive-feasibility step.

## 11. Completion criteria check (proposal §8)

1. Every family has a fully populated row — **yes** (§5; 17 families, participation split 10a/10b; all seven axes with exact enums per cell).
2. Every non-fail-closed claim cites primary evidence — **yes** (§2.1 + per-row primary links, retrieval-dated; FTN-era participation cites `load_participation`).
3. Raw data / derived artifacts / public findings / model use not conflated — **yes** (per-axis cells; hosted-transfer separated).
4. Attribution / ShareAlike / retention / redistribution obligations explicit — **yes** (§5.9, §5.10a; §5.1 family obligations).
5. Unresolved conflicts excluded or routed to qualified review, never silently admitted — **yes**; the backbone is net-authority fail-closed (§5, §6).
6. Narrow candidate set named, incl. empty-set option — **yes**, non-empty but narrow (§7).
7. Consequences for the question envelope stated — **yes** (§8).
8. Traceability to RD1 follow-ups 1, 2, and review-gate of 7 — **yes** (§12).
9. No existing TIBER artifact retroactively approved/broadened — **affirmed** (§10, §8 final bullet); this policy governs external source admissibility only.
10. Candidate document + terminal token receive fresh-context independent review — **rev. 1 reviewed (CHANGES REQUIRED); this rev. 2 head is submitted for fresh-context re-review.**
11. Executing agent stops for Joseph's separate terminal-acceptance, merge, policy-adoption, and next-frontier decisions — **yes** (draft PR; not self-merged).

## 12. Requirements traceability

| RD1 follow-up | Addressed by |
| --- | --- |
| #1 — signed source-use policy by family and intended use | §5 per-family rows; §10 interpretation rules |
| #2 — narrow admissible source set | §7 candidate set (FTN charting; FTN-era participation 10a) |
| #7 (review-gate portion) — where qualified review is required | §5 review flags; §6 gating-question column; §13 terminal rationale |

Follow-ups #3 (archive feasibility), #4 (injury source), #5 (alignment/tracking), and #6 (correction/cutoff policy) remain **parked** (§9).

## 13. Terminal result

```text
source_use_admissibility_policy_ready_for_operator_decision
```

**Rationale.** An independently-reviewable, operator-legible policy proposal now exists. A **narrow, complete** candidate policy is honestly available for an operator decision: admit — for a later archive-feasibility gate — FTN charting and the FTN-era participation slice, for local/internal analytical use under attribution, with hosted-model transfer fail-closed and publication/redistribution gated on an operator ShareAlike decision; hold the nflverse statistical backbone and the NGS-era participation slice for qualified review with net authority fail-closed on the CC BY 4.0/CC BY-SA-vs-upstream question; exclude PFR snap counts; keep all NFL-owned public surfaces manual-reference-only; hold Genius Sports and Big Data Bowl for qualified/per-release review. The held rows are dispensable to this narrow policy, so a complete decision does not depend on qualified input — satisfying the positive terminal rather than `..._requires_qualified_review`. The token is **provisional pending fresh-context independent review of this head**.

This token means **only** that a reviewed policy proposal exists. It does **not** approve the policy, admit any source, activate archive feasibility, or authorize acquisition, retention, model use, publication, or redistribution. The candidate set is a proposal for the operator's separate adoption decision.

## 14. Hard stop boundary

This document does not activate RD2, #24's three-run pilot, or #35 F1–F5. It authorizes no source acquisition, data download/sampling/retention/hashing/transformation/inspection, registry change, deployment, publication, scheduling, model run, Forecast influence, or production behavior. It is a docs-only candidate on one non-main branch in one draft PR. Execution stops here for fresh-context independent review and Joseph's separate decisions.
