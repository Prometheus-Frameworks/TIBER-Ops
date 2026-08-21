# Lane Index

Per-lane index of anchors and current state. This is the at-a-glance status
of TIBER work. The active lane is chosen weekly — see
[`weekly-cadence.md`](weekly-cadence.md).

> Reminder: only **one** implementation lane is active at a time. Everything
> else is indexed, audited, or parked.

> **Active lane: ML / modeling.** All other lanes are parked or closed below.

## Product lane

- **Owns:** Management, Observatory, roster surfaces.
- **Anchor:** TIBER-Fantasy #264 — **completed and closed.**
- **State:** **Closed.** Surface separation delivered via PR A–D:
  - #269 — Observatory naming / route / honest-status hygiene.
  - #270 — Management UI audience separation.
  - #271 — Observatory real read-only signal inventory.
  - #278 — Observatory take-triage copy / input clarity.

## Doctrine / governance lane

- **Owns:** Reality Stack, promotion gates, explicit-marker governance,
  freshness.
- **Anchor:** TIBER-Fantasy #277.
- **State:** **Parked.** Governance-convergence audit / spec ticket. Not to be
  started unless separately authorized.
- **Authorized exception:** TIBER-Ops #21 — cross-repo freshness preflight and
  #15-scoped current-state registry v0 (PR #23). Docs-only doctrine/governance
  work separately authorized under TIBER-Ops #22 (approved decision
  2026-07-13). This exception does not change the active implementation lane;
  ML / modeling remains the sole active implementation lane.
- **Related future work:** Freshness fail-closed — documented as future work,
  **not opened.** This item means **artifact/product-surface enforcement** (do
  not show users stale data) and is distinct from #21's delivered
  **agent-context** freshness protocol (preflight + registry for long-horizon
  runs); delivering #21 does not open it.

## Research / writing lane

- **Owns:** FLF paper, orchestration paper, Reality Stack writeups.
- **State:** **Parked / indexed.** FLF paper / docs live in this lane.

## ML / modeling lane — **ACTIVE**

- **Owns:** governed Forecast / PPM model evaluation, candidate-runtime
  readiness, and explicitly admitted modeling inputs.
- **Program anchor:** TIBER-Forecast #167 — 2026 Forward Forecast v0
  baseline-candidate path.
- **Current execution gate:** TIBER-Forecast #170 — the bounded
  `seasonal-ppr-2026-forward-001` candidate remains inactive until its exact
  live operator authorization is valid under TIBER-Ops #66.
- **State:** **Active by policy; stopped at the human execution gate.** The
  implementation/evidence prerequisites are materially complete:
  - Forecast #169 / PR #172 delivered the typed deterministic forward runtime.
  - Forecast #168 / PR #174 froze the base model/configuration at
    `813eff8de0b4a8d4f29f5c37abe522fe3e792ca3`.
  - TIBER-Data #227 and #228 delivered the bounded census and scoring
    reconciliation evidence.
  - Forecast PR #175 bound the admitted inputs and compatibility policies in
    the immutable artifact bundle at
    `804fb39b318bb8406cb7e3c24e6fbb9234a930c8`.
- **Pre-run status (2026-08-21):** an independent read-only check rehashed the
  declared packages/evidence and compared the six direct pre-fit runtime files
  against current Forecast `main`. Pins remain current and compatible.
  Preparation is complete; no run has occurred.
- **Teamstate disposition:** the full 2024 coverage chain is complete, but
  Forecast #98 deliberately parks the Teamstate Run 2 path after the unchanged
  full-coverage rerun showed no measured lift. Teamstate is not a blocker for
  Forward Run 1 and is not admitted into this base-only candidate.
- **Permitted preparation without a new consequential decision:** read-only
  pin/compatibility checks, exact decision-packet preparation, and review of
  already-produced evidence. Lane status alone does not authorize execution.
- **Boundaries for this lane:**
  - Any #170 output remains `candidate_only`, `production_ready: false`,
    `consumer_eligibility: never`, and
    `uncertainty_status: unavailable_not_calibrated`.
  - Do not promote, publish, deploy, activate Fantasy/Strategy consumers, or
    represent the candidate as advice.
  - Do not surface PPM outputs in Management or create rankings/product
    behavior from this lane.
  - Teamstate public-report publication remains separately gated and disabled.
  - Do not rotate the implementation lane through this factual update.

## Parked / incubation lane

- **Owns:** TIBER-Ops automation, RAG / layered intelligence, Harness, heat
  maps, office AI, agent evals.
- **State:** TIBER-Ops automation is **parked, not started.** Full backlog in
  [`parked-ideas.md`](parked-ideas.md).

## Current state summary

| Item | Lane | State |
| --- | --- | --- |
| TIBER-Fantasy #264 (PR A–D: #269/#270/#271/#278) | Product | **Completed and closed** |
| TIBER-Forecast #167 | ML / modeling | **ACTIVE program anchor** — 2026 Forward Forecast v0 candidate path |
| TIBER-Forecast #170 | ML / modeling | **Awaiting live operator gate** — pins/compatibility reverified 2026-08-21; no run executed |
| Forecast #169 / PR #172, #168 / PR #174, Data #227/#228, Forecast PR #175 | ML / modeling | **Prerequisites materially complete** — runtime, frozen base model, data evidence, and admission binding |
| Forecast #98 / completed 2024 Teamstate coverage chain | ML / modeling | **Parked, not blocking #170** — no measured lift at the tested scale/feature shape |
| TIBER-Teamstate #90 public report | ML / modeling | **Implemented but inactive** — publication remains disabled and separately gated |
| TIBER-Fantasy #277 | Governance | **Parked** — audit/spec ticket; not authorized |
| TIBER-Ops #21 freshness preflight + registry v0 (PR #23) | Governance | **Authorized docs-only exception under #22** — delivered via PR #23; effective as merged to `main` (see the registry's effective condition) |
| Freshness fail-closed (artifact/product-surface enforcement — distinct from #21's agent-context protocol) | Governance | Documented future work, **not opened** |
| FLF paper / docs | Research / writing | **Parked / indexed** research-lane material |
| TIBER-Ops automation | Parked / incubation | **Parked, not started** |
