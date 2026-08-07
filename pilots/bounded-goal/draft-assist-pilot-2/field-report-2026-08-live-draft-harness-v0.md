# Field Report: TIBER-Harness Live Draft Simulation v0

**Status:** field evidence, non-production. Agent-authored under operator direction (H4MMER), 2026-08-05 → 2026-08-07.
**Scope:** Operator ran a real 10-team full-PPR redraft slow draft (slot 3) plus 4 mock drafts, using a Claude agent as a stand-in for the ideal TIBER harness. Every gap, bottleneck, or blocker encountered while surfacing draft-relevant artifacts was logged as a finding. This document extends draft-assist-pilot-2 field evidence and follows the same rule as operator-draft-traces-v0: **data, not authority** — findings inform backlog decisions; they do not authorize implementations.
**Companion artifacts (session scratchpad, not committed):** merged draft board (live FFC ADP × TIBER 2025 outcomes × rookie alphas), per-mock VOR grades.

---

# TIBER-Harness Field Report — Live Draft Exercise
**Date:** 2026-08-05 · **Scenario:** 10-team redraft snake draft, ~2h lead time
**Goal:** Operate TIBER as if the harness were at ideal stage; log every gap, bottleneck, or blocker hit while trying to surface draft-relevant intel.

## Session setup
- All 9 repos cloned locally (TIBER-Data, -Strategy, -Fantasy, -Forecast, -FORGE, -Ops, -Rookies, -Teamstate, Role-and-opportunity-model).
- No live PostgreSQL, no platform API keys assumed — testing what the harness can surface from repo artifacts alone.

## Findings log

### F-001 · No single entry point for "draft mode"
**Severity:** structural
There is no harness-level index answering "user is drafting in 2 hours — what artifacts do I load?" Recon required fanning out searches across 9 repos just to inventory what exists. Ideal state: a manifest (e.g. in TIBER-Ops registry) mapping use-case → authoritative artifacts + freshness stamps.

<!-- Findings appended as discovered. Format:
### F-XXX · Title
**Severity:** blocker | degraded | structural | papercut
Body: what was attempted, what happened, what ideal-state looks like.
-->

### F-002 · No draft-ready player board exists anywhere in the workspace
**Severity:** blocker
The only promoted FORGE artifact (`TIBER-FORGE/exports/promoted/forge_player_static/forge_player_static_v1.json`, 59 rows / 52 players) self-describes as an "evidence compiler artifact, not a projection artifact." Nothing in 9 repos is shaped like a rankable 2026 redraft board except a small hand-seeded `player_ratings_v1.json` (last updated 2025-11-02).

### F-003 · Promoted FORGE artifact is internally uncomparable across cohorts
**Severity:** blocker (for draft use)
Three source cohorts were compiled onto no common scale: Rico Dowdle scores 76.7 while Ja'Marr Chase scores 32.0 and Bijan Robinson 25.0. Worse, the 14 highest alphas (Bowers 100, Chase 99.9…) are `generated_baseline` fixture rows the artifact's own policy says must not be read as player evidence. An agent naively surfacing "top FORGE alphas" would hand the user fabricated numbers first.

### F-004 · Promoted artifact built from stale fixture input, not best available data
**Severity:** degraded
TIBER-Data holds a genuine nflverse-sourced 2025 cohort (`data/gold/forge/forge_player_weekly_ppr_2025.cohort.v1.json`, asOf 2026-04-27), but the promoted FORGE build used an older test-fixture copy (asOf 2026-01-08). The pipeline's freshest input never reached its published output — a promotion-pipeline gap.

### F-005 · Cross-repo artifact drift: TIBER-Fantasy serves a divergent copy
**Severity:** degraded
`TIBER-Fantasy/server/artifacts/external/forge/forge_player_static_v1.json` has the same generated_at and player set but 21 rows with different alphas (McCaffrey 21.3 vs 99.2 in the promoted copy). Consumers get different answers depending on which repo they read. No sync/checksum mechanism exists.

