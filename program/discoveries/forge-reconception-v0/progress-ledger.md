# Progress ledger — forge-reconception-v0

This is the append-oriented external memory for the discovery governed by
`Prometheus-Frameworks/TIBER-Ops#31` and authorized by
`Prometheus-Frameworks/TIBER-Ops#22`. A fresh human or agent should be able to
resume from this file and the cited controls without private conversation
history.

## Lifecycle

- **Pre-merge review:** corrections may be made in place while this branch is
  unmerged, but every correction must be added to Entry 0.
- **Post-merge execution:** prior entries are immutable. Corrections are new
  append-only entries naming what they supersede.
- Only TIBER-Ops may be written. All other repositories are read-only evidence
  sources.
- This ledger records discovery, classification, and decisions. It does not
  authorize implementation, registry edits, source-repository changes, or
  activation of D2-D6.

---

## Entry 0 — Pre-merge review-correction log

Initial authoring had no review corrections. The first independent audit was
recorded at
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986180583`.
Its correctable FAIL findings were resolved as follows:

| Correction | Resolution | Source |
|---|---|---|
| The required #15 ledger lifecycle/no-rewrite control was absent | Added the #15 progress ledger to Entry 3 with its frozen commit, full SHA-256, last-change commit, and authority bound | Independent audit finding 1 |
| Two Forecast capability documents and four contract/artifact rows used unsupported authority bases | Downgraded all six to `historical_implementation_evidence`; narrowed both authority-bound columns and cited the frozen source commits rather than treating the descriptive registry or path naming as promotion | Independent audit finding 2 |
| Directly relevant Teamstate, Role-and-opportunity, and Rookies contracts were absent | Added all three to Entry 4.5 with full hashes and conservative authority records | Independent audit finding 3 |
| Control comments used bare or incorrectly located identifiers | Replaced them with permanent repo/issue comment URLs in Entries 1 and 3; Decision A is correctly located on #22 | Independent audit finding 4 |
| The first correction checkpoint omitted Forecast's root-README-linked Run 1 path audit | Added `docs/run1-path-audit-for-run2.md` to Entry 4.1 with its frozen pin and bounded canonical-documentation authority record | Second independent audit: `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986401086` |
| The second correction checkpoint omitted TIBER-Data's canonical architecture baseline and TIBER-Rookies' authoritative producer export contract | Added both with frozen pins and bounded canonical-documentation authority records; preserved the Data architecture document's conflicting FORGE identity as evidence to reconcile rather than silently selecting it | Third independent audit: `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986483766` |
| The first D2 checkpoint promoted three historical contract records into ownership allocations, omitted P01's explicit D2-conclusion exclusion, and duplicated an uncited decomposition table | Downgraded D2-R02, D2-R03, and the full D2-R04 job allocation to `unresolved — D3 input`; restored P01's authority bound; removed the duplicate ledger table and made the deliverable's fully cited §2 table the sole decomposition table | Fresh-context audit: `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987499236` |
| The first corrected D2 checkpoint left the superseded candidate-state string in the deliverable while the ledger recorded the correction state | Synchronized the deliverable and current ledger checkpoint to `d2_second_audit_state_sync_complete_pending_new_independent_verification`; retained both failed checkpoints as superseded audit history | Fresh-context re-audit: `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987578172` |
| The first D3 checkpoint did not explicitly identify Option C as the operator's prior, and each Q6 named confidence owners without fully stating every qualified claim and derivation | Disclosed C as a non-evidentiary, non-weighting prior that the comparison may defeat; expanded A–D Q6 so coverage, source reliability, classification confidence, Forecast uncertainty, and evaluative confidence each name qualified claim, owner, and derivation | Fresh-context audit: `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991694618` |

No registry or source repository was changed, and no later frontier was
activated by these corrections.

---

## Entry 1 — Activation and authority

- **Discovery issue:** `Prometheus-Frameworks/TIBER-Ops#31`
- **Program authority:** `Prometheus-Frameworks/TIBER-Ops#22`
- **Decision A:**
  `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4979981162`
- **Decision B:**
  `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4985875797`
- **Decision-B execution agent:** ChatGPT Work
- **Implementation collaborator:** Claude may be used only after a later step
  explicitly authorizes implementation. No implementation was authorized or
  performed in D1.
- **Activated step:** D1 only
- **Inactive steps:** D2-D6
- **R2 state:** `r2_parked_pending_forge_reconception`
- **Branch:** `work/tiber-ops-31-d1-inventory`
- **Base commit:** `530b4fb4f1270c1247f67180483e115fab39cb1a`
- **Activation state at D1 start:** `active_step0_pending`

The specification approved by Decision A is the proposal embedded in issue
#31. Its approved proposal SHA-256 is
`94c8a035d3363ed925f0a476f9d72568a5cf2f06199b509124f9f6fea4a81e9e`.
The complete issue body was retrieved at `2026-07-15T22:40:05Z`; its exact
decoded-body SHA-256 was
`0f806fd117ce75ce95c4a1a4b0608cebfd6fa8fd092b8d418cf2e8bdae2876c6`.

---

## Entry 2 — D1 Step 0: freshness preflight and evidence freeze

At `2026-07-15T22:45:44Z`, every repository was fetched from `origin`, the
local `main` HEAD was compared with the freshly updated `origin/main`, and the
worktree was checked for local drift.

| Repository | Frozen HEAD | Local = origin | Worktree |
|---|---|---:|---|
| TIBER-Ops | `530b4fb4f1270c1247f67180483e115fab39cb1a` | yes | clean |
| TIBER-Data | `a7c059412806470a9e0b89889cd85f01cf7aace9` | yes | clean |
| TIBER-Forecast | `49208472539bd11789b88ca8b3eb20c56a7d0db5` | yes | clean |
| TIBER-Teamstate | `3ec1d78e10fccf203239c88b905e3cf744d21c48` | yes | clean |
| Role-and-opportunity-model | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | yes | clean |
| TIBER-FORGE | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | yes | clean |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | yes | clean |
| TIBER-Rookies | `2ef92faf9a9c91a393f53e9140428451529a1c48` | yes | clean |

Compared with `registry/tiber-current-state.v0.json`, five source repositories
were unchanged. The expected advances were:

- TIBER-Ops `c702dd9...` -> `530b4fb...`: the #21 preflight and registry,
  #15 control artifacts, and related lane-index/governance changes.
- TIBER-Data `d9a5bea...` -> `a7c0594...`: formation-summary candidate,
  audit, schema, scripts, and tests only; no registered dependency or D1
  architectural source path changed.
- TIBER-Forecast `478489b...` -> `4920847...`: PR #164 v2 availability
  design documents, which are required D1 inputs.

All 28 flattened governed dependency/companion hashes and all six file-backed
policy hashes in the current registry were recomputed against the frozen
trees and matched. The two policy-absence records for TIBER-Forecast and
Role-and-opportunity-model were re-confirmed by repository-wide search. The
registry's confirmed supersessions remained unchanged.

The two inherited fail-closed observations also remained unchanged:

- **FC1:** TIBER-Fantasy's stale FORGE static mirror remains provenance-
  unverified and nonblocking for D1.
- **FC2:** TIBER-Ops#13 and TIBER-Data#212 remain issue-only context and are
  not promoted to governed fact.

**Step 0 result:** complete; evidence frozen at the commits above. Any future
resume must fetch and repeat this comparison before relying on the snapshot.

### Correction recheck

At `2026-07-15T23:38:25Z`, all eight repositories were re-fetched. Each
source repository's `origin/main` still exactly matched the frozen HEAD above;
TIBER-Ops `origin/main` remained the frozen base while the ledger branch was
the sole write location. The newly added #15 control and three architectural
files were independently hashed and matched the pins recorded below. This
recheck did not change the frozen source revisions.

At `2026-07-15T23:53:11Z`, the same eight-repository fetch comparison was
repeated after the second audit. All source revisions still matched the
original freeze. The newly added Forecast Run 1 path audit hash matched its
frozen source, so the original evidence freeze remains valid.

At `2026-07-16T00:05:34Z`, the eight remotes were fetched again after the
third audit. Every `origin/main` still matched the original freeze. The newly
added Data architecture and Rookies export-contract hashes matched their
frozen sources.

---

## Entry 3 — Control-authority inventory

For mutable issue/comment controls, the retrieval timestamp and exact decoded
body SHA-256 preserve what was read. A URL or issue number alone is not treated
as a stable pin.

| Control | Pin / retrieval | SHA-256 | Authority and use |
|---|---|---|---|
| #31 approved specification | retrieved `2026-07-15T22:40:05Z`; body updated `2026-07-15T22:26:40Z` | approved proposal `94c8a035d3363ed925f0a476f9d72568a5cf2f06199b509124f9f6fea4a81e9e`; full body `0f806fd117ce75ce95c4a1a4b0608cebfd6fa8fd092b8d418cf2e8bdae2876c6` | Governing D1-D6 specification; D1 active only |
| #22 Decision A | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4979981162`; created/updated `2026-07-15T11:24:19Z` | `efc76534163d02efcbabff7e0b3273f7f75ff93f414174ebf65e969a78b667ee` | Human approval of the specification, without D1 activation |
| #31 Decision B | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4985875797`; created/updated `2026-07-15T22:26:40Z` | `b73e3cbd58417e2addab2bd016012709dee260684a5dcc5fd3dfa2a727b69f86` | Human activation of D1 under the approved specification |
| #31 verification record | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4985475981`; created/updated `2026-07-15T21:33:39Z` | `1faf81b42fabb4ceb73e50c653f1d28eabcd3021af859cb06e1722cc6891925a` | Verification of Decision A and proposal hash; explicitly did not activate D1 |
| #22 program body | retrieved `2026-07-15T22:40:05Z`; body updated `2026-07-15T22:27:52Z` | `6ff0ddbd88efe078066b4e019a71a199adaff701db83996ab54968b556e2904e` | Program frontier and lane state: #31 D1 active, R2 parked, D2-D6 inactive |
| #15 R2 parking decision | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4973558381`; created/updated `2026-07-14T20:13:40Z` | `d5c6a529ec9bfa0c85660eb8cb27bd24fe75a5fd6785d63ea37f30e2f769889a` | Human-directed authority for the continuing R2 parking state; the comment explicitly identifies its agent authorship and operator direction |
| Freshness/current-state preflight | TIBER-Ops `docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md` at `530b4fb...`; last source change `5953357...` | `a75aed0bbc8b4edcb9e71d518cc03478c2b42ea1683d39b47a4be65e089c0206` | Canonical Step-0 procedure and known-drift interpretation |
| Current-state registry | TIBER-Ops `registry/tiber-current-state.v0.json` at `530b4fb...`; last source change `73530e3...` | `de531ecb36176c8b5c858f6927d18eadfc8efcfe6d325fe449789faf35f8d88e` | Descriptive dependency, policy, supersession, and fail-closed pins; not itself promotion authority |
| #15 goal contract | `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml`; last source change `42bc75e...` | `97a4742fc1c1dc5e9c5c50df295fdddf64188cb8fda5ade7a6370a5ca3b4300e` | Existing bounded-goal controls and R2 state; not authority to activate R2 |
| #15 progress-ledger lifecycle control | TIBER-Ops `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/progress-ledger.md` at `530b4fb4f1270c1247f67180483e115fab39cb1a`; last source change `42bc75e8ed84e0eb2acfa74d164f06a377c21381` | `974b6990c387de4bec813f6a061678afc80f3a24a0e600dce7b982f7824c1bf6` | Required two-phase lifecycle, pre-merge correction-log, and post-merge no-rewrite rule inherited by this ledger |
| Merge checklist | `runbooks/merge-checklist.md`; last source change `59933bb...` | `069630473cbf56200dd9870a468038181985ce0d30467b17b83a1d07e9a6d9c3` | Repository merge policy |
| First independent D1 audit | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986180583`; created/updated `2026-07-15T23:15:15Z` | `d65510b0d21637dc1bf5de1919aa2195c336757a82c0d2f19c0d6513edb4abd3` | Fresh-context technical correction requirements; not human approval and not D2 activation |
| Second independent D1 audit | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986401086`; created/updated `2026-07-15T23:51:51Z` | `362f9b6c3f72a1b7151a2ab11dd3dc0e7fba26cf029cae07cfed4e47f0de83ec` | Fresh-context omission finding for the root-linked Run 1 path audit; not human approval and not D2 activation |
| Third independent D1 audit | `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986483766`; created/updated `2026-07-16T00:03:39Z` | `c930016430db8e0d3a82238e26f95d35726a5fcfc0a460245d0c661f1c632e48` | Fresh-context omission findings for the canonical Data architecture baseline and Rookies producer contract; not human approval and not D2 activation |

---

## Entry 4 — Architectural-evidence inventory and authority records

Each dependency has exactly one `primary_authority_basis` from the controlled
vocabulary required by #31. `none_found` means no explicit supersession marker
was found in the frozen source, not that future evidence cannot supersede it.

### 4.1 TIBER-Forecast

| Dependency and pin | Primary authority basis | Authority ref | Authoritative for | Not authoritative for | Supersession status |
|---|---|---|---|---|---|
| `docs/capabilities/README.md` @ `4920847...`; SHA-256 `c4993f4642cdeaa68f18a180cf92109ff73cc1e4d4f277210a05fa91ef9163ac` | `historical_implementation_evidence` | frozen source commit `00336f31859bb0b40457abbbe6e6f30570cd9998`; PR #148 lacks provenance-explicit human approval | What the committed capability-directory index claims at the frozen revision | Canonical repository doctrine, production activation, or a future FORGE mission | `none_found` |
| `docs/capabilities/player-history-production-only-v0.md` @ `4920847...`; SHA-256 `0908180e3889d852b623039ebb79f4ee590f85b62bfb40581fbdf08cd3c9ef37` | `historical_implementation_evidence` | frozen source commit `00336f31859bb0b40457abbbe6e6f30570cd9998`; linked only from the capability-directory index | The production-only path and constraints documented at the frozen revision | Proof of current binding/activation, canonical doctrine, or cross-repo approval | `none_found` |
| `docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.md` @ `4920847...`; SHA-256 `5ea42362b2917e333be438b9499ed87d6e9c4b5363222601bfbcdb673c2d6c17` | `historical_implementation_evidence` | merged PR #164 / merge commit `4920847...` | What the merged v2 availability design intended and recorded | Human-approved doctrine or future FORGE role; no attributable human approval record found | `none_found` |
| `docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.json` @ `4920847...`; SHA-256 `7994e61c83d9ad1d5ddc937f42736a47d93175b3e19e80cb4c4169be83302b1c` | `historical_implementation_evidence` | merged PR #164 / merge commit `4920847...` | Machine-readable mechanics paired with the merged design | Human-approved doctrine or future FORGE role | `none_found` |
| `docs/ownership-boundaries.md` @ `4920847...`; SHA-256 `4790a90461b2025000f726df3ba2aac2f31bbe6b6c3fee454b217c706ed85f6b` | `canonical_repo_documentation` | linked by current README; registered dependency | Forecast's declared ownership boundaries | Authority over other repositories or a FORGE reconception | `none_found` |
| `docs/forecast-lane.md` @ `4920847...`; SHA-256 `616e4ea6d21c277268386ab6536204893144b584f63f64d17e9651d07b4b0466` | `canonical_repo_documentation` | linked by current README | Forecast-lane vocabulary and operating shape | Proof of #59 approval or future FORGE ownership | `none_found` |
| `docs/run-manifest-spec.md` @ `4920847...`; SHA-256 `612600b7adf1620b319f30b489909e9ad1ea06c9ab8c39b5f629d5d041f1c233` | `canonical_repo_documentation` | linked by current README | Run manifest, cutoff, and input-governance semantics | Cross-repository doctrine beyond its stated contract | `none_found` |
| `docs/run2-tts-feature-contract.md` @ `4920847...`; SHA-256 `dae837dfc4c0b38b63ff5d2901c746b9fbfc3215bae2688e99724c30b0e26227` | `canonical_repo_documentation` | linked by current README | The model-legible Teamstate feature gate for Run 2 | General FORGE architecture or approval provenance | `none_found` |
| `docs/run1-path-audit-for-run2.md` @ `49208472539bd11789b88ca8b3eb20c56a7d0db5`; SHA-256 `530bbc5d6e134eb9cf1ba4e2cc4437da1c8a9dda4764913e24b389aca904f9db` | `canonical_repo_documentation` | linked from the root README's Forecast architecture lane at the frozen revision; file last changed in `0f17f92bf9364c73115a0701efed8cd73ad6af8f` | The documented Run 1 pipeline map, manifest distinction, cutoff invariants, and proposed Run 2 attachment seam at the frozen revision | Proof that Run 2 is implemented, executable conformance beyond the audit, a D2 ownership conclusion, or activation authority | `none_found` |
| TIBER-Forecast#59; retrieved `2026-07-15T22:41:29Z`; SHA-256 `2b9d4a1e065939a1761944753360bd06a9ee248750c0357a2cb0176890e2f6b7` | `contextual_only` | open issue, updated `2026-06-22T21:07:08Z` | Historical problem framing and themes to investigate | Governed fact, accepted requirements, or approval | `none_found` |

