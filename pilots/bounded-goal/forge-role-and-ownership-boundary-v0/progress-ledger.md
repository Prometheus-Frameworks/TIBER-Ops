# Progress ledger — forge-role-and-ownership-boundary-v0

This is the append-oriented evidence ledger for the `#15` pilot campaign
(`TIBER-Ops#15`), governed by the goal contract at
`pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml`
in this same directory. It is the campaign's externalized memory: a fresh
agent or human must be able to resume from this file and the contract alone,
without private conversation history.

**Lifecycle note — two phases, two rules:**

- **Pre-merge proposal review (current phase).** While this PR is open and
  unmerged, this file and the contract may be corrected in place in
  response to review feedback (fresh-context reviewers, Codex, the human
  decision owner). Every such correction is summarized in the
  Review-correction log (Entry 0a) immediately below, naming what changed
  and why, so the correction history stays visible even though the prior
  text was edited rather than appended after. This phase ends at operator
  merge.
- **Post-merge execution (R2 onward).** Once merged and R2 is activated,
  entries become strictly append-only. **Do not rewrite prior entries.**
  Corrections are new entries that name what they supersede. Contract
  changes require the human-approved `amendment_protocol` in
  `goal-contract.yaml`.

---

## Entry 0a — Review-correction log (pre-merge proposal phase only)

Each row is a correction made to this proposal before merge, in response to
review feedback, with the commit that applied it.

| Correction | Commit | Source |
|---|---|---|
| R1 completion_evidence said "5 policy_pin file hashes"; corrected to the accurate 6 file-backed + 2 absence-record breakdown (contract + ledger Entry 3) | `7e87a1b` | Codex review |
| YAML validation command silently assumed PyYAML; documented the dependency, version, and install options explicitly (ledger Entry 12) | `7e87a1b` | Codex review |
| Post-activation write scope excluded the ledger, which R2-R5 must append to; restructured `scope.permitted_write_paths_future_execution` with explicit per-path `writable_during` | `7aae76b` | Codex review |
| R1's "full command log in progress-ledger.md" claim referenced a log that didn't exist; added ledger Entry 3a with the actual verbatim commands | `7aae76b` | Codex review |
| `contract.status: proposed_pending_human_gate_review` would become false at merge; replaced with a durable status plus a separate `effective_condition` | `907c90e` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |
| Ledger's no-rewrite rule contradicted the in-place edits already made to Entries 3/12; added this two-phase lifecycle note and this correction log | `907c90e` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |
| Freshness re-check language ("if resuming after a time gap", "reasonable staleness window") was non-deterministic; made unconditional (`step0_mandatory_invariants`, R2 `blocked_evidence`) | `907c90e` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |
| `fantasy_embedded_forge_module` note and R4's `completion_evidence`/`blocked_evidence` presented TIBER-Ops#13's route-wiring claim as fact while classifying #13 as contextual elsewhere (FC2); reworded to ground R4 in the pinned document's own text and to stop-and-escalate rather than require out-of-scope inspection | `907c90e` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |
| Entry 3a's policy-pin `verify` calls omitted the `repo_name` argument required by the 4-arg function signature (would report false `MISMATCH_or_MISSING`); corrected and re-executed for real, all `MATCH` | `907c90e` | Codex review |
| Entry 3a's repository-currency loop compared against `origin/$def` without an explicit `git fetch` first, so it could pass on stale remote-tracking refs; added `git fetch origin --quiet` to the logged loop and re-executed, still zero drift | `907c90e` | Codex review |
| The `[INDEPENDENT REVIEW]` comment attributed the four preceding corrections to "Operator independent review." The comment was subsequently edited to disclose it was Codex-authored, posted through the operator's authenticated account at Joseph's request — not a human/operator decision. Relabeled those four rows above accordingly. No technical content of those corrections was affected: each was independently verified against the actual file contents and re-executed commands before being applied, not accepted on the strength of any claimed authority. | `8e8c8c3` | Codex-authored review + operator `[PROVENANCE]` clarification comment |
| Entry 3a's repository-currency loop compared `local_head` to `remote_head` only, never against the commit actually pinned in `repository_revisions`; a rerun where both local and remote had drifted together from the pin would still print `match=YES`. Added an explicit `expected` pin per repo and a third comparison against it. | `8e8c8c3` | Codex review |
| Entry 3a's policy-absence `find` commands used `-maxdepth 1`, checking only the repository root; a nested policy file under `docs/`, `src/`, etc. in TIBER-Forecast or Role-and-opportunity-model would have been missed while still reporting "absence confirmed." Changed to an unbounded repo-wide search (excluding `.git`/`node_modules`) and re-executed for real: still zero results in either repository, so the R1 absence records are unchanged, but the log now proves that rather than assuming it. | `24ede1f` | Codex review |
| A fresh automated Codex review at head `24ede1f` (P1) found that R2's `named_evidence_gaps` required reconciling the TIBER-Data repo-boundaries doc and TIBER-FORGE ingestion spec, but neither was pinned in `governed_dependencies` — R2 as written could only rely on TIBER-Ops#13's ungoverned issue-text paraphrase of them, or immediately block. Both documents are real committed files (confirmed by direct lookup, not issue text like #13/#212); pinned both as new governed dependencies with fresh hashes after re-fetching and confirming their repos unchanged from `repository_revisions`, and reworded R2's evidence gap to cite the pinned dependency IDs directly. | `e0743bf` | Codex review (automated) |
| A separate manual `[CODEX REVIEW]` comment (properly self-labeled with provenance) suggested replacing the `*(this commit)*` placeholders in this table with durable SHAs for cold-resume clarity. Applied. | `e0743bf` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |
| A manual `[CODEX REVIEW]` on head `e0743bf` (properly self-labeled) found the P1 fix was directionally correct but left the contract internally inconsistent: it claimed alignment with "the merged registry" for all pins, R1's completion evidence still said "All 26," and `frontier.gating_condition` reported conditions 1-3/5/6 as fully satisfied, none of which accounted for the 2 newly-pinned dependencies being verified-but-unregistered in the actual merged #21 registry (independently confirmed: the registry's 16 top-level entries + companions flatten to exactly 26, and neither new document is among them, at any nesting level). Corrected throughout: added `registry_state: unregistered_verified_from_pinned_source` to both new entries; added `fail_closed_items` FC3 documenting the gap as non-blocking for merge but blocking for #21 closure and R2 activation; rewrote the header comment, R1's `completion_evidence`, `frontier.gating_condition` (now split into gate A, the #22 six-condition gate, and gate B, registry synchronization), and `terminal_authoring_decision.emitted_decision_note` to state this precisely; fixed the ledger's own stale "26" references in Entry 3 and Entry 12. | `d6488cf` | Codex-authored review (posted via the operator's account at Joseph's request; not a human decision) |

---

## Entry 1 — Campaign and contract identifiers

- **Campaign issue:** `Prometheus-Frameworks/TIBER-Ops#15` — "Define canonical
  FORGE role and cross-repository ownership boundary"
