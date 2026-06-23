# Weekly Cadence

TIBER-Ops runs on a weekly board. The board exists to enforce one rule:

> **Only one implementation lane is active at a time.**

## The weekly board

Each week the board does two things:

1. **Choose one active lane.** Exactly one implementation lane is selected for
   the week. That is where implementation work is allowed to happen.
2. **Explicitly mark everything else as parked.** Every other lane is named and
   marked parked, audited, or indexed. Silence is not allowed — if a lane is
   not the active lane, it is explicitly set aside.

"Explicitly mark" means it is written down in
[`lane-index.md`](lane-index.md). A lane that nobody mentioned is not
implicitly parked — it is a gap to close at the board.

## Board agenda

1. **Review current state.** Walk [`lane-index.md`](lane-index.md) and confirm
   each lane's status is accurate.
2. **Pick the active lane.** Choose the single lane to implement this week.
3. **Park the rest.** Explicitly mark every other lane parked / audited /
   indexed.
4. **Check for drift.** Did any work happen last week outside the active lane?
   If so, surface it — quiet implementation is a process error.
5. **Promote if needed.** If a parked idea should become active, move it per
   [`parked-ideas.md`](parked-ideas.md) and update the index.

## Outputs

- An updated [`lane-index.md`](lane-index.md) reflecting the week's active lane
  and parked lanes.
- A clear answer to: *"What is the one thing being implemented this week?"*
