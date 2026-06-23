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
- **Related future work:** Freshness fail-closed — documented as future work,
  **not opened.**

## Research / writing lane

- **Owns:** FLF paper, orchestration paper, Reality Stack writeups.
- **State:** **Parked / indexed.** FLF paper / docs live in this lane.

## ML / modeling lane — **ACTIVE**

- **Owns:** PPM, point projection / scenario / outlook work.
- **Active anchor:** Point-prediction-model #60 — first successful PPM
  model-run operator evaluation.
- **Indexed anchors:** PPM issue #49 and TIBER-Fantasy #265.
- **State:** **Active lane.** Authorized as the single active implementation
  lane following the close of the Product lane.
- **Purpose of this lane:**
  - Surface bottlenecks that prevent PPM from becoming more trustworthy.
  - Move PPM beyond player PPR-only inputs.
  - Begin connecting governed Teamstate artifacts into the PPM feature path.
- **First step (audit/spec, not implementation):** Audit/spec for **2024
  full-league Teamstate artifact production** and **PPM consumption
  boundaries**. PPM needs full-league 2024 Teamstate artifacts before
  model-run-2 can properly test richer inputs, so the first likely
  implementation/audit work happens in **Teamstate**.
- **Boundaries for this lane:**
  - This is **not** Product-lane work.
  - Do **not** surface PPM outputs in Management yet.
  - Do **not** create rankings / advice / product behavior.
  - Do **not** start #259 / #265 / #277 / freshness unless separately
    authorized.

## Parked / incubation lane

- **Owns:** TIBER-Ops automation, RAG / layered intelligence, Harness, heat
  maps, office AI, agent evals.
- **State:** TIBER-Ops automation is **parked, not started.** Full backlog in
  [`parked-ideas.md`](parked-ideas.md).

## Current state summary

| Item | Lane | State |
| --- | --- | --- |
| TIBER-Fantasy #264 (PR A–D: #269/#270/#271/#278) | Product | **Completed and closed** |
| Point-prediction-model #60 | ML / modeling | **ACTIVE** — first PPM model-run operator evaluation |
| 2024 full-league Teamstate artifacts + PPM consumption boundaries | ML / modeling | **Active first step** — audit/spec (work likely in Teamstate) |
| PPM model (#49, #265) | ML / modeling | Indexed under active lane |
| TIBER-Fantasy #277 | Governance | **Parked** — audit/spec ticket; not authorized |
| Freshness fail-closed | Governance | Documented future work, **not opened** |
| FLF paper / docs | Research / writing | **Parked / indexed** research-lane material |
| TIBER-Ops automation | Parked / incubation | **Parked, not started** |
