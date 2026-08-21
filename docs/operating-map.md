# Operating Map

TIBER-Ops is the coordination layer for TIBER work across Fantasy, Data,
FORGE, Teamstate, Rookies, PPM, FLF/research docs, and future parked ideas.

It does **not** own fantasy scoring, model logic, artifact production, product
UI, or source data. It coordinates the repos that do.

## The five lanes

### 1. Product lane

- **Scope:** Management, Observatory, roster surfaces.
- **Anchor:** TIBER-Fantasy #264 — **completed and closed** (PR A–D:
  #269 / #270 / #271 / #278).

### 2. Doctrine / governance lane

- **Scope:** Reality Stack, promotion gates, explicit-marker governance,
  freshness.
- **Current anchor:** TIBER-Fantasy #277.

### 3. Research / writing lane

- **Scope:** FLF paper, orchestration paper, Reality Stack writeups.

### 4. ML / modeling lane — **active**

- **Scope:** governed Forecast / PPM model evaluation, candidate-runtime
  readiness, and explicitly admitted modeling inputs.
- **Program anchor:** TIBER-Forecast #167 — 2026 Forward Forecast v0
  baseline-candidate path.
- **Current execution gate:** TIBER-Forecast #170 remains inactive until its
  exact live operator authorization is valid under TIBER-Ops #66.
- **Current state:** runtime, frozen base-model, Data evidence, and admission
  binding prerequisites are materially complete. The 2026-08-21 read-only
  pre-run check passed, but no candidate run has occurred.
- **Teamstate disposition:** Forecast #98 deliberately parks the completed
  2024 Teamstate Run 2 path after no measured lift at the tested scale and
  feature shape. It is not a blocker for Forward Run 1.
- ML / modeling remains the sole active implementation lane; this factual
  correction does not rotate it. See [`lane-index.md`](lane-index.md).

### 5. Parked / incubation lane

- **Scope:** TIBER-Ops automation, RAG / layered intelligence, Harness, heat
  maps, office AI, agent evals.
- See [`parked-ideas.md`](parked-ideas.md).

## Operating rule

**Only one implementation lane should be active at a time.**

Other lanes can be indexed, audited, or parked — but **not quietly
implemented**. If work starts in a lane that is not the active lane, that is a
process error to be surfaced at the weekly board, not a fait accompli.

- **Active:** the single lane currently being implemented.
- **Indexed:** tracked here with anchors and state, but not being worked.
- **Audited:** under review/spec, may produce findings, but not implementing.
- **Parked:** deliberately deferred; not started.

## How lanes relate to repos

A lane is a *theme of work*, not a repo. A single repo (e.g. TIBER-Fantasy)
can host issues that belong to different lanes (#264 product, #277 governance,
#265 modeling). The lane — not the repo — determines whether work is allowed
to be active right now.

See [`lane-index.md`](lane-index.md) for the per-lane index and current state.
