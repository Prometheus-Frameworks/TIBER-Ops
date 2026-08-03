# TIBER Governance Kernel v0

Status: **DESIGN CANDIDATE — NOT ADOPTED — NO RUNTIME AUTHORITY**

| Binding | Value |
| --- | --- |
| Design issue | [TIBER-Ops #30](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/30) |
| Operator activation | [TIBER-Ops #30 comment 5161111680](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/30#issuecomment-5161111680) |
| Human decision owner | Joseph (`@Prometheus-Frameworks`) |
| Executor | Codex |
| Pinned TIBER-Ops base | `cd60472bbff915dd3e50606a825ca7eff7029d3e` |
| Sole write repository | `Prometheus-Frameworks/TIBER-Ops` |
| Related Harness design | [TIBER-Harness #5](https://github.com/Prometheus-Frameworks/TIBER-Harness/issues/5) |
| Settled Research placement | [TIBER-Harness #6](https://github.com/Prometheus-Frameworks/TIBER-Harness/issues/6) and [PR #7](https://github.com/Prometheus-Frameworks/TIBER-Harness/pull/7) |
| Research implementation state | [TIBER-Research PR #1](https://github.com/Prometheus-Frameworks/TIBER-Research/pull/1) merged; [PR #2](https://github.com/Prometheus-Frameworks/TIBER-Research/pull/2) draft and not activation-ready |

This report is the architecture deliverable authorized by TIBER-Ops #30. It
defines a logical governed context artifact and its future assembly contract. It
does not implement a kernel, create a runtime, call a model, change an agent
instruction file, activate a Research run, adopt a source policy, or authorize a
follow-up scaffold, merge, deployment, promotion, or other state transition.

The working name **TIBER Governance Kernel** distinguishes this system-wide
operating layer from TIBER-Forecast's existing use of “kernel” for its local
scoring and inference machinery.

## 1. Answer first

TIBER should have one small, provider-neutral Governance Kernel release: an
immutable, versioned policy package applied before repository, workload, task,
and evidence material is supplied to an agent.

This report uses three distinct terms:

- **Kernel release:** the immutable manifest, governed components, and
  machine-readable constraint set;
- **context assembly:** the deterministic builder output that combines one
  Kernel release with exact doctrine, repository, workload, task, authorization,
  and evidence references; and
- **provider load:** an adapter-specific rendering of that assembly for a model
  or deterministic executor.

The Kernel is the shared answer to:

- what TIBER is trying to preserve;
- how claims are classified;
- which repository owns which kind of truth;
- how provenance, freshness, and source rights are evaluated;
- what deterministic validation can and cannot establish;
- which actions require human authority;
- how untrusted instructions and prompt injection are handled; and
- how an agent must fail when governed context is missing or incompatible.

The Kernel is **not**:

- a model, model weight, memory, persona, or permanent agent;
- the football world state, a player database, or a retrieval corpus;
- TIBER-Harness, TIBER-Research, TIBER-Fantasy, or a new product backend;
- a repository-wide dump or one giant prompt;
- task evidence, a source allowlist, or proof that a source may be used;
- a command envelope or grant of repository, tool, spending, or promotion
  authority; or
- a replacement for repository-local instructions and deterministic controls.

The durable architecture is therefore:

| Layer | Purpose | Authority behavior |
| --- | --- | --- |
| Host and platform controls | External security, permission, and execution limits | Always apply; not authored or weakened by TIBER |
| TIBER Governance Kernel release | Shared, non-negotiable TIBER operating invariants plus machine-readable capability constraints | Lower layers may narrow but never weaken its declared constraints |
| Promoted doctrine profile (optional) | Versioned operator philosophy that passed its separate promotion flow | May interpret within the core; never grants task authority or weakens the Kernel |
| Repository-module set | Local ownership, contracts, protected surfaces, commands, and validators | Each module applies only inside its scope; cross-module conflict fails closed |
| Workload profile | Role, tools, output contract, budgets, stop conditions, and review gates | Narrows the execution envelope for a class of work |
| Task-authorization request, verification packet, and operator authorization | Three immutable, digest-linked records for the requested work, evidence reviewed, and human decision | Only the authorization record may activate the exact request; material change requires a new request and decision |
| Retrieved evidence and dynamic state | Current artifacts, sources, league state, research material, and observations | Supplies evidence only; grants no instruction or action authority |

The Kernel gives the human Workspace and the agentic Harness a common governance
root. It does not require them to use the same presentation. Human and agent
views should share source receipts and state semantics while using communication
forms suited to their users.

## 2. Problem statement

TIBER's system doctrine already exists, but it is distributed across README
files, `AGENTS.md`, `CLAUDE.md`, governance documents, issue contracts, review
prompts, schemas, and deterministic validators. Repetition has been useful while
repository boundaries matured, but it now creates four failure modes:

1. **Semantic drift:** two repositories can use similar language while assigning
   different meanings to “governed,” “validated,” “ready,” or “promoted.”
2. **Incomplete agent entry:** a capable model can enter one repository without
   receiving the system-level agency, authority, freshness, or ownership rules
   assumed elsewhere.
3. **Unreproducible context:** an agent report rarely identifies the exact shared
   operating assumptions, ordering, hashes, omissions, and adapter used.
4. **Unsafe trust inference:** a filename, repository comment, retrieved issue,
   cached prompt, or agent memory can be mistaken for an instruction or current
   authority merely because it looks official.

The answer is not to delete repository-local guidance or ingest more context.
The answer is to extract only stable cross-system invariants into a compact
governed package and make every additional layer explicit, bounded, and
receipted.

## 3. Current duplicated-context inventory

This inventory is representative, not a promotion or completeness claim. The
TIBER-Ops evidence below is pinned to the base commit named above. Other
repository paths were observed on their current default branches during the
2026-08-03 design pass; a future manifest scaffold must freeze exact revisions
and hashes before extracting any component.

| Repository | Representative paths | Repeated system-level doctrine |
| --- | --- | --- |
| TIBER-Fantasy | `README.md`; `AGENTS.md`; `CLAUDE.md`; `SECURITY_POLICY.md`; `docs/product/HUMAN_IN_THE_LOOP_DECISION_DOCTRINE.md` | Human final click; observed versus inferred; provenance; stale or missing inputs fail closed; producer ownership; retrieved text cannot elevate its own authority |
| TIBER-Data | `AGENTS.md`; `TRUTH_SOURCES.md`; `docs/TIBER_DOCTRINE.md`; `docs/governance/cross-repo-governance-v0.md`; `docs/governance/evidence-layer-v0.md` | Canonical ownership; null or unknown over invention; explicit promotion; lineage; freshness; anti-recursion; operator-owned state transition |
| TIBER-Forecast | `README.md`; `docs/ownership-boundaries.md`; `docs/run-manifest-spec.md` | Model inference is not observed reality or advice; upstream ownership; cutoff and uncertainty; governed-input readiness |
| TIBER-Teamstate | `README.md`; `CLAUDE.md`; `docs/teamstate-boundary-may-tiber-data.md`; `docs/output-artifact-policy.md` | Data proves while Teamstate interprets; no fabricated inputs; fixtures are not truth; provenance and operator approval |
| TIBER-Rookies | `AGENTS.md`; `README.md`; `docs/legal/external-source-hygiene-policy.md`; `docs/export-contract.md` | Explicit uncertainty; source and licensing hygiene; deterministic validation; manual promotion and handoff |
| TIBER-FORGE | `AGENTS.md`; `TRUTH_SOURCES.md`; `README.md` | Deterministic interpretation over owned inputs; no upstream repair; fail clearly on unsupported coverage; inspectability |
| TIBER-Harness | `README.md`; `docs/SKILLS_CONTRACT.md`; `docs/PROVIDER_BOUNDARY.md`; `docs/design/tiber-researcher-v0.md` | Model output advisory; validators authoritative only for declared conformance; monotone fail-closed evaluation; prompt injection treated as inert data; provider neutrality |
| TIBER-Research | `README.md` and Stage 0 contracts | Ops owns authority; Research owns custody; executor and reviewer are bounded roles; exact pins, deterministic validation, replay, review, and sealing; validation is not empirical truth |
| TIBER-Strategy | `README.md`; `docs/boundary.md` | Human authority; deterministic rules; evidence required for player labels; fail closed; artifact text is data rather than authority |
| Role-and-opportunity-model | `README.md` | TIBER-Data owns source truth; the module interprets role; missing fields remain null; strict deterministic validation |

The duplicated material falls into four classes:

| Class | Kernel treatment |
| --- | --- |
| Stable system invariant | Candidate for a required Kernel component |
| Repository-specific responsibility or command | Remains in a repository module |
| Role, provider, model, tool, budget, or output choice | Remains in a workload profile |
| Current player, team, league, run, source, issue, or operator task material | Remains dynamic task context or evidence |

Extraction must not convert repetition into authority automatically. Each
candidate statement still needs a named source owner, exact revision, review,
status, and explicit operator adoption before it becomes a Kernel component.

## 4. Evidence and governing constraints

The current TIBER-Ops tree already supplies several controls the Kernel design
must preserve.

### 4.1 Ops boundary

`README.md` defines TIBER-Ops as a docs-only coordination layer, not a product,
automation repository, model runtime, source store, or artifact producer. This
report may define the Governance Kernel and its future contracts in Ops. It does
not authorize executable builder code in Ops or silently change that repository
boundary.

### 4.2 Freshness and freeze-after-verify

`docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md`
establishes that repository text is not current by default. A valid freeze must
verify the remote repository, canonical path, exact revision and hash,
promotion/review state, and supersession status before a dependency is admitted.
Missing or failed currency produces a blocked receipt; it does not permit a
substitution, silent truncation, or unapproved scope change.

`registry/tiber-current-state.v0.json` is manual, dated, and limited to the
declared #15 dependency set. It is useful evidence of registry shape but is not
a universal Kernel registry or proof that unlisted material is demoted.

### 4.3 Temporal and source-use separation

The Research Observatory readiness inventory distinguishes event, effective,
publication, availability, retrieval, first-observed, admissibility, and cutoff
times. The Kernel must not collapse those clocks into “updated at.”

The corrected source-admissibility policy candidate is merged but explicitly
unadopted, and its candidate source set is empty. Availability, repository
licensing, loader access, acquisition, retention, internal analysis, hosted
model use, transformation, publication, and redistribution are separate axes.
The Kernel may preserve that status-aware distinction. It must not transform
the candidate into an active policy or allowlist.

### 4.4 Workspace and agent exports

The World Workspace pilot establishes a useful interface rule: GitHub decisions,
governed artifacts, and owning runtimes remain canonical; the Workspace is a
presentation and normalization surface. Its current context packet is
pilot-local and non-canonical. It preserves source receipts, distinct clocks,
gaps, conflicts, and raw classifications separately from evidence authority.

An agent-readable export is not a command envelope, durable memory, promoted
artifact, or mutation permission. Retrieval time and cache time do not make an
upstream artifact fresh.

### 4.5 Human authority and provenance

TIBER-Ops #22 makes Joseph the human decision owner. Agents may execute only
within an approved issue, contract, and repository policy. They cannot approve
their own amendments, irreversible actions, completion claims, or promotion
from pilot to shared enforcement.

Because the same GitHub account can post human and mechanically generated text,
account metadata alone is not decision provenance. Signed and labeled operator
records, exact content identity, and the surrounding authority contract are
required.

The #30 operator-doctrine amendment further requires raw reflections to remain
non-binding. Exploration, doctrine candidates, promoted doctrine, scoped
decisions, authorization requests, technical verification, and authorization
records must remain distinct.

### 4.6 Current executable-interface boundary

This design is anchored to the current executable contracts rather than an
assumed future integration:

- TIBER-Harness is pinned at
  `eac4b0968ff4645582743421fc8bb2f6a1c2aa8b`. Its current `ModelProvider`
  receives only `prompt`, `input`, `skill`, and `fixtureId`, and returns raw
  text. Its run report does not yet bind a Kernel manifest, workload, effective
  capabilities, tools, cost, cache, evidence, or loading receipt. Harness is
  therefore not a Kernel loader today.
- TIBER-Research Stage 0 is pinned at
  `8a8039eeaa2ba1b8cae65859d43746df6b949ecd` with tree
  `582930f21d6fafafcfc55527e5aa9363c08ad417`. Its v0 job schema is closed with
  `additionalProperties: false` and has no `context_manifest_ref`. A Kernel
  reference cannot be inserted, required, or presented as a live Research
  dependency without a separately authorized schema version and migration.
- The Research common schema currently defines the epistemic values
  `observed`, `calculated`, `inferred`, `hypothesis`, `speculative`,
  `contradicted`, and `unknown`; freshness values `current`, `stale`,
  `unresolved`, and `not_applicable`; admissibility values `admitted`,
  `inadmissible`, and `unresolved`; reportability values `public_safe`,
  `internal`, `private`, `non_promotable`, and `later_review_only`; and digest modes
  `tiber-canonical-json-v1` and `tiber-raw-sha256-v1`. A future Kernel scaffold
  should reuse or explicitly version these meanings rather than create near
  synonyms.

These pins describe observed state only. They do not import either repository's
contracts into Ops, amend those contracts, or grant runtime work.

## 5. Canonical Kernel artifact model

If adopted, the canonical Governance Kernel is a logical immutable release
composed of:

1. one manifest;
2. an ordered set of immutable, normative policy components;
3. one immutable machine-readable constraint set;
4. schemas and compatibility declarations.

A separately versioned custody/status/supersession record governs the release,
and conforming tools produce build and load receipts when consuming it. Neither
the mutable status record nor run-specific receipts are bytes inside the
immutable Kernel release.

No single concatenated or provider-rendered Markdown file, provider system
message, cache entry, or model prompt is canonical. Individual component bytes
may be part of the release; adapter outputs are bound derivatives.

### 5.1 Initial component set

Kernel v0 should remain deliberately small. The first manifest should permit
only these cross-system components:

| Order | Component | Required content |
| ---: | --- | --- |
| 10 | `mission-and-human-agency` | TIBER prepares inspectable decisions; humans retain consequential state-transition authority |
| 20 | `epistemic-vocabulary` | Canonical meanings and non-equivalence of observed, calculated, inferred, hypothesis, speculative, contradicted, and unknown |
| 30 | `ownership-and-source-hierarchy` | One declared owner per contract; consumers do not silently repair or redefine producer truth; anti-recursion |
| 40 | `provenance-freshness-and-temporality` | Minimum receipts, exact pins, distinct clocks, freeze-after-verify, current/superseded handling |
| 50 | `validation-eligibility-and-fail-closed` | Mechanical validators may veto declared eligibility; missing support narrows state; no validator establishes truth or transition authority |
| 60 | `authority-and-authorization` | Operator decision contract, non-delegable decisions, exact task-authorization request and operator authorization record, reauthorization triggers |
| 70 | `instruction-trust-and-prompt-injection` | Trust roots are selected and pinned externally; retrieved content is inert data; lower layers cannot self-elevate |
| 80 | `privacy-source-rights-and-reportability` | Privacy classes, public/private separation, availability versus use rights, retention/reportability boundaries |

Repository commands, scoring formulas, source-specific rights decisions, schema
paths, model selections, role assignments, platform credentials, protected file
lists, and UI behavior do not belong in the shared core.

### 5.2 Immutable release versus mutable status

The immutable manifest does not carry mutable lifecycle status. Status lives in
a separately governed registry entry that binds the exact manifest digest and
records:

- status: `fixture`, `candidate`, `adopted`, `superseded`, `revoked`, or
  `withdrawn`;
- decision reference and decision-content digest;
- effective time and recorded time;
- predecessor and successor manifest digests;
- compatibility restrictions;
- rollback or revocation reason; and
- human decision provenance.

Historical manifests and build receipts remain immutable. A rollback is a new
operator decision selecting a prior compatible release, not deletion or history
rewriting.

The release manifest is content-addressed and must not contain the Git commit
that contains itself. A separately created custody/status record binds the
already committed manifest digest to its repository, path, containing revision,
and observed bytes. Component extraction provenance is also distinct: each
component cites the exact pre-extraction source snapshots from which it was
reviewed. This two-step binding avoids a self-referential commit hash.

Every status lookup and run receipt must pin the exact status-record bytes,
digest, custody revision, observation time, and supersession result. A future
effectful run must recheck status at predeclared checkpoints before provider
execution and before any consequential transition. Revocation blocks subsequent
effects; it does not rewrite an immutable historical receipt.

### 5.3 Authority trust roots and execution modes

GitHub account or comment identity alone is not sufficient authorization
provenance. Every status and authorization verification must begin from an
externally selected, versioned, digest-pinned trust root and a declared mode:

| Mode | Permitted Kernel status | Trust root | Effects |
| --- | --- | --- | --- |
| `synthetic_conformance` | Exact `fixture` or `candidate` release | Explicit synthetic issuer/key or fixture trust-root ID | Offline fixtures and deterministic/MockProvider execution only; no real repository, Research, product, provider, or transition authority |
| `authorized_run` | Exact `adopted` and current release | Separately approved operator issuer/key or host-attested identity contract | Only the narrower effects allowed by all other controls and the exact operator authorization |

If the trust root, signature/attestation, issuer status, or decision binding
cannot be verified, the load fails closed. This report does not select a live
operator-authentication mechanism; therefore it cannot make
`authorized_run` available. A later builder scaffold may implement only the
synthetic trust root unless separately authorized.

## 6. Manifest contract

The following example is illustrative. A scaffold issue must define the exact
schema, canonical JSON procedure, hashing mode, and status-registry contract.

```json
{
  "schema_version": "tiber-governance-kernel-manifest/v0",
  "kernel_id": "tiber-governance-kernel",
  "kernel_version": "0.1.0-candidate.1",
  "authority_contract_version": "tiber-operator-authority/v0",
  "components": [
    {
      "component_id": "mission-and-human-agency",
      "component_version": "0.1.0",
      "path": "kernel/components/mission-and-human-agency.md",
      "digest": "sha256:<lowercase-hex>",
      "digest_mode": "tiber-raw-sha256-v1",
      "required": true,
      "order": 10,
      "max_utf8_bytes": 6000
    }
  ],
  "constraint_set": {
    "schema_version": "tiber-kernel-constraints/v0",
    "path": "kernel/constraints/kernel-constraints.v0.json",
    "digest": "sha256:<lowercase-hex>",
    "digest_mode": "tiber-canonical-json-v1"
  },
  "compatibility": {
    "repository_module_schemas": ["tiber-repository-module/v0"],
    "workload_profile_schemas": ["tiber-workload-profile/v0"],
    "doctrine_profile_schemas": ["tiber-doctrine-profile/v0"],
    "task_authorization_request_schemas": ["tiber-task-authorization-request/v0"],
    "verification_packet_schemas": ["tiber-verification-packet/v0"],
    "authorization_record_schemas": ["tiber-authorization-record/v0"],
    "evidence_index_schemas": ["tiber-evidence-index/v0"],
    "routing_policy_schemas": ["tiber-routing-policy/v0"],
    "adapter_descriptor_schemas": ["tiber-adapter/v0"],
    "minimum_builder_contract": "tiber-kernel-builder/v0"
  },
  "budgets": {
    "core_max_utf8_bytes": 48000,
    "required_component_count": 8,
    "overflow_behavior": "fail_closed"
  },
  "build_rules": {
    "ordering": "ascending_explicit_order_then_component_id",
    "duplicate_component_behavior": "fail_closed",
    "missing_optional_component_behavior": "record_omission",
    "semantic_summarization": "prohibited"
  }
}
```

Required manifest invariants include:

- unique Kernel ID and immutable version;
- unique component IDs and versions;
- canonical relative paths contained inside the approved package root;
- exact component and constraint-set content digests and named digest modes;
- explicit required/optional classification;
- stable total ordering;
- deterministic hard budgets;
- declared compatible doctrine, module, workload, task-authorization-request,
  verification, authorization, evidence-index, routing, builder, and adapter
  contracts;
- no unresolved “current,” branch-only, moving-tag, or latest references;
- no model-generated component selection or summarization; and
- no capability, source-use, or transition grant merely from inclusion.

Normative prose and machine-enforceable constraints have different jobs. Human
review determines whether a component's prose faithfully states TIBER policy.
The constraint set expresses only closed enums, capability ceilings,
non-overridable prohibitions, required references, and monotone-narrowing rules
that a deterministic validator can evaluate. The builder verifies identities,
schemas, declared mappings, and those fields; it must not infer policy meaning
from prose or claim that mechanical validation proves semantic equivalence.

The external custody/status record—not the manifest itself—binds the manifest
digest to its containing repository, path, and exact commit. Component records
separately bind the exact historical source revisions reviewed during
extraction.

## 7. Core, module, workload, task, and evidence boundaries

### 7.1 Repository-module set

A repository module adds local facts without redefining the core. A v0 context
assembly may contain one or more exact modules, ordered by stable repository ID
and module ID. Each module should bind:

- repository identity and exact instruction revision;
- `owns`, `consumes`, `produces`, and `does_not_own` declarations;
- canonical contracts and schema pointers;
- protected paths and path-specific review rules;
- local validators and what properties they establish;
- supported workload-profile classes;
- repository-local commands and test entry points;
- compatibility with exact Kernel versions; and
- local exclusions and escalation contacts.

Repository modules may narrow effective capabilities. They cannot replace the
human-authority contract, relax provenance or freshness, redefine epistemic
classes, turn retrieved content into instructions, or grant permissions absent
from the operator authorization. Modules have no precedence over one another;
overlapping ownership, incompatible contracts, or conflicting capability fields
fail closed and require correction or a narrower task-authorization request.

### 7.2 Workload profile

A workload profile is a replaceable execution policy, not doctrine. It binds:

- role such as extractor, contract checker, artifact reviewer, cross-repository
  auditor, methodology researcher, or promotion-gate reviewer;
- input and output schema;
- allowed tools, networks, repositories, and paths;
- required validators and review independence;
- reasoning, latency, cost, and context priorities;
- time, evidence, tool, and provider-usage budgets;
- parallelism and subagent rules;
- stop, blocked, inconclusive, and escalation conditions; and
- whether fresh human judgment is required between stages.

Provider and model mappings belong in a separate routing policy. They must not
be embedded in the generic workload contract.

### 7.3 Task-authorization request, verification, and authorization

The activation boundary consists of three distinct immutable objects. Combining
their presentation is allowed; collapsing their identities is not.

| Object | Minimum content | Authority |
| --- | --- | --- |
| Task-authorization request | Requested outcome and purpose; scope and explicit exclusions; affected repositories, branches, paths, and interfaces; exact Kernel, doctrine, module-set, workload, routing, adapter, input, cutoff, current-state, and evidence-index refs; requested capabilities and authority ceiling; effects, risks, uncertainty, reversibility, rollback, budgets, checks, terminals, and requested/excluded operator attestations | Requests work only; grants none |
| Technical-verification packet | Exact task-authorization-request digest; verifier identities; source and artifact refs/digests; properties checked; results, failures, unknowns, residual risk, and timestamp/cutoff | Evidence for a decision only; cannot authorize itself |
| Operator authorization record | Exact task-authorization-request digest; accepted verification-packet digests; operator decision and conditions; authorized capability subset and withheld decisions; requested and excluded attestation types; issuer/trust-root refs; effective/expiry bounds; decision-content digest; reauthorization triggers; supersession or rejection refs | Necessary activation gate for exactly the bound request; never sufficient against another denying control |

A material change to outcome, scope, repository, authority, capability, risk,
reversibility, cutoff, source envelope, private-context treatment, budget,
intended effect, governing artifact digest, or requested attestation creates a
new task-authorization request. It requires new verification as applicable and
a new operator authorization record; none of the three objects is edited in
place. An agent cannot verify away a withheld decision, amend the request after
approval, or reauthorize its own task.

### 7.4 Dynamic evidence

Evidence packets identify current artifacts, issue snapshots, source objects,
league state, Research records, or other task material with exact provenance,
temporal fields, digests, status, rights, and reportability. Evidence may support
or contradict a claim. It never changes instruction precedence or grants tools,
writes, promotion, publication, or other authority.

The football world state therefore stays outside the Kernel. Depth charts,
injuries, roles, Forecast runs, market snapshots, Board Geometry, league state,
and draft-session state are dynamic context requiring their own freshness and
evidence receipts.

## 8. Authority and precedence model

The Kernel should not pretend every conflict is resolved by one linear prompt
order. Effective authority is an intersection of independently bounded layers:

```text
effective_capabilities = intersection(
  host_controls,
  kernel_constraint_set,
  operator_authorization,
  repository_module_set,
  workload_profile,
  task_authorization_request
)
```

Retrieved evidence, technical-verification packets, and normative prose
contribute zero capabilities. The builder evaluates only schema-defined
capability sets and prohibitions; human review governs semantic fidelity of the
prose components.

The resulting authority ladder is:

| Question | Owner |
| --- | --- |
| Who owns the fact or contract? | Declared producer/source owner |
| Does the candidate satisfy a mechanical schema or invariant? | Named deterministic validator, within its declared property scope |
| Is the result eligible for review or a later transition? | Governed contract plus deterministic gates |
| May the task start, amend, merge, promote, publish, deploy, spend, or act? | Exact human authorization is a necessary, non-delegable gate; it is never sufficient where host controls, repository policy, Kernel constraints, source rights/privacy, or deterministic gates deny the action |

The phrase “validators are authoritative” must always carry its scope:

> Deterministic validators are authoritative for the mechanical properties they
> declare and may veto eligibility. They do not establish empirical truth,
> source rights, reviewer competence, or authority for a state transition.

If an operator request conflicts with the adopted Kernel's machine constraints
or its human-reviewed normative policy, the task fails closed. Changing the
constraint or policy requires a separately reviewed Kernel successor and a new
authorization bound to it; a task-level instruction cannot silently override
the core. A builder can prove the machine-constraint conflict; a claimed prose
conflict requires independent human review rather than model adjudication.

## 9. Deterministic builder contract

The builder is a deterministic assembler and verifier. It is not an agent and
uses no model judgment.

### 9.1 Inputs

- declared execution mode and exact trust-root reference/digest;
- exact Kernel manifest and constraint-set bytes and digests;
- exact custody/status-record bytes, digest, revision, and observation receipt;
- all component bytes and digests;
- an ordered exact repository-module set;
- one exact promoted doctrine profile or schema-declared absence marker;
- one exact workload profile;
- one exact task-authorization request;
- the exact technical-verification packet set referenced by the decision;
- one exact operator authorization record that binds the request and verification
  digests;
- one evidence index, with evidence bodies loaded separately;
- exact routing-policy and adapter-descriptor records; and
- deterministic byte, component, and provider-token budget configuration.

### 9.2 Required procedure

1. Parse only the declared schemas and canonical forms.
2. Verify mode, trust root, issuer/signature or attestation, custody/status
   record, decision reference, and immutable manifest digest. Require an adopted
   current release in `authorized_run`; allow an exact `fixture` or `candidate`
   release only in `synthetic_conformance`.
3. Resolve the constraint set and every required component by exact path,
   version, and hash.
4. Reject duplicate IDs, paths outside the package root, moving refs, mismatched
   hashes, missing required material, or incompatible schema versions.
5. Apply deterministic ordering without semantic selection or summarization.
6. Validate the constraint set and prove from machine-readable fields that
   doctrine, repository modules, workload, task-authorization request, and
   authorization only narrow the effective capability envelope. Reject
   cross-module conflicts.
7. Verify that the authorization record binds the exact
   task-authorization-request and technical-verification digests and that none
   has been superseded or changed.
8. Verify freshness, cutoff, privacy, source-use rights/admissibility,
   availability, reportability, and budget receipts required by the workload.
9. Enforce component and aggregate byte budgets.
10. Assemble a provider-neutral context assembly that preserves layer labels,
   boundaries, exact text, and provenance.
11. Invoke a separately versioned adapter only after the context assembly passes.
12. Emit a build receipt and a load receipt even when the result fails closed.

The builder must never:

- choose doctrine with a model;
- summarize required components to fit a budget;
- use hidden provider memory as an input;
- treat a cache hit as freshness or evidence;
- repair a producer contract silently;
- substitute a different source or repository path;
- widen an allowlist, budget, role, or authority ceiling; or
- mark a run activated, promoted, or complete.

### 9.3 Failure result

A failed build produces no context assembly eligible for its declared mode. It
emits diagnostics including the failed layer, component or receipt, expected and
observed digest/version, omission or incompatibility, and the exact fail-closed
status. Budget exhaustion or context overflow is not completion.

## 10. Provider and agent adapter contract

Adapters map the context assembly into a provider load such as a Codex agent
context, Claude repository context, OpenAI system/developer input, or an Ollama
prompt. Formatting may change; semantics, segment content, precedence,
authority, and omissions may not.

Every adapter must declare:

- adapter ID, version, provider family, and supported interface;
- compatible Kernel, module, workload, and builder contract ranges;
- segment-to-provider-role mapping;
- tokenizer or token-estimator ID and version;
- unsupported instruction-precedence cases;
- cache behavior and cache-key inputs;
- required round-trip/conformance fixtures;
- rendering and escaping rules; and
- diagnostics for any provider limitation.

If a provider cannot preserve required separation or precedence, that adapter is
incompatible and the load fails closed. An adapter cannot omit a required
component because the provider has a larger or smaller context window.

Provider-side cached prompts and persisted reasoning may improve efficiency but
remain outside the evidence and authority model. A provider-load cache key must
bind the exact context-assembly digest, provider-load/request digest, execution
mode, trust-root digest, custody/status-record digest, adapter and routing-policy
digests, provider/model configuration, and tokenizer or estimator mapping. The
context-assembly digest in turn binds doctrine, ordered modules, workload,
task-authorization request, verification packets, operator authorization,
evidence index, and dynamic-context refs. Cached provider output or persisted
reasoning reuse is separately keyed to the exact provider request digest and
provider execution configuration. A cache hit never replaces build/load
validation, status checkpoints, evidence, or authority.

## 11. Context and token-budget policy

Kernel budgets should be small enough to make every required component
inspectable and stable. A large provider context window is not permission to
load the TIBERverse.

Use two budget layers:

1. **Provider-neutral deterministic limits:** UTF-8 bytes, component counts,
   evidence-object counts, and reserved segment allocations.
2. **Adapter-specific token limits:** exact tokenizer or named estimator version,
   per-layer token counts, total input ceiling, and reserved output capacity.

The manifest establishes the core hard limit. Repository, workload, task, and
evidence budgets are declared separately so dynamic material cannot crowd out
the Kernel.

Recommended allocation policy:

| Layer | Budget behavior |
| --- | --- |
| Kernel release | Manifest, constraint set, and required components are non-truncatable; overflow fails the build |
| Repository-module set | Required fields non-truncatable; optional local detail may be omitted only when predeclared and receipted |
| Workload profile | Required and non-truncatable |
| Task-authorization request, verification, and operator authorization | Required and non-truncatable; identities remain distinct |
| Evidence | Retrieved narrowly by named evidence gap; split work or fail rather than silently truncate |
| Output | Capacity reserved before the run starts |

If the exact tokenizer is unavailable, the adapter must use an approved
conservative bound or fail closed. Runtime “smart compression” by a model is
not a deterministic budget mechanism.

## 12. Loading, execution, and reporting sequence

A future Kernel-backed run should follow this order:

1. Select `synthetic_conformance` or `authorized_run` and resolve the exact
   trust root permitted for that mode.
2. Resolve the exact Kernel release through its custody/status record; require
   `adopted` and current status for `authorized_run`.
3. Verify manifest, constraint-set, and component hashes.
4. Verify the doctrine profile or declared absence, ordered repository-module
   set, workload profile, routing policy, and adapter descriptor.
5. Verify the task-authorization request, every referenced
   technical-verification packet, and the operator authorization record's exact
   digest links.
6. Verify current-state, cutoff, freshness, availability, source-use rights and
   admissibility, privacy, reportability, and evidence receipts.
7. Build the context assembly.
8. Apply the named adapter, enforce its token budget, and create the provider
   load.
9. Emit and persist the exact build and loading receipts.
10. Recheck status at the pre-execution checkpoint.
11. Run only the provider or deterministic executor permitted by the mode and
    effective capability intersection.
12. Validate structured output and apply deterministic vetoes.
13. Preserve raw output, evidence references, disagreements, missing evidence,
    and validator results.
14. Recheck status before any consequential transition, then stop at the exact
    authorized terminal or human gate.

A future run receipt must record at minimum:

- execution mode and trust-root ID/version/digest;
- Kernel ID/version, manifest and constraint-set digests, component IDs, paths,
  versions, and digests;
- exact custody/status-record bytes digest, repository revision, observed time,
  status, supersession result, operator decision refs, and every checkpoint
  result;
- doctrine-profile or absence-marker, ordered repository-module-set,
  workload-profile, task-authorization-request, technical-verification-packet,
  operator-authorization-record, evidence-index, routing-policy, and adapter
  IDs/versions/digests;
- operator decision-record IDs/digests; requested and excluded
  operator-attestation types; accepted technical-verification source
  IDs/digests; conditions, expiry, and reauthorization-trigger state;
- adapter, provider, model, reasoning, cache, and routing metadata;
- enabled tools, networks, repositories, paths, budgets, and effective
  capability calculation;
- per-layer bytes/tokens, output reserve, omissions, and overflow diagnostics;
- dynamic task sources, evidence references, namespaced epistemic/evidence,
  freshness, technical-availability, privacy, and reportability states;
- exact source-use/admissibility policy, policy status, decision ref, intended
  use axes, and per-axis outcomes;
- build-receipt and Kernel-loading-receipt refs/digests, context-assembly digest,
  and provider-load/request digest;
- provider invocation/transport ID, execution start/end times, raw response
  digest, parsed/structured-output digest, and exact output-schema ID/version;
- deterministic validator IDs, versions, properties checked, and results;
- subagent roles and shared Kernel/task pins;
- disagreements, unknowns, and unresolved evidence gaps;
- final fail-closed or handoff status.

These bindings are mandatory for failed and malformed-output runs. A field that
cannot exist because execution stopped early must carry an explicit unavailable
reason and stage; it must not be silently omitted. This prevents a descriptive
receipt from being detached from the exact request, provider load, and output it
claims to represent.

## 13. Relationship to Harness, Research, and the human Workspace

### 13.1 TIBER-Harness

TIBER-Harness remains a provider-neutral evaluation/runtime layer. The Kernel
contract is system-owned through Ops; Harness later consumes, loads, adapts, and
tests it. Harness #5 should be narrowed accordingly:

- generic workload profiles;
- provider-routing policy separate from workload semantics;
- deterministic Kernel builder/loader conformance;
- provider adapters;
- observability and receipts; and
- synthetic failure fixtures.

A future Kernel-to-Harness invocation envelope should bind, at minimum,
`invocation_id`, `execution_mode`, `trust_root_ref`, `kernel_manifest_ref`,
`kernel_status_record_ref`, `kernel_constraint_set_ref`,
`doctrine_profile_ref_or_absence`, `repository_module_refs`,
`workload_profile_ref`, `task_authorization_request_ref`,
`technical_verification_refs`, `operator_authorization_record_ref`,
`evidence_index_ref`, `routing_policy_ref`, `adapter_ref`,
`dynamic_context_refs`, `role`, `permitted_capabilities`, `validator_set`, and
`output_contract`. Every authoritative reference includes an exact version and
digest; absence is allowed only when the workload schema explicitly declares
it. A conforming run should emit distinct
`kernel_loading_receipt` and `harness_run_receipt` records. These are proposed
interfaces, not fields implemented by the current Harness.

Harness must not own a second Kernel, promote real artifacts, become a source of
football truth, or become a runtime dependency of product and domain
repositories.

### 13.2 TIBER-Research

The placement decision in Harness PR #7 remains settled:

- Ops owns activation, amendment, cancellation, promotion, revocation, and
  supersession authority;
- Research owns file-backed custody of research jobs, inputs, evidence lineage,
  attempts, packets, reviews, and seals;
- executors and reviewers are bounded roles rather than state owners; and
- Harness remains outside the live Research path unless separately authorized.

Research Stage 0 is merged. Draft PR #2 proves the Stage 1 preflight can remain
valid while `activation_ready` is false. Kernel work must not fill missing
operator inputs or infer Research activation from green tests.

Harness's current `promotionReady` result must not be reused as a Research
lifecycle decision. Research separately records process terminal, completion,
review, seal, and downstream authority; mechanical Harness conformance cannot
activate, complete, promote, or grant downstream authority to a Research job.

Research and Kernel/Harness may progress as separate campaigns. Research should
remain the empirical track; Kernel/Harness should begin as design and synthetic
conformance. Their first safe convergence is a read-only, offline Harness replay
of the existing synthetic Research fixture, using exact pins and granting no
live Research, source, promotion, or product authority.

The candidate conformance target is repository
`Prometheus-Frameworks/TIBER-Research`, commit
`8a8039eeaa2ba1b8cae65859d43746df6b949ecd`, tree
`582930f21d6fafafcfc55527e5aa9363c08ad417`, and job path
`fixtures/synthetic-complete/job.yaml`. The job has Git blob
`b1cac3eec7bccf7e3025a6147416870fcebe09b0` and raw digest
`sha256:4ef609ca1882429e7606e97bd6af67120c9eb332ae15f37574ac7de1a71f32b5`
under `tiber-raw-sha256-v1`. The attempt submission digest is
`sha256:ffa571716fb9d540d8b48d293db3dd24d99277b4d1034d4d377dfb8313d1853b`
and its archive/seal digest is
`sha256:873c41afbad7de74b70ef184e92dc3085923c1ef922aef055bb67f2bfec7b68b`;
both use `tiber-canonical-json-v1`. Any later conformance issue must re-verify
those identities and their status; this report does not authorize the replay.

Research lifecycle stages do not belong in the core Kernel. They remain a
Research workload/module contract.

### 13.3 Human Workspace

TIBER-Fantasy/Workspace is the human operator projection: state, change,
evidence, uncertainty, and decisions. Harness is the agentic projection: role,
current context, tools, evidence, authority envelope, stop conditions, and
receipts.

Both may consume evidence from the same governed world state. They need not use
one packet or identical prose. The Kernel standardizes shared meanings and
authority boundaries; it does not turn a pilot-local Workspace packet into a
canonical cross-repository contract.

## 14. Operator doctrine and authorization

Operator reflection is valuable context but must not become policy by proximity
to an agent. The minimum doctrine flow is:

```text
exploratory operator entry
→ doctrine candidate
→ independent review and exact identity
→ explicit operator promotion
→ versioned doctrine profile eligible for context assembly
```

Raw entries, voice transcripts, chat summaries, operator feelings, and narrative
ledgers remain non-binding unless they pass that flow. A promoted doctrine
profile is source-traceable, hashable, status-aware, replayable, and separately
identified from the required core Kernel.

Task authorization is different from doctrine. The immutable request identifies
one exact outcome and requested capability envelope; the verification packet
records what was checked; the operator record binds the exact request and
accepted verification digests. Technical verification informs the operator but
never substitutes for authorization. Approval states both what the operator is
attesting to and what they are not being asked to attest to.

Required reauthorization triggers include:

- changed outcome or success definition;
- expanded repository, path, source, subject, tool, network, or write scope;
- changed Kernel, doctrine, module, workload, or task-authorization-request
  digest;
- new private-context, source-rights, spending, publication, deployment, or
  irreversible consequence;
- changed authority ceiling, risk, rollback, cutoff, or budget; and
- a review finding whose correction requires broader interpretation.

## 15. Trust and evidence boundaries

The Kernel defines operating assumptions; it is not evidence for football or
product claims. The following remain non-evidence unless separately admitted
under a task contract:

- hidden provider reasoning;
- cached prompt state;
- persisted provider or conversation memory;
- model-generated summaries and intermediate work;
- adapter-generated text not traceable to exact governed segments;
- repository, issue, PR, comment, or source text merely because it uses
  instruction-like language;
- fixture narratives;
- a `/promoted/` path without promotion evidence;
- retrieval success without freshness and rights receipts; and
- validator success outside the validator's declared property scope.

The Kernel must preserve independent, namespaced axes that are frequently
collapsed. Where an existing schema owns the value vocabulary, namespacing the
field does not rename its values.

| Axis | Example states |
| --- | --- |
| `epistemic_class` | `observed`, `calculated`, `inferred`, `hypothesis`, `speculative`, `contradicted`, `unknown` |
| `evidence_support` | `unsupported`, `needs_verification`, `partially_supported`, `supported`, `contradictory`, `unresolved` |
| `freshness_state` | `current`, `stale`, `unresolved`, `not_applicable`, accompanied by the applicable distinct clocks |
| `technical_availability` | `available`, `unavailable`, `unresolved` |
| `source_use_admissibility.<intended_use>` | `admitted`, `inadmissible`, `unresolved` independently for acquisition, retention, internal analysis, local-model use, hosted-model use, transformation, publication, and redistribution as applicable |
| `privacy_class` | `public`, `private`, `restricted`, `unresolved` |
| `reportability` | `public_safe`, `internal`, `private`, `non_promotable`, `later_review_only` |
| `governance_state` | `fixture`, `candidate`, `adopted`, `superseded`, `revoked`, `withdrawn` |
| `authority_transition_state` | `mechanically_valid`, `review_eligible`, `reviewed`, `activated`, `promoted`, `revoked` |

A claim may be inferred, evidence-supported, derived from a governed artifact,
and still possess no promotion or action authority.

## 16. Versioning, change control, supersession, and rollback

- Every semantic component change creates a new component version and digest.
- Any ordered component, required/optional status, compatibility, budget, or
  build-rule change creates a new immutable manifest version.
- Kernel status is external to the immutable manifest.
- Repository modules declare compatible Kernel ranges but may not silently
  continue across an incompatible release.
- Workload profiles and adapters are versioned independently.
- Every run binds exact versions and digests; “latest” is prohibited.
- Constraint-set, component, module, workload, task, authorization, routing, or
  adapter drift fails closed.
- Supersession does not delete prior releases or invalidate historical receipts.
- Rollback is an explicit operator decision selecting an exact prior compatible
  release and recording why.
- Merge of Kernel material records bytes only. Adoption, activation, and later
  scaffold execution remain separate decisions.

The current Ops evidence contains status text that became stale after later
review or merge events. This is practical evidence for separating immutable
payloads from external mutable status records rather than editing historical
content in place.

## 17. Threat and failure analysis

| Threat or failure | Required control | Failure behavior |
| --- | --- | --- |
| Prompt injection in repository, issue, artifact, or source content | Trust roots selected externally; content segments labeled inert; tools and authority fixed before retrieval; predeclared deterministic parser/isolation and adapter-conformance checks | Continue only when those checks prove the content stayed inert and emit a receipt; otherwise block |
| Repo module weakens a core invariant | Machine-readable monotone narrowing and explicit compatibility validation; human review for claimed prose conflicts | Reject a machine conflict; block a prose conflict pending independent review |
| Task or agent self-expands scope | Exact task-authorization request, verification packets, authorization record, and capability intersection | Block and require a new request and human authorization |
| Missing or unverifiable authority trust root | Exact mode, trust-root digest, issuer status, and signature/attestation verification | No eligible context assembly |
| Stale or revoked Kernel | Exact external status receipt, checkpoints, and freeze-after-verify | Block the load or subsequent effect and preserve the historical receipt |
| Missing, duplicate, or hash-mismatched component | Deterministic manifest resolution | No eligible context assembly |
| Adapter reorders, omits, or changes semantics | Adapter conformance fixtures and provider-load receipt | Adapter incompatible; block |
| Silent token truncation | Hard byte/token budgets and reserved output capacity | Split work under new task or block |
| Kernel bloat and irrelevant-context dilution | Eight-component v0 ceiling, per-component budgets, explicit scope test | Reject component or new manifest pending review |
| Cached or persisted reasoning treated as evidence | Cache/persistence fields isolated from evidence ledger | Validation failure |
| Availability mistaken for source permission | Separate freshness, technical-availability, intended-use admissibility, privacy, retention, and reportability receipts | Mark the intended use `inadmissible` or `unresolved` and fail closed; never relabel it unavailable |
| Merged candidate mistaken for adopted policy | Immutable payload plus external decision/status registry | Candidate remains non-operative |
| Validator result mistaken for empirical truth or promotion | Declared property scope and authority ladder | Report misclassification and block transition |
| Raw operator note becomes doctrine | Candidate/promotion workflow and exact doctrine-profile digest | Note remains non-binding |
| Human and agent packets silently diverge | Shared receipt vocabulary and comparable source/evidence references | Expose mismatch; neither silently overwrites the other |
| Dual Kernel definitions in Ops and Harness | Ops owns canonical contract; Harness is a consuming implementation | Reject unpinned Harness-local doctrine as non-canonical |
| Old task replay represented as current | Exact cutoff/freshness receipts and run-time status | Label historical or block current-state claim |

## 18. Staged implementation options

### Stage D0 — this design report

- One Ops architecture candidate.
- No runtime, schema package, component extraction, or adapter.
- Operator review required.

### Stage M0 — manifest and component scaffold proposal

- Separate finite issue and authority.
- Freeze exact source revisions and propose only the eight core component slots
  identified by D0; adoption still requires a separate operator decision.
- Add docs-only schema candidates and synthetic valid/invalid fixtures for the
  manifest, constraint set, custody/status record, doctrine absence/profile,
  repository-module set, workload, task-authorization request, verification
  packet, operator authorization, evidence index, routing policy, adapter
  descriptor, and build/load/run receipts.
- Define the two-step manifest custody binding without embedding the containing
  commit in the manifest.
- Keep Ops docs-only; no executable builder or automatic agent loading.
- A merge records candidate bytes and does not adopt them.

### Stage B0 — deterministic builder/loader scaffold proposal

- Separate finite issue, sequenced after an accepted manifest candidate.
- Place executable reference tooling in Harness or another separately approved
  runtime-owning location, not Ops.
- `synthetic_conformance` only, with an explicit synthetic trust root and
  MockProvider/deterministic fixtures.
- Verify order, hashes, custody/status, machine-readable capability narrowing,
  cross-module conflicts, budgets, request/verification/authorization links,
  receipts, and fail-closed behavior.
- No provider routing, live model call, repository instruction replacement, or
  Research activation.

### Stage C0 — synthetic conformance

- Use the existing public-safe synthetic Research fixture as the first external
  consumer through a read-only wrapper owned by Harness; require no Research
  schema or repository change.
- Run deterministic and MockProvider replay only under identical Kernel,
  module-set, task-authorization-request, synthetic authorization, and evidence
  pins.
- Preserve fixture identity, disagreement, and validator results.
- No live football evidence or downstream authority.

### Stage A0 — adapter and provider benchmark

- Separate provider-specific authority, credentials, cost ceiling, and network
  policy.
- Compare agents/providers under identical pins and benchmark adapter fidelity
  and workload routing rather than assuming model assignments.
- No production binding from a benchmark result.

### Stage L0 — limited live agent entry

- Only after the Research pilot and synthetic conformance expose real context
  needs, a live operator trust root is approved, and the Kernel is adopted.
- One bounded task, one repository/module, one workload profile, one exact
  adopted Kernel, one operator authorization, and one independent review.
- Public, non-sensitive fixture or task context only until separately governed
  encryption, retention, redaction, private-receipt partitioning, and source-use
  policy exist; no private league or user context.
- No general autonomous TIBER agent or universal runtime implied.

## 19. Unresolved questions for later scaffold issues

1. Should the immutable manifest/components live permanently in Ops, or should
   Ops govern a package held by a future dedicated custody location? The v0
   candidate may be staged in Ops only through a separate docs-only exception.
2. Which exact existing statements are promoted into each of the eight core
   components, and which remain merely repeated candidate language?
3. Which canonical JSON and raw-byte hashing procedures should the Kernel reuse?
4. What live operator issuer, key, or host-attested identity contract should
   replace GitHub account/comment identity as the `authorized_run` trust root?
5. What is the first promoted operator-doctrine profile, if any?
6. What conservative provider-neutral byte limit and adapter-specific token
   budgets are justified by measured builds?
7. Which provider interfaces cannot preserve the required segment and
   instruction separation?
8. How should private user/league context be encrypted, retained, redacted, and
   excluded from public receipts in a later live workload?
9. When should #22's current-state snapshot and lane indexes be reconciled with
    the newer #30 design activation? That reconciliation is outside this report's
    write scope.

None of these questions blocks the D0 design conclusion. Each blocks the
affected scaffold detail or live stage and must not be silently assumed during
implementation.

## 20. Final recommendation

Proceed only to separately reviewed proposals for:

1. a small, docs-only manifest/component scaffold governed through Ops; and
2. a subsequent offline deterministic builder/loader scaffold in a
   runtime-owning repository, with Harness as the leading candidate.

The manifest proposal should precede builder execution. Adapter implementation,
provider routing, live Research, automatic instruction injection, and product
integration remain later decisions.

This terminal is design evidence only. It does not create, activate, or merge
either follow-up issue and grants no implementation authority:

```text
may_open_kernel_manifest_and_builder_scaffold_issues
```