The four additional Forecast documents (`forecast-lane`, `run-manifest-spec`,
`run2-tts-feature-contract`, and `run1-path-audit-for-run2`) were added because
the current README links them in the same architecture lane and their content
instantiates #59's model-legible architecture themes. No file explicitly cites
#59, so this is content continuity plus current repository linkage, not
issue-reference provenance.

**PR #164 authority gap:** the PR is merged, but the available review history
contains only a Codex `COMMENTED` review and comments posted through the
Prometheus account without an attributable human decision label. The merge
event alone does not satisfy #22's human-provenance doctrine. Its two design
files are therefore classified as `historical_implementation_evidence`, not
`human_approved_merged_architecture_decision`. This is nonblocking for D1
because the evidence remains usable within the narrower classification.

### 4.2 TIBER-FORGE

| Dependency and pin | Primary authority basis | Authority ref | Authoritative for | Not authoritative for | Supersession status |
|---|---|---|---|---|---|
| `README.md` @ `af2ca4d...`; SHA-256 `c12bcd8e099474c09dc3ca51fba70a0c9e1f068dc2b0fb72d89fe5ace568173f` | `current_implementation_self_description` | repository entry point; last change `1fca205...` | Current self-described grading layer and static evidence compiler | Human-approved future mission | `none_found` |
| `src/contracts/forge.ts` @ `af2ca4d...`; SHA-256 `ceeb45ee9833166d1192b25919b9b3ee24612f38af8a39ecea638656a45689a5` | `historical_implementation_evidence` | frozen source commit `fc619b5057d325a120d44078bb5942eade11aafb`; registry verification is descriptive only | Exact exported TypeScript contract definitions at the frozen revision | Promoted status, human-approved ownership doctrine, or desired redesign | `none_found` |
| `src/contracts/football.ts` @ `af2ca4d...`; SHA-256 `453693f1bd069326b4266ed3346443bdee729a109face215c8d8a3c7f8adc68d` | `historical_implementation_evidence` | frozen source commit `258c2919d90ba9558afd45e7403b8617bbf96887`; registry verification is descriptive only | Exact football-domain TypeScript definitions at the frozen revision | Promoted status, future mission, or implementation mandate | `none_found` |
| `docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md` @ `af2ca4d...`; SHA-256 `39dd805cc37efb98c15b8eb63f035489b56277412f4e8b2f81a6ccf9cf159a59` | `historical_implementation_evidence` | verified source pin; last change `33cce05...` | The ingestion design stated by the document | Proof that all described ingestion is current or approved doctrine | `none_found` |
| `exports/promoted/forge_player_static/forge_player_static_v1.json` @ `af2ca4d...`; SHA-256 `2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041` | `historical_implementation_evidence` | frozen source commit `1fca205469a2793de4d509026c34da1864104db9`; path naming and registry verification are not promotion provenance | Exact artifact bytes and data shape at the frozen revision | Proven promotion authority, architectural intent, or consumer freshness | `none_found` |

### 4.3 TIBER-Fantasy embedded FORGE

| Dependency and pin | Primary authority basis | Authority ref | Authoritative for | Not authoritative for | Supersession status |
|---|---|---|---|---|---|
| `server/modules/forge/MODULE.md` @ `d35d440...`; SHA-256 `32cf08fd7bb6b28813ce2f56a8608d62a1700024d1e0b734df926af40c88cc0b` | `current_implementation_self_description` | current module documentation; linked from architecture map | The live embedded module's stated legacy role and acronym | Desired end-state or proof externalization has occurred | `none_found` |
| `server/modules/forge/forgeGrading.ts` @ `d35d440...`; SHA-256 `15c57e5489eac38ee830205a1c0b9f196675f34f2ce062f75f52892c001c7057` | `historical_implementation_evidence` | frozen source implementation | Actual grading behavior, including 0.8 current / 0.2 prior blend | Approved architecture or cross-repo ownership | `none_found` |
| `server/modules/forge/recursiveAlphaEngine.ts` @ `d35d440...`; SHA-256 `1338f2d90ac06d8ae2076a99054deefa2f73ca2a1dfb833a87ecea41afba8c90` | `historical_implementation_evidence` | frozen source implementation | Actual recursive-alpha implementation evidence | Current doctrine or future mission | `none_found` |
| `docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md` @ `d35d440...`; SHA-256 `7b9b0362048d2d9dbe42fa801fb3f75236709fc56e8b0186723c0306ae66b3ba` | `canonical_repo_documentation` | linked from current module/architecture documentation | The repository's documented transition plan | Proof that the transition was executed or globally approved | `none_found` |
| `server/contracts/rankingsV2.ts` @ `d35d440...`; SHA-256 `af7f56ffdb578254438c52c56dfd482d164d1fa42f415c2b7b00518322729c39` | `historical_implementation_evidence` | frozen source commit `5b0adec654bba11c333b57d266438b237338c80f`; registry verification is descriptive only | Exact rankings-v2 TypeScript definitions at the frozen revision | Promoted status, FORGE mission, grading doctrine, or implementation mandate | `none_found` |

### 4.4 TIBER-Data and contextual cross-repository issues

| Dependency and pin | Primary authority basis | Authority ref | Authoritative for | Not authoritative for | Supersession status |
|---|---|---|---|---|---|
| TIBER-Data `docs/repo-boundaries-and-feedback-loops.md` @ `a7c0594...`; SHA-256 `c1df7ea4d628b2b1b7466e1ab35a0db12871c03770d86b60d8da33ab5c0bd9a9` | `canonical_repo_documentation` | linked from current README and AGENTS.md | Data's declared boundaries and feedback-loop responsibilities | Authority to assign another repository's future role | `none_found` |
| TIBER-Data `docs/governance/architecture/tiber-architecture-document-v1.0.md` @ `a7c059412806470a9e0b89889cd85f01cf7aace9`; SHA-256 `76a9ae28e5210123996d683f51beeceb321a97a1d5c6f3b899dbad3db8d83e58` | `canonical_repo_documentation` | active approved canonical source linked by root `README.md`, `ARCHITECTURE.md`, and `AGENTS.md`; file last changed in `096d75d0b21ad02fcb0b710160743c7dbb986184` | The active cross-repository architecture baseline at the frozen revision, including its description of TIBER-FORGE as an engineering/integration workspace | A new human decision, automatic resolution of conflicting FORGE identities, implementation truth inside FORGE, or authority to activate D2 | `none_found` |
| TIBER-Ops#24; retrieved `2026-07-15T22:41:29Z`; SHA-256 `c7beb935dd581881ab3dcde04f76b2bb55f391b0ee97e40f35ee33e7dbc2dbed` | `contextual_only` | open issue, updated `2026-07-13T16:51:38Z` | Additional problem/history context | Governed fact or accepted architecture | `none_found` |
| TIBER-Ops#30; retrieved `2026-07-15T22:41:29Z`; SHA-256 `56fd6826f74d8f87d17e9a7da85ed5b71a34b76011b1417f6813b7be58438264` | `contextual_only` | open issue, updated `2026-07-14T15:10:29Z` | Additional problem/history context | Governed fact or accepted architecture | `none_found` |
| TIBER-Ops#13; retrieved `2026-07-15T22:41:29Z`; SHA-256 `92ebf521911741407649fb1ab0cedf04ba14b1ee3547c78578e6232ae42c18cb` | `contextual_only` | closed issue, updated `2026-07-11T05:52:54Z` | Historical claims to cross-check against committed sources | Governed fact or proof of current route wiring | `none_found` |
| TIBER-Data#212; retrieved `2026-07-15T22:41:29Z`; SHA-256 `07e8ca3ed380ecb7ea7a4b8d2e0141e6d5da136727441f2190e7f28463bd75bd` | `contextual_only` | open issue, updated `2026-07-11T13:15:16Z` | Historical claims to cross-check against committed sources | Governed fact or approved boundary | `none_found` |

### 4.5 Additional contracts required to test D2 ownership hypotheses

These sources do not decide D2. They prevent D2 from reasoning about named
Teamstate, Role-and-opportunity, and Rookies ownership hypotheses without
directly pinned repository evidence.

| Dependency and pin | Primary authority basis | Authority ref | Authoritative for | Not authoritative for | Supersession status |
|---|---|---|---|---|---|
| TIBER-Teamstate `docs/contracts/team-environment-profile-v0.md` @ `3ec1d78e10fccf203239c88b905e3cf744d21c48`; SHA-256 `255b7f954b6ebab550ec811a4047dcd87238e541750ae628249f4ef157c9870a` | `historical_implementation_evidence` | frozen source commit `ed4e57c1d4a3bb28dc98db2d88b3b77391d083ca`; hash also verified by the descriptive registry | The team-environment profile contract semantics committed at the frozen revision | A D2 ownership conclusion, promotion status, runtime conformance, or human-approved doctrine | `none_found` |
| Role-and-opportunity-model `docs/contracts/role-opportunity-profile-v0.md` @ `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d`; SHA-256 `a156ff5e9f7d335a3a45e76dda8765aaa4883b158c62bc4da02eb9cf4d634bdb` | `historical_implementation_evidence` | frozen source commit `66296ed00f5fec091abcc9712cfcbd8cb94238ea`; hash also verified by the descriptive registry | The role-opportunity profile contract semantics committed at the frozen revision | A D2 ownership conclusion, promotion status, runtime conformance, or human-approved doctrine | `none_found` |
| TIBER-Rookies `docs/rookie-transition-profile-contract.md` @ `2ef92faf9a9c91a393f53e9140428451529a1c48`; SHA-256 `187fb0c68b8a9d30d7e4db0f130ceb98009af4cffb878394dded540d3d6b285b` | `historical_implementation_evidence` | frozen source commit `2ef92faf9a9c91a393f53e9140428451529a1c48`; hash also verified by the descriptive registry | The rookie-transition profile contract semantics committed at the frozen revision | A D2 ownership conclusion, promotion status, downstream adoption, or human-approved doctrine | `none_found` |
| TIBER-Rookies `docs/export-contract.md` @ `2ef92faf9a9c91a393f53e9140428451529a1c48`; SHA-256 `9b0cff08e40ac45f5bfc725e67f3b95a2a6200491af29da1af49beb4cb49c164` | `canonical_repo_documentation` | root README links the manifest/validation contract and identifies the repository as the authoritative Rookie Alpha producer; file last changed in `7bc4384991334eff73aedb9a73e73ae95431606c` | The repository's current documented Rookie Alpha producer output, manifest, scoring, and validation contract at the frozen revision | Canonical cross-repo data authority, a FORGE ownership conclusion, downstream adoption, or human approval of D2 | `none_found` |

---

## Entry 5 — D1 result and next gate

### Result

- Mandatory Step 0: **complete**.
- Control-authority inventory: **complete for the D1 sources named by #31**.
- Architectural-evidence inventory: **complete for 25 file-backed sources
  and five contextual issues, comprising the named minimum plus nine directly
  relevant additional documents**.
- Authority record: **present for every architectural dependency**.
- Source-repository changes: **none**.
- Registry edits: **none**.
- Implementation: **none**.
- D2-D6 activation: **none**.
- #15 R2: **still parked**.

### Recorded gaps and cautions

1. PR #164 lacks attributable human-approval provenance, so its merged design
   artifacts remain implementation evidence rather than approved doctrine.
2. TIBER-Ops#13 and TIBER-Data#212 remain contextual-only issue evidence.
3. FC1's stale Fantasy mirror remains provenance-unverified and must not be
   used as a current producer/consumer equivalence claim.
4. No explicit supersession marker was found for the D1 architectural files;
   `none_found` is a search result, not an eternal guarantee.
5. Six sources were conservatively classified as historical implementation
   evidence after independent review found no provenance-valid promotion or
   canonical-documentation basis. D2 must not silently elevate them.

### Checkpoint state

`d1_third_correction_complete_pending_independent_reverification`

D1 evidence has been corrected in response to the first fresh-context audit
and is ready for a different fresh-context independent verifier. Until that
review is recorded and the human decision owner explicitly advances the
frontier, D1 is not promoted to a completed program gate and D2 remains
inactive. Claude may later receive bounded implementation work only under a
separately activated implementation step.

---

## Entry 6 — D2 activation and resume preflight

### Authority transition

- **Accepted D1 checkpoint:**
  `5161b4c80e01771ff5830ad1c200fc410902a755`
- **Independent D1 PASS:**
  `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4986598174`
- **D2 frontier decision:**
  `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987203347`
- **D2 decision decoded-body SHA-256:**
  `5d2b142aa6ff29dfd230fa555fe5b2893f6097283c50181189d6e3b928f5921c`
- **Executing branch:** `work/tiber-ops-31-d2-decomposition`
- **Executing agent:** ChatGPT Work / Codex
- **Active frontier:** D2 only
- **Inactive frontiers:** D3-D6
- **R2 state:** `r2_parked_pending_forge_reconception`

The D2 frontier decision is a step-local frontier gate required by the program
invariant. It is **not** Decision C in #31 §11; Decision C remains the future
human selection of a FORGE direction after the full discovery deliverable.

### Resume freshness comparison

At `2026-07-16T02:00:16Z`, all eight remotes were fetched before D2 evidence
was used. Each of the seven read-only source repositories still matched its D1
frozen `origin/main` revision, and each worktree was clean.

| Repository | D1 frozen revision | Fresh `origin/main` match | Worktree before D2 writes |
|---|---|---:|---:|
| TIBER-Data | `a7c059412806470a9e0b89889cd85f01cf7aace9` | yes | clean |
| TIBER-Forecast | `49208472539bd11789b88ca8b3eb20c56a7d0db5` | yes | clean |
| TIBER-Teamstate | `3ec1d78e10fccf203239c88b905e3cf744d21c48` | yes | clean |
| Role-and-opportunity-model | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | yes | clean |
| TIBER-FORGE | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | yes | clean |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | yes | clean |
| TIBER-Rookies | `2ef92faf9a9c91a393f53e9140428451529a1c48` | yes | clean |

TIBER-Ops `origin/main` remained
`530b4fb4f1270c1247f67180483e115fab39cb1a`; the remote D1 branch and the new
D2 worktree both resolved exactly to the accepted checkpoint before D2 writes.
All 25 file-backed D1 dependencies were independently re-hashed and matched
the full SHA-256 values recorded in Entry 4.

The live #22 body was retrieved after program synchronization. It was updated
at `2026-07-16T01:45:08Z`; its exact decoded-body SHA-256 was
`48795f7d6a55c0db9217fa5b355c8459ebd1421fcfb117bdc163985d92520cd4`.
It records `d2_active`, D1 complete at the accepted checkpoint, #15 R2 parked,
and D3-D6 inactive.

**Resume result:** no freshness, hash, authority, or frontier mismatch. D2 may
use the frozen inventory without adding dependencies.

---

## Entry 7 — D2 semantic-job verification

### Method

The nine hypotheses from #31 were tested in their fixed order against D1's
authority-bounded pins. The executing context split the evidence read across
three read-only passes: domain/Forecast ownership, historical FORGE/Fantasy
implementation, and presentation/agent-context boundaries. Those passes were
contributors to the executing context and are **not** the later independent
completion verifier.

Every result in
`docs/architecture/forge-reconception-v0.md` is either cited to a D1 pin or
marked exactly `unresolved — D3 input`. Source authority and D2 assertion
status remain separate.

### Cited nine-row result

The sole decomposition table is §2 of
`docs/architecture/forge-reconception-v0.md`. The ledger does not duplicate
its source-bearing cells. That table contains D2-R01 through D2-R09 in the
approved order; every cell cites an evidence ID resolved to a full D1 pin in
§6 or uses the exact literal `unresolved — D3 input`.

After the first independent audit correction, only the observations/lineage,
Forecast, and Fantasy allocations are supported within current D1 authority
bounds. Teamstate, Role-and-opportunity, and the full prospect/transition-prior
job retain verified historical or producer semantics but are
`unresolved — D3 input` as ownership allocations. Synthesis, evaluation policy,
and complete agent-context ownership also remain `unresolved — D3 input`.

### Historical/current distinction

D2 kept the following evidence classes distinct:

1. The embedded Fantasy module's current legacy acronym and evaluation role.
2. `forgeGrading.ts`'s 80% current / 20% prior-Alpha blend plus bounded
   momentum.
3. `recursiveAlphaEngine.ts`'s separate persisted two-pass
   expected/surprise/stability mechanism. The two-pass engine was not
   misreported as the 80/20 blend.
4. Standalone TIBER-FORGE's current early grading/static-compiler
   self-description and bootstrap limitations.
5. Fantasy's canonical externalization plan, recorded as a documented target
   rather than executed or globally approved architecture.

Current architectural needs were then stated independently: typed provenance
and lineage; separately accountable domain interpretation; cutoff-bounded
forecasts with uncertainty; presentation separated from evaluation policy; and
reproducible, governed agent control context. No historical implementation was
allowed to define the ontology by default.

### Preserved conflicts and parked questions

D2 did not resolve the incompatible pinned FORGE identities or topology. It
parked for D3 the owner and contract for cross-source synthesis, future
evaluation-policy ownership, topology, recursion safeguards, downstream
admission gates, and complete agent-context assembly.

- Dependencies added: **none**.
- Source-repository writes: **none**.
- Registry writes: **none**.
- #15/#20 writes or state changes: **none**.
- Implementation, scaffolding, or prototypes: **none**.
- D3-D6 activation: **none**.