### F-006 · FORGE-in-Fantasy lane requires live Postgres; only bootstrap FORGE runs offline
**Severity:** structural
`TIBER-Fantasy/server/modules/forge/forgeEngine.ts` and 6 sibling services import a live drizzle DB — dead in this container. `TIBER-FORGE` itself runs fully offline (zero runtime deps, one env var) but only compiles evidence, not projections. Rebuild from real 2025 cohort is possible (`--source-backed-cohort ... --no-generated-baselines`) and is the highest-value local action, yielding ~50 players on one scale — still 2025-backward-looking.

### F-007 · Role/opportunity model outputs are synthetic fixtures
**Severity:** degraded
Player-level role artifacts contain only fake players ("Vale Q", "Harbor Z"). The 2026 team profiles cover 16 real teams but every quantitative field is null (`operator_seeded`). Role intel — exactly what a draft needs for ambiguous backfields — is qualitative tags at best.

### F-008 · Freshest real intel is 6 months old
**Severity:** degraded
`TIBER-Fantasy/data/current_intel.json` (news/injury/usage, e.g. McCaffrey Achilles note) is stamped 2026-02-11. Best current artifact overall: `TIBER-Rookies/exports/promoted/rookie-alpha/2026_rookie_alpha_postdraft_v0.json` (2026-06-14, 32 real 2026 rookies with post-draft alphas + reason codes) — clean, but rookies-only.

### F-009 · No 2026 redraft ADP exists anywhere in TIBER — the headline gap, confirmed
**Severity:** blocker
User's opening question ("does TIBER equip you with up-to-date ADPs?") answered: **no.** Only ADP-shaped artifacts are a 28-player 2026 *dynasty rookie* KTC board and a 76-player 2025-preseason RB-only ADP embedded in projection files. No FantasyPros/Underdog/FFC/Sleeper ADP snapshot is persisted to disk in any repo. ADP schema exists in Postgres migrations (`adp`, `adp_trend_7d`, `market_signals`) but no dump/seed/fixture with actual rows.

### F-010 · The active ADP sync code is silently broken
**Severity:** blocker (latent)
`TIBER-Fantasy/server/adpSyncService.ts` reads `trending?.adp || player.adp` from Sleeper endpoints that **do not return an adp field** — the gate drops every row and the sync "succeeds" with ~0 updates. Its ESPN fallback is URL-pinned to `seasons/2025`. The `[PRIMARY]` `realTimeADPService.ts` reads one hardcoded league ID and falls back to synthesized "consensus estimates." The `[DEPRECATED]` service ships a hand-typed ADP table. Meanwhile the only *correct* free source (`server/data/adpClient.ts` → fantasyfootballcalculator.com API) is wired up but never called into a persisted artifact. Classic harness failure: four ADP services, zero real ADP.

### F-011 · ECR pipeline is manual-upload, in-memory only
**Severity:** degraded
`ecrLoader.ts` requires an admin to hand-upload a FantasyPros CSV (no API access); data lives in in-memory Maps that die on restart. No ECR CSV exists on disk. Expert-consensus rankings are effectively unreachable to an agent.

### F-012 · Identity crosswalk is the binding constraint (25 records)
**Severity:** blocker (structural)
`tiber_identity_crosswalk_v1.json` maps 25 players; `player_ownership_latest.json` covers 27. Even if live ADP were fetched today, joining it to TIBER's governed 610-player 2025 production base can't happen at scale. The join layer, not the data, is the bottleneck.

### F-013 · Ingestion code pinned to past seasons
**Severity:** degraded
`ingestProjections.ts` hardcodes Sleeper season 2024 URLs; `adpSyncService.fetchESPNADP()` hardcodes 2025; Sleeper cache last refreshed 2025-11-02 (its 288 "rookies" are the 2025 class); `live_data/sleeper_week_18_*.json` are four byte-identical files (position filter never applied). Season rollover is manual and nobody rolled it.

