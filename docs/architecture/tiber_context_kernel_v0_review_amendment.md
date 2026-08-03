# TIBER Governance Kernel v0 — review amendment

Status: **DESIGN CANDIDATE AMENDMENT — NOT ADOPTED — NO RUNTIME AUTHORITY**

This document is a bounded design-only amendment to
`docs/architecture/tiber_context_kernel_v0.md` in TIBER-Ops PR #58. For the
candidate represented by that PR, the requirements below supersede any broader
or conflicting wording in the base report. This amendment does not implement a
runtime, activate Research, select a live trust root, grant provider or tool
authority, adopt the Kernel, or authorize merge or deployment.

## 1. Authorization remains live only while continuously valid

Initial validation of an operator authorization record is not sufficient for an
effectful run. The future builder/loader contract must re-resolve and revalidate
the complete authorization state immediately before every provider execution
and immediately before every consequential transition.

Each effectful checkpoint must verify, from authoritative current state:

- the exact authorization-record identity and digest;
- its effective-from and expiry bounds at the checkpoint time;
- that it has not been superseded, revoked, withdrawn, or otherwise invalidated;
- the current status of its issuer and externally selected trust root;
- the exact task-request and accepted verification-packet bindings;
- the authorized capability subset, scope, paths, networks, tools, effects,
  budgets, conditions, withheld decisions, and terminal; and
- that the effective capability intersection has not widened or otherwise
  changed since assembly.

A failed or unavailable authorization revalidation blocks the provider call or
transition and emits a failed checkpoint receipt. An authorization that was
valid during assembly grants no residual authority after expiry, supersession,
revocation, issuer invalidation, trust-root invalidation, or material bound-state
change.

## 2. Status authenticity is not status currency

A correctly signed historical Kernel status record proves that the record was
authentic when issued. It does not prove that the release is still current.
Standalone presentation of an old `adopted` record is therefore insufficient.

Every initial status lookup and every later status checkpoint must bind to a
fresh, trusted, authoritative registry head or an equivalent proof that provides
all of the following properties:

- monotonic ordering or sequence identity;
- exact registry-head or checkpoint digest and trusted custody identity;
- observation time and maximum permitted observation age;
- membership of the presented release/status record in that head; and
- current supersession, revocation, withdrawal, successor, and non-revocation
  results for the exact manifest digest.

A signed checkpoint, transparency-log proof, monotonic registry sequence, or
another separately governed mechanism may satisfy this contract only if it
provides equivalent current-state and anti-replay guarantees. A cache entry,
old observation receipt, release-local signature, or historically valid status
record cannot substitute for that proof.

If the authoritative head cannot be resolved, its freshness cannot be proven,
or it conflicts with the presented release/status record, the load or subsequent
effect fails closed. Build, load, and run receipts must record the authoritative
head/proof identity, digest, sequence, observation time, freshness result, and
supersession/revocation outcome used at each checkpoint.

## 3. Structural isolation does not prove semantic prompt inertness

Parser, segment, escaping, round-trip, and adapter-conformance checks establish
structural properties only. They may prove that untrusted bytes remained in the
declared evidence segment and that the provider load preserved the declared
layout. They cannot prove that a probabilistic model ignored instruction-like
content, that its output was semantically unaffected, or that prompt injection
was neutralized.

The candidate must therefore use the following claim boundary:

> Retrieved and repository content is untrusted data and grants no authority.
> Structural validation proves boundary preservation, not semantic inertness.
> Safety depends on externally derived authority, constrained capabilities,
> independent effect validation, and fail-closed checkpoints outside the model.

A future conforming runtime must layer containment rather than rely on labeling
alone:

1. Derive tools, networks, repositories, paths, budgets, and effect permissions
   solely from host controls, the adopted Kernel constraint set, the exact
   operator authorization, repository modules, and workload/task contracts —
   never from retrieved text or model output.
2. Disable every capability not required by the exact authorized run and expose
   only the minimum typed interfaces needed for that run.
3. Treat model-proposed tool calls and transitions as untrusted proposals;
   validate each outside the model against current authorization, scope,
   capability, schema, argument, budget, and checkpoint state before execution.
4. Require deterministic structured-output validation and preserve raw output,
   suspicious instruction-like evidence, disagreements, and validation results
   in receipts.
5. Block when required separation cannot be represented by the provider/adapter,
   when an effect cannot be independently validated, or when authorization or
   registry currency cannot be re-established.
6. Use adversarial and synthetic prompt-injection fixtures as resilience
   evidence only; passing them is not proof of immunity.

Accordingly, the prompt-injection threat row in the base report is superseded as
follows:

| Threat or failure | Required control | Failure behavior |
| --- | --- | --- |
| Prompt injection in repository, issue, artifact, or source content | Externally selected trust roots; untrusted-data segmentation; structural parser/isolation and adapter-conformance checks; independently derived least-privilege capabilities; typed tool interfaces; external validation of every proposed effect; current authorization and registry checkpoints | Structural checks may establish boundary preservation only. Continue only within the independently validated capability envelope; block any unvalidated effect, incompatible provider boundary, or failed current-state checkpoint. Never claim that the content was proven semantically inert. |

## 4. Required sequence and receipt corrections

For the candidate architecture, the future loading/execution sequence must be
interpreted with these mandatory corrections:

- Before provider execution, revalidate both the Kernel's authoritative current
  registry status **and** the complete operator authorization state described in
  section 1.
- Before any consequential transition, repeat both revalidations and recompute
  the effective capability intersection.
- Record separate results for Kernel-status currency, authorization currency,
  issuer/trust-root validity, scope/capability/budget consistency, and external
  effect validation.
- A field unavailable because execution stopped early must carry an explicit
  unavailable reason and stage; it must not be silently omitted.

These corrections apply to the builder inputs/procedure, loading sequence,
run-receipt minimums, and threat/failure analysis in the base report.

## 5. Scope held

This amendment changes only the design candidate's stated contracts and claim
boundaries. It does not:

- select or implement a registry, key, attestation, provider, adapter, builder,
  tool broker, or enforcement runtime;
- modify TIBER-Harness, TIBER-Research, or another repository;
- activate a Research workload or live provider run;
- change the Kernel's broader human-authority model; or
- adopt, merge, deploy, or promote any candidate artifact.