---

## Entry 8 — D2 candidate checkpoint

### Deliverable

- **Path:** `docs/architecture/forge-reconception-v0.md`
- **SHA-256:**
  `89a69603966c8e26072672b6a0f8fc3d46283df2428f562f8630b64aab97c99f`
- **Scope represented:** D2 only

### Candidate acceptance evidence

- Exactly nine ordered semantic-job rows are present.
- Every table allocation cites a D1 pin and authority bound, or uses the exact
  literal `unresolved — D3 input`.
- Historical FORGE intent and implementation are separated from current
  architectural needs.
- The two legacy temporal mechanisms are distinguished accurately.
- All D3-reserved choices remain unresolved.
- Only the two #31-permitted TIBER-Ops paths were written.

### Frontier state

`d2_second_audit_state_sync_complete_pending_new_independent_verification`

This executing-agent checkpoint is not self-approval. D2 remains the sole
active discovery frontier pending a different fresh-context verifier. D3-D6
remain inactive, and #15 R2 remains parked. A PASS would return the evidence
to Joseph for a separate frontier decision; it would not itself activate D3.

---

## Entry 9 — First D2 audit FAIL and bounded correction

The candidate at
`8d5041f56b0cdc7fcbdcfacbd44dd6eb2c3ab108` received a fresh-context
independent **FAIL** at
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987499236`.
The synchronized program record is
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4987501132`.

The audit found:

1. D2-R02, D2-R03, and part of D2-R04 asserted ownership using sources whose
   D1 bounds explicitly prohibited a D2 ownership conclusion.
2. The deliverable's P01 evidence row omitted that prohibition.
3. Entry 7 repeated the nine-row result without source citations.

The correction changed no evidence pin and added no dependency. It retained
the historical semantics, downgraded the affected ownership allocations to
`unresolved — D3 input`, restored P01's full bound, and removed the duplicate
ledger decomposition table. The first checkpoint is superseded and cannot be
used as D2 completion evidence.

Corrected state:
`d2_first_audit_corrections_complete_pending_new_independent_verification`.

D2 remains active in correction. D3-D6 remain inactive, and #15 R2 remains
parked.

---

## Entry 10 — Second D2 audit FAIL and state synchronization

The corrected candidate at
`9c32ea893e808d71ba88773485c230661e9277c3` received a fresh-context
independent **FAIL** at
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4987578172`.
The synchronized program record is
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4987579546`.

The authority allocations, evidence pins, single decomposition table, and
scope boundaries passed. The sole defect was that the deliverable still used
the first failed candidate's state string while the ledger used the first
correction state.

The correction synchronizes both current artifacts to:
`d2_second_audit_state_sync_complete_pending_new_independent_verification`.
No evidence, analysis, allocation, authority bound, dependency, or permitted
path changed. Both prior checkpoints remain superseded and cannot establish D2
completion.

D2 remains the sole active discovery frontier pending another different
fresh-context verifier. D3-D6 remain inactive, and #15 R2 remains parked.

---

## Entry 11 — D2 acceptance, D3 activation, and resume preflight

### Authority transition

The operator's exact signed decision is recorded at
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991320938`.
Its decoded body SHA-256 is
`c82688980fb02577f85047ade0ee4e5912db54bc7d6e7d5e6062c3957d5746e2`.
It accepts D2 complete at exact commit
`1c141b39616972cb67c663d025a78edad0414046` based on the independent PASS,
activates D3 as the sole discovery frontier, keeps #15 R2 parked, and leaves
D4-D6 inactive. It does not select a FORGE direction or authorize D4.

The synchronized #22 program body was retrieved at
`2026-07-16T11:51:27Z`, had been updated `2026-07-16T11:34:33Z`, and had
decoded SHA-256
`90d9a04c28450ab292e1c6fea3025f3dcdb20eb1a7a9555f154107b98058571e`.

The accepted D2 artifacts at `1c141b3…` were byte-verified before D3:

| Accepted artifact | SHA-256 |
|---|---|
| `docs/architecture/forge-reconception-v0.md` | `89a69603966c8e26072672b6a0f8fc3d46283df2428f562f8630b64aab97c99f` |
| `program/discoveries/forge-reconception-v0/progress-ledger.md` | `3fff8ca9cd2239efae4b1627b9897f5758e50738eca095ed896127c90f2d6fc2` |

### D3 resume preflight

At `2026-07-16T11:51:27Z`, the seven governed source repositories were fetched
and rechecked. Each `origin/main` still equaled the D1 frozen revision and each
worktree was clean:

| Repository | Reverified frozen revision |
|---|---|
| TIBER-Data | `a7c059412806470a9e0b89889cd85f01cf7aace9` |
| TIBER-Forecast | `49208472539bd11789b88ca8b3eb20c56a7d0db5` |
| TIBER-Teamstate | `3ec1d78e10fccf203239c88b905e3cf744d21c48` |
| Role-and-opportunity-model | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` |
| TIBER-FORGE | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` |
| TIBER-Rookies | `2ef92faf9a9c91a393f53e9140428451529a1c48` |

All 25 file-backed architectural dependency hashes were recomputed from the
exact frozen Git trees and matched D1: **PASS 25/25**. No dependency was added.

### Frontier state

- D3: sole active discovery frontier.
- #15 R2: `r2_parked_pending_forge_reconception`.
- D4-D6: inactive.
- Source/registry/#15/#20 writes: none.
- Implementation, prototype, migration, and deprecation: none.

---

## Entry 12 — D3 four-option comparison

### Method and independent challenge

D3 applied the approved four-options-by-eight-questions rubric from #31. The
comparison used non-compensating safety/authority gates followed by an
unweighted Pareto comparison. It did not invent numeric weights or treat the
operator's prior, contextual issue text, repository names, path labels, or
historical implementations as future authority.

Three independent read-only fresh-context analyses were commissioned before
authoring:

1. Options A and B were tested against all Q1-Q8 requirements and D1 authority
   bounds.
2. Options C and D were tested independently, with D preserved as a genuine
   null hypothesis rather than a strawman.
3. An adversarial rubric review checked 32-cell completeness, topology,
   recursion, confidence, cutoff, coherence, admission, migration, and whether
   a positive recommendation was evidentially supportable.

All three analyses were read-only and made no file, branch, commit, or GitHub
change. The adversarial result was that the frozen evidence does not select
exactly one positive recommendation. It identified underdetermination rather
than inaccessible evidence, so the correct terminal is
`forge_reconception_requires_followup`, not `forge_reconception_blocked`.

### Comparison result

- Exactly four option sections are present.
- Each option has exactly one non-empty Q1-Q8 answer.
- Every topology is acyclic after typed stage expansion.
- Every option selects Q2(a), prohibited self-reference; legacy recursion is
  quarantined rather than legitimized.
- Every Q3 supplies a counterfactual archetype/role test.
- Every Q4 addresses FC1 and minimal snapshot-bound, provenance-preserving,
  non-authoritative copies.
- Every Q5 preserves the full admission path and separate human sign-off; D
  names direct Forecast inputs.
- Every Q6 separates coverage, reliability, classification confidence,
  Forecast uncertainty, and evaluative-projection confidence.
- Every Q7 uses subject/record-bound typed availability, maximum dependency
  availability for derived values, prohibited timestamp substitutes, and
  fail-closed ambiguity.
- Every Q8 dispositions embedded and standalone FORGE without declaring either
  superseded or performing deprecation.

The decisive unresolved tradeoff is whether a canonical cross-source profile
provides reusable synthesis worth its ownership, joins, correction semantics,
and coherence cost, versus distributed composition's repeated adapters,
admissions, and hidden-divergence risk. The evidence also does not establish
which universal verdicts should survive, their owners, complete typed-
availability coverage, or the full consumer/migration graph.

### Scope accounting

- Permitted deliverable paths changed: the architecture document and this
  ledger only.
- Dependency additions: none.
- Source-repository or registry writes: none.
- #15/#20 writes or state transitions: none.
- Implementation, scaffolding, or prototypes: none.
- PR, merge, promotion, migration, cutover, or deprecation: none.
- D4-D6 activation: none.

---

## Entry 13 — D3 candidate checkpoint

### Deliverable

- **Path:** `docs/architecture/forge-reconception-v0.md`
- **SHA-256:** `dfcaa1f1fc92bb031da54d01871d99cd3afbce9d491c1950981c9127cee0304a`
- **Scope represented:** accepted D2 plus D3 comparison only
- **Terminal result:** `forge_reconception_requires_followup`
- **Positive recommendations:** zero

### Named follow-up evidence

The deliverable requires a separately authorized package covering shared
consumer demand, a bounded profile-viability contract sketch, the matching
distributed-composition map/cost, typed-availability coverage, surviving
question-specific projection consumers/owners, and the complete
embedded/standalone compatibility and migration graph. This entry does not
activate or execute that work.

### Frontier state

`d3_comparison_complete_forge_reconception_requires_followup_pending_independent_verification`

This executing-agent checkpoint is not self-approval. D3 remains the sole
active discovery frontier pending a different fresh-context verifier. #15 R2
remains parked and D4-D6 remain inactive. A PASS would validate the comparison
only; it would not select a FORGE direction or activate D4.

---

## Entry 14 — First D3 audit FAIL and bounded correction

The candidate at
`cfb75191f9f53f981596e1ae9ffcdedf682f35f9` received a fresh-context
independent **FAIL** at
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991694618`.
The synchronized program record is
`https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4991695926`.

The audit passed the four-option/32-cell structure, Q1-Q5 and Q7-Q8, evidence
and citation treatment, honest Option D comparison, two-path scope, and the
zero-recommendation `forge_reconception_requires_followup` terminal. It found
two specification-level omissions:

1. Option C was not explicitly identified as the operator's prior.
2. Each Q6 assigned confidence owners but did not fully identify every
   confidence value's qualified claim and derivation.

The bounded correction:

- explicitly records Option C as the operator's prior while stating that it is
  not evidence, a weight, tie-breaker, or conclusion and may be defeated; and
- expands all four Q6 answers so evidence coverage, source reliability,
  classification confidence, Forecast uncertainty, and evaluative-projection
  confidence each name the exact qualified claim, owner, and derivation class.

No option topology, recursion choice, recommendation, terminal result,
evidence pin, dependency, authority bound, or follow-up finding changed.

### Corrected deliverable

- **Path:** `docs/architecture/forge-reconception-v0.md`
- **SHA-256:** `d2902444c9508cb7520653d4e2c1cb015f1fba5a75263271d14fbd9ff255fc6e`
- **Terminal result:** `forge_reconception_requires_followup`
- **Positive recommendations:** zero

Corrected state:
`d3_first_audit_corrections_complete_pending_new_independent_verification`.

D3 remains the sole active discovery frontier pending a new different
fresh-context verifier. #15 R2 remains parked, D4-D6 remain inactive, and no
direction, implementation, migration, or deprecation is authorized.

---

## Entry 15 — D3-F activation and mandatory F0 evidence freeze

### Authority transition and immutable base

The accepted D3 document and Entries 0-14 above are historical evidence and
were not rewritten. This D3-F branch was created at exactly
`5a3c8747e92d99902484a059da778726f3e68900`. Before this append, the accepted
artifacts independently reproduced as raw Git blobs. They were reverified at
`2026-07-16T20:47:39.166169091Z` as:

| Accepted artifact | SHA-256 |
|---|---|
| `docs/architecture/forge-reconception-v0.md` | `d2902444c9508cb7520653d4e2c1cb015f1fba5a75263271d14fbd9ff255fc6e` |
| `program/discoveries/forge-reconception-v0/progress-ledger.md` | `6f08167ccb3f07de2305707b8f5d6a8ef5085458ae4e49e3ba8ec6fb8c9e8f54` |

The D3-F amendment's canonical boundary was independently extracted from the
heading through `*Amendment ends.*`, inclusive, with one terminal LF. It is
37,420 UTF-8 bytes and reproduced SHA-256
`9412d3970a7b014c2f17cf3060f29450609d58e4bc64f739c36948804edaff60`.

The signed activation comment makes D3-F #31's sole discovery frontier,
requires F0 first, keeps #15 R2 parked, leaves D4-D6 inactive, and forbids a
FORGE direction or implementation. It does not alter the accepted D3 terminal
`forge_reconception_requires_followup`.

### F0 fresh-fetch record

Each remote default was resolved with `git ls-remote --symref origin HEAD`.
Each remote was fetched before hashing. Source worktrees were clean at their
freshly fetched `origin/main`; the clean Ops worktree was intentionally on the
D3-F branch at the accepted D3 base rather than on `origin/main`.

| Repository | Remote URL | Default ref | Fetch completed (UTC) | Fetched tracking revision | Worktree state |
|---|---|---|---|---|---|
| TIBER-Ops | `https://github.com/Prometheus-Frameworks/TIBER-Ops.git` | `refs/heads/main` | `2026-07-16T20:21:10.192160818Z` | `530b4fb4f1270c1247f67180483e115fab39cb1a` | clean `work/tiber-ops-31-d3f-evidence` at `5a3c874...` |
| TIBER-Data | `https://github.com/Prometheus-Frameworks/TIBER-Data.git` | `refs/heads/main` | `2026-07-16T20:16:32Z` | `a7c059412806470a9e0b89889cd85f01cf7aace9` | clean `main`; HEAD = `origin/main` |
| TIBER-Forecast | `https://github.com/Prometheus-Frameworks/TIBER-Forecast.git` | `refs/heads/main` | `2026-07-16T20:18:52Z` | `49208472539bd11789b88ca8b3eb20c56a7d0db5` | clean `main`; HEAD = `origin/main` |
| TIBER-Teamstate | `https://github.com/Prometheus-Frameworks/TIBER-Teamstate.git` | `refs/heads/main` | `2026-07-16T20:15:26.234270877Z` | `3ec1d78e10fccf203239c88b905e3cf744d21c48` | clean `main`; HEAD = `origin/main` |
| Role-and-opportunity-model | `https://github.com/Prometheus-Frameworks/Role-and-opportunity-model.git` | `refs/heads/main` | `2026-07-16T20:15:26.193827934Z` | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | clean `main`; HEAD = `origin/main` |
| TIBER-FORGE | `https://github.com/Prometheus-Frameworks/TIBER-FORGE.git` | `refs/heads/main` | `2026-07-16T20:16:32Z` | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | clean `main`; HEAD = `origin/main` |
| TIBER-Fantasy | `https://github.com/Prometheus-Frameworks/TIBER-Fantasy.git` | `refs/heads/main` | `2026-07-16T20:13:37Z` | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | clean `main`; HEAD = `origin/main` |
| TIBER-Rookies | `https://github.com/Prometheus-Frameworks/TIBER-Rookies.git` | `refs/heads/main` | `2026-07-16T20:16:33Z` | `2ef92faf9a9c91a393f53e9140428451529a1c48` | clean `main`; HEAD = `origin/main` |

Every source fetched revision equals its accepted D1 frozen revision. Therefore
the F0 current bytes and historical D1 bytes are identical for every path that
still exists; no live divergence or supersession classification is required.

### Live GitHub control pins

Issue bodies were retrieved at `2026-07-16T20:26:04Z`. Comment bodies were
retrieved at `2026-07-16T20:26:24Z`. Hashes cover the exact UTF-8 body strings
returned by GitHub with no newline addition, removal, or normalization.

| Object | GitHub metadata | UTF-8 bytes | SHA-256 |
|---|---|---:|---|
| #22 body, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22` | updated `2026-07-16T20:09:47Z` | 20,734 | `8f8b87e4472c6b558a951311325606aa48e1ec03284d99e4956058fe93ca707b` |
| #31 body, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31` | updated `2026-07-16T20:08:02Z` | 43,653 | `9539d2f8afe3cbfa2ea5300b78a550af3ff707bb13bbac64a5b9d54385531340` |
| #31 D3 PASS, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4991760192` (ID `4991760192`) | `Prometheus-Frameworks`; created/updated `2026-07-16T12:22:16Z` | 1,578 | `94a8e7721741887738f783039727a8d7bca88fef14b6b298331c455435c9d79b` |
| #31 D3 acceptance, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4992880223` (ID `4992880223`) | `Prometheus-Frameworks`; created/updated `2026-07-16T14:10:37Z` | 1,817 | `1ae3b270276d760750cd9441e0a5de638855520e6055f57fd8353510aedcc5b0` |
| #31 amendment proposal, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4993464413` (ID `4993464413`) | `Prometheus-Frameworks`; created/updated `2026-07-16T15:07:18Z` | 38,582 | `8790e9ef2df8201fb67b136f4a2d21e4d522a0997d8342586240a1d50a2d2b38` |
| #31 amendment approval, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4995866746` (ID `4995866746`) | `Prometheus-Frameworks`; created/updated `2026-07-16T19:37:08Z` | 1,803 | `fd9deee5d46364b0450338693775be1df0e8fc88da6399bbb89d65d2963ebe2b` |
| #31 D3-F activation, `https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/31#issuecomment-4996111440` (ID `4996111440`) | `Prometheus-Frameworks`; created/updated `2026-07-16T20:07:40Z` | 1,780 | `706458ee7d00fa56361edc6269da5ac66d2e803c92f5dfdbe1f059e67e826692` |