### F-014 · What TIBER *does* have that's genuinely good
**Severity:** (positive control)
- `TIBER-Data/exports/promoted/nfl/player_season_coverage_v0.json`: 3,016 source-backed player-seasons incl. full 2025 (610 players), sha-pinned, governed. Promoted 2026-07-06.
- `TIBER-Rookies` promoted exports: 2026 rookie alphas pre/post-draft with reason codes (June/July 2026).
- `nfl_draft_results_2026.json`: all 257 picks of the 2026 NFL draft.
- `bounded_2026_population_census_v0.json` (candidates/, unpromoted): 658-row best-available 2026 universe.
Pattern: the governed data layer works; the market/consumption layer (ADP, projections, rankings) is where the harness starves.

### F-015 · No 2026 forward forecast exists, by explicit governance decision
**Severity:** blocker (acknowledged internally)
TIBER-Forecast's own audit (2026-07-27): "Current main cannot produce an honest forward-looking 2026 seasonal artifact." The frozen forward model's coefficients are not committed (only a sha256), so it can't even be replayed to score 2026. Every candidate manifest is `production_ready: false, consumer_eligibility: never`. The Ops capability matrix gates all player-facing draft features "AFTER 2026 FORECAST."

### F-016 · Everything is calibrated to 12-team; nothing to 10-team
**Severity:** degraded
All 7 operator draft traces, the TE research note's league contract, and the default replacement baselines assume 12-team. Only `calculateReplacementBaselines.ts` / `buildDefaultReplacementPoints.ts` accept `teams: 10` as a parameter. Key strategy premise ("usable RB tier declines steeply after ~R4") weakens at 10 teams — replacement level rises everywhere.

### F-017 · Team environment layer: real data is 2024; 2026 layer is operator-seeded nulls
**Severity:** degraded
TIBER-Teamstate's governed real data = 544 team-weeks of **2024**. The 2026 files are qualitative tags with `operator_seeded_unknown` provenance; 31/32 rows of the offensive-environment file are "unknown." No offensive-line data anywhere (`pressureRateAllowed` null and deferred). No 2025 team data at all.

### F-018 · No live-draft state surface
**Severity:** blocker (for in-draft use)
Ops capability matrix confirms: draft session, live board, clock, cursor, pick feed — absent across all repos. The harness cannot know who's been taken. In-draft operation requires the user to relay the board manually.

### F-019 · What Ops/Strategy DO have: the strategy prior is excellent
**Severity:** (positive control)
- `draft-assist-pilot-2-field-evidence-and-v0-contract-map.md`: a complete, honest v0 spec (shortlist-first, fail-closed, human-picks).
- `operator-draft-traces-v0.json`: 7 real draft traces with pick-by-pick rationale, selection intent, and recorded alternatives — the operator's revealed strategy (double-RB turns, Bowers unicorn exception, wait-at-QB pockets, flex-capacity logic).
- `2026-redraft-premium-te-leverage-research-note-v0.md`: live 2026 theses (Gibbs 1.01 BPA, Bowers top-6 personal, H1/H2 TE hypothesis separation).
Pattern confirmed: TIBER's *judgment layer* (strategy, governance, provenance discipline) is far ahead of its *data-supply layer* (market data, projections, live state).

### F-020 · The ADP gap is one HTTP call wide — self-heal succeeded
**Severity:** (positive control / indictment of the pipeline)
Live fetch of `fantasyfootballcalculator.com/api/v1/adp/ppr?teams=10&year=2026` returned HTTP 200: 246 players, 4,622 real drafts, window 2026-07-29 → 2026-08-05 (same-day fresh), with pick-level stdev and bye weeks included. This is the exact API `TIBER-Fantasy/server/data/adpClient.ts` already implements. The gap was never data access — it's that no scheduled job calls the working client and persists the result. One cron + one promotion contract closes F-009.

### F-021 · Name-based join worked at 89% where the crosswalk covers 4%
**Severity:** degraded (workaround exists)
With the 25-record identity crosswalk (F-012) unusable, a normalized-name join matched 180/202 ADP skill players to the governed 610-player 2025 season file, +14 to rookie alphas. Only 1 of the top 100 (Kenny Gainwell) matched nothing. Name-joins are fragile (suffixes, punctuation, team-context collisions) but the demonstrated ceiling is high — seeding the crosswalk from a name-join + human review of mismatches would scale it in a day.

