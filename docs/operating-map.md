# Operating Map

TIBER-Ops is the coordination layer for TIBER work across Fantasy, Data,
FORGE, Teamstate, Rookies, PPM, FLF/research docs, and future parked ideas.

It does **not** own fantasy scoring, model logic, artifact production, product
UI, or source data. It coordinates the repos that do.

## The five lanes

### 1. Product lane

- **Scope:** Management, Observatory, roster surfaces.
- **Current anchor:** TIBER-Fantasy #264.

### 2. Doctrine / governance lane

- **Scope:** Reality Stack, promotion gates, explicit-marker governance,
  freshness.
- **Current anchor:** TIBER-Fantasy #277.

### 3. Research / writing lane

- **Scope:** FLF paper, orchestration paper, Reality Stack writeups.

### 4. ML / modeling lane

- **Scope:** PPM, point projection / scenario / outlook work.
- **Current anchor:** PPM issue #49 and TIBER-Fantasy #265.

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