The live #31 approved specification boundary was also re-extracted and remains
41,563 bytes with the
approved SHA-256
`94c8a035d3363ed925f0a476f9d72568a5cf2f06199b509124f9f6fea4a81e9e`.

### Repository-file controls and policy applicability

All file rows use raw bytes at the stated applicable ref and were reverified at
exact batch-completion time `2026-07-16T20:47:39.166169091Z`. The first five
Ops controls are applicable at current `origin/main`
`530b4fb4f1270c1247f67180483e115fab39cb1a`; the accepted D3 paths are
applicable at `5a3c8747e92d99902484a059da778726f3e68900`.

| Repository/path or absence rule | SHA-256 | Applicable ref / use |
|---|---|---|
| Ops `docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md` | `a75aed0bbc8b4edcb9e71d518cc03478c2b42ea1683d39b47a4be65e089c0206` | Ops `530b4fb...`; F0/currentness procedure |
| Ops `registry/tiber-current-state.v0.json` | `de531ecb36176c8b5c858f6927d18eadfc8efcfe6d325fe449789faf35f8d88e` | Ops `530b4fb...`; descriptive registry including FC1 |
| Ops `runbooks/merge-checklist.md` | `069630473cbf56200dd9870a468038181985ce0d30467b17b83a1d07e9a6d9c3` | Ops `530b4fb...`; docs-only merge policy |
| Ops `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml` | `97a4742fc1c1dc5e9c5c50df295fdddf64188cb8fda5ade7a6370a5ca3b4300e` | Ops `530b4fb...`; inherited #15 scope/evidence/block rules |
| Ops `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/progress-ledger.md` | `974b6990c387de4bec813f6a061678afc80f3a24a0e600dce7b982f7824c1bf6` | Ops `530b4fb...`; inherited two-phase/no-rewrite lifecycle |
| Data `AGENTS.md` | `b3cddcc42a6f0f9f7e46a4bdec56194bf25cf29d12a29c0f98d2d47828fc7f85` | Data `a7c0594...`; whole repository |
| FORGE `AGENTS.md` | `579e8a820e890285d63fc53235d3106478b0e05cf1bcb0001ec1db97d5afa8f2` | FORGE `af2ca4d...`; whole repository |
| FORGE `TRUTH_SOURCES.md` | `48054e1d262ff8901d861a39980c9b2687330a9a6f327062e769ddc344bb01b4` | FORGE `af2ca4d...`; evidence ordering/fail-closed rules |
| Fantasy `AGENTS.md` | `040aed38e451bd4cf8cdd7b4d350ce550aff5b27a8eb4739d601398e0c6c9740` | Fantasy `d35d440...`; whole repository |
| Fantasy `CLAUDE.md` | `0296d6813ac7ddef8fff6f6be1a968725fc969b343507ddaec88b88deb5af90c` | Fantasy `d35d440...`; whole repository/product doctrine |
| Fantasy `SECURITY_POLICY.md` | `f5540a0849b469a3bacceeae163ee9a404b478b57c0a43f15d23f31251f1374a` | Fantasy `d35d440...`; whole repository |
| Fantasy `.claude/AGENTS.md` | `068674906fa169290062d9c8d4fc00ec1221891f6b6efa925619a6078c0fabdf` | Fantasy `d35d440...`; delegated-agent work |
| Teamstate `CLAUDE.md` | `9449e317936b0289b1e627e598c45b6a68b6d68e1ce852306b3af3bef630e55b` | Teamstate `3ec1d78...`; whole repository/path gates |
| Rookies `AGENTS.md` | `77511e117eac207061d161e171f7d7b8cea421192957d60b992776cf85d6c84b` | Rookies `2ef92fa...`; whole repository |
| Forecast formal-policy absence | zero matches | Forecast `4920847...`; repository-wide tracked-tree search |
| Role formal-policy absence | zero matches | Role `6435d8d...`; repository-wide tracked-tree search |

Forecast's formal-policy absence was reverified at
`2026-07-16T20:20:40Z`; Role's was reverified at
`2026-07-16T20:17:28.183740318Z`.

### Historical identity recheck

- Accepted D1 architectural files: **25/25** raw-byte SHA-256 values reproduced
  at their original frozen revisions.
- Every accepted D1 file-backed control/policy pin and companion checked by the
  registry preflight reproduced; the two policy-absence records remain zero.
- Accepted D3 document and ledger: **2/2** reproduced at `5a3c874...`.
- Amendment-printed historical supplemental hashes: **8/8** reproduced at the
  original D1 revisions and at F0 current revisions.
- All required current paths exist. Because all seven current heads equal the
  historical freezes, every comparison is `byte_identical_no_divergence`.

The 25 accepted architectural rows were compared individually. Exact
verification times were `2026-07-16T20:20:40Z` for Forecast/Fantasy,
`2026-07-16T20:18:52Z` for FORGE/Data/Rookies,
`2026-07-16T20:17:28.279108941Z` for Teamstate, and
`2026-07-16T20:17:28.183740318Z` for Role. The SHA in the third column is both
the historical recomputation and F0-current recomputation:

| ID | Repository/path | Historical = current SHA-256 | Result |
|---|---|---|---|
| F01 | Forecast `docs/capabilities/README.md` | `c4993f4642cdeaa68f18a180cf92109ff73cc1e4d4f277210a05fa91ef9163ac` | MATCH |
| F02 | Forecast `docs/capabilities/player-history-production-only-v0.md` | `0908180e3889d852b623039ebb79f4ee590f85b62bfb40581fbdf08cd3c9ef37` | MATCH |
| F03 | Forecast `docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.md` | `5ea42362b2917e333be438b9499ed87d6e9c4b5363222601bfbcdb673c2d6c17` | MATCH |
| F04 | Forecast `docs/experiments/rookie-transition-profile-forecast-availability-evidence-schema-v2-design-2026-07-13.json` | `7994e61c83d9ad1d5ddc937f42736a47d93175b3e19e80cb4c4169be83302b1c` | MATCH |
| F05 | Forecast `docs/ownership-boundaries.md` | `4790a90461b2025000f726df3ba2aac2f31bbe6b6c3fee454b217c706ed85f6b` | MATCH |
| F06 | Forecast `docs/forecast-lane.md` | `616e4ea6d21c277268386ab6536204893144b584f63f64d17e9651d07b4b0466` | MATCH |
| F07 | Forecast `docs/run-manifest-spec.md` | `612600b7adf1620b319f30b489909e9ad1ea06c9ab8c39b5f629d5d041f1c233` | MATCH |
| F08 | Forecast `docs/run2-tts-feature-contract.md` | `dae837dfc4c0b38b63ff5d2901c746b9fbfc3215bae2688e99724c30b0e26227` | MATCH |
| F09 | Forecast `docs/run1-path-audit-for-run2.md` | `530bbc5d6e134eb9cf1ba4e2cc4437da1c8a9dda4764913e24b389aca904f9db` | MATCH |
| G01 | FORGE `README.md` | `c12bcd8e099474c09dc3ca51fba70a0c9e1f068dc2b0fb72d89fe5ace568173f` | MATCH |
| G02 | FORGE `src/contracts/forge.ts` | `ceeb45ee9833166d1192b25919b9b3ee24612f38af8a39ecea638656a45689a5` | MATCH |
| G03 | FORGE `src/contracts/football.ts` | `453693f1bd069326b4266ed3346443bdee729a109face215c8d8a3c7f8adc68d` | MATCH |
| G04 | FORGE `docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md` | `39dd805cc37efb98c15b8eb63f035489b56277412f4e8b2f81a6ccf9cf159a59` | MATCH |
| G05 | FORGE `exports/promoted/forge_player_static/forge_player_static_v1.json` | `2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041` | MATCH |
| Y01 | Fantasy `server/modules/forge/MODULE.md` | `32cf08fd7bb6b28813ce2f56a8608d62a1700024d1e0b734df926af40c88cc0b` | MATCH |
| Y02 | Fantasy `server/modules/forge/forgeGrading.ts` | `15c57e5489eac38ee830205a1c0b9f196675f34f2ce062f75f52892c001c7057` | MATCH |
| Y03 | Fantasy `server/modules/forge/recursiveAlphaEngine.ts` | `1338f2d90ac06d8ae2076a99054deefa2f73ca2a1dfb833a87ecea41afba8c90` | MATCH |
| Y04 | Fantasy `docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md` | `7b9b0362048d2d9dbe42fa801fb3f75236709fc56e8b0186723c0306ae66b3ba` | MATCH |
| Y05 | Fantasy `server/contracts/rankingsV2.ts` | `af7f56ffdb578254438c52c56dfd482d164d1fa42f415c2b7b00518322729c39` | MATCH |
| D01 | Data `docs/repo-boundaries-and-feedback-loops.md` | `c1df7ea4d628b2b1b7466e1ab35a0db12871c03770d86b60d8da33ab5c0bd9a9` | MATCH |
| D02 | Data `docs/governance/architecture/tiber-architecture-document-v1.0.md` | `76a9ae28e5210123996d683f51beeceb321a97a1d5c6f3b899dbad3db8d83e58` | MATCH |
| T01 | Teamstate `docs/contracts/team-environment-profile-v0.md` | `255b7f954b6ebab550ec811a4047dcd87238e541750ae628249f4ef157c9870a` | MATCH |
| P01 | Role `docs/contracts/role-opportunity-profile-v0.md` | `a156ff5e9f7d335a3a45e76dda8765aaa4883b158c62bc4da02eb9cf4d634bdb` | MATCH |
| R01 | Rookies `docs/rookie-transition-profile-contract.md` | `187fb0c68b8a9d30d7e4db0f130ceb98009af4cffb878394dded540d3d6b285b` | MATCH |
| R02 | Rookies `docs/export-contract.md` | `9b0cff08e40ac45f5bfc725e67f3b95a2a6200491af29da1af49beb4cb49c164` | MATCH |

No historical mismatch, inaccessible object, unevaluable material divergence,
or necessary out-of-universe source was found.


### Supplemental evidence inventory: authority and selection mapping

Each manifest below is sorted by path and records the raw-byte SHA-256 at its
repository's F0 revision. Verification time is `2026-07-16T20:20:40Z` for
Fantasy and Forecast. Reused D1 rows retain their accepted Entry 4 authority
records. Every added row receives one of these deterministic group records:

- `FY-CURRENT`: `current_implementation_self_description`; authority ref
  Fantasy `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` plus its applicable
  policy pins; authoritative only for committed current paths, imports,
  mounts, adapters, and behavior; not authoritative for future ownership,
  desired survival, off-repository consumers, cutover, or a FORGE direction;
  supersession `none_found`.
- `FY-HIST`: `historical_implementation_evidence`; same commit/policies;
  applies deterministically to `docs/**`, `**/__tests__/**`,
  `server/tests/**`, fixture paths, and external snapshot artifacts;
  authoritative only for the recorded design/test/compatibility evidence;
  not for current production traffic, future ownership, survival, or
  direction; supersession `none_found`.
- `FC-CURRENT`: `current_implementation_self_description`; authority ref
  Forecast `49208472539bd11789b88ca8b3eb20c56a7d0db5` and each exact manifest
  path; authoritative only for current committed scoring/admission code and
  contracts; not for future cross-repository ownership, admission completion,
  policy adoption, or direction; supersession `none_found`.
- `FC-HIST`: `historical_implementation_evidence`; same commit; applies
  to `docs/**`, `data/fixtures/**`, and
  `src/api/routes/decisionBoard.ts`; authoritative only for mock,
  design, fixture, or policy-candidate evidence; not for live canonical
  output, admission completion, future ownership, or direction;
  supersession `none_found`.

Selection reasons are fixed by amendment category, not inferred from names:
Fantasy public/mounted ranking paths map to F1/F5; Player Research and
signal-validation paths to F1/F2/F4; grade/tier/ranking seeds to F5; embedded
FORGE closure to F3/F5/F6; compatibility/parity paths to F6; fixed-token scan
matches to F1/F5/F6. Forecast scoring/ranking/admission paths map to F1/F3/F5,
the decision-board mock pair to F5, and the rookie design/mirror pair to F4.
A row in more than one deterministic set carries the union of those named gaps.

Fantasy exact-category path digests are: public ranking 10,
`1da80ef16b5779a2d836282f544f6bd15c394f1a48aca6f15571ff90cf2cbec2`;
mounted ranking 2,
`279c141ec90a9a9357dfcc859345c8fa9bfde695d8c1cdc474eedcb0f193b24c`;
Player Research 32,
`f8940e91f6720319efafac20c2e7bba0aa2ac05cc549ed27cf0d34b31e5608d3`;
grade/tier/ranking 32,
`d9e7bbea8e3af63863584ced59fe12f224fe0c6d88cea60785b6214f429fdfc9`;
embedded supports 2,
`ab5b569137fe5a31c31943d8c7ea59ee4ee71fdb92dfd08daca450936f952df9`;
compatibility/parity 23,
`0d61a69cf8b5b4ac530acedecbcf714a427fe03352b95230209d84decc6d1592`.
The 204-file Fantasy union contains five reused D1 pins and 199 added sources;
its all-path digest is
`e8ee81187a70ac8e410d60721d85f912487b7ff23c8ec554f69224f2cbd194ff`,
and the added `sha256  path` digest is
`fe6f72fea18d4f7a7ef2953a3db81f47864f738f16e9dfab0943f48860ccd8c9`.
Forecast has 27 added unique sources; its path digest is
`4197d13912f8987f17b968c540353771cbd58354abf59c941ca7213a57623d9b`
and pin-line digest is
`aec229bd75f1ddb2b23a7e8448596b4a712ce0ccd1a52732ca7642e4f8c8e7a1`.

#### Fantasy complete 204-source union manifest

Sorted by path; format is `SHA-256  path`.

