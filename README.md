# TIBER-Ops

TIBER-Ops is the **coordination layer** for TIBER work across Fantasy, Data,
FORGE, Teamstate, Rookies, PPM, FLF/research docs, and future parked ideas.

It is **not** a product repo and **not** an automation repo. It is the
operating layer for coordinating TIBER's multi-repo work: deciding what is
active, what is parked, and how work moves between repos.

## What TIBER-Ops does

- Holds the operating map: which lanes exist, what each one owns, and where
  the current anchors live.
- Indexes work across repos so nothing is "quietly implemented" outside the
  active lane.
- Defines the weekly cadence that picks **one** active implementation lane and
  parks everything else.
- Provides review and merge runbooks every contributing repo can point at.

## What TIBER-Ops does NOT own

TIBER-Ops does not own:

- Fantasy scoring
- Model logic
- Artifact production
- Product UI
- Source data

Those live in their respective repos. TIBER-Ops only coordinates.

## Repository contents

| Path | Purpose |
| --- | --- |
| [`docs/operating-map.md`](docs/operating-map.md) | The lanes, what each owns, and the core operating rule. |
| [`docs/lane-index.md`](docs/lane-index.md) | Per-lane index of repos, anchors, and current state. |
| [`docs/parked-ideas.md`](docs/parked-ideas.md) | Incubation backlog — explicitly parked, not in progress. |
| [`docs/weekly-cadence.md`](docs/weekly-cadence.md) | How the weekly board picks one active lane. |
| [`runbooks/pr-review.md`](runbooks/pr-review.md) | The questions every PR must answer. |
| [`runbooks/merge-checklist.md`](runbooks/merge-checklist.md) | Pre-merge checklist and guardrails. |

## Scope of this repository

This repo is **docs-only**. By design it contains:

- No code
- No GitHub Actions
- No automation
- No scripts
- No package files
- No agents
- No issue bots
- No external integrations
- No runtime behavior

If TIBER-Ops ever grows automation, that is a separate, explicitly promoted
lane — see [`docs/parked-ideas.md`](docs/parked-ideas.md). Until then this is
an operating map, nothing more.
