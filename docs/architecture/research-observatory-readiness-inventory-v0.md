# Research Observatory readiness inventory v0

Status: **RD1 discovery record — requires follow-up**  
Owning issue: [TIBER-Ops #24](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/24)  
Authority: [signed RD1 activation in TIBER-Ops #22](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5026996803)  
Audit date: 2026-07-20 UTC  
Terminal result: `source_temporal_audit_requires_followup`

## 1. Decision in plain language

TIBER has enough accessible football data to begin defining a narrow Research Observatory source policy, but it does **not** yet have evidence that supports a cutoff-faithful historical replay or an unrestricted recurring source corpus.

The central issue is not whether a dataset contains old games. It is whether TIBER can prove which exact bytes and revisions were available at the declared research cutoff. A final 2024 dataset retrieved in 2026 may support retrospective analysis; it cannot be represented as what was knowable after Week 8 of 2024.

The audit therefore terminates `source_temporal_audit_requires_followup`. This result does not activate RD2, construct a snapshot, select a replay cohort, ingest data, generate questions, run a model, schedule work, promote an artifact, or expand a registry.

## 2. Scope and method

RD1 inspected only:

- current TIBER artifacts, manifests, contracts, and issue evidence;
- official source documentation, repositories, licences, terms, update schedules, and source metadata;
- fields, seasons, grains, access paths, correction behavior, mutability, retention, provenance, and point-in-time reconstruction capability;
- the time semantics needed to evaluate future cutoff-bound evidence.

This is a technical source-rights inventory, not legal advice. An upstream repository licence was recorded as evidence, but it was not treated as resolving conflicting or narrower third-party terms. Unknown rights fail closed.

## 3. Admission rules established by RD1

A source is not eligible for a future cutoff-bound Observatory run merely because it is public, downloadable, or historically complete. Admission requires all of the following:

1. **Permitted use:** the intended acquisition, retention, transformation, publication, redistribution, and model use are each allowed or explicitly bounded.
2. **Exact-byte identity:** TIBER can identify the bytes used with a locally computed cryptographic hash and an immutable TIBER object identity.
3. **Availability evidence:** the record has enough evidence to establish when those bytes became eligible for use.
4. **Revision handling:** corrections create a successor revision; they do not silently rewrite an earlier run.
5. **Cutoff enforcement:** no evidence first observed or effectively published after the cutoff can enter that run.
6. **Provenance:** provider, source family, season, grain, licence, attribution, retrieval, loader, schema, transformation, and derived-artifact identity are retained.
7. **No semantic substitution:** absent fields stay absent. For example, `shotgun = false` is not automatically an official under-center formation label, and aggregate receiving metrics are not receiver tracking coordinates.

## 4. Time semantics

Future architecture must preserve these distinct timestamps and identities. They are not interchangeable.

| Term | Meaning | Fail-closed rule |
| --- | --- | --- |
| `event_time` | When the football event or source-described event occurred: kickoff, play, practice report, roster transaction, or correction. | Never use it as proof that TIBER could already observe the fact. |
| `effective_at` | When the underlying status or correction takes effect, if the source states it. | It describes the football fact, not when the revision became knowable. |
| `published_at` | Provider-stated time when a particular revision was first published. | Null when the provider does not expose a trustworthy value; never infer it from football week or game date. |
| `source_available_at` | Earliest independently proved provider availability time for the exact revision. | May equal `published_at`; null when a mutable provider surface does not preserve revision identity. |
| `retrieved_at` | UTC time for each TIBER acquisition of the exact bytes. | Required for every retained source object. |
| `first_observed_at` | Earliest proved TIBER acquisition time for that exact content hash. | Default availability evidence when no immutable provider history exists. |
| `admissible_at` | Earliest time the exact revision may enter a cutoff-bound TIBER run. | Default to the later of trustworthy `source_available_at` and `first_observed_at`. A later acquisition may use an earlier time only in an explicitly labeled `verified_archive` mode that proves immutable publication and revision identity; otherwise never backdate it. |
| `revision_id` | Provider revision/asset identity when available, plus TIBER's content hash. | A local hash without provider revision metadata is a local fingerprint, not proof of the provider's prior state. |
| `cutoff_at` | Closed-world boundary for a research run. | Admit a source revision only when `admissible_at <= cutoff_at` and its exact bytes were retained. |
| `supersedes_revision_id` | Link from a correction or replacement to the prior retained revision. | Prior snapshots remain unchanged; corrections are additive successors. |

Provider deadlines and update cadences are context, not publication proof. A Thursday-after-corrections policy may define when to capture play-by-play, but it does not prove the state of an asset that TIBER did not actually retain that Thursday. A later historical acquisition is cutoff-eligible only when the provider's archive supplies independently verifiable immutable publication and revision evidence; nflverse's overwriteable date archive has not yet met that bar.

## 5. External source inventory

### 5.1 nflverse and nflreadpy

| Source family | Coverage and grain | Update, correction, and mutability | Rights finding | Point-in-time finding | RD1 classification |
| --- | --- | --- | --- | --- | --- |
| Play-by-play | 1999 onward; game/play rows through [`load_pbp`](https://nflreadr.nflverse.com/reference/load_pbp.html). | Updated after game days; NFL corrections commonly arrive Monday–Wednesday, and nflverse identifies Thursday as the cleanest weekly load. Fixed release filenames are overwritten. | [`nflverse-data`](https://github.com/nflverse/nflverse-data) declares [CC BY 4.0](https://github.com/nflverse/nflverse-data/blob/main/LICENSE.md), while [`nflreadr` terms](https://github.com/nflverse/nflreadr#terms-of-use) state that NFL data belong to their owners. Downstream applicability is unresolved. | The [`nflverse-data-archives` release list](https://github.com/nflverse/nflverse-data-archives/releases) exposes dated archives. The [archive workflow](https://github.com/nflverse/nflverse-data/blob/main/.github/workflows/run_archive.yaml) runs Thursdays in September–January and monthly in February–August; the [archive code](https://github.com/nflverse/nflverse-data/blob/main/R/archive.R) defaults to RDS and uploads with overwrite enabled. Asset/date completeness and exact digests therefore require individual verification. Current release URLs are not historical revisions. | **Conditional; rights decision and TIBER-owned exact-byte retention required.** |
| Weekly player/team stats | 1999 onward; player-week and team-week derivatives of play-by-play. | Shares play-by-play correction exposure; historical values may also change with calculation code. Stable release filenames are overwritten. | Inherits play-by-play rights uncertainty. | Same coarse archive limits; some RDS metadata can record nflfastR version/timestamp, while CSV loses it. | **Conditional.** |
| Games and schedules | Past and future game rows through [`load_schedules`](https://nflreadr.nflverse.com/reference/load_schedules.html), including identifiers, date/time, teams, scores, rest, and market fields. | The [official schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) says the combined file refreshes every five minutes. Future dates/times and completed-game fields can change; the stable asset is not a revision identity. | Repository-level CC BY applies, while every underlying field/source and intended use has not yet been separately cleared. | Dated archive assets may provide coarse observations, but each selected date needs an asset/digest check and field-specific source review. | **Conditional; split stable game identity from mutable schedule/result fields.** |
| Weekly rosters | 2002 onward; player/team/week through [`load_rosters_weekly`](https://nflreadr.nflverse.com/reference/load_rosters_weekly.html). | Current season rebuilt daily around 07:00 UTC; no documented correction/finalization contract. | Upstream identified as an NFL API; retain `NFL via nflverse` provenance and resolve rights. | Football `week` is not availability time. The [dated archive releases](https://github.com/nflverse/nflverse-data-archives/releases) supply only periodic observations, and required assets must be checked per date. | **Conditional.** |
| Depth charts | Team/player/week rows back to 2001 through [`load_depth_charts`](https://nflreadr.nflverse.com/reference/load_depth_charts.html). | The [official schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) says daily around 07:00 UTC; from 2025, updates are appended with a timestamp rather than represented only by week. A timestamp improves ordering but does not freeze the rolling release asset. | Source-specific upstream rights were not resolved by RD1. A repository-level licence is insufficient without that disposition. | Timestamped 2025+ rows may improve as-of filtering after exact-byte capture; earlier weekly rows and rolling assets do not prove when TIBER could know a change. | **Conditional; rights and revision semantics follow-up.** |
| Injuries | 2009–2024; weekly report rows with `date_modified` through [`load_injuries`](https://nflreadr.nflverse.com/reference/load_injuries.html). | The [official nflverse schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) says the source died after 2024: no 2025 data and no ETA. | Historical upstream rights remain subject to the same unresolved source-use policy. | `date_modified` helps but does not replace publication/retrieval evidence; there is no current feed. | **Blocked for current-season Observatory use.** |
| Snap counts | 2012 onward; PFR game/player snap counts. | Scheduled frequently in season, but the pipeline may not revisit already scraped games; no correction service level is documented. | [Sports Reference's data-use policy](https://www.sports-reference.com/data_use.html) creates an additional model-use conflict that a repository-level CC label should not be presumed to cure. | Only periodic observations appear in the [dated archive releases](https://github.com/nflverse/nflverse-data-archives/releases); required assets must be checked per date. | **Excluded pending express rights review.** |
| Weekly NGS aggregates | 2016 onward; thresholded passing, rushing, and receiving player-week aggregates through [`load_nextgen_stats`](https://nflreadr.nflverse.com/reference/load_nextgen_stats.html). | Current season can be rebuilt nightly; earlier weeks may change. No public revision history. Players below provider thresholds are absent, not zero-valued. | NFL-source rights ambiguity remains unresolved. | Only periodic observations appear in the [dated archive releases](https://github.com/nflverse/nflverse-data-archives/releases). No raw x-y tracking coordinates. | **Conditional and missing-not-at-random.** |
| FTN charting | 2022 onward; a 29-field subset of manually charted play-level data through [`load_ftn_charting`](https://nflreadr.nflverse.com/reference/load_ftn_charting.html), including starting hash, quarterback location, motion, play action, screens, RPO, and throw-quality flags. | FTN says plays are charted within 48 hours; the [nflverse schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) checks every six hours in season, but delivery is provider-dependent and the rolling asset can be replaced. | Explicit CC BY-SA 4.0 with attribution to FTN Data via nflverse. Adapted-database/share-alike handling requires a separate decision. | Potentially useful for in-season play-level questions after capture, but the source does not supply receiver-width coordinates or all-receiver route denominators. Archive asset/date completeness must be verified. | **Conditional; materially useful but not a WR-width solution.** |
| Participation | 2016 onward; play-level personnel, players, formation, route, and coverage fields through [`load_participation`](https://nflreadr.nflverse.com/reference/load_participation.html). | NFL NGS through 2022. From 2023, FTN supplies data only after the postseason; it is not an in-season weekly feed. | Explicit CC BY-SA 4.0; attribution differs by era. Adapted-database/share-alike handling requires a separate decision. | Can support bounded historical questions, not live weekly discovery for 2023 onward. It does not expose receiver width coordinates. | **Conditional; unsuitable as the live weekly backbone.** |

The [nflverse update schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html) is useful capture context, not an archive guarantee. [`nflreadpy`](https://github.com/nflverse/nflreadpy) is an MIT-licensed access client, not a licence for the underlying data; its cache and loader version must be included in provenance.

### 5.2 NFL-owned public surfaces and licensed feeds

| Source family | Useful content | Temporal limitation | Rights limitation | RD1 classification |
| --- | --- | --- | --- | --- |
| NFL Game Books | Public per-game PDFs with official score/stat detail. | RD1 identified a current PDF but did not identify a documented revision ID, replacement time, or superseded-PDF archive. | [NFL terms](https://www.nfl.com/legal/terms/) allow individual informational use but prohibit systematic retrieval to build a collection/database without written consent. | **Human reference/manual verification only.** |
| NFL Injury Report | Practice and game-status information subject to mandatory club filing/update rules. | RD1 did not identify a row-level publication timestamp, revision ID, or complete filing history on the public week pages. Filing deadlines are not timestamps. | Same NFL terms. | **Human reference only; not an automated snapshot source.** |
| NFL stats and correction pages | Official current tables and some old/new stat correction deltas. | Correction dates do not establish a complete prior snapshot; exact time zone, revision identity, and completeness guarantee are absent. | Same NFL terms. | **Manual corroboration only.** |
| Public Next Gen Stats / NFL Pro | Aggregate metrics, visual route tools, advanced dashboards, and day-after-game NGS availability. | No documented historical revision stream, metric-version contract, or raw coordinate export. | Consumer access is not a machine-use, export, or retention licence. | **Reference-only.** |
| Genius Sports official feed | NFL identifies Genius Sports as exclusive distributor of official real-time play-by-play and proprietary NGS through 2027–28. | Contract would need to define latency, corrections, archive, and version behavior. | Cost, availability, derived-work, retention, publication, and open-source rights are unknown. | **Potential licensed path; follow-up required.** |
| Big Data Bowl releases | Selected historical tracking and traditional data for bounded competition tasks. | Dataset/task-specific, not a recurring weekly feed. | Each competition's exact terms must be audited before retention or production reuse. | **Dataset-specific research candidate only.** |

Primary NFL references: [Game Books](https://support.nfl.com/hc/en-us/articles/35869678028180-Game-Books), [official filing calendar](https://operations.nfl.com/calendar-events/nfl-important-dates), [stat corrections](https://fantasy.nfl.com/research/statcorrections), [NFL Pro FAQ](https://support.nfl.com/hc/en-us/articles/35869706651156-NFL-Pro-FAQ-s-and-Answers), [Genius Sports distribution announcement](https://www.nfl.com/news/nfl-extends-strategic-partnership-with-genius-sports), and [Big Data Bowl](https://operations.nfl.com/programs-initiatives/innovation/big-data-bowl).

## 6. Current TIBER evidence inventory

TIBER's truth policy is fail-closed: raw support and supported scope must be verified; absent evidence is not synthesized. See [TIBER-Data `TRUTH_SOURCES.md`](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/main/TRUTH_SOURCES.md).

| TIBER artifact | Current-main finding | Temporal finding | Observatory use |
| --- | --- | --- | --- |
| `team_week_raw_v0` 2024 | [Manifest](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/main/data/manifests/team_week_raw_v0_2024_real_source_candidate.manifest.json) marks a governed, real-data, 544-row, 32-team, Weeks 1–18 artifact. It pins SHA-256 for nflverse play-by-play and schedules. | Both release URLs are explicitly mutable and `immutableSourceRef` is null. Retrieval occurred on 2026-06-27, after the 2024 season. The hashes prove the 2026 retrieval bytes, not weekly 2024 availability. | Valid final-state retrospective evidence; **not** cutoff-faithful historical evidence. The open text of [#162](https://github.com/Prometheus-Frameworks/TIBER-Data/issues/162) is stale relative to current main. |
| `formation_summary_v0` 2024 | [Merged PR #215](https://github.com/Prometheus-Frameworks/TIBER-Data/pull/215) produced a 32-team regular-season candidate from 33,225 qualifying plays, with 111 aborted plays excluded. It is candidate real data and ungoverned. | Pinned source hash, but mutable rolling URL and 2026-07-14 retrieval. | Retrospective shotgun/non-shotgun/unknown formation summary only. No pistol, official under-center, receiver width, route, motion, or shift fields. |
| 2025 source-backed weekly roster/PPR/usage files | Current main contains populated source-backed files: [roster map](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/main/data/processed/evidence/roster_player_team_map_2025.source_backed.json) (14,348 rows), [PPR outcomes](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/main/data/processed/evidence/player_weekly_ppr_outcomes_2025.source_backed.json) (6,394 rows), and [usage](https://github.com/Prometheus-Frameworks/TIBER-Data/blob/main/data/processed/evidence/player_weekly_usage_2025.source_backed.json) (6,326 rows). | They describe a completed season rather than preserved weekly acquisition states. Canonical promoted fixture defaults must not be confused with an explicit source-backed rebuild. | Useful for final-state method checks. Roster `active_roster_status` is unknown throughout; routes, route participation, team rush attempts, rush share, red-zone targets/carries, and snap share are null in the usage source. |
| Role-and-opportunity lab | Current committed examples are fixtures/fictitious scenarios, not a governed upstream dataset. | No source revision timeline. | Contract/method development only; not empirical NFL evidence. |
| Rookies inputs | Local hashes and named sources exist, but this audit did not find complete licence, terms, snapshot-rights, and point-in-time metadata for every named source. | Local hashes alone do not prove past availability or source reuse rights. | Follow-up source-by-source review; no adverse legal conclusion inferred. |

No governed current injury, depth-chart history, participation, receiver-alignment, or raw tracking corpus was found in the audited TIBER source universe.

## 7. Question support boundary

| Research question family | Present status | Why |
| --- | --- | --- |
| Team/game/play meta-trends derivable from ordinary play-by-play | **Retrospectively testable; prospectively plausible** | Current final-state PBP derivatives exist. A future cutoff-faithful run still requires rights disposition and TIBER-owned exact-byte capture. |
| Player-week outcomes and basic opportunity proxies present in weekly stats | **Retrospectively testable with caveats** | Source-backed 2025 outcomes/usage exist, but route, snap, red-zone, and some denominator fields are absent/null. |
| Weekly injury/availability-conditioned research | **Not currently supportable as a recurring lane** | nflverse's injury source ended after 2024; NFL public pages are terms-constrained and temporally incomplete. |
| Historical formation tendencies using shotgun flag | **Narrowly testable** | The current formation artifact distinguishes shotgun/non-shotgun/unknown only. |
| WR condensed formation, receiver width, and all-route studies | **Not currently testable from retained TIBER sources audited here** | Current artifacts lack receiver width and route denominators. nflverse participation has formation/routes but not width coordinates and is postseason-only from 2023; FTN charting adds selected play labels but not width/all-route denominators. Public NFL displays are not a licensed raw feed. |
| Raw player-tracking discovery | **Unavailable in the public recurring source set** | A licensed NFL/Genius path or a separately cleared competition dataset would be needed. |

This boundary should guide question generation later: the Observatory must route a question to `testable_now`, `testable_with_declared_proxy`, `requires_new_source`, or `blocked_by_rights_or_temporal_truth` before any computation. Defining or implementing that router belongs to a later approved phase.

## 8. Minimum provenance required before a source can advance

For every proposed source asset, record at least:

- provider, dataset family, season, grain, schema, row count, and event bounds;
- licence identifier/version/link, required attribution, upstream terms link, and terms retrieval date;
- intended-use decisions separately for internal analysis, model use, retention, redistribution, and publication;
- repository, release tag, filename, exact download URL, asset ID, byte size, and provider digest when available;
- HTTP ETag/Last-Modified and redirect target when available;
- retrieval start/end UTC, local SHA-256, and immutable local object identity;
- embedded source timestamp/version fields and whether they survived file-format conversion;
- access client/commit/version, loader arguments, cache mode/hit, and transformation code commit;
- `event_time`, `effective_at`, `published_at`, `source_available_at`, `retrieved_at`, `first_observed_at`, `admissible_at`, `cutoff_at`, `revision_id`, evidence mode, and supersession link;
- schema/dtype hash, derived-artifact hash, quality checks, and known selection/censoring behavior.

A stable URL, football week, file modification time, current checksum, or repository tag alone is insufficient.

## 9. Follow-up required before any RD2 decision

1. **Signed source-use policy:** resolve, source family by source family, the relationship between nflverse's declared CC licences and upstream NFL, FTN, PFR/Sports Reference, or other provider terms. Record model use, retention, public output, and redistribution separately.
2. **Narrow admissible source set:** explicitly approve or reject PBP, player/team stats, schedules, weekly rosters, depth charts, NGS aggregates, FTN charting, participation, and all third-party-derived families. PFR snap counts remain excluded until expressly cleared.
3. **Historical cohort feasibility check:** inspect the exact nflverse archive assets, hashes, embedded timestamps, completeness, and loader compatibility for any candidate date. Do not treat the archive schedule as proof that every required asset exists.
4. **Current injury decision:** identify and audit a replacement provider or formally remove injury-conditioned questions from the initial Observatory envelope.
5. **Alignment/tracking decision:** either remove WR-width/all-route questions from the initial envelope or pursue an expressly licensed dataset/feed. Do not infer width from formation labels.
6. **Correction/cutoff policy:** choose declared capture points per admitted source family. Thursday-after-corrections is a defensible PBP candidate, but no equivalent finalization rule has been proved for every source.
7. **Rights owner review:** obtain operator and, where warranted, qualified legal/licensing review before a public or recurring corpus is authorized.

## 10. RD1 stop boundary

This inventory is the terminal RD1 evidence package. It recommends no autonomous continuation.

The next permitted action is independent review of this audit and then a separate operator decision. Until that decision, do not:

- activate RD2 or design/construct a snapshot implementation;
- download or retain a new research corpus;
- select or replay a historical cohort;
- generate or route research questions in production;
- run ingestion, modeling, forecasting, scheduling, or promotion;
- modify freshness/governance registries or expand #24's execution authority.

**Terminal result: `source_temporal_audit_requires_followup`.**
