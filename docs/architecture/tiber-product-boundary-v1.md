# TIBER Product Boundary v1

**Status:** Architecture direction recorded as locked in [TIBER-Ops #64](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64); implementation inactive.  
**Authority effect:** Documentation only. This document does not authorize a UI rewrite, route removal, runtime deployment, MCP expansion, authentication design, data promotion, or repository mutation.  
**Human decision owner:** Joseph (`@Prometheus-Frameworks`).  
**Last reconciled:** 2026-08-20.

## 1. Decision

> **Bring your own agent. Bring your own evidence. Bring your own ideas. TIBER provides the governed football world and the machinery for reasoning across them.**

TIBER should not compete to become the user’s general-purpose conversational agent, memory provider, fantasy platform, proprietary-data vendor, or universal dashboard.

TIBER should become the durable football context system that good agents can plug into.

The product boundary is:

- the human manages the mission;
- the agent interprets the request, traverses the terrain, and constructs the immediate interface;
- TIBER preserves the governed map, its evidence, its history, and its authority boundaries.

Or more compactly:

> **Humans speak in context. Agents structure it. TIBER remembers it.**

## 2. North star

> **Build the best football context system that good agents can plug into.**

TIBER should increase the value of football knowledge an operator already has access to. It should not require that knowledge to originate inside TIBER.

TIBER therefore behaves more like durable context infrastructure than a conventional rankings destination. Its distinguishing value is that it also contributes governed football artifacts, canonical identity, Shared Reality, provenance, Forecast and Research outputs, uncertainty, and longitudinal state.

Two independent improvements should compound:

```text
better agents
  → make existing TIBER context easier to use

better TIBER context
  → makes every compatible agent more useful
```

## 3. Responsibility boundary

| Actor | Owns | Does not own by default |
| --- | --- | --- |
| **Human operator** | Mission, questions, beliefs, evidence they are entitled to use, confirmation, fantasy decisions, retention and sharing choices | Schema construction, repository navigation, or manually translating natural language into every durable field |
| **User’s agent** | Conversation, voice and multimodal interaction, personal interaction style, temporary reasoning context, reminders, presentation, generated views, and translation of natural language into bounded TIBER operations | Canonical football truth, silent evidence promotion, unrestricted mutation, final fantasy authority, or authoritative long-term storage of TIBER objects |
| **TIBER** | Canonical identity, Shared Reality, observations and events, provenance and clocks, source-rights semantics, Research and Forecast artifacts, uncertainty and Missing Witnesses, context-bound models, append-only history, validation, and transparent inspection | The user’s primary chatbot, every proprietary dataset, generic agent memory, arbitrary dashboard generation, or external-platform execution |
| **External fantasy platform or connector** | Authoritative account, league, roster, transaction and execution state; credential enforcement; platform-side precondition checks | TIBER evidence authority or the user’s decision |
| **Human-facing TIBER software** | Stable inspection and control surfaces over TIBER-owned state | Anticipating every possible workflow or permanently hosting every useful projection |

Governed league actions such as rosters, picks, and transactions should be represented as durable league state when TIBER has a lawful, reliable source. The agent may interpret that state for the operator, but should not remain its only store.

Similarly, a durable conditional football claim belongs in TIBER context. The agent may own the alarm clock that rechecks it.

## 4. Shared Reality and operator-local context

TIBER must preserve the difference between shared football reality and evidence or beliefs available only to one operator.

### 4.1 Evidence scopes

1. **TIBER Shared Reality**  
   Governed evidence and state TIBER may retain and report under its source contracts.

2. **Operator-private evidence**  
   Proprietary, licensed, local, or personal material the operator is entitled to use but TIBER is not entitled to redistribute or promote globally.

3. **Operator-supplied ephemeral evidence**  
   A screenshot, excerpt, observation, or temporary conversation artifact that may inform bounded private reasoning without becoming a shared dataset.

4. **Operator hypothesis or inference**  
   A belief, supposition, question, or interpretation. It is not evidence merely because an operator or agent stated it.

Private evidence may enrich an operator’s model without entering Shared Reality. Another operator does not inherit it. Any retained reference, derived claim, or provenance record must remain within the source’s rights, retention, and reportability boundaries.

Private branches must be invisible by default. Comparing two operators’ divergent trees requires appropriate permission from both sides; revealing that a private branch exists may itself leak competitive information.

### 4.2 The field, not the locker room

The ability to bring private evidence is not permission to ingest or model leaguemates’ private communications or psychology.

Chat-derived, coercively obtained, or psychological evidence about leaguemates is inadmissible in every TIBER scope. It is not merely non-promotable; it is non-representable in TIBER objects, including operator-private workspaces.

TIBER may reason about observable game and league actions. It must not become a system for surveilling or profiling the people behind them.

## 5. Canonical Fantasy front door: Pulse + Use TIBER

The canonical TIBER Fantasy entrance has two responsibilities:

> **Show me what TIBER currently sees, then show me how to use that context wherever I work.**

### 5.1 Pulse / Shared Reality

The upper portion should expose recent governed changes in TIBER’s represented football world.

A Pulse item exists because TIBER’s state changed, not merely because an article was published.

A Pulse event should make inspectable:

- the verified event or observation;
- resolved entities;
- source, provenance, and clocks;
- which TIBER artifacts or subsystems are affected;
- which outputs are updated, stale, recomputing, blocked, or under review;
- what remains unknown;
- whether the event changed Shared Reality, TIBER interpretation, or neither.

Pulse must not become a generic news feed or a rankings table. It is a mobile-readable inspection surface for TIBER state, change propagation, uncertainty, and provenance.

### 5.2 Use TIBER

The lower portion should help an operator take TIBER context into their preferred workflow.

It should include:

- connection paths for supported agents and MCP clients;
- plain-language setup instructions;
- tool and permission explanations;
- concrete example prompts and demonstrations;
- links to Shared Reality, provenance, methodology, and open-source records;
- clear distinctions between read, bounded write, and unavailable capabilities.

Example workflows may include:

- “Bring up the models I track for this roster. What changed this week?”
- “Build a working model around this player and show what evidence would change it.”
- “I follow the Jets. Show the important changes to their offensive environment.”
- “Compare this private route dataset against TIBER without publishing my data.”
- “Create a temporary draft or research board from these governed artifacts.”

### 5.3 Shared view versus operator-local view

- **Pulse:** shared/public TIBER view of governed football-world changes.
- **Connected agent:** operator-local view of why those changes intersect the operator’s models, roster, research mission, or private evidence.

The homepage does not need to render every personalized dashboard to support personalized reasoning.

## 6. Canonical UI versus generated projections

TIBER owns durable state and governed primitives. Interfaces are projections of that state and need not all be canonical or permanent.

Before building a substantial UI surface, ask:

> **Does this need to be canonical TIBER inspection or control UI, or is it one possible projection an agent could construct from TIBER artifacts?**

### 6.1 Canonical TIBER UI

Canonical surfaces are justified where users need a stable shared representation or control boundary, including:

- Pulse and World-state changes;
- evidence, provenance, freshness, and artifact history;
- entity identity and state inspection;
- context-model history and append lineage;
- permissions, privacy, account, workspace, and security state;
- operator confirmation and authority decisions;
- stable share, fork, and replay views where permitted;
- canonical human-readable renderers for governed objects.

### 6.2 Generated or specialist projections

The following are projections by default, not automatic permanent-product obligations:

- rankings and tiers tables;
- roster cockpits;
- draft boards;
- weekly comparison views;
- player and team research boards;
- scenario and stress-test labs;
- weekly briefs;
- portfolio-risk views;
- custom reports and visualizations.

These may still be useful as:

- agent-generated temporary interfaces;
- durable reports when citation or replay matters;
- example workflows and demonstrations;
- specialist inspection views;
- reusable application operations or MCP tools;
- archived references to prior experiments.

This direction does not itself delete rankings, Tiers, scenario labs, or any other existing surface. It removes the assumption that their existence in code makes them a required canonical destination.

Before removal or migration, each surface must be audited for live callers, durable contracts, reusable methods, governance lessons, and active user value.

## 7. MCP and transport neutrality

MCP is an important agent-facing transport. It is not TIBER’s domain architecture.

The durable dependency direction is:

```text
Domain objects
  Shared Reality
  Event
  ContextBoundEntityModel
  ResearchRun
  Artifact

Application operations
  resolve entity
  inspect state
  inspect contract
  validate candidate
  get/save model
  append observation
  inspect lineage

Transport adapters
  MCP
  HTTP
  native clients
  future app tools
```

If MCP disappeared, the domain objects and application operations should remain coherent and testable.

Transport credentials answer who or what may call a service. They do not establish that a human approved a consequential action. Read permission, bounded context writes, evidence promotion, and external-platform execution are separate capabilities and must remain separately governable.

TIBER must remain provider-neutral. ChatGPT, Claude, Grok, local agents, native clients, and future interfaces should assemble compatible TIBER objects rather than creating provider-specific truths.

## 8. Capability parity without repository authority

> **Repo access is today’s scaffolding. Governed introspection should become tomorrow’s product capability.**

A connected agent should be able to inspect TIBER deeply enough to reason correctly without receiving software-maintainer authority.

Candidate capability families include:

### Kernel or governance introspection

- inspect contracts and schema versions;
- validate a candidate against the real contract;
- explain a rejection;
- inspect authority classes and promotion ceilings;
- inspect lineage, receipts, digests, and freshness;
- discover governed precedents.

Whether TIBER-Kernel is the final owner remains an open design question under [TIBER-Ops #67](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/67).

### World

- resolve canonical entities;
- inspect current Shared Reality;
- inspect events, transitions, artifacts, clocks, and unknowns.

### Operator context

- retrieve and persist context-bound models;
- append observations and RFIs under bounded authority;
- preserve operator-local and Shared Reality boundaries.

### Research

- inspect bounded runs;
- submit candidate outputs through governed custody;
- inspect state without self-review or self-promotion authority.

Capability parity does not imply:

- git push or repository mutation;
- PR merge;
- canonical schema editing;
- artifact-history rewriting;
- direct publication into Shared Reality;
- broad cross-workspace writes;
- autonomous fantasy-platform action.

Read breadth and mutation breadth must be independently configurable. Canonical publication remains a separate governed act.

## 9. Non-goals

This architecture direction does not authorize or require:

- a broad TIBER-Fantasy rewrite;
- immediate removal of existing pages, routes, APIs, or modules;
- a general-purpose TIBER chatbot;
- TIBER-owned voice transcription or generic multimodal tooling;
- a universal dashboard generator;
- replacement of Sleeper or another fantasy platform;
- reproduction of every proprietary football dataset;
- bypassing licenses, paywalls, access controls, or source terms;
- silent promotion of private or ephemeral evidence;
- unrestricted agent writes;
- autonomous start/sit, waiver, trade, draft, lineup, or roster execution;
- remote MCP hosting, OAuth, or multi-tenant authentication;
- repository access as the normal product interface;
- a decision that rankings or scenario analysis must disappear;
- treating an API key, connected tool, or available write method as human approval.

The platform-neutral exact-action architecture in [TIBER-Ops #39](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/39) remains parked. Any future platform execution requires a separate activation and must preserve platform-owned state, exact payload approval, state revalidation, expiry, and receipts.

## 10. Implementation implications and gates

This document establishes direction only. Each implementation requires a separately scoped issue and explicit authority.

Recommended follow-up sequence:

1. **Promote and reconcile documentation**  
   Mark older conflicting product-positioning documents as historical or partially superseded without erasing their implementation evidence.

2. **Run a bounded Fantasy surface-and-consumer audit**  
   Classify every mounted route, API, module, and unmounted historical surface as:
   - canonical inspection/control;
   - reusable domain or MCP capability;
   - useful generated projection/demo;
   - archive or quarantine;
   - delete after replacement and verified consumer removal.

3. **Define the Pulse event contract**  
   Reuse governed World, event, identity, provenance, freshness, uncertainty, and impact-propagation primitives. Audit TIBER-Rookies Devy Pulse before creating a duplicate architecture.

4. **Design the Use TIBER path**  
   Document supported clients, connection methods, permissions, concrete workflows, failure states, and safe demos.

5. **Separate capabilities from current pages**  
   Preserve reusable contracts and calculations independently of whether their existing UI remains mounted.

6. **Expand governed introspection before granting repository access**  
   Resolve the ownership and minimal read surface requested by Ops #67.

7. **Preserve deletion discipline**  
   Prove imports, routes, callers, scripts, deployments, and tests before removal. Quarantine ambiguous code first and delete only after its replacement and consumer migration are verified.

No step above is activated by this document.

## 11. Supersession and related records

### 11.1 Source records promoted by this document

- [TIBER-Ops #64 — Bring your own agent, evidence, and ideas](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64)
- [Ambient football context, not canonical dashboard](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64#issuecomment-5319392694)
- [Canonical Fantasy front-door direction — Pulse + Use TIBER](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64#issuecomment-5331101249)
- [Architecture lock — frontier leverage and product boundary](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64#issuecomment-5334181969)
- [Architecture lock — capability parity without repository authority](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/64#issuecomment-5334449053)

### 11.2 Related architecture and pilots

- [TIBER World Workspace decisions](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/57)
- [World Workspace pilot record PR](https://github.com/Prometheus-Frameworks/TIBER-Ops/pull/56)
- [Capability parity through Kernel/MCP](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/67)
- [Platform-neutral agent-readiness interface](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/39)
- [Context-bound entity model MCP pilot](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/issues/332)
- [Merged minimal stdio MCP adapter](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/pull/333)
- [Causal thesis lineage](https://github.com/Prometheus-Frameworks/TIBER-Research/issues/9)
- [Agent-ready thesis-tree pilot](https://github.com/Prometheus-Frameworks/TIBER-Research/issues/10)

### 11.3 Older product documents

Where they conflict, this document supersedes only the older documents’ assumptions about TIBER’s primary product boundary and canonical front door:

- [TIBER v1 Product Surface](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/main/docs/TIBER_V1_SURFACE.md)
- [TIBER Product Shell Realignment Plan](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/main/docs/architecture/TIBER_PRODUCT_SHELL_REALIGNMENT_PLAN.md)
- [TiberClaw API Platform Vision](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/main/docs/TIBER_API_PLATFORM_VISION.md)
- [TIBER Rankings v2 Definition](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/main/docs/architecture/TIBER_RANKINGS_V2_DEFINITION.md)
- [TIBER Rankings v2 Explanation Surface](https://github.com/Prometheus-Frameworks/TIBER-Fantasy/blob/main/docs/architecture/TIBER_RANKINGS_V2_EXPLANATION_SURFACE.md)

Those records remain valid as historical evidence and may still contain useful implementation contracts, audits, and migration details. This document does not close their issues, remove their code, or decide the final disposition of their surfaces.

Later explicit operator decisions supersede this document.