```text
9cdf8ee578262f91069dc26686de4f27ad0e5950b4358c8c378ed8c4815057ef  client/src/App.tsx
82ed4f2a0fbae2a13e4bb1961285cf919df19eb1f785ac8f671c8cd7cfb2fd1a  client/src/api/forge.ts
1ed7eccef0018661ef97a247dc09f99f614d43dc6ebf6d10f4b6eed69bfbaeaa  client/src/components/ForgeRankingsTable.tsx
0d9dd4171e24a296725313d3f99d08a0c50def4c1bf26c789b712adfb6ddddbc  client/src/components/data-lab/PlayerResearchSummaryBlock.tsx
dabb5023fd34ccec5be2f1f1f3e062bcb9db09d564a6ad04d5ae6708ad24e924  client/src/components/data-lab/PlayerResearchWorkspaceView.tsx
408ec0d3a2fa680114b6e8450e57621819fa75bf97761eb1c96773ae50ef6659  client/src/components/player/CompareDrawerContent.tsx
7f4060dba7ac3f4a8f3bca395e211dd79b2f88c599e22651f2e3f1d3fcd3f4c3  client/src/components/tabs/PlaybookTab.tsx
c6c5fe836e4714f397d5ba7302968b78168690bf6f9d697fbb7a37f593e4a38a  client/src/index.css
31f74825a593b14d39817a100098dd611471e5406e9fd58cee96093aa5f4d1aa  client/src/lib/playerResearch.ts
7e20ca83c3a30840b3a56eb41a07ca2531befefeaaf61814cd0e4769ef1a426e  client/src/pages/Architecture.tsx
fc2dc8abe61eba3eaf9b5db131554b31ea8fbfa0c3d268b868dc517f1ec0bf23  client/src/pages/ForgeLab.tsx
21c47a22f9b0eb5c1a79c1e6f6bb08549e51fab6b4556bab4240c9b4a86551b6  client/src/pages/ForgeLabEquationSandbox.tsx
c61ef8c9c6c3754d06a81f82f938852cf9b53324cebcfd56b2943833109bbfb4  client/src/pages/ForgeTransparency.tsx
46787c7aadf6663f611ac91f9fd4f849e09fda8401c08b6b8bdd77fe39147d2d  client/src/pages/ForgeWorkbench.tsx
da9a8a22f94db3b43608d1739a919066bbca545f4df5addc7d61a9bf8ce6c05d  client/src/pages/IdpLab.tsx
0e430cbe85e3ac9b24340803ff6adbdea3596e130189e394c8e6abaccd9259d6  client/src/pages/MatchupsPage.tsx
2f4e47944104fdf99651afc21c4e7c5f019c63f087c573d316e41e8c4b7a3edd  client/src/pages/PlayerPage.tsx
eefc50a188ff68ea869bf455ea4e934151f61fab41ecaa824c75d11e3e0000db  client/src/pages/PlayerResearchLab.tsx
c8fd2fbf05bcbb4e429644b2efa9d845cb4add9c3cafd1dca7add7ea0143f65a  client/src/pages/QBRankingsSandbox.tsx
0c96703db96bf6c4e2ebd84ea1dbb2f5b665b1ec7aaf036af7c945a7d3716996  client/src/pages/RBRankings.tsx
a731c79fa4e01f491516c0c4055940ea7a028d8a53a11435990df238dfe40c88  client/src/pages/RankingsHub.tsx
6a8546e2ab9f465b9782d304c722d6701354169b18b0c8165f870452ca518624  client/src/pages/SchedulePage.tsx
fe9cab99f08839a94c638269f27f0e6245e91b0c574a8833d14ebdd78098fdd0  client/src/pages/TiberClawPage.tsx
6ad708c316431e9b198c4bbc8196584f192548c1f9e3c1ca36da343b0980ce1c  client/src/pages/TiberManagementDashboard.tsx
022a380b2351380c2cb5a0f4871e0b7352dde1ffbcd8eea57429d4315778f964  client/src/pages/TiberTiers.tsx
ec3aad6ed4cabd2da8c2aed58f5a711b9e6a54b0cc3237286df7cc459131ec8f  client/src/pages/WRRankings.tsx
67df815135e42278203caed1b1703ef53b01727fdbd96ef6fa2081d96b28c899  client/src/pages/WRRankingsSandbox.tsx
cba578b3465e484a93f48ea8594cd6e4266bd1107ca14066db1b8e1e0d440b49  client/src/pages/admin/ForgeHub.tsx
42379371e219d35b7b3c966d78f04d775edd22e97cca79c21393493a4df91491  client/src/pages/admin/ForgeSimulation.tsx
7e31b67b2d44880bf392000241e6a4d1080f759b7bb9a695fcd107cdc5aef28b  client/src/pages/admin/HomepageRedesign.tsx
5e7edf6206458aad189c7cdd11e744cfed05a8491dba1265cea461c9b66ee24c  client/src/pages/admin/PlayerMapping.tsx
eef4c9e099c282d265b7c3d37fa8da90b8fd81736e6f0573b3a9e7583980e2a4  client/src/pages/admin/PlayerResearch.tsx
81ffd533fb29cb767746e57a48d380ecc2cabd4077e1445fb0cf373d756e2a7b  client/src/pages/tiberTiersV2Mapper.ts
04cdf822c30d1f056799083c1463360d55f62a4c01bd35587d7ff68ec97239d5  data/role-opportunity/role_opportunity_lab.json
c2731f729dc259df4623a1365003cea8ef79c600b7beeed49816d904375861ba  data/signal-validation/export_manifest.json
8ada53fd96940b1dba3db7e15185a7b763344a70c11191b1e37fbf9cb6b01486  data/signal-validation/wr_best_recipe_summary.json
0eb28e5ac6dbef3db76b271f7f4cadf24cbbdce6f0beb70695779160c574d1d8  data/signal-validation/wr_breakout_candidates_latest.json
b0eab31e12d2fd758a8a1eb7f8102dd5d73bf8db08e524699e25e1aea689212b  data/signal-validation/wr_case_study_summary_2024_to_2025.json
5f0ce56b0be5b884b2ab6e1e83d31df54c095d6d10701162ab55e0864b8dbf1f  data/signal-validation/wr_player_signal_cards_2024.csv
bc5cce17d73908b90a36e95945a869a75b021f9a82a6b8060b41823310432abf  data/signal-validation/wr_player_signal_cards_2025.csv
7b9b0362048d2d9dbe42fa801fb3f75236709fc56e8b0186723c0306ae66b3ba  docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md
46150b195b9f64cc0ae777147d1b6da932416be79c875ed691f6550719dcd786  docs/architecture/TIBER_RANKINGS_V2_DEFINITION.md
60853974aa48a48fd1cf39cc4f27509925c2e949c8cb492e819681e90bbbc693  docs/product/MANAGEMENT_PHASE3_CHECKPOINT.md
4b33815e289da3252246703b650ae03f1b912416c8ace1b6e6e345d194cad087  server/api/trade-eval/index.ts
dd35bd3db44288beb5cb76f7023695a3555799100da3e3584951e1096e5b6453  server/api/v1/routes.ts
cc2254a8d712976184ce370ecc2f932831d65925773b9e5dde924948d9b5cf14  server/artifacts/external/forge/forge_player_static_v1.json
fc1448fd22b99d71160f03f8ea6083c1446ba8dbb6db76e69f3e5828f9d46a70  server/artifacts/external/strategy/dynasty_strategy_ontology_v1.json
af7f56ffdb578254438c52c56dfd482d164d1fa42f415c2b7b00518322729c39  server/contracts/rankingsV2.ts
037bfed8a3429640837db4ca0721065fa0471ac375182e3c943ee168022bf519  server/doctrine/asset_insulation_model.ts
322e937cb3bf0e038e35140594147caa7878864adab82bbd6fe1cb9caa83852b  server/doctrine/league_market_model.ts
cea9be5b8705bf87accddb0b3dd41d79e4e2bc56c5a48013fce05597507d8b33  server/doctrine/positional_aging_curves.ts
126643a7be72ba53bcca786c8ed50f16561dba5f0e68ff62dd7e51b723cd3dca  server/infra/apiRegistry.ts
4a25d7af2e179970c707cc40993b2220616ff11b25abf47e36415f358af342a6  server/integrations/sleeperClient.ts
784527105ec4d9fbe9a0eac470692871117bb27f97397774a3aeb4a551197bca  server/modules/externalModels/MODULE.md
2691aa85c222bee603a8fa9e115ad8905c1dcb406cde66e2e16ea1eda78d7905  server/modules/externalModels/ageCurves/ageCurvesAdapter.ts
5e18ea7c50c4e840a9724a4dd596b4cbe070f9679a41f7b96e28369199e52175  server/modules/externalModels/ageCurves/ageCurvesClient.ts
95a5b0205278d1a933a691714fc955d5d2a4e7f52ada9c0c31f40f4e13bd751a  server/modules/externalModels/ageCurves/ageCurvesService.ts
055a82ac28ac6c29f59c65deed5e49f9ec91c581f11336dc4ebf826f893b7526  server/modules/externalModels/ageCurves/types.ts
f221c76d0daf5dff3e04b9fa645f1b7b71377ee92e302fcc1c78aef47c94d8e2  server/modules/externalModels/artifactFreshness.ts
db98205c71942932d37ed7eaae5712db1a5284685e22f468a0a35d5f44b169da  server/modules/externalModels/forge/README.md
ea923e8d50641fcd8f1c73ac1cfc80e60e1ee824765075a6daeb2762950ea97c  server/modules/externalModels/forge/__tests__/forgePlayerStaticAdapter.test.ts
0b9c61220ee2238c8b8c307097d7aa68995ca3ab6dbf17cc6f2f0a46ecb72c43  server/modules/externalModels/forge/__tests__/forgeService.test.ts
32dcda6404d7401331645947c20650b39d5090236d07b83f9ece37ea3e237c3e  server/modules/externalModels/forge/__tests__/playerDetailEnrichment.test.ts
3b2dafd48312849dfb09783426819a1bfe6244fafb7e65209737bb4bbfa45308  server/modules/externalModels/forge/fixtures/forgeParityFixtures.ts
d3ac2b4440ad50bba00fdff436d2e7fbe8f0e9dbc17a5c911f96ca5d27ca9a8e  server/modules/externalModels/forge/forgeAdapter.ts
08a21850da02be58fd9b7063c71923cf274b702a0f638529e7b7eff836df7d85  server/modules/externalModels/forge/forgeClient.ts
fb71fcf03e3733f8962188143715249f7cc5a6a23a014902b6204024c1f2df18  server/modules/externalModels/forge/forgeCompareService.ts
1d74d8a7bb0d1ae86319676fea62a2d2d4a13fa3ce964f2719f566fbf1deb02c  server/modules/externalModels/forge/forgeMigrationReviewService.ts
c5c9520113af1159b76450e85c03766f2655599ffc1d59a124075de1933e9915  server/modules/externalModels/forge/forgeParityHarness.ts
65dfb540c1aa6bb8f9020870f2848c8515d6d0b192bd70d5d03ee7df6bceda5b  server/modules/externalModels/forge/forgeParityReportExporter.ts
b3201811515b1668af719edb219850051b9e3d177bfbca412bf4d73e0ccbbeaf  server/modules/externalModels/forge/forgeParityReportService.ts
c50821da572ddf9a11c8fcb653e3f07b731c4eeed0fb9ca9edc22da486f1d9f7  server/modules/externalModels/forge/forgePlayerStaticAdapter.ts
73e9ec3b33ba030043c6d01afc2916f86815809b53815e7736b2abf1a53c0238  server/modules/externalModels/forge/forgePlayerStaticClient.ts
8bccdbef23c9051778362288d865fe89b577c2016c2e813867601c7d409b45b6  server/modules/externalModels/forge/forgePlayerStaticService.ts
44ff3ba32cba71b9f33c402199d0bc4226c3e5584713f7ea6c7e8d532508c123  server/modules/externalModels/forge/forgePlayerStaticTypes.ts
c10ac006a88d2bf5b82bdd4d0b082a10e9f02c22a89a6b930efe1341c5b93b1b  server/modules/externalModels/forge/forgeService.ts
83952e7b632bb762a2ca92832f7806d68a5eba2ce63ea365f77a36aa520a1232  server/modules/externalModels/forge/forgeSourceSelector.ts
8d96786ed1c5ba9af4f1096ab3bda5993ce27f4aad12a69b233c700c77accfcc  server/modules/externalModels/forge/playerDetailEnrichment.ts
4bf83b6730b1a93e72f5b8fcadf23386485bc52c765f528d5245f74791cbf1a1  server/modules/externalModels/forge/runForgeParityHarness.ts
abc3630e50746f491717d53a1cdb7f7bbcf3005dfa9d737279bf107ad741d8c0  server/modules/externalModels/forge/runForgeParityReport.ts
56b14188e5efa18d66fef4d6ee29c10146dba7f63e839a12028568af97fe0240  server/modules/externalModels/forge/types.ts
95bebeb57dab857fabb958e5dd37d9bfc5976522933d24a219ad25447e501fe3  server/modules/externalModels/identity/tiberIdentityCrosswalkAdapter.ts
1afde7a296e65e32ca2f3215b52e07419183eabb8ebb6e347e68887b8b738e9f  server/modules/externalModels/identity/tiberIdentityCrosswalkClient.ts
9fa4eb799bbf6ae83ae99af9d6b5779164429351a4b3388f7a49c5a819635e3c  server/modules/externalModels/identity/tiberIdentityCrosswalkService.ts
9ebb1f970745e826329b4d54260a059fe8fab7d25cf013743dcefda12dd04dd3  server/modules/externalModels/identity/tiberIdentityCrosswalkTypes.ts
b04ab26af5d0e62d74cfb8559d0cc376b6a0a762eb1bee4eea6343397037f035  server/modules/externalModels/playerOwnership/playerOwnershipAdapter.ts
bf1eb01c2cbf08a579102f951e04cf8c0258ad28beddf1297bf0610696bf0512  server/modules/externalModels/playerOwnership/playerOwnershipClient.ts
fe4bdd20212e35ef8d7d56a0a9b400b759e2f86913d13e6238a57243900018f4  server/modules/externalModels/playerOwnership/playerOwnershipService.ts
392ed7e83afec5ca5c892d4a2befe40ee064a26b7803484c5e031cef654545fa  server/modules/externalModels/playerOwnership/types.ts
1cf471d7b9f8ee640fab5b2c2344c7ba4511b6df34602d94175933c469aa3801  server/modules/externalModels/playerResearch/README.md
5f617324ade3d746964b5c95ca3c310af4d81833d0eb1a81faa9bba5694fa741  server/modules/externalModels/playerResearch/playerResearchService.ts
568e146f6c8800f9aac6ce9e145c72f7ce8b0f68fb4e7e9de7083f42fa747888  server/modules/externalModels/playerResearch/types.ts
b618af6b8344fc9d340a7a13b7289e016d470369ca27dd1ab0cdab36f3e95d31  server/modules/externalModels/pointScenarios/pointScenariosAdapter.ts
a3ed9027d25a042fb70cf35a20a8f488310922f3ef7213f72efea434f9064d0d  server/modules/externalModels/pointScenarios/pointScenariosClient.ts
8251e275c1d2d5b2eb1c5873dfe8528f4c0327e2245a5d423666d6f9b267b6a9  server/modules/externalModels/pointScenarios/pointScenariosService.ts
04850f640399aeef647d43444da434defc706dacd266172d543f3006c8bee040  server/modules/externalModels/pointScenarios/types.ts
595ce1b188549ef4bd56df3285f6fd5451af5eda280e6f5008d52bd696114ae4  server/modules/externalModels/roleOpportunity/roleOpportunityAdapter.ts
1c9e77c93b8ec1f0b0ba5ba705404b7a725673130061573658f452a3158b5360  server/modules/externalModels/roleOpportunity/roleOpportunityClient.ts
9bfec4d97b8c5447ad3af971b9dd5a480696ba37c3fb49a35795f692ee6d5f77  server/modules/externalModels/roleOpportunity/roleOpportunityService.ts
8a0ab075921114848f3f9aaeaf13e64c5df2b6fd5e1ce0c20338446caf97c9dd  server/modules/externalModels/roleOpportunity/types.ts
fb74367b9742360e06bcdedea5c346503065089e429d73bc77ff59a2e30a724a  server/modules/externalModels/rookies/rookieArtifactAdapter.ts
f95f58041aab8352de1e3c450c8856a8319cc79549b9557d7c54b8ab42a34233  server/modules/externalModels/rookies/rookieArtifactClient.ts
5c75e40c6190fb7e1e7ed9efedae3277f6f9566e4c201f84124cc07a753e6f94  server/modules/externalModels/rookies/rookieArtifactService.ts
0d3309a54d0d1502b76b42bfe8ca38729f79815fdca0a8680f02e93badb5a263  server/modules/externalModels/rookies/types.ts
4ee4c6248e51ac968621ce91c75cf2d75ea64d293cfc032a3a99b44215e46e33  server/modules/externalModels/scoring/scoringRequestMappers.ts
09b6ba5eea21d3d25ee64ccdad393f979fe4c3209cff3476b0b3cb22b25cfc78  server/modules/externalModels/scoring/scoringService.ts
f7b9b6ba622c94bea13c66b6ac73a7ce95bb249993a716700aab15fda933c7d8  server/modules/externalModels/scoring/scoringServiceClient.ts
5d3c85231d23a853feb9320be136223418bcb68735c0a873bd8275a7029c7ee4  server/modules/externalModels/scoring/types.ts
756d32741246c3b4d09277123518ab4aec31f3ba1d5b82c08bc88be8a7e8d59d  server/modules/externalModels/signalValidation/signalValidationAdapter.ts
8fa32f620ca38b38af0cef3f8c5c8278fb3a48a509226a0724982ee4fe951da8  server/modules/externalModels/signalValidation/signalValidationClient.ts
3eee294afb58226c40bc0ff690df16387873fab8b9d01f6f88ab4b248947935c  server/modules/externalModels/signalValidation/signalValidationService.ts
96bf11040814b6dc230736dc6409312ebf6030bbe2301d2bf1dadbf66b84b0a9  server/modules/externalModels/signalValidation/types.ts
080f6eedfcfa51a410bc23a80a85dff41e27703d63f5128f0546a488a41b4081  server/modules/externalModels/strategyOntology/StrategyOntologyIntegration.ts
7b71facdcec9d2c0e7103ae0a72e184da9476c31fd071399abd912b8dfa721b1  server/modules/externalModels/strategyOntology/strategyOntologyAdapter.ts
98e05d04e0878008cca18dea1a637b36fc920b62ba78920bafb7be99d59742e7  server/modules/externalModels/strategyOntology/strategyOntologyClient.ts
37f3e16d74d282617f533d12bff0614b039d68b36deb5790866a362b50b7f333  server/modules/externalModels/strategyOntology/types.ts
32cf08fd7bb6b28813ce2f56a8608d62a1700024d1e0b734df926af40c88cc0b  server/modules/forge/MODULE.md
e02790d253122b034169f2a586af92c2293a151caa7ad67c3ec341f71250cec0  server/modules/forge/__tests__/alphaEngine.test.ts
9a8845e255a63913d64174a8ff955e7391b353a6fe418dbcf17bfbdb36ec2df7  server/modules/forge/__tests__/contextModifiers.test.ts
cc1241ef58bbd4febb7d6b681550edd6c1094fcb114994f509eea29dcb844794  server/modules/forge/__tests__/forgeEngine.test.ts
e5130ca45bbefd2673d85559f48b3678e2a6aba5a73948c7e3ebe2224bca0b32  server/modules/forge/__tests__/forgeIntegration.test.ts
66fd79614e5a8cbd98c0c4bb4202782f928316e9fef307365f6f6c12f4011ca1  server/modules/forge/alphaEngine.ts
663e768f1bbfeb72f641e72eaef66594e0ab58b6ed63e160deb46c12c8e2d9de  server/modules/forge/alphaV2.ts
e2c0431986981d1fb9c65fd6db9b6873c3caf06ee5dd298055771d71c175ff7a  server/modules/forge/context/contextFetcher.ts
53aa146ee4502c3cd607a201b364b1084e5f1b6bc21015c4c67ea192037b58e7  server/modules/forge/contextModifiers.ts
0ba8170764f3ea33a672ec49ab9a1e71bcd96a47aec633bc8ff0c90b95122454  server/modules/forge/dvpMatchupService.ts
a9dfb6eddcfe35596b13e588f98432f8f4c1d90a2c6c340c7326a17a65561e51  server/modules/forge/envMatchupRefresh.ts
beb7b3a6dd907c6082c060b7a78176b00effd07e93bfcc7f3a4c93fdb00ca958  server/modules/forge/environmentService.ts
d5b0974fd72c2980e1310e67904e99d8d58b64fc10820ecfc607423bd97cb69b  server/modules/forge/features/qbFeatures.ts
4f3fb2b4da8371a55dc478f53db085093a447cb3d55e06cf570e89a4cb948822  server/modules/forge/features/rbFeatures.ts
13ef434f23a42b6f5271839468d952a4874f6ac1d8b9d0abc5c98e67af34b9a4  server/modules/forge/features/teFeatures.ts
e59ff745488972d7962066ede7c958b746d02f7ac2aa913b91bbd3d2a55910ba  server/modules/forge/features/wrFeatures.ts
10d3e22c5e8fce14b571775a40c958b62329ae7610d6d82b840fa6d356a78cf1  server/modules/forge/fibonacciPatternResonance.ts
ebe8bf6aa3944388febaa367be6265e580870b509f68373fb708a9d8a67fac57  server/modules/forge/forgeAlphaModifiers.ts
76f6f8dad0ee9617dca552cb927dd90fffb370ac7f6f318fbba0a9415422a2a2  server/modules/forge/forgeEngine.ts
85daa3ed575f685f5875b4e24d638ffa3193fb4509afadb2beec2cb5fdbe5d8a  server/modules/forge/forgeFootballLens.ts
4b0fcc912912ec36a2f64918f94a5783ef2127ec796522f7d5e4f75152c30c24  server/modules/forge/forgeGateway.ts
c2df033a3da3c5aacd6de9d4f73696bbfdaa921c485372813f9ed75ea7acaa26  server/modules/forge/forgeGradeCache.ts
15c57e5489eac38ee830205a1c0b9f196675f34f2ce062f75f52892c001c7057  server/modules/forge/forgeGrading.ts
35244155cacb1a755f74f31bf5cca523d0b0434debac91dbecb3a2dcfb3944e2  server/modules/forge/forgePlayerContext.ts
063ed09a09689d94f4d209145e198a69cec76038686a3d61ad8995fe5dcf16d0  server/modules/forge/forgeService.ts
7ca51249884ff59bf81d407ce886b6a0cf81380d427402f9f4cd89225b04b4be  server/modules/forge/forgeSnapshot.ts
a6bbee6f8618b47ebf00b06d9e02fd26ff06a0e4f6990fb2fe74d13f995e5c8c  server/modules/forge/forgeStateService.ts
f52cac39ea88083c3a34cb77745cfdad0e14c85abb3fa78d705459443a1abc8e  server/modules/forge/helpers/sosMultiplier.ts
16ff8b11af871c2600abb51c2c5443e8ac2e2d93f6f2e48f2afea145a223a4c2  server/modules/forge/idp/idpBaselines.ts
870d20cdc8e149f6f998d5fef463e201d07ea7fb6457b74e702bb894072ca13f  server/modules/forge/idp/idpCalibration.ts
4117ec5ef73c6c7b56be4197b2ea538ca40e13c75928daf60e4535e664e395ac  server/modules/forge/idp/idpForgeEngine.ts
8259cdbbc30d8fe5e9e934be3f5ea87f93aca3513e81a1f94676f1c7d3fc5200  server/modules/forge/idp/idpForgeRoutes.ts
e0bb944adbfd2e864e16b01a1fe7ee130498e5d1003300187c07ded4e5d48c62  server/modules/forge/idp/idpIngestion.ts
4836a63e0026d8d04b465537d10461a3aa759cba5a0d9f3e0789917fab5de04d  server/modules/forge/idp/idpPillars.ts
fcb2da23ef01a023eb62ef7157c33710a3383227786aebb1a4ae4592de7a70af  server/modules/forge/idp/idpTeamContext.ts
52f083d9da0314119dbd8356affe57c3ab7cc94d08855e8d99c613fd27bd03c5  server/modules/forge/index.ts
42b90d584347d1336ba8337435377e53a0f73e7ab79167977a2ce7f24da9cd3a  server/modules/forge/matchupService.ts
b2f96c04669abd17f52fe1e01edb8b29d9fea39da59d6ecc3def2ca31e95df28  server/modules/forge/qbContextPopulator.ts
1338f2d90ac06d8ae2076a99054deefa2f73ca2a1dfb833a87ecea41afba8c90  server/modules/forge/recursiveAlphaEngine.ts
c2535df106c6b444b25d37a5436b1fd4912d066237e50cc551d7895c8fcff155  server/modules/forge/robustNormalize.ts
97a23d203eba6dfe4d33fe5f7f41b3a10275c8ca1c2f8e765870aa79898315da  server/modules/forge/roleConsistencyPillar.ts
fd4f9df876c5610a0d317eda3b5e45aa94a9759acf8071d422f1ce20b20afc07  server/modules/forge/routes.ts
469eaec10ac7e45f3ddc676d0557e542b060014fd99324d5a9ca91d5fe826d53  server/modules/forge/simulation/forgeSimService.ts
4bcd33ef2221ab3095c451a4143b1a852cd89abbc6f4a14481fc6d3c29a7679f  server/modules/forge/snapshotDataValidator.ts
9196ab041582931ddd97525351876af97b0e048a0273871d18d7952e8b9d9ff4  server/modules/forge/sosService.ts
aa08baa1a7feac1e2b8d2179bbb0ff08ce651cce42f6af05daffb43b9d011046  server/modules/forge/tiberTiers.ts
b75e81fec84a534d45db934a6f48388f2736848504c7baf394423d62a167cc03  server/modules/forge/types.ts
585f63e3b66770548b04c680228da6d5af3e2b1f54e020059869da08ba071354  server/modules/forge/utils/playerIdResolver.ts
05700e0e0ec157f18f7b4f4a3165b5c329a6f95655256c801bf9013a423b0a56  server/modules/forge/utils/scoring.ts
59a8654b78b700edd1525726b98c228657a7b43be7bacd557f92b1348abe6c4b  server/modules/forge/xfpVolumePillar.ts
cd1d5a8e63bb335b171fd4e15bdd5ec7bcdd424c05d1824d74e386b209376bbd  server/modules/management/forgeEvidenceActivationDiagnostics.ts
25924bbaa4864c4e7efe14f391a055d514ac5ce45669ea53081193eb7cffbacf  server/modules/management/managementGateEvaluator.ts
450fca062d45477afa0ded2e601dac96b9e4c838c46c230c7aed95b552ee2512  server/modules/management/strategyContextActivationDiagnostics.ts
ae9f414743b2b41277325b5331b55e1f26165dc4e45aa8ae66973a57d610a161  server/modules/metricMatrix/tiersNeighborsService.ts
0c859f4f4a3325d46073c5fb072cfe2b924b4f21bdc4c992a507f811a674ce21  server/modules/sos/MODULE.md
495eff9a1df8f701843587600e3a963ea38b3a7230316d7a630de210c6aa9f1b  server/routes.ts
48719eb9063e3970c8a2668b737cb6095a97caebf7423f42753f1d8f64b276c6  server/routes/__tests__/apiSmoke.test.ts
361a8422c3a93fcae355686aa7d99f5b7346f7dc6cf937163639df9b4cf27979  server/routes/__tests__/rankingsV2Routes.test.ts
931de1b9711437e92f0a934b8c48e43545b8e1d04e9d8448abe178ab1b471794  server/routes/dataLabPlayerResearchRoutes.ts
6c4309501be8250342045af75f0e2765f08daea60b6380d1e91fdfabc0d222cf  server/routes/fireRoutes.ts
f98735429816b46c47fae203adf8d6334365897635baf026ed833528d0531d2e  server/routes/forgeIntegrationRoutes.ts
63ebb45f2626c10e4f139e48066e46c0789467933de217df147016b72cacd290  server/routes/forgeSimRoutes.ts
ae8706ee0f58c1aa0268df4113e1e0b1ffc6f043d2b85101942b77d8cbdba671  server/routes/idpAdminRoutes.ts
6c339ab5c8e8a148c86ece183c2304b10948db191651f632b810d696988d67b6  server/routes/managementRoutes.ts
5bcc2b41844ce110e2b05a2003d30424699c43f07082ba198c725c40b8534a00  server/routes/playerMappingRoutes.ts
a4bb800f0f161f547630bd76aed518bdfee4e37aaa32704f5231b8e682ae72c1  server/routes/rankingsV2Routes.ts
e39e4d3e31d12641a39fa45ee7c282804efa4ed84b335a545e731dbd7dca66d1  server/routes/strategyRoutes.ts
366c00d7f09e4d14f4d49b79e9d01989ecce8dab947d0252ef2bdb7d28af1b98  server/scripts/backfill2025TiberScores.ts
37590754efda293dfb12479195eebd07a4b05c1cc482d2c0eb3bbafe7a0beee7  server/services/__tests__/leagueDashboardService.test.ts
74901ce68d0b8cacc8006fc793c0efb0dabd56c1b92ae564802ea3acb4fdecdf  server/services/forgeContextLoader.ts
4e91dc7bbe1e8b090cb6fd6a65b0f64be8ef4f9cb89b4d43c7f851757cb6f486  server/services/forgeRebuildService.ts
db0c783ace66f59267ba93480a586270f1b22c8515cb5825ac0c872ecc6e4ba2  server/services/leagueDashboardService.ts
57851cfa2d4f94d054c937118ca23d934384cc2c84a60a8188440b79b6113657  server/services/system/featureAuditService.ts
bfc75b6c51f27bb05b326a867f295b7fb35443d67106ac22d47b2cd9565d4641  server/services/teamDirectionClassifier.ts
397a7c4ecdfe6cf162c5d8f1b239266c603a2997cb7ec7b10eda5afe32eb7e8b  server/services/trade/tradeLogic.ts
4fab11a53c4b4a78673a0d18c5dd9a1de11cb69a7a7bc4046353501bddce0e7c  server/services/xFptsConfig.ts
af5e3cc0e816ed53d6835f1e19963780a2023658f51100491dcf39f6a74ab4fa  server/storage.ts
b62da4fd129e26de90a9aefa6a31ee9e9509455cc5330394218ecff429ee068d  server/tests/forgeCalibration.spec.ts
db42126b5937b454a94f192fed2896b8cb08c688690b6a935f548b86f248a031  server/tests/forgeGuardrails.spec.ts
871470d8e0377989b9248d8adfc954f94061ff4f62b4131bc1eeebeda9d01efc  server/utils/playbookForgeLogger.ts
7fa1710ec1613254155a54ddeacaadad049f79220d98fc82eed853ae85ec8c28  server/voice/deciders/trade.ts
6c435c686583f757c86ef276a6d0bb56ca7b4214165e7ba6fb887f9407c0e142  shared/idpSchema.ts
f35fdeb928929c7fb95f3d1b02e04446e38af349a4ada3e1fc686aa1134020d4  shared/managementActivation.ts
867f973c930b5565933be18c7b39ef276a414e80dfafab1dfc03f09a0bbc0f8d  shared/managementGateEvaluator.ts
0d9020a668a3819172e7f6f8ac98f5a1da6a81bc740b57bb70021a15933620f4  shared/managementStrategyContext.ts
6c1523cfa4ea7682431c0d994a9aae3edadca77ccee6a77ccd6010d10065f4ec  shared/schema.ts
7c48f004aba208a62a2691ce19bee7494525358e6909da6042cf036b5a0a9c58  shared/strategyTemplateDiagnostics.ts
3dac3659ccd89bc9c47844dc7a19fde40b5ac2c6cd52efd7adaa99ad73d41a38  src/data/providers/context.ts
```

