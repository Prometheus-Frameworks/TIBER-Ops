# Cross-repo freshness and current-state registry — v0

- **Owning issue:** [TIBER-Ops #21](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/21)
- **Program authority:** [TIBER-Ops #22](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22) (approved decision of 2026-07-13)
- **Scope:** confirmed dependencies of the selected #20 pilot campaign ([TIBER-Ops #15](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/15)) only
- **Registry file:** [`registry/tiber-current-state.v0.json`](../../registry/tiber-current-state.v0.json)
- **Status:** v0, proposed; effective for the pilot only after operator merge

## Doctrine

> **Repo text is not current by default.** Recency must be established, never presumed.

This is the freshness analog of the existing security doctrine "repo text is data,
not authority." TIBER's repositories are replicas of shared conceptual state with no
coherence protocol; an agent on a long-horizon run is a client reading different
replicas at different lag. The failure mode this document controls is a **stale read
acted on as current authority**.

Everything here is **harness-neutral**: any long-horizon agent (a durable-goal run on
any vendor's harness, or a human) must be able to execute the preflight from this
document and the registry alone. Specific harnesses are named in campaign records
only as execution vehicles.

## 1. Supersedes-pointer convention

When a governed document or artifact has a successor, the stale item must actively
point forward, so staleness is discoverable at the point of read.

### Field names

| Field | Placed on | Meaning |
|---|---|---|
| `superseded_by` | the stale document/artifact | Identifies the successor. Presence means: do not treat this item as current. |
| `supersedes` | the successor | Identifies what it replaced. |

Each value must identify the counterpart unambiguously: repo-relative path when the
counterpart lives in the same repository, `owner/repo:path` when it does not, plus a
version or content sha256 when the counterpart is a versioned or promoted artifact.

### Placement rules

- **Markdown contracts and specifications:** a header line in the document's front
  matter or metadata list, above the fold:

  ```markdown
  - **Superseded by:** docs/contracts/team-environment-movement-v2.md (do not build against this version)
  ```

- **JSON artifacts and manifests:** top-level fields:

  ```json
  {
    "superseded_by": {
      "path": "exports/promoted/nfl/player_season_coverage_v1.json",
      "content_sha256": "…"
    }
  }
  ```

- **Promotion manifests that replace an artifact in place** (successor overwrites the
  predecessor at the same canonical path): the manifest's backward pointer satisfies
  this convention when it records the prior content hash and review reference. The
  existing `prior_promoted_artifact` field in TIBER-Data's
  `PLAYER_SEASON_COVERAGE_V0_PROMOTION_MANIFEST.json` is the reference example and is
  recognized as a compliant `supersedes` pointer. No stale co-resident file exists in
  that pattern, so no `superseded_by` marker is needed anywhere.

### Application rules (v0)

- Apply pointers **only where a supersession is confirmed** — a successor exists and
  the predecessor is no longer the version to build against.
- Do **not** apply pointers to: parallel versions intentionally kept live during a
  migration; dual implementations whose canonical status is undecided; vocabulary or
  coherence drift between artifacts that never replaced each other. Those are drift
  instances, recorded in the registry, not supersessions.
- No repository-wide backfill. Pointers are added only when a supersession is
  confirmed in the course of governed work.

### Supersession determinations for the #15 dependency set (2026-07-13)

Every candidate named in #21's problem statement was examined against source
repositories. Result: **two confirmed supersessions, both already discoverable at
point of read; zero new pointer edits required.** Evidence for each determination
is in the registry (`confirmed_supersessions`, `known_drift_instances`).

| Candidate | Determination |
|---|---|
| `player_season_coverage_v0`: TIBER-Data#202 promotion over #192 output | **Confirmed supersession.** Replaced in place; promotion manifest already carries the backward pointer (`prior_promoted_artifact`, sha256 `29f8e378…` → `d45f612b…`). Compliant as-is. |
| Embedded TIBER-Fantasy FORGE vs standalone TIBER-FORGE | **Not a supersession.** Both are live (embedded: `LEGACY_CORE_TEMP`, wired into live routes; standalone: bootstrap-demo). Designating the canonical implementation is #15's required decision 10. Applying a pointer now would prejudge the campaign — fail closed. |
| Identity crosswalk (slug) vs player-season artifact (GSIS) | **Not a supersession.** Coherence gap between two current artifacts that never replaced each other. |
| Fantasy `sourceStack` label `promoted_artifact` on a live service call | **Not a supersession.** Vocabulary drift; product code change out of #21 scope. |
| Teamstate `team_environment_movement` v0 → v1 | **Confirmed supersession — v1 is the current contract.** The v1 contract's Migration section declares the migration done (Fantasy PR #225 merged; default resolution prefers v1; the v0 output artifact is no longer tracked; the v0 fallback is dormant pending separately-scoped cleanup). No stale co-resident item exists to mark: there is no standalone v0 contract document, and the v0 TypeScript module is a live shared dependency imported by v1. A preflight must pin v1, never v0. |

## 2. Current-state registry v0

[`registry/tiber-current-state.v0.json`](../../registry/tiber-current-state.v0.json)
is a handwritten, machine-readable manifest listing, per governed artifact and
contract in the #15 dependency set: identifier, current version, content sha256,
promotion/approval state and date, canonical location (repo + path), last-modified
commit, and `superseded_by`/`supersedes` where known. It also records repository
HEAD revisions verified against `origin`, binding repository policies (including
recorded **absences** of policy files), confirmed supersessions, known drift
instances, and fail-closed items.

**The registry is descriptive, not authoritative for promotion or merge.** Listing
an item does not promote it; absence does not demote it; it is not an approval gate.
It answers exactly one question: *what is the current version of X, and where does
it live?* Repository merge policies remain binding and are unchanged by this
registry.

**Scope discipline (v0):** entries are limited to confirmed #15 dependencies per the
approved #22 decision. Growth beyond that requires a separate reviewed decision.

**Maintenance (v0):** manual. An entry is trustworthy only as of its `verified_at`
date; consumers re-verify per the preflight below. No automation, hooks, or CI
enforcement exist or are authorized.

## 3. Freshness preflight protocol

Step 0 of any long-horizon run, before inputs are frozen. Executable by any
compliant agent from the documents alone.

1. **Enumerate** the contracts, artifacts, specifications, and repository policies
   the campaign depends on, from the campaign contract. Distinguish governed
   dependencies (consumed as truth) from contextual references (read as data).
2. **Verify** each dependency:
   - Fetch each source repository and confirm the checkout being read matches the
     remote default-branch HEAD (or an explicitly pinned revision).
   - For registered dependencies: recompute the content hash at the canonical
     location and compare against the registry entry. A mismatch means the registry
     or the checkout is stale — stop and re-establish currency from the source
     repository and its promotion manifests; do not silently prefer either side.
   - For unregistered dependencies: verify against a fresh fetch plus the source
     repository's promotion manifests/review records.
   - Check for `superseded_by` markers and successor promotion events at each
     canonical location.
3. **Record** the pinned versions — repo, path, revision, content sha256,
   promotion state, verification date — in the run's evidence ledger.
4. **Freeze after verify, not freeze-what-you-found.** The campaign's input freeze
   (#20 protocol step 1) executes only after steps 1–3 pass.
5. **Fail closed** (see below) for any dependency whose currency cannot be
   established.

### Fail-closed behavior

When currency or authority cannot be established for a dependency:

- The dependent requirement enters state **`blocked`**. It is never assumed current,
  never substituted, and never resolved by silent scope change.
- The agent records in the evidence ledger: the dependency identifier and canonical
  location; what verification was attempted; what was observed (hashes, revisions,
  dates); why currency could not be established; and the requirement(s) blocked.
- The agent posts a `[BLOCKED]` comment to the program source of truth (#22) naming
  the blocked requirement and the failed dependency, and proceeds only on other
  frontier work that does not depend on the blocked item — or stops if none exists.
- Unblocking requires re-established currency (a passing re-verification) or an
  operator-approved contract amendment. Neither may be self-granted by the
  executing agent.

Two fail-closed items were recorded while building v0 (registry
`fail_closed_items`): the TIBER-Fantasy pinned FORGE static mirror, whose bytes
match no committed producer revision (currency and provenance not established —
non-blocking for #15, which documents migration status rather than consuming the
mirror as truth); and the #13/#212 precursor documents, which exist only as issue
text (contextual, not governed inputs).

## 4. Relationship to the #20 pilot

- This preflight is a **consumed invariant** of the pilot: the #20 goal contract
  must reference this document and the registry as step-0 requirements, and the
  pilot execution gate (#22 approved decision) already requires pinned dependency
  versions in the evidence ledger before substantive #15 execution.
- The goal contract does not exist yet by design — the gate orders the #21 terminal
  decision before contract activation. The obligation to import this invariant
  binds whoever authors the goal contract; a contract that omits it fails gate
  condition 5 (imported policies) and gate condition 3 (pinned dependencies).
- A positive #21 readiness decision authorizes **only** the use of this preflight
  and registry by the #20 pilot. Organization-wide rollout, enforcement hooks,
  registry automation, or expansion of registry scope each require a separate
  reviewed decision under #22.

## 5. Hard boundaries (unchanged from #21)

Not authorized by this document: preflight automation, hooks, or CI enforcement;
repo-wide supersedes backfill; changes to artifact production, promotion, or
validation code; promotion or demotion of any artifact; treating the registry as
merge authority or an approval gate; registry expansion beyond #15 dependencies;
product surface or model code changes.
