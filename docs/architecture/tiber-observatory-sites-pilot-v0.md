# TIBER World Workspace — owner-only Sites pilot record v0

Status: **PILOT DEPLOYED / RATIFICATION POSTED / DOCUMENTATION PENDING REVIEW /
LONG-TERM FIT UNDECIDED**

| Binding | Value |
| --- | --- |
| Present-state authority | [TIBER-Ops #22 ratification record](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5145331704) |
| Earlier pilot and design record | [TIBER-Ops #35](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/35) |
| Human decision owner | Joseph (`@Prometheus-Frameworks`) |
| Sole write repository for this record | `Prometheus-Frameworks/TIBER-Ops` |
| Pinned Ops base | `26ba68ed8a9ba67fdd9543dbd0d4e8107ff4e71c` |
| Owner-only Site | [TIBER World Workspace](https://tiber-world-workspace.jmas-tiber.chatgpt.site) |
| Site source checkpoint | `9d28db0f955fcab738e2b209fc7fdea6f30a7c52` |
| Site saved version | `3` |
| Site deployment receipt | `appgdep_6a6c9667d7a88191a31e5f1cf2b07351` (`succeeded`) |
| Execution ledger | [`progress-ledger.md`](../../pilots/bounded-goal/tiber-observatory-sites-pilot-v0/progress-ledger.md) |

This document records the interface pilot that now exists. It does not claim
that #35 previously authorized a persistent World Workspace deployment. The
2026-07-31 #22 record ratifies the current owner-only state and authorizes this
documentation-only reconciliation package. The package does not activate,
replace, resume, or complete a TIBER program frontier.

The ledger uses `pilots/bounded-goal/`, the nearest merged TIBER-Ops convention
for a bounded package with a progress ledger, instead of introducing the
previously proposed but still absent `program/discoveries/` tree. This is a
path-only convention choice.

## 1. Answer first

The World Workspace is useful as a **read-only reasoning surface over imperfect
TIBER evidence**, not as a universal dashboard or a new source of truth.

Its distinctive job is to keep five things visible at the same time:

1. what the live product currently reports;
2. which governed evidence supports or conflicts with that report;
3. when each source was observed and when its underlying evidence applies;
4. what is missing, stale, partial, or uncomputed; and
5. what a human or agent may do next without receiving operational authority.

The interface should retain the "world model" feel only where it improves
situational legibility: one coherent workspace, multiple evidence layers,
source receipts, explicit contradictions, and portable agent-readable exports.
It should not become a second product backend, a hidden recommendation engine,
or a permanent collection of one-off dashboards.

## 2. Authority and epistemic boundary

The Site is a presentation and normalization surface. GitHub decisions,
governed repository artifacts, and the owning TIBER runtimes remain canonical.

| Role | Authority in this pilot |
| --- | --- |
| Joseph | Human meaning, corrections, access decisions, and every operational or program decision |
| TIBER Management/Data Lab | Live source behavior for the fields each endpoint actually owns |
| Governed repository artifacts | Provenance, model/data promotion state, contracts, and program authority |
| World Workspace adapter | Bounded retrieval, normalization, freshness labeling, and failure preservation |
| World Workspace UI/export | Human and agent legibility only; no mutation or decision authority |
| Reasoning agent | May compare, summarize, identify conflicts, and propose questions from the exported packet; may not act on TIBER |

`TIBER_WORKSPACE_CONTEXT_V1` is a **pilot-local, non-canonical read model**. It
is not a promoted cross-repository contract. If TIBER later needs a shared
read-model contract, ownership belongs in TIBER-Data or another separately
approved contract-owning repository—not implicitly in the Site or TIBER-Ops.

The persistent workspace also remains in explicit tension with #35's later
design direction: **maximum situational legibility with minimum permanent
product weight**. Whether the World shell should persist, generate immutable
briefs, or become a hybrid is an operator decision this pilot is meant to make
easier. Deployment is not adoption.

## 3. Deployed architecture

```text
TIBER-Fantasy live GET surface
      | Management/Data Lab plus league, sync, rankings, and rookies
      | live product state, derived diagnostics, source-specific clocks
      v
Owner-only Site server adapter
      | fixed upstream + fixed user, allowlisted GETs, timeout, cache/coalescing
      v
TIBER_WORKSPACE_CONTEXT_V1
      | normalized values + source receipts + gaps + conflicts
      +-----------------------+
      |                       |
      v                       v
Human workspace          Agent-readable export
      |                       |
      +-----------+-----------+
                  v
        Joseph retains action authority
```

There is no Site-owned D1 or R2 store. The Site does not ingest league
credentials, receive a caller-selected upstream URL, or expose TIBER write,
sync, merge, deploy, promotion, or approval controls.

### 3.1 Same-origin adapter boundary

The browser calls the Site's same-origin adapter. The adapter is required
because the current upstream does not allow the Site browser origin through
CORS. Its deployed boundary is:

- one server-configured upstream origin;
- one fixed pilot identity: `user_id=default_user`;
- a fixed allowlist of seven upstream paths;
- `GET` only, with no caller-supplied method or request body;
- no upstream credential or arbitrary header passthrough;
- an 8-second upstream timeout;
- a 30-second cache/coalescing window; and
- explicit error receipts rather than healthy-looking fallback values.

"GET-only" describes the Site boundary, not a proof that every upstream GET is
internally side-effect-free. In particular, the current Management
`team-direction` path invokes dashboard computation that may persist a
Management snapshot. A future strict no-side-effect contract must be proved in
the upstream implementation, not inferred from HTTP method alone.

## 4. Exact live source inventory

All paths are resolved against the single server-configured TIBER-Fantasy live
deployment. The surface includes Management and Data Lab plus league context,
league sync, rankings, and rookies. The base origin is not accepted from the
browser or included in the client bundle.

| Source ID | Allowlisted GET path | Workspace use | Failure/freshness rule |
| --- | --- | --- | --- |
| `league_context` | `/api/league-context?user_id=default_user` | League identity, format, season, scoring, roster context | Missing identity makes the workspace partial; never substitute a demo league |
| `team_direction` | `/api/management/team-direction?user_id=default_user` | Raw Management classifier, confidence, rationale, position values | Keep raw classification separate from evidence-authority state |
| `draft_picks` | `/api/league-sync/picks?user_id=default_user` | Recorded draft-pick context | An incomplete ledger is labeled incomplete; absence is not zero picks |
| `weekly_rankings` | `/api/rankings/v2/weekly` | Weekly ranking availability | Empty/uncomputed cache is a gap, not an empty authoritative ranking |
| `rookies_2026` | `/api/rookies/2026` | 2026 rookie artifact availability | Missing artifact remains unavailable; no synthetic rookie rows |
| `teamstate_movement` | `/api/data-lab/team-environment-movement` | Team-environment movement availability | Missing artifact remains unavailable; no inference from other team fields |
| `promoted_status_2026` | `/api/data-lab/promoted-status?season=2026` | FORGE/promotion diagnostics and activation metadata | Stale or failed gates remain visible and cannot be collapsed into the raw classifier |

The current route set is public and does not present a proved authentication or
rate-limit boundary. It has no single governed, versioned aggregate contract;
several routes are unversioned, while `/api/rankings/v2/weekly` carries a route
version. Owner-only Site access reduces exposure of this UI; it does not repair
the upstream boundary. Before broader use, TIBER-Fantasy should expose an
authenticated, versioned, bounded aggregate or equivalent governed read
surface.

## 5. Pilot-local read model

`TIBER_WORKSPACE_CONTEXT_V1` normalizes the seven receipts without pretending
they share one clock or one authority class. At minimum, an exported packet
must preserve:

```text
schema_version
workspace_observed_at
mode
overall_status
league_context
management_raw_classification
evidence_authority
rankings_state
rookie_state
teamstate_state
draft_pick_state
gaps[]
conflicts[]
source_receipts[]
```

Each source receipt preserves the source ID, allowlisted path, Site retrieval
time, upstream observation/availability time when emitted, response outcome,
freshness state, and error or gap code. The Site retrieval clock must never
overwrite an upstream artifact, computation, or promotion clock.

The UI and export distinguish:

- `ready`: required evidence is present and current for the displayed claim;
- `partial`: some evidence is present and at least one declared dependency is
  missing, uncomputed, malformed, or in conflict;
- `stale`: evidence was retrieved successfully but failed its freshness or
  activation rule; and
- `unavailable`: the source could not support a value.

These are presentation states, not model confidence scores or program
terminals.

## 6. Production observation on 2026-07-31 UTC

An authorized request through the owner-only Site access path, using an
already-configured bypass credential, returned the live read model rather than
fixtures.

| Field | Observed value | Interpretation boundary |
| --- | --- | --- |
| Schema | `TIBER_WORKSPACE_CONTEXT_V1` | Pilot-local and non-canonical |
| Mode | `live` | Adapter reached the configured upstream |
| Overall status | `partial` | At least one useful source succeeded and declared gaps remain |
| League | `Morts FF Dynasty` | Management league identity |
| Team | `Garbage Time` | Management team identity |
| Season / scoring | `2026` / `PPR` | Context only; not proof that every downstream artifact matches this scoring profile |
| Raw team classifier | `REBUILD` / `low` confidence | Management output, displayed as reported |
| FORGE activation evidence | `19/30`, `63%`, stale, effective Level 1 | Evidence-authority view; does not silently rewrite the raw classifier |
| Recorded positional values | WR `13.5`; QB `26.9` | Preserved as Management values without inventing units or rank semantics |
| Draft-pick state | Round 3 recorded; 11 entries unscored | Partial ledger, not a complete pick valuation record |

Declared live gaps were:

- weekly rankings not computed: `forge_cache_empty_uncomputed`;
- 2026 rookie artifact missing;
- Teamstate Movement artifact missing; and
- FORGE freshness gate not enforced:
  `FORGE_G6_DIAGNOSTIC_NOT_ENFORCED`.

The most important conflict is deliberate and visible: the raw Team Direction
classifier cites stale FORGE alpha, while activation metadata says G6 fails and
the effective evidence level is Level 1. The Site preserves both statements and
labels the conflict. It does not choose one by hiding the other.

This observation is a dated deployment check, not a durable canonical snapshot.
Values may change after any source clock advances. The live response preserved
workspace and source-specific clocks, but their exact values were not copied
into this reconciliation document; this table is therefore not a clock-complete
receipt.

## 7. Observatory boundary

The current deployed surface is wired to the **TIBER-Fantasy live GET surface**,
including Management and Data Lab plus league, sync, rankings, and rookie
routes. The existing Observatory proper is client-only and exposes no accepted
backend reasoning contract that this Site can consume. The interface may
present an "Observatory" lens over live diagnostics, but it must not imply that
a governed Observatory reasoning service exists today.

A future backend must separately define inputs, versioning, provenance,
freshness, deterministic versus model-derived fields, failure semantics,
privacy, and human/agent authority before the Site treats it as a source.

## 8. Failure and trust semantics

| Condition | Required representation | Forbidden representation |
| --- | --- | --- |
| Timeout or network failure | Source receipt `unavailable`; overall state `partial` or `unavailable` | Reuse an unlabeled prior value as current |
| HTTP or parse error | Preserve status/error code and affected fields | Generic healthy state |
| Empty rankings cache | `uncomputed` gap | A valid empty ranking or rank zero |
| Missing artifact | Named unavailable artifact | Synthesized row or inferred substitute |
| Stale activation evidence | `stale` with its source clock | Current/active badge |
| Conflicting sources | Show both claims, authorities, and clocks | Silent last-write-wins resolution |
| Incomplete picks | Partial ledger with known counts | Complete portfolio claim |
| Unknown unit/meaning | Preserve raw value and label the ambiguity | Invented unit, score, percentile, or rank |
| Unauthorized caller | Owner-only access denial | Public fallback view |

The adapter's 30-second cache is transport smoothing only. It does not make an
upstream artifact fresh and does not change its evidence clock.

## 9. Agent-readable use

The workspace is designed so a reasoning agent can consume the same bounded
packet a human sees. A useful export includes:

- the pilot-local schema version;
- normalized values without decorative UI text;
- all gaps and conflicts;
- individual source receipts and clocks;
- raw classifier and evidence-authority fields as separate objects; and
- the human-authority boundary.

An agent may use this packet to explain current state, compare evidence, name
missing contracts, draft questions, or propose a bounded next investigation.
It must not treat the export as a command envelope, durable memory, promoted
artifact, or permission to mutate TIBER. Exports inherit the Site's owner-only,
private boundary and may not be published or shared without separate human
authorization.

## 10. Known architecture and governance gaps

1. The upstream GET surface is public, lacks a proved authentication/rate-limit
   contract, and has no single governed/versioned aggregate contract; several
   routes remain unversioned.
2. `default_user` is a shared pilot identity boundary, not an acceptable
   multi-operator identity model.
3. Browser CORS requires a server proxy, increasing the importance of the
   allowlist and upstream-origin controls.
4. The Management `team-direction` GET may persist a snapshot internally.
5. FORGE raw-classifier and G6/effective-level evidence currently conflict.
6. Weekly rankings, the 2026 rookie artifact, and Teamstate Movement are
   unavailable or uncomputed in the observed packet.
7. The pick response is not a complete, clocked asset ledger.
8. Observatory proper has no accepted backend reasoning contract.
9. `TIBER_WORKSPACE_CONTEXT_V1` has no cross-repository owner and therefore
   must remain Site-local.
10. A persistent World shell may violate the spirit of #35 if it accumulates
    permanent product weight instead of generating compact decision lenses.

## 11. Deployment, access, and rollback

### Deployment receipt

- Site project: `appgprj_6a6c0acd21748191a238e603ec7c012b`
- Saved version: `appgprj_6a6c0acd21748191a238e603ec7c012b~appgver_9ccd71e0de088191854ae6210967ef2c`
- Source checkpoint: `9d28db0f955fcab738e2b209fc7fdea6f30a7c52`
- Deployment: `appgdep_6a6c9667d7a88191a31e5f1cf2b07351`
- Deployment result: `succeeded`
- Access: custom owner-only
- Durable Site storage: none

### Rollback procedure

1. Disable or delete the owner-only Site deployment through Sites management.
2. Verify the Site URL no longer returns the workspace to an unauthenticated or
   previously authorized browser.
3. Remove any operator navigation link that implies the Site remains current.
4. Preserve this GitHub record as historical evidence; append a dated rollback
   receipt rather than rewriting the deployment history.
5. Confirm that no canonical TIBER state, artifact, or workflow depended on the
   Site. No back-migration is expected because the pilot owns no canonical data.

Rollback does not require a TIBER-Fantasy or TIBER-Data mutation. Credential
disposition remains governed by the applicable incident or decommission policy;
this pilot record creates no replacement rule.

## 12. Review questions

This draft asks Joseph and future reviewers to decide, separately:

1. Should the World Workspace remain a persistent shell, become generated
   immutable decision briefs, or use a small shell that opens generated lenses?
2. Should TIBER-Fantasy expose one authenticated/versioned aggregate read API
   so the Site does not normalize seven public endpoints?
3. Is a shared cross-repository read model justified? If yes, should TIBER-Data
   own and promote it?
4. What is the minimum accepted Observatory backend contract before the UI may
   present agent synthesis as Observatory output?
5. Which missing source—rankings, rookies, Teamstate Movement, picks, or FORGE
   freshness—should be repaired first under a separately authorized frontier?

This document deliberately emits no program terminal and authorizes none of
those follow-ups.