#### Fantasy dynamic path manifests

The per-file pins are in the 204-source union above.

##### `data/signal-validation/` — 6 committed files

```text
data/signal-validation/export_manifest.json
data/signal-validation/wr_best_recipe_summary.json
data/signal-validation/wr_breakout_candidates_latest.json
data/signal-validation/wr_case_study_summary_2024_to_2025.json
data/signal-validation/wr_player_signal_cards_2024.csv
data/signal-validation/wr_player_signal_cards_2025.csv
```

##### `server/modules/forge/` — 46 committed non-test files

Only paths beneath `server/modules/forge/__tests__/` were excluded.

```text
server/modules/forge/MODULE.md
server/modules/forge/alphaEngine.ts
server/modules/forge/alphaV2.ts
server/modules/forge/context/contextFetcher.ts
server/modules/forge/contextModifiers.ts
server/modules/forge/dvpMatchupService.ts
server/modules/forge/envMatchupRefresh.ts
server/modules/forge/environmentService.ts
server/modules/forge/features/qbFeatures.ts
server/modules/forge/features/rbFeatures.ts
server/modules/forge/features/teFeatures.ts
server/modules/forge/features/wrFeatures.ts
server/modules/forge/fibonacciPatternResonance.ts
server/modules/forge/forgeAlphaModifiers.ts
server/modules/forge/forgeEngine.ts
server/modules/forge/forgeFootballLens.ts
server/modules/forge/forgeGateway.ts
server/modules/forge/forgeGradeCache.ts
server/modules/forge/forgeGrading.ts
server/modules/forge/forgePlayerContext.ts
server/modules/forge/forgeService.ts
server/modules/forge/forgeSnapshot.ts
server/modules/forge/forgeStateService.ts
server/modules/forge/helpers/sosMultiplier.ts
server/modules/forge/idp/idpBaselines.ts
server/modules/forge/idp/idpCalibration.ts
server/modules/forge/idp/idpForgeEngine.ts
server/modules/forge/idp/idpForgeRoutes.ts
server/modules/forge/idp/idpIngestion.ts
server/modules/forge/idp/idpPillars.ts
server/modules/forge/idp/idpTeamContext.ts
server/modules/forge/index.ts
server/modules/forge/matchupService.ts
server/modules/forge/qbContextPopulator.ts
server/modules/forge/recursiveAlphaEngine.ts
server/modules/forge/robustNormalize.ts
server/modules/forge/roleConsistencyPillar.ts
server/modules/forge/routes.ts
server/modules/forge/simulation/forgeSimService.ts
server/modules/forge/snapshotDataValidator.ts
server/modules/forge/sosService.ts
server/modules/forge/tiberTiers.ts
server/modules/forge/types.ts
server/modules/forge/utils/playerIdResolver.ts
server/modules/forge/utils/scoring.ts
server/modules/forge/xfpVolumePillar.ts
```

#### Fantasy fixed-token scan — 90-path F0 disposition

This is the §4.1 static F0 disposition, not F1 consumer-demand analysis and not a product-priority/survival claim. `mounted product` means a current static route/import chain was observed; `admin/experimental` includes mounted admin/lab/workbench/script paths; `server-internal` is implementation/support code beneath mounted server entry points; `compatibility` is the externalization/parity/legacy bridge; `unmounted` means no mounted static entry was found in the closed source tree. Counts: mounted product 15; server-internal 19; compatibility 12; admin/experimental 16; unmounted 12; test-only 12; docs-only 4.

