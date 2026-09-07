# 2026 season operations — LIVE

**Operator-declared effective date:** September 7, 2026

**Scope:** NFL 2026 reporting and operator planning; documentation only.

**Calendar snapshot at declaration:** Week 1 preparation, before the regular-season opener.

> TIBER's 2026 season operations are live. The operating question moves from
> "what might the role become in camp?" to "what has actually changed in
> availability, deployment, opportunity, and the operator's decision context?"

"Live" describes the operator's reporting posture. It is not a machine-readable
runtime switch, source-admission receipt, production-readiness claim, or
implementation-lane rotation. It does not declare every TIBER capability live.

## Calendar boundary

Sources checked September 7, 2026:

- [NFL Football Operations — important dates](https://operations.nfl.com/calendar-events/nfl-important-dates):
  September 6 was the final day of preseason training camp; the opening practice
  and game-status reporting window is September 6–12.
- [Patriots' dated Week 1 broadcast notice](https://www.patriots.com/news/how-to-watch-listen-patriots-at-seahawks-week1),
  published September 5: New England at Seattle is scheduled for Wednesday,
  September 9, at 8:20 p.m. Eastern / September 10 at 00:20 UTC.

These are cited calendar observations, not new admitted TIBER-Data artifacts.
September 7 is the operating-posture date, not the first-game date. The scheduled
kickoff is not evidence that the game has occurred. Later reports must verify
their own as-of calendar and game state; this paragraph is a dated snapshot.

Keep the decision target separate from observed evidence coverage. A Week 1
question does not establish any Week 1 snaps, finalized outcomes, or complete
league-wide coverage. Do not change runtime season/week detection, mark a week
complete, or freshen an artifact from this document.

## Reporting convention: NFL Season Signal

Use **TIBER NFL Season Signal — YYYY-MM-DD** for the ongoing report, with an
explicit as-of time and decision week. Preserve earlier Camp Signal reports as
historical records; do not rename or rewrite their conclusions retroactively.

Prioritize meaningful evidence deltas:

1. Official practice participation, game-status reports, transactions, inactives,
   and confirmed restrictions. Distinguish an estimated walkthrough report from
   observed practice, an app injury tag from an official designation, and being
   active from receiving a normal workload.
2. Attributable first-team and personnel evidence before kickoff; after games,
   source-backed snaps, routes, touches, targets, alignments, and high-value roles.
   Third downs, two-minute work, pass protection, routes, and goal-line carries
   are separate functions, not interchangeable evidence of "RB2" or "TE2."
3. Contradictions against the camp thesis and prior ledger state. A later
   correction appends or supersedes; it does not erase what was known earlier.

Use the team's actual game-day reporting cycle, not a universal Wednesday
assumption. The NFL calendar specifies Sunday–Tuesday practice reports for a
Wednesday game and Wednesday–Friday reports for a Sunday game. On game day,
verify inactives and restrictions. After play, report only what the available
source actually covers, separating partial/in-progress data from finalized
outcomes. This is reporting guidance, not a newly scheduled job.

For every material item, keep **observation, inference, source confidence,
hypothesis confidence, market implication, and missing witness** separate.
Preserve event/effective, source-publication, retrieval, and record times when
available; do not invent precision or refresh evidence by retrieving it again.
A published beat projection is evidence of that analyst's expectation, not
observed deployment. Repeated syndicated copies are not independent witnesses.

For usage metrics, name the source, game/window, denominator, exclusions, and
coverage. Where available, distinguish competitive snaps from garbage time and
explain injury or opponent/game-script distortions. If those fields are absent,
say so; do not manufacture routes or personnel packages from a box score.
One game can change a hypothesis without proving a stable season-long role.

Separate near-term redraft/lineup utility from dynasty value. An observed ADP
move requires comparable platform, format, and timestamped snapshots. A predicted
price move is inference. Once drafting ends, draft ADP remains acquisition
context, not a live weekly price or a universal trade valuation.

Quiet days receive a short hold/watch note, not another apparent evidence delta.
Exclude uncorroborated highlights, generic praise, duplicate closures, and
unsupported coach-speak interpretation.

## Operator-board continuity

Carry forward the existing watch subjects rather than opening a new universe:
Jacksonville and Bhayshul Tuten; New England and Eli Raridon; Pittsburgh and
Michael Pittman Jr., Roman Wilson, and Germie Bernard; Malik Nabers; and Dallas's
backup-running-back roles, including the historical Jaydon Blue competition.

These are research priorities, not assertions of today's team, health, or role.
Reverify current membership and competition before reporting. Once a transaction
resolves an old team-role hypothesis, preserve its closure and track any new
team context separately. Apply the same standards to the already-followed
Seattle/George Holani and Chicago backfield questions.

The public Draft Review URL remains Joseph's stated product priority. That
priority is not a lane rotation or deployment authorization.

## Evidence and authority boundaries remain unchanged

- **Source truth:** TIBER-Data retains ownership of source admission, canonical
  identity, and realized outcomes. This declaration admits no feed or artifact
  and authorizes no acquisition, ingestion, backfill, or play-by-play buildout.
- **Forecast:** [Forecast #170](https://github.com/Prometheus-Frameworks/TIBER-Forecast/issues/170)
  remains the owner of its exact run authorization.
  [#185](https://github.com/Prometheus-Frameworks/TIBER-Forecast/issues/185) is the
  readiness companion, not execution permission. Preserve the frozen
  `seasonal-ppr-2026-forward-001` pins and candidate/non-consumable boundary.
  Current news cannot enter that run or turn its seasonal output into a weekly,
  ROS, or current September forecast. Recheck the current control records before
  any action; this document does not certify whether an execution occurred later.
- **Ledger:** [Fantasy #356](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/issues/356),
  [#325](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/issues/325), and
  [#327](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/issues/327) retain
  their own durability, identity, and write gates. Reports are candidate notes,
  not durable appends. Recheck current lineage and baseline binding before any
  separately authorized write; do not replay stale ready-to-write payloads.
- **Product and agents:** no Draft Review or other consumer activation, remote
  MCP, authentication, persistent-agent runtime, or automatic roster action.
  [Ops #69](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/69) and each
  owning issue retain their independent sequence and acceptance boundaries.
- **Operations:** no repository/default-branch merge, deployment, scheduler
  change, credentials, model/scoring change, source promotion, issue closure, or
  blanket permission to repair historical documentation. The existing
  [lane index](lane-index.md) and [weekly board](weekly-cadence.md) are unchanged.
  [Ops #66](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/66) and
  [#77](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/77) still govern
  action-specific authority and inherited downstream effects.

A green review or the word "live" supplies none of those permissions.

## Pickup checklist

At the next operator session:

- Re-read the owning issues and current authorization; distinguish current
  repository, deployed release, frozen experiment, and candidate-note states.
- Verify the actual NFL reporting/game window and source freshness.
- Read prior evidence before proposing deltas; preserve unresolved identities,
  conflicts, unavailable fields, and operator-local versus shared context.
- Return a compact report: what changed, why it matters, what is still unknown,
  and the smallest decision requiring Joseph. Stop at the task's existing limit.

This document defines the handoff, not unattended execution. No scheduled-task
configuration was changed by preparing it.

## Provenance

Joseph directly requested: "Let's declare season 2026 as officially live," in
the September 7 live conversation, together with an Ops documentation update.
ChatGPT materialized that request as this bounded docs-only change. GitHub
account attribution and this text are not independent human-origin proof and
cannot transfer consequential authority to a later agent or session.

See the [operator direction record](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5570853707) for the bounded preparation scope.