- **Pilot protocol issue:** `Prometheus-Frameworks/TIBER-Ops#20`
- **Freshness prerequisite issue:** `Prometheus-Frameworks/TIBER-Ops#21`
  (deliverables merged via PR #23, commit `e0497a0df592f8c788110a8b0e282268d97c8216`;
  remains open pending this contract's merge and post-merge confirmation)
- **Program authority issue:** `Prometheus-Frameworks/TIBER-Ops#22`
- **Authoring issue (this work):** `Prometheus-Frameworks/TIBER-Ops#25`
- **Pilot identifier:** `forge-role-and-ownership-boundary-v0`
- **Contract file:** `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml`
- **Ledger file (this file):** `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/progress-ledger.md`

## Entry 2 — Authoring timestamp and revision

- **Authoring timestamp:** `2026-07-13T22:36:33Z`
- **TIBER-Ops branch:** `claude/tiber-ops-25-pilot-contract-ledger`
- **TIBER-Ops base commit:** `e0497a0df592f8c788110a8b0e282268d97c8216`
  (main HEAD at authoring time — the merge commit for PR #23, which landed
  the #21 freshness preflight document and current-state registry)
- **Confirmed:** the two #21 artifacts referenced as step-0 invariants by
  the contract are present at this base commit:
  - `docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md`
  - `registry/tiber-current-state.v0.json`

## Entry 3 — R1 preflight procedure and observed results

**Requirement:** R1 — Freshness preflight and verified input freeze
**Procedure:** Re-ran the merged #21 preflight in full rather than copying
registry values. For each of the 7 governed-source repositories: fetched
`origin`, resolved the remote default branch, and compared local `HEAD` to
`origin/<default>`. For each governed dependency and policy pin listed in
the merged registry: recomputed `sha256sum` against the working tree at the
verified commit and compared to the registry's pinned hash.

**Repository currency (all re-fetched and compared 2026-07-13T22:36:33Z):**

| Repo | Verified HEAD | Matches registry pin |
|---|---|---|
| TIBER-Ops | `e0497a0df592f8c788110a8b0e282268d97c8216` | n/a (write repo, post-#23-merge) |
| TIBER-Data | `d9a5beaacf12e3fbd74becd02db3d2ac39e48905` | yes |
| TIBER-Forecast | `478489b565a97a1179d6010ebf9b1b4326a50c04` | yes |
| TIBER-Teamstate | `3ec1d78e10fccf203239c88b905e3cf744d21c48` | yes |
| Role-and-opportunity-model | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | yes |
| TIBER-FORGE | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | yes |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | yes |
| TIBER-Rookies | `2ef92faf9a9c91a393f53e9140428451529a1c48` | yes |

**Result:** zero drift. All 7 governed-source repositories are at the exact
commits pinned in the merged registry (`registry/tiber-current-state.v0.json`,
verified 2026-07-13 during PR #23). No repository advanced between the
registry's verification and this contract's authoring.

**Artifact/contract hash re-verification:** all 28 `governed_dependencies`
entries and all 6 file-backed `policy_pins` entries (Teamstate, Data,
Fantasy, Rookies, FORGE, TIBER-Ops) in the goal contract were independently
recomputed via `sha256sum` against the current working tree and matched
their pinned values with zero mismatches. Of the 28 dependencies, 26 are
also present in the merged #21 registry and were cross-checked against it;
the remaining 2 (`tiber_data_repo_boundaries_and_feedback_loops`,
`tiber_forge_data_to_forge_ingestion_spec`, added after a P1 review finding
— see Entry 0a) are verified directly from source at their pinned
revisions but are **not yet present in the merged registry** — see FC3
below and `fail_closed_items` in the contract; this is non-blocking for
these control artifacts but blocking for #21 closure and R2 activation.
The remaining 2 `policy_pins` entries (TIBER-Forecast,
Role-and-opportunity-model) are absence records, not file hashes — their
absence was reconfirmed by a repo-wide directory search, per Entry 5. See
Entry 4 for the full list.

**Fail-closed items re-checked:**
- **FC1** (TIBER-Fantasy pinned FORGE static mirror,
  `server/artifacts/external/forge/forge_player_static_v1.json`, sha256
  `cc2254a8d712976184ce370ecc2f932831d65925773b9e5dde924948d9b5cf14`):
  re-hashed, unchanged. Still does not match the TIBER-FORGE producer's
  current promoted artifact (`2020a52b...`). Status unchanged from the
  merged registry: not current, provenance unverified, non-blocking for this
  contract's requirements.
- **FC2** (TIBER-Ops#13 and TIBER-Data#212 exist only as issue text): still
  true; no committed document has appeared in either repository since the
  registry was authored.
- **FC3 (new, recorded this round):** `tiber_data_repo_boundaries_and_feedback_loops`
  and `tiber_forge_data_to_forge_ingestion_spec` are verified from source
  at their pinned revisions but are not registered in the merged #21
  registry. Non-blocking for R1/these control artifacts; **blocking for
  #21 closure and R2 activation** — see `frontier.gating_condition` (B) in
  `goal-contract.yaml`. Clearing FC3 requires a separately scoped #21
  registry amendment, not performed here.

**R1 state: `complete`.** No mismatch, no inaccessible repository, no new
unresolved policy conflict, no unknown-currency dependency was found (FC3
is a scope-completeness gap in the merged registry, not a currency or
verification failure of R1's own re-checks). Input freeze for R1's scope
is now in effect as of this timestamp; the two FC3 dependencies are frozen
as source-verified, not as registry-registered.

## Entry 3a — R1 full command log

Verbatim commands executed to produce Entry 3's results, run from
`/home/user/TIBER-Ops` (write repo checkout) against sibling checkouts of
the 7 governed-source repositories at `/home/user/<repo-name>`. Included
here because R1's `completion_evidence` in `goal-contract.yaml` references
a "full command log in progress-ledger.md" — this entry is that log, not a
paraphrase of it. A fresh reviewer without those exact sibling checkouts
must substitute their own clone paths but can reuse these commands
verbatim otherwise.

**1. Repository currency (7 governed-source repos):**

```bash
declare -A pinned=(
  [TIBER-Data]=d9a5beaacf12e3fbd74becd02db3d2ac39e48905
  [TIBER-Forecast]=478489b565a97a1179d6010ebf9b1b4326a50c04
  [TIBER-Teamstate]=3ec1d78e10fccf203239c88b905e3cf744d21c48
  [Role-and-opportunity-model]=6435d8d3c2c4e53dc45ab57a05a2716e2b47598d
  [TIBER-FORGE]=af2ca4d5f67f04ed1fc58fef50051c8169545d11
  [TIBER-Fantasy]=d35d440f24beaa275f6eb2f36cdd37a9c4989c3f
  [TIBER-Rookies]=2ef92faf9a9c91a393f53e9140428451529a1c48
)
for d in TIBER-Data TIBER-Forecast TIBER-Teamstate Role-and-opportunity-model TIBER-FORGE TIBER-Fantasy TIBER-Rookies; do
  echo "=== $d ==="
  cd /home/user/$d
  git fetch origin --quiet
  def=$(git remote show origin 2>/dev/null | sed -n 's/.*HEAD branch: //p')
  local_head=$(git rev-parse HEAD)
  remote_head=$(git rev-parse origin/$def 2>/dev/null)
  expected="${pinned[$d]}"
  match_local_remote=$([ "$local_head" = "$remote_head" ] && echo YES || echo NO)
  match_vs_pin=$([ "$remote_head" = "$expected" ] && echo YES || echo NO)
  echo "default=$def local_head=$local_head remote_head=$remote_head pinned=$expected local_eq_remote=$match_local_remote remote_eq_pinned=$match_vs_pin"
  git status --porcelain | head -2
  cd /home/user
done
```

Observed: `local_eq_remote=YES` (checkout matches its own freshly-fetched
origin, not read from a possibly-stale remote-tracking ref) **and**
`remote_eq_pinned=YES` (origin is still exactly the commit pinned in
`repository_revisions`, not merely self-consistent) for all 7 repos, with
empty `git status --porcelain` for each (no local drift). Exact HEADs are
in Entry 3's table. A future rerun of this loop with an unmodified `pinned`
map will surface any real upstream drift as `remote_eq_pinned=NO` even if
`local_eq_remote=YES` — that gap (checked here, was previously absent) is
exactly what the prior version of this loop could not detect.

**2. Governed-dependency file hashes (28 entries) — verify function and
invocations:**

```bash
verify() {
  repo_dir=$1; repo_name=$2; path=$3; expected=$4
  actual=$(sha256sum "/home/user/$repo_dir/$path" 2>/dev/null | cut -d' ' -f1)
  if [ "$actual" = "$expected" ]; then st="MATCH"; else st="MISMATCH_or_MISSING actual=$actual"; fi
  echo "$repo_name|$path|$st"
}
verify TIBER-Data TIBER-Data exports/promoted/identity_crosswalk/tiber_identity_crosswalk_v1.json 5ce5cd3f5dc8fd27c28c5a5fb283431ac648f764c3f8f2b645f6ad924338f263
verify TIBER-Data TIBER-Data schemas/tiber_identity_crosswalk_v1.schema.json da7189ce7d067556b9b7a7510151fb0e0d775fe8feeebc3f18a97951104660c0
verify TIBER-Data TIBER-Data exports/promoted/nfl/player_season_coverage_v0.json d45f612b207085df00b4b080e4f55ce1abbd060dcbf30b0bee777ff833ddd8ac
verify TIBER-Data TIBER-Data exports/promoted/nfl/PLAYER_SEASON_COVERAGE_V0_PROMOTION_MANIFEST.json 5e9a382db0681e7a808a1d5fdf4334653cf2f0b26314c45425b333aa2024d154
verify TIBER-Data TIBER-Data src/contracts/v1/forgeWeeklyPlayerInput.ts e8b354675aa160fb3c14d8f695c4e4146ed6367098494f7f3671b84e6b2919e4
verify TIBER-Data TIBER-Data docs/contracts/evidence-layer-v0.md 48c0949811e69f81bb51c6f84e5af394469838b9bc713991c437599c0b89e148
verify TIBER-Data TIBER-Data docs/repo-boundaries-and-feedback-loops.md c1df7ea4d628b2b1b7466e1ab35a0db12871c03770d86b60d8da33ab5c0bd9a9
verify TIBER-Teamstate TIBER-Teamstate docs/contracts/team-environment-profile-v0.md 255b7f954b6ebab550ec811a4047dcd87238e541750ae628249f4ef157c9870a
verify TIBER-Teamstate TIBER-Teamstate src/contracts/teamEnvironmentProfile.ts 75295dd955ee71527af6e3b3e707da5fbc490e7af6918fd8996e616d5725dd15
verify TIBER-Teamstate TIBER-Teamstate docs/contracts/team-environment-movement-v1.md ee3ac8ba16a10fb13d98d86effdafe9c4ab605bbeb27a8a047d60219a498e0ee
verify TIBER-Teamstate TIBER-Teamstate src/contracts/teamEnvironmentMovementV1.ts b0a1308bb4b31493c09bdf4ae5ab70f6b5cf100991172951c8acae8586ba544a
verify Role-and-opportunity-model Role-and-opportunity-model docs/contracts/role-opportunity-profile-v0.md a156ff5e9f7d335a3a45e76dda8765aaa4883b158c62bc4da02eb9cf4d634bdb
verify Role-and-opportunity-model Role-and-opportunity-model src/types/roleOpportunityProfileV0.ts 2fca35020d3cf4830a54f932dcbb47520792177eaef1f699032dac16bcde9498
verify TIBER-FORGE TIBER-FORGE src/contracts/forge.ts ceeb45ee9833166d1192b25919b9b3ee24612f38af8a39ecea638656a45689a5
verify TIBER-FORGE TIBER-FORGE src/contracts/football.ts 453693f1bd069326b4266ed3346443bdee729a109face215c8d8a3c7f8adc68d
verify TIBER-FORGE TIBER-FORGE exports/promoted/forge_player_static/forge_player_static_v1.json 2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041
verify TIBER-FORGE TIBER-FORGE docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md 39dd805cc37efb98c15b8eb63f035489b56277412f4e8b2f81a6ccf9cf159a59
verify TIBER-Fantasy TIBER-Fantasy docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md 7b9b0362048d2d9dbe42fa801fb3f75236709fc56e8b0186723c0306ae66b3ba
verify TIBER-Fantasy TIBER-Fantasy server/modules/forge/MODULE.md 32cf08fd7bb6b28813ce2f56a8608d62a1700024d1e0b734df926af40c88cc0b
verify TIBER-Fantasy TIBER-Fantasy server/contracts/rankingsV2.ts af7f56ffdb578254438c52c56dfd482d164d1fa42f415c2b7b00518322729c39
verify TIBER-Rookies TIBER-Rookies exports/promoted/rookie-transition-profile/2026_rookie_transition_profile_v0.json c95b941c7855612daccfc2226fc51e0e34dbb2ebe8a2487596675d2522a22f37
verify TIBER-Rookies TIBER-Rookies exports/promoted/rookie-transition-profile/2026_rookie_transition_profile_v0.csv 3005bcd6ad4ffc87a312c6926e20c5e3658747012855aa9d8ccfa33d898545e6
verify TIBER-Rookies TIBER-Rookies exports/promoted/rookie-transition-profile/2026_manifest.json 0acf361c6d2d8cc6f684026481a5aa279e9f7fa718256fad78da0366d5804413
verify TIBER-Rookies TIBER-Rookies docs/rookie-transition-profile-contract.md 187fb0c68b8a9d30d7e4db0f130ceb98009af4cffb878394dded540d3d6b285b
verify TIBER-Forecast TIBER-Forecast src/contracts/projectionArtifacts.ts a11f3030ada3b9fa932915978b8de2b9a1a353275496819c439b926b597fd012
verify TIBER-Forecast TIBER-Forecast docs/ownership-boundaries.md 4790a90461b2025000f726df3ba2aac2f31bbe6b6c3fee454b217c706ed85f6b
verify TIBER-Forecast TIBER-Forecast docs/experiments/rookie-transition-profile-forecast-consumption-design-2026-07-11.md 3792da358b92011df04b21819e59b117a1c242a652baa74c813727df42355090
verify TIBER-Forecast TIBER-Forecast data/fixtures/tiberRookies/ROOKIE_TRANSITION_PROFILE_V0_MIRROR_PROVENANCE.json 2639d5acb11e8d77400700e814ad9c50dba9bf0a46f3f80413e4f0d51860aaa6
```

Observed: all 28 invocations printed `MATCH`, zero mismatches. (The final
two — `tiber_data_repo_boundaries_and_feedback_loops` and
`tiber_forge_data_to_forge_ingestion_spec` — were added after a
fresh-context Codex finding that R2 required reconciling these two
documents' FORGE-role definitions without either being pinned; both repos
were re-fetched and confirmed still at their pinned `repository_revisions`
commit before hashing, at `2026-07-13T23:19:17Z`.)

**3. Policy pins (6 file-backed) and absence confirmation (2 repos):**

```bash
verify TIBER-Teamstate TIBER-Teamstate CLAUDE.md 9449e317936b0289b1e627e598c45b6a68b6d68e1ce852306b3af3bef630e55b
verify TIBER-Data TIBER-Data AGENTS.md b3cddcc42a6f0f9f7e46a4bdec56194bf25cf29d12a29c0f98d2d47828fc7f85
verify TIBER-Fantasy TIBER-Fantasy SECURITY_POLICY.md f5540a0849b469a3bacceeae163ee9a404b478b57c0a43f15d23f31251f1374a
verify TIBER-Rookies TIBER-Rookies AGENTS.md 77511e117eac207061d161e171f7d7b8cea421192957d60b992776cf85d6c84b
verify TIBER-FORGE TIBER-FORGE AGENTS.md 579e8a820e890285d63fc53235d3106478b0e05cf1bcb0001ec1db97d5afa8f2
sha256sum runbooks/merge-checklist.md   # TIBER-Ops, run from this repo's own checkout

echo "--- absence checks (repo-wide, not root-only) ---"
find /home/user/TIBER-Forecast -type f \( -iname "CLAUDE.md" -o -iname "AGENTS.md" -o -iname "MERGE_POLICY*" -o -iname "SECURITY_POLICY*" \) -not -path "*/node_modules/*" -not -path "*/.git/*"
find /home/user/Role-and-opportunity-model -type f \( -iname "CLAUDE.md" -o -iname "AGENTS.md" -o -iname "MERGE_POLICY*" -o -iname "SECURITY_POLICY*" \) -not -path "*/node_modules/*" -not -path "*/.git/*"
```

Observed: all 6 file-backed pins `MATCH` (using the 4-argument `verify()`
signature from block 2 above — `repo_dir repo_name path expected` — an
earlier draft of this log omitted `repo_name` for these five calls, which
would have hashed the wrong path and reported a false mismatch; corrected
and re-executed for this entry); both `find` invocations returned empty
output — repo-wide, not just at the repository root (an earlier draft of
this log used `-maxdepth 1`, which would have missed a nested policy file
under e.g. `docs/` or `src/`; re-run unbounded and the result is unchanged:
no policy file exists anywhere in either repository, so the absence
records stand).

**4. FC1 re-check:**

```bash
sha256sum /home/user/TIBER-Fantasy/server/artifacts/external/forge/forge_player_static_v1.json
# compare against producer: /home/user/TIBER-FORGE/exports/promoted/forge_player_static/forge_player_static_v1.json
```

Observed: Fantasy mirror sha256 `cc2254a8d712976184ce370ecc2f932831d65925773b9e5dde924948d9b5cf14`,
unchanged from the value recorded during #21; still does not equal the
TIBER-FORGE producer's current sha256 `2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041`.

## Entry 4 — Dependency and policy pins (full list)

All entries below were independently re-verified at `2026-07-13T22:36:33Z`
(re-fetched repository, re-hashed file). Authoritative copy is in
`goal-contract.yaml` under `governed_dependencies`, `policy_pins`, and
`repository_revisions`; this entry is a ledger-side duplicate for
cold-resume readability.

**Governed dependencies (28):**

| id | repo | path | sha256 (first 12) |
|---|---|---|---|
| tiber_identity_crosswalk_v1 | TIBER-Data | exports/promoted/identity_crosswalk/tiber_identity_crosswalk_v1.json | `5ce5cd3f5dc8` |
| identity_crosswalk_schema | TIBER-Data | schemas/tiber_identity_crosswalk_v1.schema.json | `da7189ce7d06` |
| player_season_coverage_v0 | TIBER-Data | exports/promoted/nfl/player_season_coverage_v0.json | `d45f612b2070` |
| player_season_coverage_v0_promotion_manifest | TIBER-Data | exports/promoted/nfl/PLAYER_SEASON_COVERAGE_V0_PROMOTION_MANIFEST.json | `5e9a382db068` |
| forge_weekly_player_input_v1 | TIBER-Data | src/contracts/v1/forgeWeeklyPlayerInput.ts | `e8b354675aa1` |
| evidence_layer_v0 | TIBER-Data | docs/contracts/evidence-layer-v0.md | `48c0949811e6` |
| tiber_data_repo_boundaries_and_feedback_loops | TIBER-Data | docs/repo-boundaries-and-feedback-loops.md | `c1df7ea4d628` |
| team_environment_profile_v0 | TIBER-Teamstate | docs/contracts/team-environment-profile-v0.md | `255b7f954b6e` |
| team_environment_profile_v0_types | TIBER-Teamstate | src/contracts/teamEnvironmentProfile.ts | `75295dd955ee` |
| team_environment_movement_v1 | TIBER-Teamstate | docs/contracts/team-environment-movement-v1.md | `ee3ac8ba16a1` |
| team_environment_movement_v1_types | TIBER-Teamstate | src/contracts/teamEnvironmentMovementV1.ts | `b0a1308bb4b3` |
| role_opportunity_profile_v0 | Role-and-opportunity-model | docs/contracts/role-opportunity-profile-v0.md | `a156ff5e9f7d` |
| role_opportunity_profile_v0_types | Role-and-opportunity-model | src/types/roleOpportunityProfileV0.ts | `2fca35020d3c` |
| forge_core_contract | TIBER-FORGE | src/contracts/forge.ts | `ceeb45ee9833` |
| forge_football_lane_contract | TIBER-FORGE | src/contracts/football.ts | `453693f1bd06` |
| forge_player_static_v1 | TIBER-FORGE | exports/promoted/forge_player_static/forge_player_static_v1.json | `2020a52b2e94` |
| tiber_forge_data_to_forge_ingestion_spec | TIBER-FORGE | docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md | `39dd805cc37e` |
| fantasy_forge_externalization_transition_spec | TIBER-Fantasy | docs/architecture/FORGE_EXTERNALIZATION_TRANSITION_SPEC.md | `7b9b03620480` |
| fantasy_embedded_forge_module | TIBER-Fantasy | server/modules/forge/MODULE.md | `32cf08fd7bb6` |
| fantasy_rankings_v2_contract | TIBER-Fantasy | server/contracts/rankingsV2.ts | `af7f56ffdb57` |
| rookie_transition_profile_v0_2_0 | TIBER-Rookies | exports/promoted/rookie-transition-profile/2026_rookie_transition_profile_v0.json | `c95b941c7855` |
| rookie_transition_profile_v0_2_0_csv | TIBER-Rookies | exports/promoted/rookie-transition-profile/2026_rookie_transition_profile_v0.csv | `3005bcd6ad4f` |
| rookie_transition_profile_v0_2_0_manifest | TIBER-Rookies | exports/promoted/rookie-transition-profile/2026_manifest.json | `0acf361c6d2d` |
| rookie_transition_profile_contract | TIBER-Rookies | docs/rookie-transition-profile-contract.md | `187fb0c68b8a` |
| forecast_projection_artifacts_contract | TIBER-Forecast | src/contracts/projectionArtifacts.ts | `a11f3030ada3` |
| forecast_ownership_boundaries | TIBER-Forecast | docs/ownership-boundaries.md | `4790a9046192` |
| forecast_rookie_transition_profile_consumption | TIBER-Forecast | docs/experiments/rookie-transition-profile-forecast-consumption-design-2026-07-11.md | `3792da358b92` |
| forecast_rookie_transition_profile_mirror_provenance | TIBER-Forecast | data/fixtures/tiberRookies/ROOKIE_TRANSITION_PROFILE_V0_MIRROR_PROVENANCE.json | `2639d5acb11e` |

**Policy pins (8, including 2 recorded absences):**

| repo | path | sha256 (first 12) / status |
|---|---|---|
| TIBER-Teamstate | CLAUDE.md | `9449e3179362` |
| TIBER-Data | AGENTS.md | `b3cddcc42a6f` |
| TIBER-Fantasy | SECURITY_POLICY.md | `f5540a0849b4` |
| TIBER-Rookies | AGENTS.md | `77511e117eac` |
| TIBER-FORGE | AGENTS.md | `579e8a820e89` |
| TIBER-Forecast | *(none)* | **absence confirmed** — no CLAUDE.md/AGENTS.md/MERGE_POLICY/SECURITY_POLICY |
| Role-and-opportunity-model | *(none)* | **absence confirmed** — no formal agent/merge policy file |
| TIBER-Ops | runbooks/merge-checklist.md | `069630473cbf` |

Full sha256 values (not truncated) are recorded in `goal-contract.yaml`.

## Entry 5 — Absence records and fail-closed conditions

- **Policy absences (not blocking):** TIBER-Forecast and Role-and-opportunity-model
  have no formal agent/merge-policy file. Recorded explicitly rather than
  assumed; governance in those repos is enforced informally (PR template /
  README / contract guardrails per the merged registry's findings).
- **FC1 (not blocking for R1–R5):** TIBER-Fantasy's pinned FORGE static
  mirror does not match the TIBER-FORGE producer's current promoted
  artifact, byte-level or semantic, across all 8 historical producer
  revisions (verified during #21, re-confirmed unchanged during this R1
  re-run). R4 must disclose this honestly rather than assume the mirror is
  current.
- **FC2 (not blocking, contextual only):** TIBER-Ops#13 (closed) and
  TIBER-Data#212 (open) exist only as GitHub issue text; no committed
  repository document exists for either. Treated as data per the repo-text
  invariant, not as governed dependencies.
- **No new fail-closed condition was discovered during this R1 re-run.**

## Entry 6 — Requirement states at authoring handoff

| Requirement | State |
|---|---|
| R1 — Freshness preflight and verified input freeze | `complete` |
| R2 — Canonical FORGE role and non-responsibilities | `pending_execution_gated` |
| R3 — Repository ownership and artifact boundaries | `pending` |
| R4 — Cross-repository semantics and migration state | `pending` |
| R5 — Deliverable assembly, independent audit, terminal decision | `pending` |

## Entry 7 — Frontier state (exactly one)

**Current frontier requirement: R2.**

R2 is execution-gated behind two things, not one: (A) the `#22` approved
decision's six-condition pilot execution gate, and (B) registry
synchronization — 2 of this contract's 28 `governed_dependencies`
(`tiber_data_repo_boundaries_and_feedback_loops`,
`tiber_forge_data_to_forge_ingestion_spec`) are verified from source but
not yet present in the merged `#21` registry (`fail_closed_items` FC3).
Gate (B) is **not currently satisfied** and is not cleared by merging this
contract; it requires a separately scoped `#21` registry amendment. Only
once both (A) and (B) are satisfied may the human decision owner (Joseph,
`@Prometheus-Frameworks`) record an explicit activation decision on `#22`.
See `frontier.gating_condition` in the goal contract for the full text. No
requirement other than R2 may become the active frontier without an
approved contract amendment.

## Entry 8 — Parked discoveries inherited from #22 (not activated)

The following are copied from `#22`'s Parked work section for continuity.
They are **not** part of this contract's requirements and are **not**
activated by this ledger entry:

- **Stale Fantasy FORGE mirror** (same item as FC1 above) — potential
  Fantasy-lane refresh; out of this campaign's write scope (TIBER-Ops only).
- **Forecast's superseded player-season pin** — TIBER-Forecast's committed
  source-gate evidence (Forecast#117) pins the pre-TIBER-Data#202 hash;
  potential Forecast-lane refresh; out of this campaign's write scope.
- **`#24` — parked proposed weekly NFL meta-trend research pilot** — inactive,
  unrelated to this campaign, requires its own future human activation
  decision.

## Entry 9 — Unresolved questions

- Which of the four candidate FORGE role concepts (deterministic grading
  layer; evidence arbitration layer; signal synthesis layer; audit and
  validation layer) becomes canonical is explicitly **not** decided by this
  contract — that is R2's substantive work, gated pending human activation.
- Whether FC1's stale Fantasy mirror should be refreshed is out of this
  campaign's scope (write-restricted to TIBER-Ops); R4 will need to state
  this limitation explicitly when documenting migration status.

## Entry 10 — Decision required from the human owner

1. Review this contract and ledger (this PR). Note the terminal authoring
   decision means these control artifacts are ready for review/merge, not
   that R2/#15 execution is ready to begin.
2. Merge this PR to `Prometheus-Frameworks/TIBER-Ops` `main` (human action,
   not autonomous) if satisfied. This installs the control artifacts but
   does **not** activate R2 and does **not** close `#21`.
3. The next program frontier after that merge is a separately scoped `#21`
   registry amendment: add and verify
   `tiber_data_repo_boundaries_and_feedback_loops` and
   `tiber_forge_data_to_forge_ingestion_spec` in
   `registry/tiber-current-state.v0.json` on `main` (`fail_closed_items`
   FC3, `frontier.gating_condition` gate B). This is narrowly scoped to
   these 2 confirmed `#15` dependencies, not a repo-wide registry
   expansion.
4. Once gate B is cleared, confirm on `#21` that both the original
   contract-integration criterion (the merged `#21` preflight/registry
   referenced as invariants — already satisfied by this contract) and the
   new registry-completeness criterion are met.
5. Confirm the `#22` approved decision's six-condition pilot execution
   gate (gate A) is satisfied per `frontier.gating_condition` — conditions
   1, 2, 5, and 6 are satisfied as of this authoring; condition 3 requires
   gate B above; condition 4 is satisfied by step 2's merge.
6. Only once both gate A and gate B are satisfied, record an explicit
   activation decision on `#22` authorizing R2 to begin, per the
   frontier's `no_substantive_15_work_before_gate` condition.

No other decision is requested by this authoring task. This ledger entry
does **not** ask for or imply approval to begin R2, `/goal` execution, or
any #15 architectural decision.

## Entry 11 — Reference links

- Campaign: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/15
- Pilot protocol: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/20
- Freshness prerequisite: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/21
- Program source of truth: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22
- This authoring issue: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/25
- Merged freshness deliverables PR: https://github.com/Prometheus-Frameworks/TIBER-Ops/pull/23
- Freshness preflight document: `docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md`
  (`Prometheus-Frameworks/TIBER-Ops` main, as of `e0497a0`)
- Current-state registry: `registry/tiber-current-state.v0.json`
  (`Prometheus-Frameworks/TIBER-Ops` main, as of `e0497a0`)

---

## Entry 12 — Authoring-phase validation evidence

- **YAML validation command:**
  `python3 -c "import yaml; yaml.safe_load(open('pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml'))"`
- **Parser dependency (not added to the repo):** this command requires
  PyYAML, which is not part of the Python standard library and is not
  declared anywhere in TIBER-Ops (a docs-only repo with no package
  manifest). In this authoring session's environment, PyYAML `6.0.1` is
  present as the system package `python3-yaml`
  (`/usr/lib/python3/dist-packages/yaml/`), so the command above ran without
  installing anything. A reviewer whose environment lacks PyYAML must
  install it first (e.g. `pip install pyyaml` or `apt install python3-yaml`)
  to reproduce this exact command, or substitute any other standard YAML
  parser already available to them (e.g. `ruby -ryaml -e`) and confirm the
  same structural facts below. No parser dependency was added to the
  TIBER-Ops repository itself — this is an ambient tool requirement of the
  reviewer's own environment, consistent with #25's "validate with an
  available standard parser" instruction.
- **Result:** parses successfully. Top-level keys, 5 requirements (`R1`–`R5`),
  28 `governed_dependencies` (26 registered in the merged #21 registry + 2
  verified-but-unregistered per FC3), 8 `policy_pins`, 8
  `repository_revisions`, 3 `fail_closed_items` (including FC3),
  `frontier.current_requirement: R2`, and
  `terminal_authoring_decision.emitted_decision: pilot_contract_ready_for_human_gate_review`
  all confirmed present and correctly typed by direct inspection of the
  parsed object (not just a parse-success check).
- **Scope compliance:** only the two files in this directory were created or
  modified by this authoring issue. No other path under
  `Prometheus-Frameworks/TIBER-Ops` was touched. No other repository was
  written to.
- **Terminal authoring decision:** `pilot_contract_ready_for_human_gate_review`
  — the contract and ledger are ready for independent fresh-context review
  and the operator's merge/gate decision. This does not authorize merge or
  any substantive `#15` execution.

## Entry 13 — Post-merge registry synchronization recorded (TIBER-Ops#22 amendment)

Appended per a Joseph-signed `[DECISION — APPROVED]` on TIBER-Ops#22
(2026-07-14T11:40:51Z), approving a Codex-authored `[AMENDMENT PROPOSAL]`
to align this contract and ledger with the already-merged registry state.
Entries 1-12 above are untouched (byte-for-byte); this entry only appends.

**Approval chain:**
- Joseph's PR #28 merge approval: https://github.com/Prometheus-Frameworks/TIBER-Ops/pull/28#issuecomment-4964564637
- Amendment proposal (Codex-authored via Joseph's account, not itself a
  decision): https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4967610950
- Joseph's signed approval of that proposal: https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4968743572

**PR #28 merge facts:**
- Approved head: `73530e3b73b865dff9e2149738f9420c73694928`
- Merge commit: `eb4651bc025a8571d6a0b058e084327fd7d4ee1d`
- Registry amendment record: `A1` in `registry/tiber-current-state.v0.json`

**Fresh 28-of-28 reconciliation, re-run against current TIBER-Ops `main`
at `eb4651bc025a8571d6a0b058e084327fd7d4ee1d`:**

```bash
python3 - <<'PY'
import yaml, json
contract = yaml.safe_load(open('pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml'))
registry = json.load(open('registry/tiber-current-state.v0.json'))
flat = {}
for e in registry['entries']:
    flat[(e['repo'], e['path'])] = e['content_sha256']
    for c in e.get('companions', []):
        flat[(e['repo'], c['path'])] = c['content_sha256']
deps = contract['governed_dependencies']
matched = [d['id'] for d in deps if flat.get((d['repo'], d['path'])) == d['content_sha256']]
print(f"contract governed_dependencies: {len(deps)}")
print(f"registry flattened (entries+companions): {len(flat)}")
print(f"matched: {len(matched)}/28")
ids = [e['id'] for e in registry['entries']]
print(f"registry top-level entry IDs unique: {len(ids) == len(set(ids))} ({len(ids)} entries)")
PY
```

Observed output:

```
contract governed_dependencies: 28
registry flattened (entries+companions): 28
matched: 28/28
registry top-level entry IDs unique: True (18 entries)
```

**#21 and #27 terminal states:** both closed.
- `#21` (`state_reason: completed`, `closed_by: Prometheus-Frameworks`,
  `closed_at: 2026-07-14T01:38:58Z`) — independently re-audited against
  all 8 original acceptance criteria in the [PR #28 post-merge
  checkpoint](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4964576928);
  all 8 confirmed satisfied.
- `#27` — closed by this agent after confirming its acceptance criteria
  were satisfied by the merged PR #28.

**Gate status, current:**
- **Gate A** (the `#22` approved decision's six-condition pilot execution
  gate): all 6 conditions satisfied. Condition 3 (governed dependencies
  pinned and registered) is satisfied now that gate B (below) resolved;
  condition 4 (contract + ledger exist) satisfied since PR #26 merged.
- **Gate B** (registry synchronization, `fail_closed_items` FC3):
  satisfied as of the PR #28 merge above. Resolution text recorded
  directly on FC3 and on both affected `governed_dependencies` entries in
  `goal-contract.yaml` (this same TIBER-Ops#22 amendment).

**R2 status: still `pending_execution_gated`, not activated.** This entry
records that both gates are satisfied; it is explicitly **not** a human
activation decision. Per `frontier.no_substantive_15_work_before_gate` and
the `#22` approved decision, R2 may not begin substantive execution until
the human decision owner records a separate, explicit, signed
`[DECISION — APPROVED]` on `#22` confirming both gates and explicitly
authorizing R2 to begin. No such decision has been recorded as of this
entry.

**Validation for this amendment:**
- YAML re-parses successfully after all `goal-contract.yaml` edits (see
  PR description for this issue's amendment for the exact command and
  output).
- `git diff --name-only` against the pre-amendment `main` confirms only
  `pilots/bounded-goal/forge-role-and-ownership-boundary-v0/goal-contract.yaml`
  and this ledger file changed.
- Entries 1-12 above confirmed unchanged (this entry is a pure append).

**Terminal decision for this amendment:**

```
contract_state_sync_ready_for_human_merge_review
```

Means only that these two control-artifact edits are ready for Joseph's
independent review and merge decision. Does not authorize merge, R2
activation, or any further program-state change beyond what is recorded
above.

## Entry 14 — Review correction: stale binding-location commit pin (PR #29)

An automated Codex review of PR #29 (head `bb433c4c0f`) found that Entry
13's gate-B-satisfied claim was undermined by
`step0_mandatory_invariants.binding_location_note`, which still pinned
the freshness preflight documents to PR #23's merge commit `e0497a0` --
the 26-entry registry, containing neither FC3 dependency. An executor
following Step 0 literally at that pinned commit would re-fetch the
stale registry, find both FC3 dependencies missing, and re-block R2
against Entry 13's own "satisfied" claim.

**Fix:** `binding_location_note` no longer pins to a frozen historical
commit. It now states the binding principle directly (documents are
binding only as *currently* present on TIBER-Ops `main`, re-verified at
the point of use, never assumed from any commit named anywhere in this
contract, past or present) and narrates the commit history
(`e0497a0` -> `6b773ab` -> `eb4651b` -> this amendment) as context, not
as the binding pointer.

Re-validated after the fix: YAML parses; the 28-of-28 reconciliation
still passes against current `main`; only `goal-contract.yaml` changed
for this correction (this ledger entry is the sole change to
`progress-ledger.md`, itself a pure append after Entry 13).

## Entry 15 — R2 activation recorded; mandatory Step 0 freshness re-verification executed (PASS)

Appended 2026-07-14 by Claude Code (delegated execution agent,
execution-only authority) as the required activation record and Step 0
evidence, before any substantive R2 action. Entries 1–14 above are
untouched (pure append). This entry records evidence and a human
decision's permanent link; it is not itself a human decision.

**Human activation decision (permanent link):** Joseph
(`@Prometheus-Frameworks`), signed
[`[DECISION — APPROVED] 2026-07-14 — Activate R2`](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4972885214)
(2026-07-14T19:00:13Z). R2 is thereby the sole active frontier;
R3–R5 remain inactive. Activation checkpoint:
[`[CHECKPOINT] 2026-07-14 — R2 activated; mandatory Step 0 pending`](https://github.com/Prometheus-Frameworks/TIBER-Ops/issues/22#issuecomment-4972897991).

**Step 0 execution window:** 2026-07-14T19:20:48Z – 2026-07-14T19:23:27Z,
run per `step0_mandatory_invariants` and section 3 of the merged
`docs/architecture/cross-repo-freshness-and-current-state-registry-v0.md`,
from sibling checkouts at `/home/user/<repo-name>`, reusing the verbatim
command shapes from Entry 3a (fetch-first currency loop with explicit
pin comparison; 4-arg `verify()` hash function; repo-wide absence
`find`; Entry 13's 28-of-28 reconciliation script).

**1. Repository currency (all 8 repos, freshly fetched from origin):**

| Repo | origin default HEAD (fresh) | local_eq_remote | vs contract `repository_revisions` pin |
|---|---|---|---|
| TIBER-Ops | `530b4fb4f1270c1247f67180483e115fab39cb1a` | YES | matches PR #29 merge commit (Entry 13/14 state) |
| TIBER-Data | `a7c059412806470a9e0b89889cd85f01cf7aace9` | YES | **ADVANCED** from `d9a5bea...` (see below) |
| TIBER-Forecast | `49208472539bd11789b88ca8b3eb20c56a7d0db5` | YES | **ADVANCED** from `478489b...` (see below) |
| TIBER-Teamstate | `3ec1d78e10fccf203239c88b905e3cf744d21c48` | YES | matches pin |
| Role-and-opportunity-model | `6435d8d3c2c4e53dc45ab57a05a2716e2b47598d` | YES | matches pin |
| TIBER-FORGE | `af2ca4d5f67f04ed1fc58fef50051c8169545d11` | YES | matches pin |
| TIBER-Fantasy | `d35d440f24beaa275f6eb2f36cdd37a9c4989c3f` | YES | matches pin |
| TIBER-Rookies | `2ef92faf9a9c91a393f53e9140428451529a1c48` | YES | matches pin |

`git status --porcelain` empty for all 8 (no local drift). The two
advances were examined commit-by-commit (`git log --stat` over the
pin..HEAD range) before being accepted as non-blocking:

- **TIBER-Data** `d9a5bea..a7c0594` — one commit, `a7c0594` "Implement
  source-backed formation_summary_v0 2024 team-season candidate
  (#215)". Strictly additive (12 new files: candidate export +
  validation, manifest, schema, scripts, tests, audit docs). No
  governed-dependency path touched. The new `formation_summary_v0`
  artifact family is NOT a campaign dependency and does not enter scope
  (per `scope.scope_addition_rule`).
- **TIBER-Forecast** `478489b..4920847` — one commit, `4920847` "Design
  record-bound availability evidence schema v2 for
  rookie_transition_profile_v0.2.0 (#164)". Strictly additive (2 new
  design-only documents under `docs/experiments/`). No
  governed-dependency path touched. The new design doc explicitly
  declares itself design-only and does not supersede the pinned
  `forecast_rookie_transition_profile_consumption` document (its single
  "superseded" mention is an internal open item about TIBER-Rookies
  band-table documentation, not a supersession marker on any governed
  dependency).

Per the merged preflight protocol, repository-HEAD advance with all
governed content hashes verifying is currency re-established at the new
HEADs, not a failure. The HEADs in the table above are the Step 0
verified revisions for R2's input freeze.

**2. Governed dependencies (28/28):** every `governed_dependencies`
entry re-hashed via `sha256sum` against the freshly-fetched working
trees; all 28 `MATCH` their pinned `content_sha256`, zero mismatches,
zero missing files (verbatim invocation list identical to Entry 3a
block 2).

**3. Policy pins:** all 6 file-backed pins re-hashed, all `MATCH`
(Teamstate CLAUDE.md, Data AGENTS.md, Fantasy SECURITY_POLICY.md,
Rookies AGENTS.md, FORGE AGENTS.md, TIBER-Ops
runbooks/merge-checklist.md). Both absence records reconfirmed by
repo-wide `find` (TIBER-Forecast, Role-and-opportunity-model): zero
policy files anywhere in either repo.

**4. Registry reconciliation (Entry 13 script, re-run against current
`main` at `530b4fb`):** contract governed_dependencies: 28; registry
flattened (entries+companions): 28; **matched: 28/28**; registry
top-level entry IDs unique: True (18 entries).

**5. Supersession sweep:** no `superseded_by` marker present in or on
any of the 28 governed dependency files; no successor promotion event
found at any canonical location.

**6. Fail-closed items re-checked:**
- **FC1** — unchanged. Fantasy mirror still
  `cc2254a8d712976184ce370ecc2f932831d65925773b9e5dde924948d9b5cf14`;
  producer still
  `2020a52b2e941fbcd7a78130399380351da914959663ff9f1abf15affece1041`.
  Still not current / provenance unverified; still non-blocking (R4
  must disclose, not consume).
- **FC2** — still true. No committed repository document has appeared
  for TIBER-Ops#13 or TIBER-Data#212 (the sole new TIBER-Data commit is
  the #215 formation-summary candidate, unrelated to the #212 attribute
  methodology). Both remain contextual issue text, re-read at execution
  time, never governed fact.
- **FC3** — remains `resolved_registered` (reconfirmed by check 4).

**7. Contract validation:** `goal-contract.yaml` parses (PyYAML), 28
governed_dependencies, frontier `R2` /
`execution_gated_pending_human_confirmation` — that stored status field
is the pre-activation text; Joseph's signed decision linked above is
the activation record that supersedes it operationally, per the
contract's own rule that activation is recorded on #22 rather than by
editing the contract (no contract edit is authorized under R2).

**Step 0 result: PASS.** No drift in any governed dependency, no
inaccessible repository, no policy conflict, no unresolved
contradiction, no currency failure. Input freeze for R2 is in effect
as of this entry against the repository revisions in the table above
and the 28 pinned content hashes. Discovered upstream advances
(TIBER-Data#215 formation-summary candidate; TIBER-Forecast#164
schema-v2 design) are recorded here as observed, additive,
out-of-scope repo evolution — not new dependencies, not parked work
items, and not blockers.

**Frontier after this entry:** R2 — active, Step 0 complete;
substantive R2 work is now authorized within the merged contract's
`authorized_actions_when_unblocked` for R2 only. R3–R5 remain pending
and inactive. This entry does not claim any R2 completion.

## Entry 16 — R2 substantive evidence: canonical FORGE role selection, reconciliation, and non-responsibilities

Appended 2026-07-14 by Claude Code (delegated execution agent,
execution-only authority), immediately after Entry 15's passing Step 0,
under Joseph's signed R2 activation decision (linked in Entry 15).
Entries 1–15 untouched (pure append). This entry produces R2's
completion evidence; it does **not** self-certify R2 as complete —
per the `independent_completion_verification` invariant, completion
requires a fresh-context verification that is not performed by this
executing agent. This entry drafts no part of the R5 architecture
document and modifies no source repository.

All inputs below were consumed at the revisions and content hashes
frozen by Entry 15 (Step 0 input freeze). TIBER-Ops#15 issue text was
re-read at execution time as contextual data per FC2, not as governed
fact; every load-bearing claim cites a pinned governed dependency.

### 16.1 The three inconsistent governed role definitions (verbatim anchors)

1. **`tiber_data_repo_boundaries_and_feedback_loops`**
   (TIBER-Data `docs/repo-boundaries-and-feedback-loops.md`, sha256
   `c1df7ea4d628...`): section "3) Adjudication / grading layers"
   names FORGE as its example and states (line 61): "FORGE should
   resolve disagreement between upstream signals and operate as an
   explicit **arbitration layer**. It must not blindly echo one repo's
   output or collapse multi-signal adjudication into model-copy
   behavior." Layer requirements: multi-signal reasoning and conflict
   resolution; traceability of which inputs influenced final grades;
   reject circular evidence paths.
2. **`forecast_ownership_boundaries`**
   (TIBER-Forecast `docs/ownership-boundaries.md`, sha256
   `4790a9046192...`): section 5 "What this repo does not own":
   "**Deterministic grading/tiering policy (owned by TIBER-FORGE)**";
   section 7 flags "deterministic grading/tiering behavior that may
   belong in TIBER-FORGE" as a boundary-risk area. Forecast owns
   scoring/projection logic, expected points, ranges, confidence,
   replacement/VORP outputs (sections 2/4).
3. **`tiber_forge_data_to_forge_ingestion_spec`**
   (TIBER-FORGE `docs/architecture/TIBER_DATA_TO_FORGE_INGESTION_SPEC.md`,
   sha256 `39dd805cc37e...`): "TIBER-FORGE must evolve from bootstrap
   scaffold into the **fantasy signal grading layer** for football
   rankings" (§A); "TIBER-FORGE **grades fantasy signal** from governed
   inputs and interpreted context" (§B); FORGE owns "scoring formulas
   and weighting policies over supplied inputs; penalties/boosts and
   tier derivation; deterministic fallback behavior that exposes
   missing upstream features without fabricating them; confidence
   scoring logic; explanation primitives and reason generation;
   evaluation/rankings outputs and deterministic execution behavior"
   (§C).

### 16.2 Reconciliation

The three definitions are not three roles; they are one role described
from three vantage points, and they nest without contradiction:

- The Forecast doc assigns the **ownership**: deterministic
  grading/tiering policy belongs to FORGE (and to no other repo).
- The FORGE ingestion spec assigns the **domain scope**: the thing
  being graded is fantasy signal for football rankings, computed from
  governed inputs and interpreted context that FORGE does not itself
  produce.
- The TIBER-Data doc constrains the **operating discipline**: FORGE's
  grading must be adjudicative — multi-signal, conflict-resolving,
  traceable, and non-circular — rather than single-source echo. Note
  the Data doc's own section heading places FORGE in an
  "Adjudication / **grading**" layer: even the source of the
  "arbitration layer" phrasing classifies FORGE as a grading layer
  whose grading takes arbitration form.

No pinned source contradicts another on any concrete boundary: all
three place FORGE strictly downstream of TIBER-Data source truth,
Teamstate/Role-and-opportunity interpreted context, and Forecast
modeled outputs, and strictly upstream of TIBER-Fantasy product
presentation; all three deny FORGE ownership of source truth,
interpretation, projection, and presentation. The inconsistency named
by #15 is vocabulary ("arbiter, grader, auditor, fantasy-signal
layer"), not contractual conflict.

### 16.3 Selected canonical primary role

From the four #15 candidate concepts (deterministic grading layer;
evidence arbitration layer; signal synthesis layer; audit and
validation layer), R2 selects:

> **TIBER-FORGE is the deterministic grading layer of TIBER** — the
> sole owner of evaluative judgment over fantasy signal: scores,
> grades, tiers, rankings, confidence, and their machine-readable
> explanations, computed by explicit, reproducible, versioned policy
> over governed source truth, interpreted context, and modeled
> forecasts supplied by upstream repositories. Its grading is
> adjudicative by obligation: where multiple governed upstream signals
> disagree, FORGE must resolve the disagreement explicitly and
> traceably (evidence arbitration is a retained secondary
> responsibility and a required property of the grading policy, not a
> separate role). FORGE creates no truth: every FORGE output is
> derived evaluative judgment, never source-grounded evidence.

**Rationale, cross-referenced against the six sources required by R2's
`completion_evidence`:**

- **`forge_core_contract`** (TIBER-FORGE `src/contracts/forge.ts`,
  sha256 `ceeb45ee9833...`): the machine contract is a grading
  contract — `EvaluationScore` (overall, tier, rankHint, weighted
  `ScoreComponent[]` each carrying a `reason`), `Confidence` with the
  literal type `deterministic: true`, `reasons[]`, and `SourceMetadata`
  that discloses mode/parity (`bootstrap-demo`,
  `parityStatus: 'bootstrap-scaffold' | 'football-lane-v1'`). Both
  determinism and per-component traceability are load-bearing in the
  type system, matching "deterministic grading" and the Data doc's
  traceability requirement simultaneously.
- **`forge_football_lane_contract`** (TIBER-FORGE
  `src/contracts/football.ts`, sha256 `453693f1bd06...`):
  `ForgeWeeklyPlayerInput` is input-only and carries provenance/support
  fields (`sourceSetId`, `sourceUpdatedAt`, `asOf`, `featureCoverage`,
  `qualityFlags`, `dataConfidenceHint`);
  `NormalizedFootballScoringInput` keeps input classes structurally
  distinct (opportunity / efficiency / environment / stability /
  provenance) rather than collapsing them into one generic signal;
  season grading types again hard-code `deterministic: true`
  confidence. The grading layer's own contracts preserve the
  evidence-class distinctions FORGE is required not to blur.
- **`forecast_ownership_boundaries`**: explicitly assigns
  "deterministic grading/tiering policy" to TIBER-FORGE. Selecting
  "evidence arbitration layer" as the primary role instead would leave
  the grading/tiering policy that Forecast disclaims formally unowned;
  selecting deterministic grading honors the only explicit cross-repo
  ownership assignment in the pinned set.
- **`tiber_data_repo_boundaries_and_feedback_loops`**: satisfied by
  making arbitration an obligation of the grading policy: multi-signal
  reasoning and conflict resolution are required wherever multiple
  governed inputs exist; traceability is discharged through the
  component/reason primitives noted above; circular evidence paths are
  rejected by classifying prior FORGE outputs as a distinct input
  class that is never evidence (16.4). The doc's own "Adjudication /
  grading layers" heading confirms grading-with-arbitration-discipline
  is a faithful reading, not a demotion of its "arbitration layer"
  phrase.
- **`tiber_forge_data_to_forge_ingestion_spec`**: "fantasy signal
  grading layer" is the selected role's domain scope verbatim; the
  spec's FORGE-responsibilities list (scoring formulas, weighting,
  penalties/boosts, tier derivation, deterministic fallback that
  exposes rather than fabricates missing features, confidence,
  explanation primitives, deterministic execution) is precisely the
  content of "deterministic grading policy."
- **`forge_player_static_v1` `score_source_policy`** (TIBER-FORGE
  `exports/promoted/forge_player_static/forge_player_static_v1.json`,
  sha256 `2020a52b2e94...`): the promoted artifact's policy block
  distinguishes `player_specific` ("the only score_source that counts
  as player-specific FORGE evidence") from `fallback_default` and
  `generated_baseline` (which "must not be interpreted as
  player-specific FORGE evidence... confidence input... or
  player-specific alpha"). FORGE's own promoted output already
  practices row-level evidence-class honesty — grading that labels the
  evidentiary standing of its own rows rather than laundering
  fallbacks into judgments, consistent with the selected role and
  inconsistent with none.

**Why not the other three candidates:**

- **Evidence arbitration layer (as primary):** arbitration presumes
  multiple governed upstream signals to arbitrate. At the pinned
  revisions, FORGE's only defined ingestion seam is the single
  `ForgeWeeklyPlayerInput` lane (mode `bootstrap-demo`,
  `parityStatus: bootstrap-scaffold` per `forge_core_contract` and the
  ingestion spec §B); Forecast/Teamstate/Role-and-opportunity inputs
  are contract-anticipated but not yet wired. A primary role FORGE
  cannot yet exercise would misdescribe the pinned reality, and it
  would leave deterministic grading/tiering policy — which Forecast
  explicitly disclaims to FORGE — unowned. Arbitration is retained as
  a defining obligation of the grading policy instead.
- **Signal synthesis layer:** no pinned governed source uses this
  concept for FORGE. Worse, "synthesis" names exactly the failure mode
  the TIBER-Data doc guards against: producing a blended signal that
  can be mistaken for evidence. FORGE's output is evaluative judgment,
  which must never be relabeled as a source-grounded signal
  (anti-recursion rule; projection-layer rule "never relabel...
  outputs as source-grounded facts" applies a fortiori to judgment).
- **Audit and validation layer:** validation of source truth,
  schemas, and provenance is TIBER-Data's assigned responsibility
  (ingestion spec §C: source adapters, freshness, normalization,
  contract versioning; Data boundaries doc: "schema semantics and
  validation boundaries"). FORGE's related-but-narrower duty is
  deterministic fallback behavior that *exposes* missing upstream
  features without fabricating them, plus disclosure metadata — an
  obligation of honest grading, not an audit mandate over upstream
  repos. No pinned source assigns FORGE an audit role.

### 16.4 Explicit FORGE non-responsibilities

Grounded per source; FORGE does **not** own:

1. **Source truth, provenance, identity, or normalization** — owned by
   TIBER-Data (ingestion spec §C; Data boundaries doc "Ownership and
   scope"). FORGE must not mutate upstream artifacts (spec §H) and
   must not fabricate usage, routes, PPR outcomes, identity, source
   metadata, team context, or role context (spec §D notes, §H).
2. **Team-environment interpretation** — owned by TIBER-Teamstate
   (spec §A/§C).
3. **Player-role interpretation** — owned by Role-and-opportunity-model
   (spec §A/§C).
4. **Modeled projection: expected points, ranges, replacement/VORP,
   projection confidence** — owned by TIBER-Forecast
   (`forecast_ownership_boundaries` §2/§4). FORGE consumes modeled
   facts as one input class; it does not compute projections.
5. **Product presentation, filtering, comparison UX, and
   product-facing explanation rendering** — owned by TIBER-Fantasy as
   cockpit (spec §A/§C; Data boundaries doc layer 4). Long-term
   ranking math does not belong in Fantasy (spec §A), and presentation
   does not belong in FORGE.
6. **Final player opinions as upstream truth.** FORGE outputs are
   terminal derived judgments for downstream consumption; they re-enter
   upstream modeling only via the Data doc's exception path (converted
   into a new source-backed artifact with independent provenance and
   governed ingestion), never automatically (anti-recursion rule,
   "Bad loop" example — which names "FORGE boosts player" as a link in
   the invalid loop). Prior FORGE outputs are a distinct input class,
   never evidence.
7. **Promotion, merge, or governance authority** — operator-owned
   across all repos (policy_pins; `no_autonomous_irreversible_action`
   invariant). Listing in any registry or export is descriptive, not
   promotive.
8. **Candidate discovery (GOBLIN)** — read-only inspection context
   only when a contract explicitly provides it; candidates must not
   silently alter weights, tiers, confidence, or reasons (spec §E).

### 16.5 Preserved distinction: source truth / transformation lineage / modeled facts / evaluative judgment

Required by R2's third authorized action; preserved as follows:

- **Source truth** — TIBER-Data governed artifacts and contracts (and
  Teamstate/Role-and-opportunity interpreted context as governed,
  provenance-labeled *interpretations* of reality, per spec §B/§C).
- **Transformation lineage** — carried, not owned: provenance fields
  (`sourceSetId`, `sourceUpdatedAt`, `asOf`, `featureCoverage`,
  `qualityFlags`) travel through `ForgeWeeklyPlayerInput` into
  `NormalizedFootballScoringInput.provenance` and surface in output
  `SourceMetadata`; FORGE must propagate lineage through grading, never
  sever or re-originate it.
- **Modeled facts** — Forecast's expected points, ranges, confidence,
  VORP: derived opinions conditioned on assumptions (Data doc layer 2),
  a distinct FORGE input class, never source truth.
- **Evaluative judgment** — FORGE's exclusive output class: score,
  grade, tier, rank, confidence, explanation. Judgment cites its
  evidence (component reasons, score_source labels) and is never
  reclassified as any of the other three. The `score_source_policy`
  demonstrates the discipline inside a promoted FORGE artifact today.

These four classes are pairwise non-interchangeable; #15's finer
six-class input taxonomy (direct observations, normalized evidence,
modeled forecasts, contextual state, external opinions, prior FORGE
outputs) refines the first three classes plus prior-output exclusion
and is R3/R4 material, not collapsed here.

### 16.6 R2 state after this entry

R2's three authorized actions are executed: role selected and
justified (16.3), three definitions reconciled (16.2),
non-responsibilities defined (16.4), distinctions preserved (16.5),
cross-referenced against all six sources named in
`completion_evidence`. **R2 state: evidence_complete_pending_independent_verification.**
Per the `independent_completion_verification` invariant and
`evidence_standards`, R2 may be recorded `complete` only after a
fresh-context verification (not this executing agent) reproduces this
entry's claims from the pinned sources; the frontier does not advance
to R3 by this entry. No amendment, no scope change, no source-repo
modification, no R5 drafting occurred. FC1/FC2 obligations remain
owned by R4 and are unaffected by this entry.