### F-022 · Data quality: ghost player in the governed 2025 file
**Severity:** papercut (provenance-significant)
`player_season_coverage_v0_2025...json` row 1: "Philip Rivers, QB, season 2025, 31.66 PPR" — a player retired since 2020, in a sha-pinned, promoted, `identity_confidence: source_verified` artifact. Likely an upstream nflreadpy identity or filtering bug. Notable because it slipped through the strictest governance chain in the workspace; suggests promotion review checks manifests but not content plausibility.

### F-023 · 2026 offseason movement is invisible to every TIBER artifact
**Severity:** blocker (freshness)
The live ADP feed exposed roster movement no TIBER artifact knows: A.J. Brown → NE, Kenneth Walker → KC, Jaylen Waddle → DEN, Mike Evans → SF, DK Metcalf → PIT, Travis Etienne → NO, Javonte Williams → DAL, David Montgomery → HOU, DJ Moore → BUF, Davante Adams → LAR. TIBER's freshest roster view (Sleeper cache) is 2025-11-02; player_ownership covers 27 players. Any TIBER-side team-context reasoning silently assumes last year's rosters.

### F-024 · League scoring profiles cannot be represented; INT data is null everywhere
**Severity:** degraded
User's league is 6pt passing TD / -2 INT. TIBER-Forecast fails closed on any non-generic scoring profile (by design), and the data layer can't support a manual adjustment either: the gold cohort has `passingTds` for only 22 QBs, and `interceptions` is `null` in every artifact checked — the scoring rules *claim* -2/INT but the totals verifiably never applied it (Goff's pprTotal reconciles to the penny without INTs). The QB Data Lab CSV has CPOE/EPA process metrics but no passing TD or INT columns. Result: 6pt-TD adjustment possible for 22 QBs; INT penalty unmodelable.

### F-025 · 2025 outcome mirror has no games-played column → injury-year distortion
**Severity:** degraded
`player_season_coverage_v0_2025` carries `season_ppr` only — no games, no PPG. Season-total VOR therefore punishes injury-shortened seasons invisibly: Lamar Jackson (raw 214.9), Burrow (134.5), Jayden Daniels (114.3) rank as unstartable when the market prices them QB3/4/6 — almost certainly missed-games artifacts, but the artifact cannot distinguish 9 elite games from 17 mediocre ones. The 2022-2024 mirror HAS games/ppg; the 2025 outcome layer dropped them.

### F-026 · Strategy research notes carry market assumptions that go stale silently
**Severity:** papercut (process)
The TE leverage note recorded a live open question — "Sleeper mocks leave Bowers ~28; operator expects live rooms take him ~16" — flagged correctly as unverified. Live 10-team ADP (2026-08-05) resolves it: Bowers 40.7, McBride ahead of him at 35.2. The note had no mechanism to be re-annotated when market evidence became available; its acquisition-window assumptions were ~2 rounds off by draft day. Ideal state: research notes declare their market assumptions as versioned fields a market-snapshot job can diff and flag.

### F-027 · Emergent capability: league-design simulation from existing data
**Severity:** (opportunity)
Mid-session the user revealed they were the commissioner choosing settings, not just drafting into them. The 2025 positional point curves + the replacement-demand formula from TIBER-Forecast answered "which roster config keeps 8-team stud-density while preserving waiver quality" quantitatively (worst-starter points vs best-waiver points per config). No TIBER repo has this as a feature; it fell out of existing artifacts in one query. A "commissioner mode" (roster/scoring config → starter quality, wire quality, bye-week pain) is a low-cost, high-delight capability sitting on data TIBER already governs. Session outcome: league locked at QB/2RB/3WR/TE/2FLEX + 5 bench based on this analysis.

### F-028 · Platform ADP divergence: Sleeper vs FFC differ by 1+ rounds on specific players
**Severity:** degraded (market-data design input)
User's mock screenshots show Sleeper in-app ADP materially diverging from the FFC market feed: G. Wilson 40.9 (Sleeper) vs 28.2 (FFC); L. Burden 41.1 vs ~54. Since the user's home league drafts on Sleeper, platform-local ADP likely predicts room behavior better than cross-platform consensus. Ideal harness: snapshot multiple ADP sources, store divergence per player, and let draft-assist weight the source matching the room's platform. Single-source ADP is a hidden model risk.

### F-029 · Emergent capability: the mock-trace grading loop
**Severity:** (opportunity — strongest product signal of the session)
Across 5 mock runs the session settled into a repeatable loop: screenshot roster → OCR picks → score vs merged board (VOR captured, ADP delta per pick) → detect behavioral patterns → prescribe the untested branch for the next run. Findings this loop produced that no single artifact could: a repeated-selection habit (same RB taken 4/4 runs, ~9 picks early); in-room validation of the TE-fade acquisition window (premium TE reached pick 23 in 4/4 rooms); platform ADP divergence (F-028); bye-week clustering as a recurring blind spot; and comparison-class coverage (C1/C2/C4 from the operator's own research note, drafted from the same slot). This is TIBER-Ops' draft-assist trace protocol running live with the agent as the recorder/grader. The missing harness pieces it exposes: pick ingestion (screenshots instead of a draft-state feed, F-018), per-run trace persistence, and cross-run habit analytics.

### F-030 · Live-draft validation (session 1, picks 1–43 + turn planning)
**Severity:** (field evidence)
The real draft (10-team slow draft, slot 3) validated the prep loop end-to-end: JSN 1.3 → Pickens 2.8 → Chase Brown 3.3 → Etienne 4.8 → G. Wilson 5.3 — every pick at or under market, byes spread by design. Live findings:
- **Disappears-first ordering** (take the player who won't survive to your next pick, using room-local ADP) drove every turn decision and repeatedly beat naive best-available.
- **Room-local behavior dominated global ADP**: RB-aggressive early, WRs sliding (as in all 4 mocks), rookies going 2 rounds early (Tate ~55 vs market 76), TE apathy then a sudden run (Loveland sniped 1 pick after user passed).
- **Shield logic** emerged as a reusable primitive: a higher-priced same-position player (Tyler Warren) or a position-sated adjacent manager (the Bowers owner) protects a target across the turn gap; when the shield disappears, flip the pick order.
- **F-025 (games-played blindness) was the single most recurring live handicap**: G. Wilson, Lamar, McLaurin, Hurts, Nico all required the operator's injury/context knowledge to overrule or reinterpret trailing VOR.
- **Operator camp intel (Fannin target reports, Corum committee fear, Cook role rumor) is the freshest data in the loop** — the harness's role was pricing those thesis clicks against market, not replacing them. This matches TIBER product doctrine (human decision authority) surprisingly well: the ideal harness prices conviction rather than dictating picks.

## Summary assessment

**Central pattern:** TIBER's judgment/governance layer (provenance discipline, fail-closed contracts, operator draft traces, strategy ontology) is materially ahead of its data-supply layer (market data, projections, current rosters, live state). The harness starves not for lack of pipes — working clients and schemas exist — but because nothing operates them on a schedule and nothing promotes their output.

**Top 5 recommended issues, in leverage order:**
1. **ADP snapshot job** (closes F-009/F-010): daily cron calling the existing FFC client → promoted `adp_snapshot_v0` artifact with format/teams parameterization. ~1 day of work.
2. **Identity crosswalk expansion** (closes F-012): bootstrap from normalized-name join vs Sleeper dump + FFC, human-review the <15% fuzzy tail (closes F-021 fragility).
3. **Season-rollover audit** (closes F-013): grep for hardcoded seasons in ingestion paths; make season a config value with a staleness alarm.
4. **Artifact drift detection** (closes F-005): checksum manifest consumed by TIBER-Fantasy at startup; refuse divergent mirrors.
5. **FORGE rebuild from real cohort** (closes F-003/F-004 partially): `--source-backed-cohort --no-generated-baselines` build, and stop promoting fixture-derived rows above real evidence.

**Draft-day verdict:** with one live fetch + name-join, the harness produced a defensible 10-team board (ADP + 2025 VOR + rookie alpha + byes) in ~20 minutes. At ideal stage this exists before the user asks.
