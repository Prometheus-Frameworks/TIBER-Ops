# Merge Checklist

Run this before merging any PR. It is the gate that keeps work inside its lane
and inside scope. Pairs with [`pr-review.md`](pr-review.md).

## Pre-merge checklist

- [ ] **Lane named.** The PR states its lane (product, doctrine/governance,
      research/writing, ML/modeling, parked/incubation).
- [ ] **Owning repo named.** The repo that owns the capability is identified.
- [ ] **Change summarized.** What changed is clear.
- [ ] **Out of scope stated.** What the PR deliberately does not touch is
      explicit.
- [ ] **Guardrails confirmed.** The PR respects the constraints it claims.
- [ ] **Tests / builds reported.** What ran and the result are recorded.
- [ ] **Follow-ups parked.** Deferred work is captured in
      [`../docs/lane-index.md`](../docs/lane-index.md) or
      [`../docs/parked-ideas.md`](../docs/parked-ideas.md), not left implicit.
- [ ] **Active-lane check.** The work belongs to the week's active lane, or is
      an explicitly allowed non-implementation exception.

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

## Merge

Only merge once every box above is checked and the guardrails hold.