| Disposition | Path |
|---|---|
| admin/experimental | `client/src/api/forge.ts` |
| unmounted | `client/src/components/ForgeRankingsTable.tsx` |
| mounted product | `client/src/components/player/CompareDrawerContent.tsx` |
| unmounted | `client/src/components/tabs/PlaybookTab.tsx` |
| mounted product | `client/src/index.css` |
| mounted product | `client/src/pages/Architecture.tsx` |
| admin/experimental | `client/src/pages/ForgeLab.tsx` |
| unmounted | `client/src/pages/ForgeLabEquationSandbox.tsx` |
| mounted product | `client/src/pages/ForgeTransparency.tsx` |
| admin/experimental | `client/src/pages/ForgeWorkbench.tsx` |
| admin/experimental | `client/src/pages/IdpLab.tsx` |
| unmounted | `client/src/pages/MatchupsPage.tsx` |
| mounted product | `client/src/pages/PlayerPage.tsx` |
| admin/experimental | `client/src/pages/QBRankingsSandbox.tsx` |
| unmounted | `client/src/pages/RBRankings.tsx` |
| unmounted | `client/src/pages/RankingsHub.tsx` |
| mounted product | `client/src/pages/SchedulePage.tsx` |
| mounted product | `client/src/pages/TiberClawPage.tsx` |
| mounted product | `client/src/pages/TiberManagementDashboard.tsx` |
| mounted product | `client/src/pages/TiberTiers.tsx` |
| unmounted | `client/src/pages/WRRankings.tsx` |
| admin/experimental | `client/src/pages/WRRankingsSandbox.tsx` |
| admin/experimental | `client/src/pages/admin/ForgeHub.tsx` |
| admin/experimental | `client/src/pages/admin/ForgeSimulation.tsx` |
| unmounted | `client/src/pages/admin/HomepageRedesign.tsx` |
| admin/experimental | `client/src/pages/admin/PlayerMapping.tsx` |
| admin/experimental | `client/src/pages/admin/PlayerResearch.tsx` |
| unmounted | `server/api/trade-eval/index.ts` |
| mounted product | `server/api/v1/routes.ts` |
| compatibility | `server/artifacts/external/forge/forge_player_static_v1.json` |
| server-internal | `server/artifacts/external/strategy/dynasty_strategy_ontology_v1.json` |
| server-internal | `server/doctrine/asset_insulation_model.ts` |
| server-internal | `server/doctrine/league_market_model.ts` |
| server-internal | `server/doctrine/positional_aging_curves.ts` |
| server-internal | `server/infra/apiRegistry.ts` |
| docs-only | `server/modules/externalModels/MODULE.md` |
| docs-only | `server/modules/externalModels/forge/README.md` |
| test-only | `server/modules/externalModels/forge/__tests__/forgePlayerStaticAdapter.test.ts` |
| test-only | `server/modules/externalModels/forge/__tests__/forgeService.test.ts` |
| test-only | `server/modules/externalModels/forge/__tests__/playerDetailEnrichment.test.ts` |
| compatibility | `server/modules/externalModels/forge/forgeCompareService.ts` |
| compatibility | `server/modules/externalModels/forge/forgeMigrationReviewService.ts` |
| compatibility | `server/modules/externalModels/forge/forgeParityReportService.ts` |
| compatibility | `server/modules/externalModels/forge/forgePlayerStaticAdapter.ts` |
| compatibility | `server/modules/externalModels/forge/forgePlayerStaticClient.ts` |
| compatibility | `server/modules/externalModels/forge/forgePlayerStaticService.ts` |
| compatibility | `server/modules/externalModels/forge/forgePlayerStaticTypes.ts` |
| compatibility | `server/modules/externalModels/forge/forgeService.ts` |
| compatibility | `server/modules/externalModels/forge/forgeSourceSelector.ts` |
| compatibility | `server/modules/externalModels/forge/playerDetailEnrichment.ts` |
| docs-only | `server/modules/forge/MODULE.md` |
| test-only | `server/modules/forge/__tests__/alphaEngine.test.ts` |
| test-only | `server/modules/forge/__tests__/contextModifiers.test.ts` |
| test-only | `server/modules/forge/__tests__/forgeEngine.test.ts` |
| test-only | `server/modules/forge/__tests__/forgeIntegration.test.ts` |
| server-internal | `server/modules/forge/alphaEngine.ts` |
| server-internal | `server/modules/forge/envMatchupRefresh.ts` |
| server-internal | `server/modules/forge/forgeEngine.ts` |
| server-internal | `server/modules/forge/forgeGateway.ts` |
| server-internal | `server/modules/forge/forgeGradeCache.ts` |
| server-internal | `server/modules/forge/forgeGrading.ts` |
| server-internal | `server/modules/forge/forgeService.ts` |
| server-internal | `server/modules/forge/forgeSnapshot.ts` |
| server-internal | `server/modules/forge/index.ts` |
| mounted product | `server/modules/forge/routes.ts` |
| server-internal | `server/modules/forge/types.ts` |
| server-internal | `server/modules/metricMatrix/tiersNeighborsService.ts` |
| docs-only | `server/modules/sos/MODULE.md` |
| mounted product | `server/routes.ts` |
| test-only | `server/routes/__tests__/apiSmoke.test.ts` |
| test-only | `server/routes/__tests__/rankingsV2Routes.test.ts` |
| mounted product | `server/routes/fireRoutes.ts` |
| compatibility | `server/routes/forgeIntegrationRoutes.ts` |
| admin/experimental | `server/routes/forgeSimRoutes.ts` |
| admin/experimental | `server/routes/idpAdminRoutes.ts` |
| admin/experimental | `server/routes/playerMappingRoutes.ts` |
| mounted product | `server/routes/rankingsV2Routes.ts` |
| mounted product | `server/routes/strategyRoutes.ts` |
| admin/experimental | `server/scripts/backfill2025TiberScores.ts` |
| test-only | `server/services/__tests__/leagueDashboardService.test.ts` |
| server-internal | `server/services/forgeContextLoader.ts` |
| admin/experimental | `server/services/forgeRebuildService.ts` |
| server-internal | `server/services/leagueDashboardService.ts` |
| admin/experimental | `server/services/system/featureAuditService.ts` |
| unmounted | `server/services/trade/tradeLogic.ts` |
| test-only | `server/tests/forgeCalibration.spec.ts` |
| test-only | `server/tests/forgeGuardrails.spec.ts` |
| unmounted | `server/voice/deciders/trade.ts` |
| server-internal | `shared/schema.ts` |
| unmounted | `src/data/providers/context.ts` |

#### Forecast five TypeScript directory manifests and supplemental pins

##### `src/services/scoring/` — 8

```text
e72ad65a055a8756b06340392b2e3ea0910cc5392fed8eb14b2f91d1e9e134da  src/services/scoring/buildTiberViewsService.ts
1a97aa399e482a71656dbbf39c1aa760561c14307ea213cb4ac47be338546164  src/services/scoring/generateReplacementBaselinesService.ts
93f8f85b3d9a84a811e2e3f5229faff587a689314c2c6d695f17b5d3d89ec32c  src/services/scoring/rankWeeklyScoringService.ts
13b61ec2d0d5fb0f73d2c891423cbffdef13d26e7217f8a8b6fd3d47610c92da  src/services/scoring/resolveReplacementPoints.ts
359375f0f9f0414757d7bbd64017aa02519a56f4503ffe3023b9ed86eccac735  src/services/scoring/scoreRosService.ts
13cd53b18bd2a1739e166c072582793410730a3b443249baaae5cddbb408c2ea  src/services/scoring/scoreWeeklyBatchService.ts
f21b0fb2d35c314b0375bb00d4c7ce5befe7f02ff633f9a02ed0c845a0cb30cc  src/services/scoring/scoreWeeklyBatchWithOverlayService.ts
c7062315a19bf539b7485d415c66596dfaa09df0a99f71509c03ecbc0fbe73c2  src/services/scoring/scoreWeeklyPlayerService.ts
```

##### `src/calculators/range/` — 2

```text
74202b1279a75c09dcc53c009626172e97f8ea9ac277113a6015307359b44f31  src/calculators/range/calculateRangeProfile.ts
5c9e46be8393479321d4b4f1902014e737abf75c0294389785606fca3695b944  src/calculators/range/calculateStabilityScore.ts
```

##### `src/calculators/replacement/` — 2

```text
d7a2f47b01dd8f779d8f8cdaaf1c26e04bb4e4a50e21b926b35053b817ad8daa  src/calculators/replacement/buildDefaultReplacementPoints.ts
342d2ab3ebc5949323fe0e25f9ed4d260a59086a478053f9cf954639276ac016  src/calculators/replacement/calculateReplacementBaselines.ts
```

##### `src/calculators/vorp/` — 1

```text
6578b1760cd7e073334c0adbd2a9229ec6e6ff1e3cc9f72a21eb144e9cf4f4bf  src/calculators/vorp/calculateVorp.ts
```

##### `src/calculators/xfpg/` — 4

```text
d2c7f04dddf867a0c197bf33258f3a053dbc13e57ca5cb9fb66807fcfd6932af  src/calculators/xfpg/calculateExpectedPoints.ts
452e01ce0f7201f7fdfe7cbdeac77f6c1727d2993b145e9742a004ef7711ac96  src/calculators/xfpg/calculatePassCatcherXfpg.ts
9923b70c7930ab448fa63434df899f4e61c11d246fd51373df5b03003073773f  src/calculators/xfpg/calculateQbXfpg.ts
b70a70e36ebee5e3e8c02081c1b69b33d4cb99b9bb39902aea197deedb5120df  src/calculators/xfpg/calculateRbXfpg.ts
```

##### Complete 27-source added-supplemental union

```text
2639d5acb11e8d77400700e814ad9c50dba9bf0a46f3f80413e4f0d51860aaa6  data/fixtures/tiberRookies/ROOKIE_TRANSITION_PROFILE_V0_MIRROR_PROVENANCE.json
ed3ffe68bd49a6a013cb1f70ce348f43bbe5597a4c0a9c101076bb22fd71cda6  docs/decision-board.md
3792da358b92011df04b21819e59b117a1c242a652baa74c813727df42355090  docs/experiments/rookie-transition-profile-forecast-consumption-design-2026-07-11.md
dce95053453b1db4e6c79a60dd4df2cf288457c220b64db3405bb3ef1d62aff3  src/api/routes/decisionBoard.ts
8835efc309a75fcff006362ef6296c12ed821c4aaf77c3c571a98b286a56a148  src/api/routes/tiberScoring.ts
74202b1279a75c09dcc53c009626172e97f8ea9ac277113a6015307359b44f31  src/calculators/range/calculateRangeProfile.ts
5c9e46be8393479321d4b4f1902014e737abf75c0294389785606fca3695b944  src/calculators/range/calculateStabilityScore.ts
d7a2f47b01dd8f779d8f8cdaaf1c26e04bb4e4a50e21b926b35053b817ad8daa  src/calculators/replacement/buildDefaultReplacementPoints.ts
342d2ab3ebc5949323fe0e25f9ed4d260a59086a478053f9cf954639276ac016  src/calculators/replacement/calculateReplacementBaselines.ts
6578b1760cd7e073334c0adbd2a9229ec6e6ff1e3cc9f72a21eb144e9cf4f4bf  src/calculators/vorp/calculateVorp.ts
d2c7f04dddf867a0c197bf33258f3a053dbc13e57ca5cb9fb66807fcfd6932af  src/calculators/xfpg/calculateExpectedPoints.ts
452e01ce0f7201f7fdfe7cbdeac77f6c1727d2993b145e9742a004ef7711ac96  src/calculators/xfpg/calculatePassCatcherXfpg.ts
9923b70c7930ab448fa63434df899f4e61c11d246fd51373df5b03003073773f  src/calculators/xfpg/calculateQbXfpg.ts
b70a70e36ebee5e3e8c02081c1b69b33d4cb99b9bb39902aea197deedb5120df  src/calculators/xfpg/calculateRbXfpg.ts
0a340deef30a8be23d086eac08291d4dce4ab414079e57123cccc862648c546a  src/contracts/scoring.ts
75b08deef88a5140a8cb511d90c84ec1c8dabcecfbe7ccc7323da008e558c8fb  src/contracts/tiberScoring.ts
d243ceae098bace14350fb19da8eab0f2a9e0cc5a46bd96ae0b6922f1c581ee7  src/core/scoringSystem.ts
94ac69e6a0c7096fcb986def83a74ec05ca9ba92e27eed47a2366deb5a6d4e23  src/services/result.ts
e72ad65a055a8756b06340392b2e3ea0910cc5392fed8eb14b2f91d1e9e134da  src/services/scoring/buildTiberViewsService.ts
1a97aa399e482a71656dbbf39c1aa760561c14307ea213cb4ac47be338546164  src/services/scoring/generateReplacementBaselinesService.ts
93f8f85b3d9a84a811e2e3f5229faff587a689314c2c6d695f17b5d3d89ec32c  src/services/scoring/rankWeeklyScoringService.ts
13b61ec2d0d5fb0f73d2c891423cbffdef13d26e7217f8a8b6fd3d47610c92da  src/services/scoring/resolveReplacementPoints.ts
359375f0f9f0414757d7bbd64017aa02519a56f4503ffe3023b9ed86eccac735  src/services/scoring/scoreRosService.ts
13cd53b18bd2a1739e166c072582793410730a3b443249baaae5cddbb408c2ea  src/services/scoring/scoreWeeklyBatchService.ts
f21b0fb2d35c314b0375bb00d4c7ce5befe7f02ff633f9a02ed0c845a0cb30cc  src/services/scoring/scoreWeeklyBatchWithOverlayService.ts
c7062315a19bf539b7485d415c66596dfaa09df0a99f71509c03ecbc0fbe73c2  src/services/scoring/scoreWeeklyPlayerService.ts
2428044ab00f6b5f4492c44836e0fb4ef178f225e289eabab2248d4341df77e2  src/transforms/tiberScoring.ts
```

#### FORGE, Data, and Rookies supplemental manifests

Verification time for these raw Git blobs was
`2026-07-16T20:18:52Z`. Reused D1 rows retain their accepted Entry 4
authority records. Added FORGE code uses group `G-CURRENT`:
`current_implementation_self_description`, authority ref FORGE
`af2ca4d5f67f04ed1fc58fef50051c8169545d11` plus `AGENTS.md` and
`TRUTH_SOURCES.md`, authoritative only for current committed service,
contract, ingestion, and compatibility behavior, and not for future
ownership, survival, production completeness, or direction. FORGE docs,
scripts, and fixtures use `G-HIST`:
`historical_implementation_evidence`, authoritative only for recorded
design/bootstrap/parity evidence and not cutover readiness or future
disposition. Both have `supersession_status: none_found`; their selection is
tied to F3/F5/F6.

Added Data rows use `D-CURRENT` and Rookies rows use `R-CURRENT`, both
`current_implementation_self_description` at their exact F0 commits plus their
applicable `AGENTS.md`. They are authoritative only for the current committed
contract/artifact bytes and declared metadata, not for future synthesis owner,
consumer admission, complete availability, or direction; both record
`supersession_status: none_found`. Their selection is tied to F1/F2/F4.

```text
TIBER-FORGE @ af2ca4d5f67f04ed1fc58fef50051c8169545d11
c12bcd8e099474c09dc3ca51fba70a0c9e1f068dc2b0fb72d89fe5ace568173f  README.md
39dd805cc37efb98c15b8eb63f035489b56277412f4e8b2f81a6ccf9cf159a59  docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md
326b976db68be587828f25e2ae5d2c51cf52043e243fc84862379566a789aed3  docs/forge-player-static-v1.md
2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041  exports/promoted/forge_player_static/forge_player_static_v1.json
a8f36c9483f145dd850aec4f7fd8a00e9092ec0b78396115b6b4d181fcd34008  scripts/build-player-static-artifact.js
778a987fa34d7703d887694498d6d61ad67d3b18e7ef154851cc5c61699af0dd  src/adapters/forgeWeeklyPlayerInput.ts
983f096840ffef7262ec0695695e74eb79eaef26fd621a4638e68c5637d71240  src/app.ts
d586938a1aac61edfa7dbf0ebe2d67ea94da46c3b02e6ab933c41c0756f3c47c  src/config/env.ts
453693f1bd069326b4266ed3346443bdee729a109face215c8d8a3c7f8adc68d  src/contracts/football.ts
ceeb45ee9833166d1192b25919b9b3ee24612f38af8a39ecea638656a45689a5  src/contracts/forge.ts
f78c350131c306b1cbb8fa0ee6658a0223fb2a918a62ba9b8dbffd25614479d4  src/contracts/sourceBackedCohort.ts
483bfdc7058f9f747311047d10bd9e8fe2ae4e83df15a930eafb189e8db99b94  src/contracts/validation.ts
8869937f98180cfff6460aaa49f2102b18f95ec0484dc4caba6b7cad2013da6d  src/ingestion/forgeSeasonArtifact.ts
37347f3948835447f05b0bc9329872474bc14250455af6866a849ecb68d321e6  src/ingestion/forgeWeeklyArtifact.ts
f3a0d57d2501ce287b58f4985ca3c8f1817fdd3f2620c8849da3ee580d0e7824  src/ingestion/sourceBackedCohortArtifact.ts
74d69d03308444ae4bdf6651c16e6752a4636c8f7ccaf1e9e730c2510390b46b  src/openapi/document.ts
da5b1607e2feab0b8bdf87532d93cc47686f654d96078285728dd0829dfa7b05  src/server.ts
02654fb90bedd9cb9dafd4e5ba7089b2dc48677b5817db119d8dadc9e419fdb4  src/services/footballForgeService.ts
41e4b4d0682b26a899c93692c26911558a1d358cb53f7f465c6dbac7266e4eec  src/services/forgeService.ts
bdb6f76418e99a7447824a4962966dba2663d23c392f29899ffb6d2378c3e4a9  src/services/playerStaticArtifactService.ts
ca08f07b98d64b5d11846860910d14f221209bcb8e00381dac8763fe10e9c8c7  src/services/seasonForgeService.ts
cb137e255156cbd1bc813b60c5acf84e0b5ad42af9fffcbcee53bb153fad4708  src/validation/sourceBackedCohort.ts
f424be0728636fca3ea880716b6feecb33ccabf1803ff33ba43932b40a966687  tests/fixtures/artifacts/forge_player_weekly_ppr_2025.cohort.v1.json
c4959195ed48be1bfa861eecb80f43e1bea6beea21d30d073665679a37ee7cd6  tests/fixtures/artifacts/forge_player_weekly_ppr_2025.management_mapped_source_backfill.v1.json
33f6c89b66c8733c49aead6f184419646b11a1bb7f892b59d9eee16ddbe5fe42  tests/fixtures/artifacts/forge_season_player_input_2025.real_players_sample.json

TIBER-Data @ a7c059412806470a9e0b89889cd85f01cf7aace9
76a9ae28e5210123996d683f51beeceb321a97a1d5c6f3b899dbad3db8d83e58  docs/governance/architecture/tiber-architecture-document-v1.0.md
c1df7ea4d628b2b1b7466e1ab35a0db12871c03770d86b60d8da33ab5c0bd9a9  docs/repo-boundaries-and-feedback-loops.md
5ce5cd3f5dc8fd27c28c5a5fb283431ac648f764c3f8f2b645f6ad924338f263  exports/promoted/identity_crosswalk/tiber_identity_crosswalk_v1.json
d45f612b207085df00b4b080e4f55ce1abbd060dcbf30b0bee777ff833ddd8ac  exports/promoted/nfl/player_season_coverage_v0.json
6aee8de0d174371b42c82d548353ded0475d9383493d79bb171fd2adb2ebd53e  exports/promoted/player_ownership/events/player_ownership_events_2026.jsonl
b781f9a098ca6490bb8ae97601c9d7d233b054813c2fa0d7839d85a30eb7552a  exports/promoted/player_ownership/player_ownership_aliases.json
179a20410dac7d4b148966b2e577971ca4cad2da859cdaa397fde76461d5ccb7  exports/promoted/player_ownership/player_ownership_latest.json
da7189ce7d067556b9b7a7510151fb0e0d775fe8feeebc3f18a97951104660c0  schemas/tiber_identity_crosswalk_v1.schema.json
e8b354675aa160fb3c14d8f695c4e4146ed6367098494f7f3671b84e6b2919e4  src/contracts/v1/forgeWeeklyPlayerInput.ts

TIBER-Rookies @ 2ef92faf9a9c91a393f53e9140428451529a1c48
9b0cff08e40ac45f5bfc725e67f3b95a2a6200491af29da1af49beb4cb49c164  docs/export-contract.md
187fb0c68b8a9d30d7e4db0f130ceb98009af4cffb878394dded540d3d6b285b  docs/rookie-transition-profile-contract.md
0acf361c6d2d8cc6f684026481a5aa279e9f7fa718256fad78da0366d5804413  exports/promoted/rookie-transition-profile/2026_manifest.json
c95b941c7855612daccfc2226fc51e0e34dbb2ebe8a2487596675d2522a22f37  exports/promoted/rookie-transition-profile/2026_rookie_transition_profile_v0.json
```

