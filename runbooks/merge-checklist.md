# Merge Checklist

Run this before any PR merge or other default-branch update. Technical
readiness is necessary but does not authorize execution. Pair this checklist
with [pr-review.md](pr-review.md).

Authority follows [TIBER-Ops #66](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/66),
its active interim live-instruction model, and the pre-execution record
procedure clarified in [#77](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/77).
The [#22 process correction](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-5309048092)
requires canonical materialization before execution. Decision labels,
GitHub authorship, agent reports, and review approval are not independent
human-origin proof.

## Technical readiness

For a PR merge, the readiness record is the PR description and its linked
review/evidence. For a separately authorized default-branch update without a
PR, use a dated readiness comment on the target issue in the owning repository.
Bind that comment to the exact proposed update and current default-branch
state, and link it in the decision packet and canonical TIBER-Ops #22 authority
record. It must supply equivalent answers to [pr-review.md](pr-review.md) and
evidence for all eight checks below; the absence of a PR waives no check.
This alternative records readiness only. It grants no permission to bypass a
required PR or any stricter task, actor, repository, or authority gate.

- [ ] **Lane named.** The readiness record states its lane (product,
      doctrine/governance, research/writing, ML/modeling, parked/incubation).
- [ ] **Owning repo named.** The repo that owns the capability is identified.
- [ ] **Change summarized.** What changed is clear.
- [ ] **Out of scope stated.** What the update deliberately does not touch is
      explicit.
- [ ] **Guardrails confirmed.** The update respects the constraints stated in
      its readiness record.
- [ ] **Tests / builds reported.** What ran and the result are recorded.
- [ ] **Follow-ups parked.** Deferred work is captured in
      [`../docs/lane-index.md`](../docs/lane-index.md) or
      [`../docs/parked-ideas.md`](../docs/parked-ideas.md), not left implicit.
- [ ] **Active-lane check.** The work belongs to the week's active lane, or is
      an explicitly allowed non-implementation exception.

## Blocking authority preflight

This procedure grants no task, merge, default-branch, deployment, or
scope-amendment authority. Preserve stricter task and repository restrictions,
including actor restrictions and any prohibition on self-merge. A direct
default-branch write is not a shortcut around the gate or the PR process.

- [ ] **Decision packet prepared.** Identify repository, PR and intended
      transition (or the separately specified default-branch update), exact
      reviewed head or previously authorized deterministic binding, current
      base/default-branch state, changed-path/scope envelope, independent
      review disposition and its head, unresolved-thread state, and required
      checks. Link the evidence and state the actual permitted/prohibited
      downstream effects.
- [ ] **Effects and tier established.** Classify the transition under #66
      using its highest downstream effect. Include automatic deployment,
      activation, publication, and changes to scope or authority where
      applicable. Docs-only content does not establish absence of those
      effects. Unknown effects block execution; they are not assumed absent.
- [ ] **Authority and executor established.** For R2, verify the exact bounded
      live instruction or valid delegation envelope, including its objective
      conditions, expiry, permitted actors, and terminal action. For R3 under
      the interim rule, the acting agent must directly receive Joseph's exact
      live instruction at the transition point. A preparatory instruction or
      clean review is insufficient. Do not request a second decision merely
      to perform the bookkeeping covered by the same bounded instruction.
- [ ] **Canonical record materialized before execution.** The receiving agent
      records the decision in TIBER-Ops #22 and links that record from the
      target PR (or target issue for a separately specified non-PR transition).
      Record repository/target, exact head/state binding, bounded action,
      permitted/prohibited effects, conditions, decision time, source/location,
      receiving agent/session, recording time, applicable expiry/revocation
      and single-use limits, and technical evidence references. Identify
      Codex/Claude/other preparing system and disclose whether independent
      human-origin verification was available. Quote or faithfully summarize
      only the relevant instruction; do not invent provenance, timestamps,
      or proof, or expose sensitive conversation content. Under the interim
      model this is an agent-materialized audit record, not an authenticated
      transferable receipt. Record creation and readback must succeed.
- [ ] **Record and target rechecked immediately before execution.** The same
      receiving agent reads the canonical record and checks it against the
      live instruction and current target. Recheck head/base binding, changed
      paths, scope, effects, review at the bound head, unresolved-thread gate,
      required checks, executor eligibility, expiry/revocation, and prior
      consumption. Honor a deterministic binding only if it was already
      authorized and cannot be amended by the agent.
- [ ] **No blocking mismatch.** Missing/unverifiable materialization,
      ambiguous authority or identity, stale/mismatched state, conflicting
      instructions, expanded scope, changed/uncertain effects, an ineligible
      executor, failed/missing required checks or review conditions, expired
      or revoked authority, or possible prior consumption stops execution.
      Do not silently rebase, substitute a head, waive a gate, broaden an
      envelope, or use a copied record to repair the mismatch.

R0/R1 preparation and expressly included R2 implementation, testing,
review, and repair may continue within their existing bounded authority.
They do not require repeated clerical approvals. A handoff can carry that
preparatory context, but a different agent, later session, scheduled routine,
or GitHub-only reader cannot treat an agent-materialized record as standalone
R3 human-origin proof. The consequential transition returns to the live gate
unless a separately established verifiable receipt path exists.

This checklist documents procedure. It does not authenticate human origin or
mechanically prevent forgery, replay, bypass, or races. #17 owns the access and
trust-boundary audit; #66 remains the receipt-design dependency. No verifier,
signer, credential, ruleset, branch protection, or workflow is established here.

## Guardrails for this repo (TIBER-Ops)

TIBER-Ops is docs-only. A PR here must introduce:

- No code
- No GitHub Actions
- No automation
- No scripts
- No package files
- No agents
- No issue bots
- No external integrations
- No runtime behavior

If a PR to this repo would add any of the above, it does not belong here yet —
it is a promotion of the parked "TIBER-Ops automation" idea and must go through
the weekly board first. See [`../docs/parked-ideas.md`](../docs/parked-ideas.md).

## Execute and record

Execute only when technical readiness, the authority preflight, and all
applicable guardrails pass. Perform only the one bounded authorized
transition; do not enable continuing auto-merge or expand its effects.

Record UTC execution time, the reviewed source head, resulting merge commit
or exact default-branch update, action reference, and authority consumption
in a linked follow-up to the canonical record and target PR/issue. Preserve
the pre-execution record and chronology. Report observed downstream effects
separately from effects whose outcome remains unknown.

If the action result or subsequent recording is uncertain, stop, report the
gap, and reconcile read-only within existing authority; do not retry the
transition blindly or claim successful consumption without evidence.
