# PR Review Runbook

Every PR in any TIBER repo should answer the questions below — in its
description or in review. The point is coordination: a reviewer should be able
to tell, without guessing, which lane the PR belongs to and whether it stays
inside scope.

## Questions every PR must answer

1. **What lane is this?**
   Product, doctrine/governance, research/writing, ML/modeling, or
   parked/incubation. (See [`../docs/operating-map.md`](../docs/operating-map.md).)

2. **What repo owns it?**
   The repo that owns the underlying capability — not necessarily where the
   issue is filed.

3. **What changed?**
   A concrete summary of the change.

4. **What is explicitly out of scope?**
   What this PR deliberately does **not** touch.

5. **What guardrails apply?**
   The constraints this PR must respect (e.g. docs-only, no runtime behavior,
   governance/freshness rules).

6. **What tests / builds ran?**
   What was actually run, and the result.

7. **What follow-up remains parked?**
   Anything discovered but deliberately deferred — link to the lane index or
   parked ideas as appropriate.

## Lane check

Confirm the PR's lane matches the **active** lane for the week, or that it is
an explicitly allowed exception (indexing, auditing, docs). Implementation work
outside the active lane should be flagged — see
[`../docs/weekly-cadence.md`](../docs/weekly-cadence.md).

## Before approving

- All seven questions above are answered.
- Scope and out-of-scope are stated, not implied.
- Guardrails are respected.
- Follow-ups are parked in the index, not left as silent TODOs.

See also [`merge-checklist.md`](merge-checklist.md).