The Data event search returned exactly the one 2026 JSONL path printed above.
The standalone FORGE builder passed `node --check`; its two source-backed
defaults, generated-baseline default, and output fixture all existed and
parsed as JSON. The builder itself was not executed because it writes output.

### Exact commands, universe, exclusions, and absences

Freshness/default checks used `git remote get-url origin`, `git ls-remote --symref origin HEAD`, `git fetch --prune origin`, `git rev-parse refs/remotes/origin/main`, and `git status --porcelain=v2 --branch --untracked-files=all`.

Dynamic manifests were generated from the fetched tree, never the worktree:

```bash
# Fantasy committed signal-validation universe; no exclusions
git ls-tree -r --name-only "$rev" -- data/signal-validation | LC_ALL=C sort

# Fantasy committed embedded-FORGE universe; the amendment's sole exclusion
git ls-tree -r --name-only "$rev" -- server/modules/forge \
  | awk 'index($0,"server/modules/forge/__tests__/")==0' \
  | LC_ALL=C sort

# Fantasy fixed-token scan. Case-sensitive fixed strings, all tracked files
# under exactly server/, client/src/, shared/, and src/; no file-type exclusion.
git grep -l -F \
  -e '/api/forge' -e '/api/rankings' -e '/api/tiers' -e 'modules/forge' \
  -e 'forgeService' -e 'forgeGateway' -e 'runForgeEngine' -e 'gradeForge' \
  -e 'forgeAlpha' -e 'forge_alpha' -e 'forgeTier' -e 'forge_tier' \
  -e 'FORGE_PLAYER_STATIC_V1' "$rev" -- server client/src shared src \
  | sed "s#^$rev:##" | LC_ALL=C sort -u

# Forecast committed TypeScript files under exactly the five amendment dirs.
# The only filter is the required .ts suffix.
git ls-tree -r --name-only "$rev" -- \
  src/services/scoring src/calculators/range src/calculators/replacement \
  src/calculators/vorp src/calculators/xfpg \
  | awk '/\.ts$/' | LC_ALL=C sort

# Raw-byte pin used for every path
git cat-file blob "$rev:$path" | sha256sum
```

Confirmed absences/closures: Fantasy exact §4.1 paths `101/101` present, `0` missing; Forecast exact §4.1 paths `20/20` present, `0` missing; Fantasy scan disposition mapping `90/90` with no missing or extra mapped path; no required dynamic manifest was empty; both target worktrees had no untracked files. These are closed-repository static claims only: no grep result is treated as proof about deployed traffic or off-repository consumers.

Additional deterministic searches were:

```bash
# Data committed ownership-event match universe
git ls-tree -r --name-only "$rev" -- \
  exports/promoted/player_ownership/events \
  | rg '^exports/promoted/player_ownership/events/player_ownership_events_.*\.jsonl$' \
  | LC_ALL=C sort

# Formal repository-policy presence/absence at historical and current refs
git ls-tree -r --name-only "$ref" \
  | rg -i '(^|/)(CLAUDE\.md|AGENTS\.md|MERGE_POLICY[^/]*|SECURITY_POLICY[^/]*)$'

# Historical/current raw-byte identity
git cat-file blob "$revision:$path" | sha256sum
```

The tracked-source universe was exactly the amendment's enumerated paths,
complete dynamic directories, Data event pattern, and fixed Fantasy
roots/tokens. Transitive imports did not add sources. Embedded-FORGE paths
beneath `server/modules/forge/__tests__/` were excluded only from the
mandatory non-test closure, but fixed-token matches there remained admitted
and were dispositioned `test-only`. Roadmaps/self-audits, unlisted files,
deployed traffic, runtime state, production queries, and off-repository
consumers were excluded. No grep miss is asserted as evidence that deployed or
off-repository consumers do not exist.

Confirmed F0 absences/closures:

- Fantasy exact amendment paths: 101/101 present; dynamic manifests nonempty;
  fixed-token dispositions: 90/90, no missing or extra mapping.
- Forecast exact amendment paths: 20/20 present; all five TypeScript manifests
  nonempty.
- Data event pattern: exactly one committed match.
- Forecast and Role formal policy searches: zero matches at both historical
  and F0 current refs.
- No required current path, revision, issue/comment object, or policy object
  was inaccessible.
- No source default head diverged from the accepted D1 freeze.
- No necessary material dependency was discovered outside §4.1.

### F0 result and frontier state

Three separate read-only evidence partitions independently returned PASS:
Fantasy/Forecast; FORGE/Data/Rookies; and Teamstate/Role. A second independent
fixed-token scan reproduced all 90 paths and the 15/19/12/16/12/12/4
disposition totals. The root control recheck also passed. No reviewer found an
identity failure, missing required source, unevaluable material divergence, or
necessary out-of-universe source.

**F0 terminal:** `d3f_f0_pass`.

- D3-F remains #31's sole active discovery frontier.
- F1 is the next permitted requirement; this F0 record contains no F1-F6
  conclusion, weighting, recommendation, or direction.
- #15 R2 remains `r2_parked_pending_forge_reconception`.
- D4-D6 remain inactive.
- No direction was selected or implemented.
- No source repository, registry, #15/#20 record, prototype, implementation,
  model run, production query, runtime traffic, deployment, PR, merge,
  migration, deprecation, cutover, or repository disposition was changed.

---

## Entry 16 — F0 pre-review verification-time correction record

Remote candidate `1c3d98976e91bcf57c69d0be19c2d97e9f955637`
contained exact refs, paths, and hashes for the repository-file controls and
policies, but its shared table described their verification only as occurring
"during F0." A fresh-context pre-review correctly identified that this did not
satisfy the amendment's deterministic requirement for an exact verification
time on every repository-file pin.

The affected raw Git blobs were reverified as one batch with completion time
`2026-07-16T20:47:39.166169091Z`. Entry 15 now records that exact time for all
repository-file control and policy rows, exact per-repository verification
times for the 25 D1 architectural rows, and exact recheck times for both formal
policy absences. No path, revision, hash, manifest, authority classification,
selection reason, search result, disposition, analysis, or terminal changed.

The correction commit is
`71a8436ec591b8a6432fef663b32fdf4e4a116c7`. The accepted D3 document and
Entries 0-14 remain byte-immutable. This new entry records the correction here
rather than modifying accepted Entry 0, as required by the D3-F amendment's
stricter immutable-base boundary.

Post-correction artifact SHA-256 values before this record was appended were:

| Artifact | SHA-256 |
|---|---|
| `docs/architecture/forge-reconception-v0.md` | `aac2faee39579fae43e4f5d18f672ba0fb283095406f741ee3e2da18656a71bb` |
| `program/discoveries/forge-reconception-v0/progress-ledger.md` | `14805e0f96a4be7041a44d841cf930bd26a8d3404be41024ceb97ac1fa00abfb` |

F0 remains `d3f_f0_pass`; D3-F remains the sole frontier with F1 next. #15 R2
remains parked, D4-D6 remain inactive, and no direction or implementation is
selected.

---

## Entry 17 — F0 closed-control-universe correction record

Fresh-context pre-review found that candidate `8ff6a283e7d12d862a62034b5ed7469122596d97`
included two additional useful records in the F0 live-control table: the
amendment-audit comment `4993473639` and the #22 activation-checkpoint comment
`4996128792`. The amendment's §4.1 Ops-control universe uses “plus only” and
does not enumerate either object. Neither is required to verify the proposal,
signed approval, signed activation, accepted D3 state, or live #22/#31 bodies.

Both rows were therefore removed from the F0 evidence inventory, and the
supplemental decision document no longer cites the amendment-audit comment as
an admitted control. No GitHub comment was edited or deleted. The amendment
proposal, signed approval, signed activation, accepted D3 PASS/decision, live
issue bodies, accepted files, #21 procedure, and registry remain pinned.

No source path, raw hash, manifest, search result, authority classification,
analysis, or F0 terminal changed. F0 remains `d3f_f0_pass`; D3-F remains the
sole frontier with F1 next; #15 R2 remains parked; D4-D6 remain inactive; and
no direction or implementation is selected.

---

## Entry 18 — F0 policy-absence boundary clarification

Pre-review of candidate `98387821ed324d15c935766af574dabbe10dfecf`
questioned whether pinning the Forecast and Role root READMEs as “informal
guardrails” added files outside §4.1. Neither README is needed to establish the
two formal-policy absence records: those are reproducible tracked-tree search
results at exact revisions. The two optional README pins and the Forecast
authority group's repository-entrypoint reference were therefore removed.

Forecast and Role still retain their accepted D1 architectural evidence and
their exact policy-absence searches/times. Forecast supplemental code is
grounded by exact commit plus exact manifest path, not by the removed root
README. No evidence path required by §4.1, hash, manifest, search match,
authority classification, analysis, or terminal changed.

F0 remains `d3f_f0_pass`; D3-F remains the sole frontier with F1 next; #15 R2
remains parked; D4-D6 remain inactive; and no direction or implementation is
selected.

---

## Entry 19 — F1 partial inventory and source-universe block

### Authority and method

F1 began only after mandatory F0 passed at
`7863a1a07c62060f360a3314b013aacb62b35fe0` with independent review recorded
in TIBER-Ops#31 comment `4996566565`. The executing analysis stayed read-only
in all seven source repositories and traced only the F0-admitted paths,
fixed-token matches, exact imports, route registrations, and service calls.

F1 applied the amendment's definition of an evidenced current consumer:
committed F0-revision code with a reproducible static chain to a mounted entry
point. It did not treat path names, similar field names, a route definition,
an import, documentation, or current runtime behavior as sufficient by itself.

### Exact stopping objects

One raw-byte replay batch completed at `2026-07-16T21:38:28.687240665Z` at
the F0-frozen revisions and reproduced these ten known necessary but
unadmitted objects reached before the fail-closed stop:

| Repository | Revision | Excluded path | SHA-256 | Prevented trace |
|---|---|---|---|---|
| TIBER-Forecast | `49208472539bd11789b88ca8b3eb20c56a7d0db5` | `src/server.ts` | `a8887606440c063f52c4b6b5fd4824e25534ea8b7c18859fa2b542512cc1d44c` | Served application entry |
| TIBER-Forecast | same | `src/api/app.ts` | `b671266a530de60cc418b18d1c56ed709cc7a92b1140c3d7552d745fd799f1ff` | Route registration/mount middle |
| TIBER-Forecast | same | `src/api/routes/scoring.ts` | `dfbc18342b74e31961e814c3288df52856e90e3b9bc5ddaa489b9c37fb8db953` | Five raw scoring questions and adapters |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | `client/src/main.tsx` | `77de0b5e8dabac65fc1390a8e472bc971e0644dbf570def9f589562972d5ec28` | Client-to-`App.tsx` root |
| TIBER-Fantasy | same | `server/index.ts` | `30a729ac29e4b6dec298a4c127b059e4a39a387f7255534951000fa5136cd86e` | `/api/v1` and `registerRoutes` server mounts |
| TIBER-Fantasy | same | `server/routes/playerIdentityRoutes.ts` | `91a4f0381d0b2411280739bdd9d7e6660e589a84af2cf87506cdb12675a75e9b` | PlayerPage weekly/ROS scoring middle |
| TIBER-Fantasy | same | `server/routes/tiberRoutes.ts` | `47aa2f19b0446a1f55e8b4c030c3be4055715947931c5cd0fd8e1d29928a9028` | TIBER chat to `forgeContextLoader` middle |
| TIBER-Fantasy | same | `client/src/lib/queryClient.ts` | `3e231529f0006b18d0bdf0fcaf18d96cf22f029a1c3e1055485d6aa7ae1dc0cb` | Query-key default fetch for ranking/Management paths |
| TIBER-Fantasy | same | `server/routes/adminForge.ts` | `ea4ca01f599f3166dc39fc9cb681bd6a57aee247f19dfca08955ffd40ae88c69` | Admin FORGE rebuild route/service middle |
| TIBER-Fantasy | same | `server/routes/leagueDashboardRoutes.ts` | `7bfb6630130c5c4dad38f795b8cdbd7ee2253e036c5e0c23ff83270dd1cd4c8b` | Management league-dashboard route/service middle |

These objects are outside §4.1. Their hashes and boundary roles are recorded
only to make the stop reproducible; they were not admitted as consumer
evidence. Forecast `src/public/index.ts` at the same revision reproduced
`be218977001224765af49e08b98af0e60534e3e31a52cd398e47ef76ca9db99c`
but was nonessential export-only context, so it remains parked rather than
joining the blocking set.

Amendment §7 permits this terminal before normal F1 completion. This is the
exact known set reached during completed partial work, not a claim that
forbidden transitive expansion produced an exhaustive repository closure.

This finding prospectively supersedes Entry 15's statement that no necessary
material dependency was discovered outside §4.1. It does not alter F0's
fetched revisions, identities, hashes, manifests, search counts, policies,
controls, or accepted bytes.

### Completed partial work

- **Forecast:** admitted `tiberScoring.ts` and
  `buildTiberViewsService.ts` support four internal route questions—weekly
  card, weekly ranking, ROS card, and weekly compare—but their application and
  served-process mounts are unproved. The excluded raw scoring router prevents
  complete enumeration of five additional scoring questions.
- **Fantasy:** the admitted App, page, route, FORGE, scoring, and compatibility
  code supports route-declared tiers, schedule, TIBERClaw, FORGE inspection,
  PlayerPage, Management, ranking-sandbox, admin rebuild, delta API, and API-v1
  rows. Missing roots and middles prevent the required current-consumer
  classifications and several request/service chains, including Management's
  league-dashboard route and the admin rebuild route.
- **Player Research:** admitted code supports two UI compositions of the same
  route-declared player/season research question through one service that
  combines signal validation, role/opportunity, age curves, point scenarios,
  and ownership.
  It is question-specific composition with mixed grains and unresolved
  cutoff/correction/ownership semantics, not direct evidence of a neutral
  shared profile.
- **Shared demand:** no admitted current Forecast-to-Research, Forecast-to-
  FORGE, or common neutral-profile consumption edge was established. Similar
  names do not align identity, grain, cutoff, correction, and semantic-owner
  contracts.
- **Accounting:** Entry 15's fixed-token disposition remains `90/90` with
  `15` mounted-product, `19` server-internal, `12` compatibility, `16`
  admin/experimental, `12` unmounted, `12` test-only, and `4` docs-only
  file labels. F1 cannot promote those labels into complete consumer evidence
  without the excluded mount/service middles.

The missing objects prevent normal F1 completion, all-three-class accounting,
complete scan-hit disposition under the mounted-chain rule, the F2 viability
gate, and honest execution of F2-F6 or synthesis. Under amendment §§4.1, 7,
and 8, the decision document therefore records the single blocked terminal
and zero recommendation before later requirements begin.

### Unknowns, scope accounting, and frontier state

Runtime/deployment traffic, environment configuration, data/cache/artifact
population, off-repository consumers, product priorities, survival
requirements, future owners, and option weighting remain unchanged unknowns.
They are not used as the block rationale.

Relative to F0 `7863a1a07c62060f360a3314b013aacb62b35fe0`, the candidate
changes only:

- `docs/architecture/forge-reconception-v0.md`; and
- `program/discoveries/forge-reconception-v0/progress-ledger.md`.

Both changes are append-only with zero deletion. No source repository,
registry, #15/#20 state, implementation, prototype, model run, runtime query,
issue in a source repository, PR, merge, deployment, migration, cutover,
deprecation, or repository disposition changed.

D3-F remains #31's sole discovery frontier in a stopped state. F2-F6 did not
begin. #15 R2 remains `r2_parked_pending_forge_reconception`; D4-D6 remain
inactive; A-D remain unresolved; and no FORGE direction is selected or
implemented. Fresh-context verification of the exact published head is
required before this executing-agent record may be treated as a technically
verified checkpoint.
