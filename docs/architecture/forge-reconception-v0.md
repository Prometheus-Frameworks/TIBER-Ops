# FORGE reconception decision document v0

> **Status:** D3 candidate checkpoint — pending fresh-context independent
> verification. D3 is the sole active discovery frontier under
> [the signed frontier decision](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991320938).
> D4–D6 remain inactive, and TIBER-Ops#15 R2 remains
> `r2_parked_pending_forge_reconception`.
>
> **Evidence freeze:** D1 checkpoint
> [`5161b4c80e01771ff5830ad1c200fc410902a755`](https://github.com/Prometheus-Frameworks/TIBER-Ops/commit/5161b4c80e01771ff5830ad1c200fc410902a755).
> D2 checkpoint
> [`1c141b39616972cb67c663d025a78edad0414046`](https://github.com/Prometheus-Frameworks/TIBER-Ops/commit/1c141b39616972cb67c663d025a78edad0414046)
> is the accepted semantic baseline. No source outside the D1 freeze is used as
> architectural evidence.

This document is the incremental deliverable governed by TIBER-Ops#31. Sections
1–6 preserve the accepted D2 semantic decomposition and evidence index.
Sections 7–10 add D3's four-option comparison. The comparison does not
authorize a FORGE direction, implementation, migration, deprecation, or D4.

## 1. D2 method and authority discipline

D2 tests the nine ownership hypotheses in the approved specification [C1].
It does not treat the hypotheses as conclusions. A responsibility is allocated
only to the extent supported by a D1-pinned source and its recorded authority
bound. Where the freeze cannot establish an allocation, the result is exactly
`unresolved — D3 input`.

The assertion-status vocabulary is:

- `verified_current_at_freeze`: supported by canonical repository
  documentation or a current implementation self-description, within the
  cited source's authority bound;
- `verified_historical_at_freeze`: supported only as committed historical
  implementation or contract evidence;
- `documented_target_not_executed`: a canonical repository plan, not proof of
  execution or cross-repository approval;
- `contextual_hypothesis`: problem or direction context that is not governed
  fact; and
- `unresolved — D3 input`: the evidence freeze does not authorize D2 to settle
  the question.

These statuses never promote a source beyond D1's authority classification.
In particular, current self-description does not approve a future mission,
historical implementation does not establish current ownership, a transition
plan does not prove execution, and contextual issue text does not establish
architecture.

## 2. Verified semantic-job decomposition

The table preserves the exact nine-row order from #31. “D2 allocation” means
the bounded responsibility supported at the frozen revisions; it is not a
successor-architecture choice.

| Row | Semantic job | Hypothesis tested | D2 allocation | Assertion status | Evidence and authority bound | D3 handoff |
|---|---|---|---|---|---|---|
| D2-R01 [C1] | Preserve observations and lineage [C1] | TIBER-Data / domain source repositories [C1] | **Verified with qualification:** TIBER-Data owns canonical contracts, schema semantics, provenance expectations, cross-repository language, and integration governance. Domain repositories remain producers for their own bounded artifacts; Data does not own final player opinions, rankings, or downstream scoring. [D01][D02][R02] | `verified_current_at_freeze` within the cited boundaries. [D01][D02][R02] | Both Data documents are `canonical_repo_documentation`; the Rookies export contract is canonical only for its producer output. None assigns another repository's future role. [D01][D02][R02] | FORGE topology and any canonical synthesized-player-state owner are `unresolved — D3 input`. [D01][D02] |
| D2-R02 [C1] | Interpret team environment [C1] | TIBER-Teamstate [C1] | `unresolved — D3 input`. The pinned Teamstate contract documents team-environment semantics and auditable profiles, but D1 explicitly bars it from establishing a D2 ownership conclusion; Forecast establishes only its own declared consumption boundary. [T01][F01] | `verified_historical_at_freeze` for contract semantics; ownership allocation is `unresolved — D3 input`. [T01][F01] | The Teamstate contract is `historical_implementation_evidence`, not promotion, runtime conformance, human-approved doctrine, or a D2 ownership conclusion. Forecast is not authority over another repository. [T01][F01] | `unresolved — D3 input`. [C1] |
| D2-R03 [C1] | Interpret player role and opportunity [C1] | Role-and-opportunity-model [C1] | `unresolved — D3 input`. The pinned contract documents role/opportunity semantics, evidence, confidence, readiness, and read-only Teamstate attachment, but D1 explicitly bars it from establishing a D2 ownership conclusion; Forecast establishes only its own consumption boundary. [P01][F01] | `verified_historical_at_freeze` for contract semantics; ownership allocation is `unresolved — D3 input`. [P01][F01] | The contract is `historical_implementation_evidence`, contract-first, and not a complete export pipeline, promotion record, human doctrine, or D2 ownership conclusion. V0 is WR/TE-only; RB is future and QB excluded. [P01] | `unresolved — D3 input`. [C1] |
| D2-R04 [C1] | Maintain prospect / transition priors [C1] | TIBER-Rookies [C1] | `unresolved — D3 input`. The current Rookie Alpha producer contract is verified, and the historical transition contract separates pre-draft market proxy from observed post-draft outcome, but neither establishes ownership of the full prospect/transition-prior job or downstream admission. [R01][R02] | `verified_current_at_freeze` for the producer contract and `verified_historical_at_freeze` for transition semantics; ownership allocation is `unresolved — D3 input`. [R01][R02] | The export contract is canonical only for TIBER-Rookies' producer output. The transition contract is `historical_implementation_evidence` and not authoritative for a D2 ownership conclusion. [R01][R02] | `unresolved — D3 input`. [C1] |
| D2-R05 [C1] | Synthesize cross-source player-state representation [C1] | Candidate FORGE successor, consumer-local composition, distributed ownership, or no canonical representation [C1] | `unresolved — D3 input`. Legacy Fantasy combines context with scoring state, standalone FORGE flattens governed inputs for grading, and the transition plan leaves the future data-feed/data-access boundary open. [G01][G02][Y01][Y04] | `unresolved — D3 input`. [G01][G02][Y01][Y04] | The cited sources describe current or historical implementations and a Fantasy-local transition plan; none establishes the future owner, canonical state contract, join rules, persistence boundary, or freshness rules. [G01][G02][Y01][Y04] | `unresolved — D3 input`. [C1] |
| D2-R06 [C1] | Produce outcome forecasts and uncertainty [C1] | TIBER-Forecast [C1] | **TIBER-Forecast**, for fantasy-outcome scoring/projection logic and uncertain forecasts: expected points, ranges, confidence, cutoff-bounded run identity, and model-inference metadata. Forecast outputs are derived signals, not observations or product advice. [F01][F02][F03][D01] | `verified_current_at_freeze` within Forecast's declared boundary. [F01][F02][F03] | The three Forecast sources are `canonical_repo_documentation`; they specify the lane and manifests but do not prove executable conformance or complete upstream wiring. [F01][F02][F03] | How any successor consumes forecasts without laundering inference into source truth is `unresolved — D3 input`. [F03][D01] |
| D2-R07 [C1] | Apply evaluation policy (dynasty / weekly / bestball verdicts) [C1] | Derived projection; owner decided by D3 [C1] | `unresolved — D3 input`. Historical FORGE sources implement mode-specific weights, Alpha, tiers, confidence, explanations, temporal adjustments, and ordering, but no pinned authority adopts those schemes as the future policy or owner. [G01][G02][Y01][Y02][Y03] | `unresolved — D3 input`. [G01][G02][Y01][Y02][Y03] | Current and historical implementation evidence proves that evaluation occurred; it cannot turn weights, recursion, calibration, or tiers into required future ontology. [G01][G02][Y01][Y02][Y03] | `unresolved — D3 input`. [C1] |
| D2-R08 [C1] | Present information to users [C1] | TIBER-Fantasy [C1] | **TIBER-Fantasy**, for product-specific UI integration, response shaping, filtering, comparison, explanation, orchestration, caching, and failure handling. Evaluation/ranking policy is outside this presentation allocation. [D01][D02][Y01][Y04] | `verified_current_at_freeze` for the product boundary; `documented_target_not_executed` for externalization. [D01][D02][Y01][Y04] | Data's architecture baseline identifies Fantasy as the product/application consumer. The Fantasy transition plan is canonical only for its documented plan; it does not prove execution or global approval. Embedded FORGE remains an active legacy dependency. [D02][Y01][Y04] | Product/adapter boundaries under each candidate architecture remain `unresolved — D3 input`. [Y04] |
| D2-R09 [C1] | Assemble agent operating context [C1] | Kernel / Ops (#30 direction; contextual) [C1] | **Verified floor:** TIBER-Ops supplies governed authority, freshness, pinning, and fail-closed control context. Complete agent-context assembly, runtime/interface boundaries, and final ownership are `unresolved — D3 input`. [O01][O30] | `contextual_hypothesis`; final allocation is `unresolved — D3 input`. [O01][O30] | The preflight is authoritative only for its control procedure. #30 is `contextual_only` and remains parked; it cannot establish a Kernel implementation or accepted architecture. [O01][O30] | `unresolved — D3 input`. [C1] |

### 2.1 D2 allocation summary

- Bounded current allocations supported by D1 authority: observations and
  lineage governance to TIBER-Data; outcome forecasts/uncertainty to
  TIBER-Forecast; product presentation to TIBER-Fantasy. [D01][D02][F01][Y04]
- Historically evidenced semantics without an authorized D2 owner allocation:
  team environment, role/opportunity, and rookie transition. Their hypotheses
  remain `unresolved — D3 input`. [T01][P01][R01][R02]
- Reserved for D3: the three historically evidenced ownership hypotheses,
  canonical cross-source synthesis, future evaluation-policy ownership,
  complete agent-context ownership, and all successor topology. [C1][O30]
- No row makes historical deterministic grading the default future ontology.
  [G01][G02][Y01][Y02][Y03]

## 3. Historical FORGE and current architectural need

### 3.1 Historical and current implementation identities

| Evidence-backed identity | Verified distinction | Authority limit |
|---|---|---|
| Embedded Fantasy FORGE [Y01] | At the freeze, `FORGE` means **Football-Oriented Recursive Grading Engine** in the active legacy Fantasy module. It combines weekly statistics, role data, team context, and strength of schedule into Volume, Efficiency, Team Context, and Stability, then emits Alpha/tier results for redraft, dynasty, and bestball. [Y01] | `current_implementation_self_description`; it describes an active legacy module, not the desired successor mission. [Y01] |
| Prior-Alpha blend in `forgeGrading.ts` [Y02] | After mode/position weighting, the grading path applies `0.8 * current + 0.2 * priorAlpha`, then clamps momentum to ±3 before calibration and tiering. [Y02] | `historical_implementation_evidence`; the formula is not a future requirement. [Y02] |
| Stateful two-pass engine in `recursiveAlphaEngine.ts` [Y03] | A separate path computes pass-0 Alpha, then uses prior persisted state to derive expected Alpha, surprise, volatility/momentum adjustment, pass-1 Alpha, and an eight-result history. It is not the same mechanism as the 80/20 blend. [Y03] | `historical_implementation_evidence`; persistence and recursive semantics remain D3 questions. [Y03] |
| Standalone TIBER-FORGE [G01][G03] | The repository currently self-describes as an early, standalone deterministic grading layer and static evidence compiler, downstream of governed source truth and interpreted context. It is explicitly not production-complete or live-ingestion-backed. Its static artifact contains player-specific evidence plus explicitly non-evidence baseline rows. [G01][G03] | README is current self-description, not future mission approval. The artifact's exact bytes do not establish promotion provenance, consumer freshness, or a desired ontology. [G01][G03] |
| Fantasy externalization plan [Y04] | Fantasy documents a staged extraction target in which an external service would own model-side evaluation/rankings while Fantasy retains adapters, orchestration, compatibility responses, UI integration, caching, feature flags, and failure handling. [Y04] | `documented_target_not_executed`; no extraction, parity proof, cutover, or deletion is established. [Y04] |

The historical record therefore contains more than one FORGE identity and more
than one temporal mechanism. D2 preserves those differences. It does not use
the acronym, the embedded module, the standalone repository, or the
externalization plan as an automatic definition of what FORGE must become.

### 3.2 Conflicts that D2 preserves rather than resolves

The D1 pins disagree about the legacy coordinate system:

- Data's feedback-loop doctrine places FORGE after point prediction as an
  adjudication/grading layer. [D01]
- Data's active architecture baseline calls TIBER-FORGE an
  engineering/integration workspace. [D02]
- Standalone FORGE describes Data, Teamstate, and Role-and-opportunity feeding
  deterministic grading, with Fantasy as cockpit and no Forecast input in the
  stated boundary. [G01][G02]
- Forecast describes itself as the outcome projection engine and assigns
  deterministic grading/tiering to TIBER-FORGE. [F01]
- Fantasy's transition plan treats current grading/ranking logic as an
  extraction candidate but does not prove that extraction occurred. [Y04]

Those statements are evidence to compare in D3; they are not smoothed into a
single D2 conclusion.

### 3.3 Current architectural needs, without a successor choice

The pins support the following needs independently of which D3 option wins:

1. **Source truth and derived opinion stay typed and separated.** Provenance,
   uncertainty, support limits, and upstream lineage must survive downstream
   transformations; downstream outputs cannot return as upstream truth without
   a new source-backed, governed artifact. [D01]
2. **Domain interpretations remain separately accountable.** Team environment,
   role/opportunity, and rookie-transition evidence expose provenance,
   readiness, coverage, and explicit missing states rather than fabricating
   continuity. [T01][P01][R01]
3. **Forecasts remain inference with cutoffs and uncertainty.** A run needs
   identity, exact inputs, governance state, uncertainty, and movement evidence;
   forecast output is not observed reality. [F02][F03]
4. **Capability admission remains explicit and gated.** Forecast's committed
   capability path separates source-artifact identity, rehearsal, validation,
   threshold review, binding review, implementation, and activation
   verification; each stage narrows rather than accumulates authority. This is
   historical implementation evidence for an admission pattern, not
   cross-repository doctrine or automatic precedent. [F04][F05]
5. **Product presentation remains distinct from evaluation semantics.** Fantasy
   may shape, filter, compare, explain, cache, and orchestrate outputs without
   silently owning ranking math. [D02][Y04]
6. **Agent reasoning context must be reproducible and governed.** The verified
   control floor is pinning, authority, freshness, and fail-closed behavior.
   #30 adds a provider-neutral Kernel direction only as contextual input; its
   ownership and runtime remain unresolved. [O01][O30]

These are architecture constraints and evaluation inputs, not a declaration
that the successor is a repository, artifact, capability, split, or retirement.

## 4. Explicit D3 input queue

The following questions remain deliberately unresolved:

1. `unresolved — D3 input`: whether a canonical cross-source player-state
   representation exists, and if so who owns its contract, joins, time grain,
   freshness, persistence, and correction semantics. [G02][Y04]
2. `unresolved — D3 input`: whether evaluation policy is combined with
   synthesis, split into declared projections, kept in FORGE, distributed, or
   retired. [G01][Y02][Y03]
3. `unresolved — D3 input`: which topology resolves the contradictory flows in
   the pinned Data, Forecast, FORGE, and Fantasy documents. [D01][D02][F01][G02][Y04]
4. `unresolved — D3 input`: whether any prior FORGE state survives, and under
   which time-indexing, decay, reset, correction, leakage, and non-recursive
   baseline safeguards. [Y02][Y03]
5. `unresolved — D3 input`: how Teamstate, Role-and-opportunity, Rookies, and
   Forecast artifacts are admitted, including readiness and downstream
   adoption gates. [T01][P01][R01][F03][F04][F05]
6. `unresolved — D3 input`: whether Kernel/Ops owns complete agent-context
   assembly and what boundary separates governed kernel, repository context,
   task material, and retrieved evidence. [O01][O30]

D2 does not compare or score candidate architectures against these questions.

## 5. D2 checkpoint result

- Exactly nine semantic jobs are present in the approved order. [C1]
- Every allocation is cited to a D1 pin and bounded by D1's authority record;
  every unestablished allocation is marked `unresolved — D3 input`. [L1]
- Historical acronym, embedded grading, prior-Alpha blending, stateful two-pass
  recursion, standalone grading/compiler identity, and the externalization plan
  are recorded separately. [G01][Y01][Y02][Y03][Y04]
- Current architectural needs are stated without choosing a successor
  architecture or owner for D3-reserved responsibilities. [C1]
- No dependency was added, no source repository or registry was changed, no
  implementation was created, and #15 R2 remains parked. [C2][L1]

Accepted checkpoint state:
`d2_complete_at_1c141b39616972cb67c663d025a78edad0414046`.

The signed D3 frontier decision records D2 complete at that exact commit based
on an independent PASS and activates D3 only. [C3] D2 therefore remains a
frozen input; this document does not reopen or revise its allocations.

## 6. Evidence pin index

Every file pin below was recomputed at D2 start and matched D1. Authority
classes and limits reproduce or conservatively narrow the D1 ledger [L1].

| ID | Frozen source | SHA-256 | D1 authority class and bound |
|---|---|---|---|
| C1 | Approved specification in [TIBER-Ops#31](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31), approved-proposal bytes frozen in D1 | `94c8a035d3363ed925f0a476f9d72568a5cf2f06199b509124f9f6fea4a81e9e` | Governing D1–D6 specification; the issue-local status metadata is outside the hashed boundary. |
| C2 | [D2 frontier decision](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987203347), exact decoded body | `5d2b142aa6ff29dfd230fa555fe5b2893f6097283c50181189d6e3b928f5921c` | Signed human authority to complete D1 and execute D2 only; not §11's future FORGE-direction Decision C. |
| C3 | [D3 frontier decision](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991320938), exact decoded body | `c82688980fb02577f85047ade0ee4e5912db54bc7d6e7d5e6062c3957d5746e2` | Signed human authority accepting D2 at exact commit `1c141b3…` based on independent PASS and activating D3 only; not authority for D4 or a FORGE direction. |
| C4 | [TIBER-Ops#22](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22) live program body, retrieved `2026-07-16T11:51:27Z`; body updated `2026-07-16T11:34:33Z` | `90d9a04c28450ab292e1c6fea3025f3dcdb20eb1a7a9555f154107b98058571e` | Program state synchronized to D3 as the sole frontier, R2 parked, and D4–D6 inactive; not authority for a direction choice. |
| L1 | `Prometheus-Frameworks/TIBER-Ops:program/discoveries/forge-reconception-v0/progress-ledger.md` @ `5161b4c80e01771ff5830ad1c200fc410902a755` | `87b9154d0ab673724290c4c4e9d56aaa7fb736cae7f780e004d738a9791b564f` | D1 execution history, evidence inventory, and authority records at the independently accepted checkpoint. |
| L2 | `Prometheus-Frameworks/TIBER-Ops:docs/architecture/forge-reconception-v0.md` @ `1c141b39616972cb67c663d025a78edad0414046` | `89a69603966c8e26072672b6a0f8fc3d46283df2428f562f8630b64aab97c99f` | Accepted D2 semantic decomposition and bounded D3 input queue; not a D3 conclusion. |
| L3 | `Prometheus-Frameworks/TIBER-Ops:program/discoveries/forge-reconception-v0/progress-ledger.md` @ `1c141b39616972cb67c663d025a78edad0414046` | `3fff8ca9cd2239efae4b1627b9897f5758e50738eca095ed896127c90f2d6fc2` | Accepted D1/D2 execution history through the corrected D2 checkpoint. |
| D01 | `Prometheus-Frameworks/TIBER-Data:docs/repo-boundaries-and-feedback-loops.md` @ `a7c059412806470a9e0b89889cd85f01cf7aace9` | `c1df7ea4d628b2b1b7466e1ab35a0db12871c03770d86b60d8da33ab5c0bd9a9` | `canonical_repo_documentation`; Data's declared boundary and anti-recursion doctrine, not authority to assign another repository's future role. |
| D02 | `Prometheus-Frameworks/TIBER-Data:docs/governance/architecture/tiber-architecture-document-v1.0.md` @ `a7c059412806470a9e0b89889cd85f01cf7aace9` | `76a9ae28e5210123996d683f51beeceb321a97a1d5c6f3b899dbad3db8d83e58` | `canonical_repo_documentation`; active cross-repository architecture baseline, not implementation truth or automatic resolution of conflicting FORGE identities. |
| F01 | `Prometheus-Frameworks/TIBER-Forecast:docs/ownership-boundaries.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `4790a90461b2025000f726df3ba2aac2f31bbe6b6c3fee454b217c706ed85f6b` | `canonical_repo_documentation`; Forecast's declared ownership boundary, not authority over other repositories or a reconception decision. |
| F02 | `Prometheus-Frameworks/TIBER-Forecast:docs/forecast-lane.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `616e4ea6d21c277268386ab6536204893144b584f63f64d17e9651d07b4b0466` | `canonical_repo_documentation`; Forecast vocabulary and operating shape, not executable conformance or future FORGE ownership. |
| F03 | `Prometheus-Frameworks/TIBER-Forecast:docs/run-manifest-spec.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `612600b7adf1620b319f30b489909e9ad1ea06c9ab8c39b5f629d5d041f1c233` | `canonical_repo_documentation`; run manifest, cutoff, uncertainty, and input-governance semantics, not cross-repository doctrine beyond the stated contract. |
| F04 | `Prometheus-Frameworks/TIBER-Forecast:docs/capabilities/README.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `c4993f4642cdeaa68f18a180cf92109ff73cc1e4d4f277210a05fa91ef9163ac` | `historical_implementation_evidence`; committed capability-admission path, not canonical doctrine, production activation, or a future FORGE mission. |
| F05 | `Prometheus-Frameworks/TIBER-Forecast:docs/capabilities/player-history-production-only-v0.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `0908180e3889d852b623039ebb79f4ee590f85b62bfb40581fbdf08cd3c9ef37` | `historical_implementation_evidence`; the committed reference capability's recorded path and gates, not proof of current binding beyond its stated scope or precedent for another capability. |
| F06 | `Prometheus-Frameworks/TIBER-Forecast:docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `5ea42362b2917e333be438b9499ed87d6e9c4b5363222601bfbcdb673c2d6c17` | `historical_implementation_evidence`; record-bound typed-availability design, not human-approved doctrine, populated evidence, implementation, or admission. |
| F07 | `Prometheus-Frameworks/TIBER-Forecast:docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.json` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `7994e61c83d9ad1d5ddc937f42736a47d93175b3e19e80cb4c4169be83302b1c` | `historical_implementation_evidence`; machine-readable mechanics paired with F06, with the same authority limits. |
| F08 | `Prometheus-Frameworks/TIBER-Forecast:docs/run2-tts-feature-contract.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `dae837dfc4c0b38b63ff5d2901c746b9fbfc3215bae2688e99724c30b0e26227` | `canonical_repo_documentation`; Forecast's model-legible Teamstate feature gate, not proof of a production-ready input or a general FORGE architecture. |
| F09 | `Prometheus-Frameworks/TIBER-Forecast:docs/run1-path-audit-for-run2.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `530bbc5d6e134eb9cf1ba4e2cc4437da1c8a9dda4764913e24b389aca904f9db` | `canonical_repo_documentation`; pipeline audit, cutoff invariants, and a proposed attachment seam, not proof that Run 2 is implemented. |
| T01 | `Prometheus-Frameworks/TIBER-Teamstate:docs/contracts/team-environment-profile-v0.md` @ `3ec1d78e10fccf203239c88b905e3cf744d21c48` | `255b7f954b6ebab550ec811a4047dcd87238e541750ae628249f4ef157c9870a` | `historical_implementation_evidence`; committed team-environment contract semantics, not promotion, runtime conformance, human doctrine, or a D2 conclusion. |
| P01 | `Prometheus-Frameworks/Role-and-opportunity-model:docs/contracts/role-opportunity-profile-v0.md` @ `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | `a156ff5e9f7d335a3a45e76dda8765aaa4883b158c62bc4da02eb9cf4d634bdb` | `historical_implementation_evidence`; committed role/opportunity contract semantics, not promotion, runtime conformance, a D2 ownership conclusion, or future architecture. |
| R01 | `Prometheus-Frameworks/TIBER-Rookies:docs/rookie-transition-profile-contract.md` @ `2ef92faf9a9c91a393f53e9140428451529a1c48` | `187fb0c68b8a9d30d7e4db0f130ceb98009af4cffb878394dded540d3d6b285b` | `historical_implementation_evidence`; committed transition-profile semantics, not downstream adoption, promotion authority, or a D2 ownership conclusion. |
| R02 | `Prometheus-Frameworks/TIBER-Rookies:docs/export-contract.md` @ `2ef92faf9a9c91a393f53e9140428451529a1c48` | `9b0cff08e40ac45f5bfc725e67f3b95a2a6200491af29da1af49beb4cb49c164` | `canonical_repo_documentation`; current Rookie Alpha producer output, not canonical cross-repository data authority or downstream adoption. |
| G01 | `Prometheus-Frameworks/TIBER-FORGE:README.md` @ `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | `c12bcd8e099474c09dc3ca51fba70a0c9e1f068dc2b0fb72d89fe5ace568173f` | `current_implementation_self_description`; current grading/compiler identity, not human-approved future mission. |
| G02 | `Prometheus-Frameworks/TIBER-FORGE:docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md` @ `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | `39dd805cc37efb98c15b8eb63f035489b56277412f4e8b2f81a6ccf9cf159a59` | `historical_implementation_evidence`; stated ingestion/grading design, not proof of live ingestion, implementation, or approved doctrine. |
| G03 | `Prometheus-Frameworks/TIBER-FORGE:exports/promoted/forge_player_static/forge_player_static_v1.json` @ `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | `2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041` | `historical_implementation_evidence`; exact artifact bytes and shape, not promotion provenance, architectural intent, or consumer freshness. |
| G04 | `Prometheus-Frameworks/TIBER-FORGE:src/contracts/forge.ts` @ `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | `ceeb45ee9833166d1192b25919b9b3ee24612f38af8a39ecea638656a45689a5` | `historical_implementation_evidence`; exact service contract definitions, not promoted status or desired redesign. |
| G05 | `Prometheus-Frameworks/TIBER-FORGE:src/contracts/football.ts` @ `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | `453693f1bd069326b4266ed3346443bdee729a109face215c8d8a3c7f8adc68d` | `historical_implementation_evidence`; exact football-lane types, not promoted status or future mission. |
| Y01 | `Prometheus-Frameworks/TIBER-Fantasy:server/modules/forge/MODULE.md` @ `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `32cf08fd7bb6b28813ce2f56a8608d62a1700024d1e0b734df926af40c88cc0b` | `current_implementation_self_description`; live legacy role and acronym, not desired end-state or proof of externalization. |
| Y02 | `Prometheus-Frameworks/TIBER-Fantasy:server/modules/forge/forgeGrading.ts` @ `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `15c57e5489eac38ee830205a1c0b9f196675f34f2ce062f75f52892c001c7057` | `historical_implementation_evidence`; exact grading and prior-blend behavior, not approved architecture or cross-repository ownership. |
| Y03 | `Prometheus-Frameworks/TIBER-Fantasy:server/modules/forge/recursiveAlphaEngine.ts` @ `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `1338f2d90ac06d8ae2076a99054deefa2f73ca2a1dfb833a87ecea41afba8c90` | `historical_implementation_evidence`; exact stateful two-pass behavior, not current doctrine or future mission. |
| Y04 | `Prometheus-Frameworks/TIBER-Fantasy:docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md` @ `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `7b9b0362048d2d9dbe42fa801fb3f75236709fc56e8b0186723c0306ae66b3ba` | `canonical_repo_documentation`; Fantasy's documented transition plan, not proof that the transition executed or received global approval. |
| Y05 | `Prometheus-Frameworks/TIBER-Fantasy:server/contracts/rankingsV2.ts` @ `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `af7f56ffdb578254438c52c56dfd482d164d1fa42f415c2b7b00518322729c39` | `historical_implementation_evidence`; exact mode/lens/horizon contract scaffold, not live conformance, promotion, or future grading doctrine. |
| O01 | `Prometheus-Frameworks/TIBER-Ops:docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md` @ `530b4fb4f1270c1247f67180483e115fab39cb1a` | `a75aed0bbc8b4edcb9e71d518cc03478c2b42ea1683d39b47a4be65e089c0206` | Canonical freshness/pinning/authority procedure, not a Kernel implementation or complete agent-context architecture. |
| FC1 | `Prometheus-Frameworks/TIBER-Ops:registry/tiber-current-state.v0.json` @ `530b4fb4f1270c1247f67180483e115fab39cb1a` | `de531ecb36176c8b5c858f6927d18eadfc8efcfe6d325fe449789faf35f8d88e` | Descriptive current-state record; establishes only that Fantasy's pinned FORGE mirror is stale and provenance-unverified, so it must fail closed and cannot prove producer/consumer parity. |
| O30 | `Prometheus-Frameworks/TIBER-Ops#30`, retrieved `2026-07-15T22:41:29Z`; issue updated `2026-07-14T15:10:29Z` | `56fd6826f74d8f87d17e9a7da85ed5b71a34b76011b1417f6813b7be58438264` | `contextual_only`; problem and direction context, not governed fact, accepted architecture, or activation authority. |

## 7. D3 comparison method

D3 starts from the accepted D2 checkpoint [L2][L3] and the unchanged D1
freeze. At resume preflight, all seven source repositories were clean at their
frozen revisions and all 25 file-backed dependency hashes matched. The only
new controls are the signed D3 activation and synchronized program state.
[C3][C4]

The comparison applies two stages:

1. **Non-compensating admissibility gates:** authority honesty; an acyclic,
   cutoff-safe topology; separation of source truth, contextual
   interpretation, classification, forecast, evaluative projection, and
   presentation; provenance/coherence safety; full Forecast admission; and
   migration honesty. One failed gate cannot be offset by strengths elsewhere.
2. **Unweighted Pareto comparison among admissible designs:** ownership and
   contract clarity; duplication/coherence burden; new owners, joins, contracts,
   and adapters; Forecast integration; migration/compatibility risk;
   operational coupling; unverified design hypotheses; and reversibility.

No approved evidence supplies weights for a numeric score. A positive
recommendation therefore requires exactly one admissible option to dominate
the others on every material dimension, or every alternative to fail a
mandatory gate. Otherwise the required terminal is
`forge_reconception_requires_followup`. [C1]

The following statements are common constraints, not hidden preference for an
option:

- Domain owners retain source semantics; Forecast retains outcome inference and
  forecast uncertainty; Fantasy retains presentation/orchestration. Carrying a
  value never transfers ownership. [D01][D02][F01]
- Operational timestamps do not establish public availability. Eligible
  evidence is subject- and record-bound, uses a closed availability kind, and
  fails closed when missing or contradictory. A derived value's availability
  is the maximum of every required evidence, derivation, and cohort dependency.
  [F03][F06][F07]
- `coverage`, source reliability, classification confidence, Forecast
  uncertainty, and evaluative-projection confidence qualify different claims
  and cannot collapse into one generic confidence. [C1][G03][Y01]
- The Fantasy mirror named by FC1 is quarantined; it is neither current truth
  nor parity evidence. [FC1]
- The embedded Fantasy engine remains a live `LEGACY_CORE_TEMP` dependency, and
  standalone FORGE remains bootstrap/demo and non-production-complete. Neither
  supersedes the other. No option below performs deprecation. [G01][Y01][Y04]

Each option is a design hypothesis. “Commitment” describes what the option
would mean if later selected; it is not an adoption claim.

## 8. Four-option comparison

### 8.1 Option A — standalone deterministic grading/tiering repository

This is role continuity, not literal behavioral status quo. Current standalone
FORGE is not production-complete, and Q2, Q6, and Q7 require a material
refounding of its historical behavior. [G01][G02][G03]

#### Q1 — Topology and Forecast relation

**Commitment:** `domain artifacts → Forecast`; then `domain artifacts +
cutoff-bound Forecast outputs → standalone FORGE projection → Fantasy`.
Forecast is an input to FORGE and never consumes a FORGE output. This chooses
Data's Forecast-then-adjudication direction and preserves Forecast's inference
boundary, while rejecting the Forecast-absent standalone ingestion sketch as
future doctrine. [D01][F01][G02]

**Status/gap:** acyclic as designed, but no frozen source proves live
Forecast-to-FORGE integration, promoted joins, or end-to-end conformance.

#### Q2 — Recursion

**Selection: (a), prohibited self-reference.** No prior FORGE grade, tier,
Alpha, artifact, or persisted engine state may influence the current result;
longitudinal features must be rederived from pinned observations. The 80/20
prior blend and separate two-pass persisted engine lack the full approved
safeguards and remain historical only. [D01][Y02][Y03]

Legacy recursive fields may be displayed only as typed legacy output. A
compatibility adapter cannot claim semantic parity with the nonrecursive
successor, and confidence cannot grow merely from repetition.

#### Q3 — Archetype versus role

**Testable boundary:** a label that changes when only current team,
depth-chart, or bounded usage-window facts change is a Role-and-opportunity
interpretation; Option A emits no synthesis-layer archetype at all. It emits
only declared-question evaluations. [P01]

This preserves a clean boundary but provides no shared descriptive archetype;
that absence is an explicit A consequence, not an omission.

#### Q4 — Coherence cost and FC1

A creates no canonical cross-source profile. Its artifact contains derived
evaluation, declared question/policy/version, typed confidence, and exact
upstream artifact/run references. Any copied input value must be minimal,
immutable, snapshot-bound, reproducible, provenance-preserving, and marked
`non_authoritative_copy`; mutable “latest” mirrors fail closed. [O01][FC1]

This limits canonical duplication, but every evaluation still owns its joins
and conflict handling. Existing static artifacts do not prove promotion
provenance, consumer freshness, or this coherence contract. [G03]

#### Q5 — Forecast admission

A sends no FORGE output into Forecast, so no FORGE admission is instantiated.
Forecast admits domain-owned inputs and retains ownership of its adapter only.
If A were later amended to enter Forecast, the required path would be:
`owned promoted source → identity-verified mirror/rehearsal → validation →
threshold review → binding review → inert implementation → activation
verification → distinct human sign-off`. Ownership would not transfer.
[C1][F04][F05]

#### Q6 — Verdict and confidence semantics

Grades, tiers, and rankings survive only as FORGE-owned evaluative projections
bound to a declared question, population, scoring assumptions, horizon,
cutoff, policy version, and derivation. Unqualified `forge_alpha` is retired.
[G04][G05]

Evidence coverage remains with the artifact producer; source reliability with
the domain owner; classification confidence with the classifier/Role owner;
Forecast uncertainty with Forecast; and evaluative-projection confidence with
FORGE. Existing generic confidence fields do not satisfy that taxonomy.

#### Q7 — Cutoff and typed availability

Every input binds exact subject, source record, repo/path/version/hash,
`availability_time_kind`, validator-derived `available_at`, and the evaluation
cutoff. Eligibility is strictly before cutoff; unknown, contradictory, or bare
date evidence fails closed. `generated_at`, ingestion, retrieval, refresh,
verification, file, and Git times are prohibited substitutes. [F03][F06][F07]

Current `asOf`/`sourceUpdatedAt` fields do not prove compliance, so A is not
production-ready under this rule. [G02][G04][G05]

#### Q8 — Migration and implementation disposition

Embedded Fantasy FORGE stays live as `LEGACY_CORE_TEMP`, frozen against new
engine scope and available for compatibility/rollback. It can be superseded
only after an authorized A contract, adapters, route-by-route dual run, consumer
inventory and migration, acceptance criteria, rollback proof, and cutover.
Standalone FORGE is a possible host, not an already promoted successor; its
bootstrap/static state remains comparison and reproducibility evidence.
[G01][Y01][Y04]

FC1 cannot prove parity. Recursive parity is explicitly unavailable. No
calendar retirement date or deprecation is claimed; unknown consumers and
thresholds remain unresolved.

**A assessment:** a simple acyclic evaluation boundary and low profile-copy
burden, offset by substantial redesign hidden by the word “status quo,” absent
Forecast integration evidence, consumer uncertainty, and no shared synthesis.
A is coherent as a target hypothesis, not as an existing solution.

### 8.2 Option B — unified synthesis/evaluation capability

One owner and contract family would contain typed descriptive and evaluative
stages. “Unified” cannot mean one cyclic record or one undifferentiated Alpha.

#### Q1 — Topology and Forecast relation

**Commitment:** domain artifacts produce immutable `profile_core P(cutoff)`;
Forecast consumes an admitted subset of P and emits run F; the unified
capability then consumes the unchanged P plus optional F to emit evaluations E;
Fantasy presents P/E. Forecast is both consumer and input, but at different
typed stages and run identities. Evaluation never feeds P or Forecast.
[D01][F01][G02]

The expanded DAG is acyclic. No frozen source establishes this staged unified
contract, its owner, or same-run orchestration.

#### Q2 — Recursion

**Selection: (a), prohibited self-reference.** Neither prior P nor prior E may
influence a new P/E merely because it is versioned. Temporal features are
recomputed from pinned source snapshots; prior results may appear only in
reporting/diff surfaces. [D01][Y02][Y03]

Legacy recursive fields may be separately typed for compatibility but never
enter `profile_core`, Forecast, evaluation, or confidence. Semantic parity with
the recursive engine is not promised.

#### Q3 — Archetype versus role

**Testable boundary:** role states deployment/opportunity in a declared
team/time window; a B archetype is a versioned cross-source classification that
requires at least two independently owned domain blocks and must not change
when only team, depth-chart, or bounded usage facts change. If it can be
computed from Role fields alone, it is role interpretation, not archetype.
[P01][R01]

No frozen source supplies the archetype ontology, classifier, thresholds, or
owner; this is a proposed contract test.

#### Q4 — Coherence cost and FC1

`profile_core` owns reconciliation and descriptive synthesis, not copied source
truth. It preferentially stores derived fields plus exact source references.
Any necessary copied field carries original owner, subject, artifact/version/
hash, cutoff/availability, correction lineage, reproducibility rule, and
`non_authoritative_copy`. Research snapshots are immutable and content
addressed; mutable shadows are forbidden. [D02][O01][FC1]

B centralizes joins/explanations but has the highest release coupling and
stale-copy risk. No evidence establishes its join grain, correction rules, or
minimal materialization boundary.

#### Q5 — Forecast admission

Only an allowlisted, promoted `profile_core` subset may enter Forecast:
`owned promoted profile → identity-verified mirror/rehearsal → validation →
threshold review → binding/leakage review → inert-by-default implementation →
independent activation verification → distinct human sign-off`. Forecast owns
the adapter and binding decision, never the profile; E, grades, tiers, ranks,
and evaluative confidence are ineligible. [C1][F04][F05]

No B profile or admission evidence exists at the freeze.

#### Q6 — Verdict and confidence semantics

The contract has hard namespaces: `profile_core` for descriptive synthesis;
`forecast_refs` for Forecast-owned inference; and `evaluations[]` for
question-bound grades, tiers, and ranks. Every evaluation names question,
assumptions, horizon, cutoff, owner, ruleset, and input hashes. There is no
contract-global Alpha or confidence. [F01][Y05]

Profile owner records evidence coverage; originating domains retain source
reliability; classifier owner records classification confidence; Forecast
retains forecast uncertainty; evaluation owner records projection confidence.
One contract does not collapse or transfer those claims.

#### Q7 — Cutoff and typed availability

P freezes only subject-bound records with closed typed availability strictly
before its cutoff. A derived field's `available_at` is the maximum of all
required source, derivation, and cohort dependencies. F pins the exact P hash
and cutoff; E pins the exact P/F pair and may add no later evidence. Build,
generation, event, retrieval, availability, and evaluation times stay distinct.
[F03][F06][F07]

Current inputs do not collectively demonstrate this coverage; B is a target
contract, not a populatable production artifact.

#### Q8 — Migration and implementation disposition

Embedded FORGE stays live as `LEGACY_CORE_TEMP` through a separately authorized
unified contract, Forecast admission, adapters, dual-read/dual-run evidence,
consumer migration, acceptance gates, rollback, and cutover. Standalone FORGE
remains bootstrap/historical evidence and perhaps a future host only after a
separate repository decision; its static artifact cannot be relabeled P.
[G01][G03][Y01][Y04]

Fantasy's monolithic external-scoring plan does not cover B's added synthesis
responsibility. Neither implementation is deprecated or declared superseded.

**B assessment:** it reconciles the three historical arrow directions and
centralizes traceability, but bears the highest semantic-conflation,
coordination, and mirror burden. Its safe internal staging resembles C while
retaining tighter ownership/release coupling. It remains logically admissible,
but evidentially weak and unimplemented.

### 8.3 Option C — canonical profile plus separate projections

C separates descriptive synthesis from prediction, evaluation, and product
presentation. A profile is justified only if it performs reusable synthesis,
not if it merely renames a mirror or pointer bundle.

#### Q1 — Topology and Forecast relation

**Commitment:** `Data + Teamstate + Role/opportunity + Rookies → canonical
profile → Forecast adapter / research snapshot / Fantasy`; separately,
`profile + optional typed Forecast run → question-bound projection → Fantasy`.
Relative to the profile, Forecast is a consumer only. Forecast may be input to
a separate projection but never to the profile or domain truth. [D01][F01][G02]

This resolves the contradiction by splitting the overloaded FORGE coordinate:
domains feed profile, profile feeds Forecast, and Forecast may feed evaluation.
The topology is proposed, not established.

#### Q2 — Recursion

**Selection: (a), prohibited self-reference.** No prior Alpha, tier, rank,
profile, projection, or recursive state enters the profile, Forecast adapter,
or a new projection. Prior outputs may be reported but cannot change result or
confidence. [D01][Y02][Y03]

A typed `legacy_forge_projection` compatibility surface may quarantine old
behavior while the live engine remains, but cannot blend it into C or claim
semantic parity.

#### Q3 — Archetype versus role

**Testable boundary:** an archetype is a descriptive cross-source trait pattern
that remains unchanged when only the player's team, depth-chart placement, or
bounded usage window changes; a role interpretation is the team-and-time-bound
deployment/opportunity label that changes with those facts. [P01][R01]

The role side is evidenced historically. The archetype classifier, vocabulary,
thresholds, and owner are not; they remain C design hypotheses.

#### Q4 — Coherence cost and FC1

The profile must add cross-source identity/time reconciliation, explicit
missingness/conflict handling, or reproducible descriptive classification. It
stores synthesis outputs, source references/hashes, and only values necessary
to reproduce the output or make a declared snapshot self-contained. Every copy
retains owner, subject, cutoff/availability, lineage, correction rule, and
`non_authoritative_copy`. Builds are immutable/content-addressed and fail
closed on mismatch. [O01][FC1]

One governed join can prevent consumer divergence. The material defeater is
unproven value: if C stores too little it is an empty pointer wrapper; too much
recreates FC1. Inputs also span team-, player-week-, player-season-, rookie-,
and run-level grains. No freeze evidence proves two consumers need the same
neutral synthesis.

#### Q5 — Forecast admission

The profile owner retains the artifact; Forecast owns only its allowlisted
adapter and admission decision. Required path: `owned promoted profile →
identity-verified mirror/rehearsal → real/baseline/shuffled validation across
disjoint origins → threshold review → binding/leakage review → inert-by-default
implementation → independent activation verification → distinct human
sign-off`. Partial-field admission does not admit the whole profile.
[C1][F04][F05][F08][F09]

No profile, adapter, validation, review, or sign-off exists in the freeze.

#### Q6 — Verdict and confidence semantics

The canonical profile contains no grades, tiers, ranks, `forge_alpha`, or
Forecast inference. Those survive only as separately governed projections that
name question/horizon, league/scoring/policy assumptions, owner, ruleset,
cutoff, and input profile/Forecast hashes. Forecast does not acquire dynasty or
best-ball policy; Fantasy does not create it by sorting. [F01][Y05]

Profile owner records evidence coverage; source owners retain reliability;
classifier owner records classification confidence; Forecast retains forecast
uncertainty; projection owner records evaluative confidence. Owners and
derivations for the new classifier/projections remain unresolved.

#### Q7 — Cutoff and typed availability

Each profile field binds exact subject and record, repo/path/version/hash,
closed `availability_time_kind`, validator-derived `available_at`, profile
cutoff, and derivation lineage. A synthesized field uses the maximum availability
of every required source/derivation/cohort dependency. Strictly-before-cutoff
eligibility and fail-closed ambiguity apply. Forecast pins the profile in its
run manifest; projections pin both profile and Forecast run. [F03][F06][F07]

F06/F07 are design-only and current domain artifacts do not collectively prove
populatable typed availability. C is not implementation-ready.

#### Q8 — Migration and implementation disposition

Embedded Fantasy FORGE remains live as `LEGACY_CORE_TEMP` and a compatibility/
rollback baseline. Its composition responsibility would move to the profile;
grading/tiering to declared projections; envelopes to Fantasy adapters. It
stays until route-by-route dual-run acceptance, cache/consumer migration,
rollback retirement, and separate cutover authority. Standalone FORGE remains
a bootstrap/static reproducibility fixture until promoted profile/projection
contracts and a separate repository-disposition decision exist. [G01][Y01][Y04]

FC1 is never migration truth. Exact host, consumer graph, thresholds, and
calendar duration remain unresolved; no deprecation occurs.

**C assessment:** the clearest semantic separation and a plausible single
coherence point, offset by no established owner, contract, join grain,
archetype, correction policy, typed inputs, or proof that reusable neutral
synthesis beats consumer-local composition. C is a conditional target, not an
evidence-established winner.

### 8.4 Option D — retire/distribute with no canonical representation

D retires the overloaded FORGE coordinate. It does not remove the need to
replace live integration or govern question-specific evaluations.

#### Q1 — Topology and Forecast relation

**Commitment:** domain artifacts flow directly to Forecast adapters and to
immutable research/inference snapshots; domain artifacts and optional declared
projections flow to Fantasy. There is no FORGE successor node or canonical
cross-source profile. Forecast output flows only to evaluation, audit, or
presentation and never back to source truth or a later Forecast input.
[D01][D02][F01]

D dissolves the conflicting historical arrows instead of choosing one. It is
acyclic, but direct consumer composition is not currently proven complete.

#### Q2 — Recursion

**Selection: (a), prohibited self-reference.** No domain adapter, Forecast
feature, research snapshot, or new projection consumes legacy FORGE output.
Prior results may be reported/audited but cannot score the next run. A typed
compatibility result may coexist while the embedded engine remains, without
entering D's architecture. [D01][Y02][Y03]

Thus D quarantines rather than legitimizes recursion and does not claim legacy
semantic parity.

#### Q3 — Archetype versus role

**Testable boundary:** D has no canonical cross-source archetype. Any
consumer-local archetype must remain unchanged when only team, depth-chart, or
bounded usage facts change; a label that changes is Role-and-opportunity
interpretation. A consumer may emit no archetype at all. [P01]

Any local classifier must name its owner/version and cannot masquerade as
shared player state.

#### Q4 — Coherence cost and FC1

D creates no canonical synthesized copy. A consumer composes ephemerally for a
single run or emits an immutable content-addressed, consumer-specific snapshot
with minimal non-authoritative copies and exact owner/source/hash/cutoff/
availability/correction lineage. Every mirror verifies producer identity and
currency or fails closed. [O01][FC1]

This avoids an unproven ontology but multiplies identity/time joins, conflict
rules, correction logic, admissions, schema drift, and explanations. Local
compositions can become hidden inconsistent FORGEs; FC1 is reduced, not
automatically solved.

#### Q5 — Forecast admission

Forecast independently admits TIBER-Data identity/lineage/outcome contracts,
Teamstate environment artifacts, Role-and-opportunity profiles, and the
question-appropriate Rookies transition/prior artifacts. Each source traverses
the full path: `owned promoted source → identity-verified mirror/rehearsal →
validation → threshold review → binding/leakage review → inert implementation
→ activation verification → distinct human sign-off`. Forecast owns adapters,
not sources; one source's PASS admits no other. [C1][F01][F04][F05]

T01/P01 do not prove promoted runtime inputs, and R02 proves only its narrow
producer contract. The direct graph is not currently admission-ready.

#### Q6 — Verdict and confidence semantics

D retires universal `forge_alpha`, tiers, and rankings. A surviving verdict
must be a separately governed consumer/question-specific projection with named
question, assumptions, horizon, cutoff, version, derivation, and owner; absent
that owner/contract, the surface retires. Forecast ordering stays forecast
inference, and Fantasy presentation cannot silently become policy. [F01][Y05]

Domain owners retain coverage/reliability; any local classifier owns
classification confidence; Forecast owns forecast uncertainty; each declared
projection owns evaluative confidence. Current projection owners and consumer
tolerance for retirement remain unresolved.

#### Q7 — Cutoff and typed availability

Every domain field independently carries record/subject-bound typed
availability and is checked against the consumer run cutoff. A local derived
field uses the maximum availability of all source, derivation, and cohort
dependencies; Forecast's manifest and research snapshots pin the complete
source set. Operational timestamps and ambiguity fail closed. [F03][F06][F07]

D has no shared layer to repair missing semantics, so every owner/consumer must
implement compatible rules. Current artifacts do not collectively prove that
coverage.

#### Q8 — Migration and implementation disposition

Embedded Fantasy FORGE remains `LEGACY_CORE_TEMP` and the compatibility/
rollback path. Composition is replaced route by route with direct domain
adapters; each grade/tier/rank is replaced by an owned projection or explicitly
retired. The engine remains until all known/off-repo consumers, caches,
contracts, dual-run criteria, rollback, and separate cutover authority are
resolved. Standalone FORGE is not D's successor; it remains historical/demo
evidence until a separately authorized archive/reshape/delete decision.
[G01][Y01][Y04]

Unknown consumers, exact route replacements, projection owners, and retirement
timing remain indeterminate. No deprecation occurs.

**D assessment:** the honest null hypothesis avoids a new canonical ontology
and central mirror, but multiplies composition/admission burden and risks
divergent hidden FORGEs. Evidence proves neither that distributed composition
is cheaper nor that a shared profile is necessary. D remains viable.

## 9. D3 result

All four options contain a coherent design-hypothesis variant that answers all
eight mandatory questions. Literal current-state A fails, but the approved
option can be refounded while preserving its standalone evaluation role; that
redesign must not be mislabeled as unchanged status quo. B, C, and D likewise
require unbuilt contracts and future owners.

| Option | Principal advantage | Material defeater / unknown | D3 disposition |
|---|---|---|---|
| A | Simple standalone evaluation boundary; no canonical profile | Material refoundation, absent Forecast integration/admission evidence, no shared synthesis | Admissible target hypothesis; not dominant |
| B | One accountable staged contract reconciles all historical arrows | Highest conflation, mirror, coupling, and coordination burden; no owner/profile evidence | Admissible target hypothesis; not dominant |
| C | Cleanest separation of description, prediction, evaluation, and presentation | Reusable profile value, owner, joins, grains, correction rules, archetype, and cutoff coverage unproved | Admissible conditional target; not dominant |
| D | Avoids inventing an unproved canonical ontology | Duplicates joins/adapters/admission and may create hidden divergent FORGEs | Admissible null hypothesis; not dominated |

The frozen evidence eliminates unsafe variants—cycles, recursive carry-forward,
generic Alpha/confidence, untyped availability, stale mirrors, and fabricated
migration—but does not eliminate all but one option. Most importantly, it does
not settle C's shared-profile value against D's distributed-composition cost.
No approved weighting policy resolves semantic separation, duplication,
governance overhead, migration risk, feature continuity, and reversibility.

**D3 terminal result:** `forge_reconception_requires_followup`.

This result makes **zero recommendations** and does not express a fallback
preference. It is not `forge_reconception_blocked`: the comparison is complete
and the sources were available. Additional evidence is needed before a positive
direction can be selected:

1. a consumer-demand inventory for Forecast, Fantasy, and research that
   identifies genuinely shared neutral synthesis versus question-specific
   composition;
2. a bounded profile-viability contract sketch naming candidate owner, exact
   identity/time grains, joins, conflict/correction behavior, minimal
   materialization, and the test that prevents both empty-wrapper and FC1-mirror
   failure;
3. a distributed-composition map and cost/risk comparison for the same consumer
   paths, including repeated admissions and schema drift;
4. a typed-availability coverage assessment for the proposed domain inputs,
   without substituting operational timestamps;
5. an inventory of every grade/tier/ranking consumer and a decision on which
   question-specific projections must survive and who could own them; and
6. complete embedded/standalone consumer, compatibility, parity, rollback, and
   repository-disposition requirements.

That package is separately scoped future discovery and is not executed or
activated by this checkpoint. A human-approved weighting/priority statement
would also be required if the evidence leaves a Pareto tradeoff rather than one
strictly dominant option.

## 10. D3 candidate checkpoint

- Four and only four approved options are compared.
- Each option answers Q1–Q8, declares Forecast's typed position, chooses exactly
  one recursion classification, gives a counterfactual archetype/role boundary,
  addresses FC1, preserves the full Forecast admission sequence, separates five
  confidence claims, uses record-bound typed availability, and dispositions
  both existing implementations without deprecation. [C1]
- Every future owner, contract, adapter, projection, migration, and repository
  disposition remains a hypothesis or later decision.
- No dependency, source repository, registry, #15/#20 state, implementation,
  prototype, PR, merge, or deprecation was created.
- #15 R2 remains `r2_parked_pending_forge_reconception`; D4–D6 remain inactive.

Candidate checkpoint state:
`d3_comparison_complete_forge_reconception_requires_followup_pending_independent_verification`.

This executing-agent checkpoint is not self-approval. Fresh-context independent
verification is required before D3 can be accepted. A PASS would validate this
comparison only; it would not select a FORGE direction or activate D4.
