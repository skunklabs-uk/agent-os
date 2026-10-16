# team-execution: execution evidence

**Status:** Active — accepted bounded team-execution outcome, 2026-10-12. Historical sandbox acceptance remains recorded separately in [Task50](https://github.com/skunklabs-uk/agent-os/issues/50).
**Mission:** [35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Authority:** [approved specification](../SPEC-team-execution.md), [Archived Plan and direct execution approval](archive/team-execution-plan.md#task-tracker-and-approval-gate), Active REQ-0001/RFC-0001.
**Current result:** The Product Owner accepted team-execution at `95591316a83e1d0ce761cfca1c317385d454f2e8` and authorized Agent OS documentation PR/merge after independent review. This includes the accepted Waypoint delivery and the separate positive Pocock Ready delivery, with their declared limits. IWANT main merge and all deployment remain excluded.
**Language:** English is authoritative; Product Owner updates are in Italian.

## Percorso omp-web ritirato — 16 ottobre 2026

La successiva consegna Kubernetes e i relativi prerequisiti di login, binding
e acceptance browser/MCP sono superati dalla [decisione di dismissione](../CAPABILITY-MAP-agent-team.md#dismissione-del-percorso-omp-web--16-ottobre-2026).
Le istruzioni operative dedicate sono rimosse. Le prove dei moduli indipendenti
riportate sotto restano nei loro perimetri originali; la dismissione non
costituisce accettazione del percorso remoto nativo né migrazione di sessioni.

## Direct Product Owner acceptance and current authority

The earlier user decision accepted Tasks43–50 within their documented limits and explicitly excludes full team-execution approval, merge and deployment. The original reviewed snapshot and raw remain immutable historical evidence; this acceptance does not extend that review to later edits.

The [pilot Plan and delivery delegation](archive/team-execution-plan.md#pilot-delivery-delegation), followed by the continuation approval recorded in [waypoint-db#16](https://github.com/skunklabs-uk/waypoint-db/issues/16), authorized and enabled native Osmani execution on NOVBSCWOLaulMaU. PR22 is merged; initial PR/main CI passed, and the Product Owner confirmed the Alpha/Beta smoke on 2026-10-12. [Task20](https://github.com/skunklabs-uk/waypoint-db/issues/20) owns the retained-evidence inventory and the declared post-merge raw-retention exception explicitly accepted by the Product Owner on 2026-10-12. No deploy, production or full-module acceptance is implied. The separately selected Pocock mission is now IWANT#523; its current result and remaining limits are recorded below. Selection/setup are no longer pending.

The historical Task50 ten-scenario table records the accepted sandbox boundary and is not retroactively regraded by the pilot. The pilot adds real-project Osmani delivery, actual successful initial PR/main CI and reported user smoke, with the stated retention limit. It does not prove positive Pocock, a real CI failure/correction, recover the lost original startup log or authorize Agent OS module delivery. The separate IWANT result and current reconciliation are recorded below. Tasks43–50 stay closed.

On 2026-10-12 the independent final reviewer checked the original requirements and primary evidence at `1b4cc087779db4a964001dcb44d5604c321e775b`, then verified the two required status-pointer corrections at `95591316a83e1d0ce761cfca1c317385d454f2e8`, with no remaining findings ([review report](https://github.com/skunklabs-uk/agent-os/issues/35#issuecomment-6121272826)). The Product Owner subsequently answered “Approvo modulo e consegna documentale” to the explicit module-acceptance and Agent OS documentation-only PR/merge request. This is the applicable authority for closeout; it is separate from the pilot delegation. The completed execution plan is archived. The specification remains behavioral authority for the accepted module; the subsequent custom mobile/MCP path is superseded by the decommissioning decision linked above. This acceptance does not certify the complete MVP, replace the Active Codex/Workspace consumer, authorize IWANT merge, or authorize any deployment.

## Positive Pocock delivery — IWANT#523

The user selected the existing [IWANT#523](https://github.com/skunklabs-uk/iwant/issues/523), retained original triage labels, approved attachment withdrawal/restoration without a reason, and delegated technical coordination. Subsequent explicit authority covered the private synthetic Ceph test (100 MiB), PR/initial CI/GHCR previews, then the two automatic events caused by the final PR-description edit and Ready transition. No AWS, main merge or deployment is authorized. IWANT#522 remains open for its external acceptance/output/runtime prerequisites; this work does not close or modify that mission.

[PR640](https://github.com/skunklabs-uk/iwant/pull/640) is Ready at `f8b342b82716b6e319bfef67814eee9d9ff0b9c6`, application base `b2940aa9991840c52e886788b13516808c3694e3`. The graph reuses #638→#639. Real isolated native writers and distinct native mergers produced local integrations `de5e32310bcb973831a933bb55f8bc49144e6669` and `20bac19bede295244171619fa06531d11f370fde`; this is not an IWANT main merge. The last application candidate `15fa1518349c283924472d90ba3810159ca73c5e` has the same code as the reviewed head; the later delta contains four documentation files.

### Sources, invocation and route

OMP18.8.7 and the original Pocock pin `24fe0ef7737efae15c87225755e9f6f5965e4888` were retained. Native `dev.autoqa: false`, `PI_AUTO_QA=0`, isolated writers/apply false, fixed existing provider/model and zero automatic retries remained in effect. The final writer configuration used a 20-minute runtime limit and 40 soft requests; two concurrent workers were enabled only for the independent final review. These are technical limits, not a monetary ceiling or a transfer of the Waypoint allowance.

Actual native route: setup with sequential confirmations and original labels → ask-matt → explicitly requested grill-with-docs with domain-modeling/grilling → to-spec and confirmed seam → to-tickets and approved #638→#639 graph → implement-spec with original tdd, isolated branches and separate mergers → independent parallel Standards/Spec code-review → original pr format → Ready → original retro and writing-for-agents. Setup commit: `6bb59ac17d8a792f5fb4f83a88614ed239a41b01`.

User-only setup/ask-matt/grill-with-docs originated in explicit user requests. Subsequent technical commands, seam and graph decisions, and retro were forwarded by the coordinator under the user's later explicit delegation to handle technical decisions. They were not literally typed by the Product Owner and are not evidence that initial profile selection authorizes unattended user-only skills. Native command expansion/read and real execution are preserved. Planning journal `01a12df7-4704-76b4-884d-23499ca21502` runs continuously through the graph; implementation journal `01a12e82-35d8-7158-8fca-006a4c77dea0` is a separate, repeatedly resumed continuous session. No compaction event was observed in either; no single uninterrupted process across both is claimed.

### Functional evidence and independent review

[#638 evidence](https://github.com/skunklabs-uk/iwant/issues/638#issuecomment-6120082220) covers authenticated upload/list/download, permissions, failure consistency, real PostgreSQL/PostgREST and Ceph, a valid PDF accepted at 20 MiB with matching downloaded hash, and rejection at 20 MiB+1. [#639 evidence](https://github.com/skunklabs-uk/iwant/issues/639#issuecomment-6120907267) covers editor/admin repeated withdrawal/restoration without reason, unchanged file/identity, duplicate no-op without extra audit events, readable withdrawn files, app+database/API restart, viewer mutation denial, valid PDF/PNG and unchanged financial data. Four cancel/close-versus-transition concurrency cases passed on `8148c0ab`; subsequent changes are UI-only. Actual application screenshots at 1440/390 px show contextual controls and history. This is coordinator testing, not a user-device or user-smoke claim.

The full application exposed a real defect on `8148c0ab`: shared detail-panel JavaScript moved each attachment action into a global circular toolbar. A separate writer corrected the cause; behavioral JS regression and full-app browser GREEN are on `15fa1518`. Static rendering alone had missed the defect. Failed driver selectors, the original UI RED, corrected driver and GREEN remain distinct.

[Independent review reports](https://github.com/skunklabs-uk/iwant/pull/640#issuecomment-6121070461) identify exact head `f8b342b8`, separate native clean contexts and original sources; Standards and Spec each report zero findings. Both explicitly distinguish source/raw inspection from tests they did not personally execute. Initial CI on that head passed: Quality38226478374, Controlled Runtime38226478365, Schema Migrator38226478362 and Preview38226478367, attempt1. Later metadata-event runs are governed by the separate approval and retain their real results in PR640; their existence is not a manual rerun.

### Durable raw, inventory and retrospective

The owning local evidence root on NOVBSCWOLaulMaU is `/home/iingenito/.local/state/agent-os/pocock-iwant/`. It retains original planning/implementation journals and child results, immutable incremental Git bundles, configs, corrected and original raw, and `browser638/` and `browser639/` scripts/logs/screenshots. Reviewer access is local; no claim is made that all raw bytes are published on GitHub. Credential files remain outside this evidence root and Git. Review/public reports contain no credential values; full source/private journals are not uploaded as a public archive. `pocock-source-manifest-523.json` records all37 pinned skill files, byte matches and the27 configured original names; `native-skill-read-index.json` locates actual URI reads. Historical negative resolver observations are retained, not repeated merely for this closeout.

The historical Task49 full catalog below remains an immutable statement of that sandbox window. For this later IWANT window, outcomes change to EXECUTED for: setup-matt-pocock-skills, ask-matt, grill-with-docs, domain-modeling, grilling, to-spec, to-tickets, implement-spec, tdd, diagnosing-bugs, codebase-design, code-review, pr, retro and writing-for-agents. `pr` was applied by the coordinator to the PR body, not claimed as an additional native URI invocation. All other12 configured skills remain AVAILABLE_NOT_USED; the10 excluded in-progress/misc entries remain CATALOGUED_UNAVAILABLE. Original user-only metadata is unchanged. EXECUTED describes the observed bounded use, not every possible workflow branch or a guarantee of perfect TDD in every recovery increment.

The [native retrospective](https://github.com/skunklabs-uk/iwant/issues/523#issuecomment-6121142418) proposes durable checkpoints before timeouts, alignment between owned Git worktree and captured checkout, earlier real-JS browser checks, compact tool-path/runtime pointers and bounded provider-error continuation. Several writer timeouts, nested-worktree empty captures, a provider overload and recovery interventions are retained as rework, not relabeled clean first-pass execution. No new global rules, frameworks, issues or services were introduced. AWS, object backup/restore, production headroom, user smoke and deployment remain unverified/outside current authority; IWANT issues stay open under their PR-delivery lifecycle.

### Current ten-scenario reconciliation

This table supplements the historical Task50 table; it does not reopen #43–#50 or extend its review to this SHA. PASS means the stated bounded scenario has observable evidence, not that the whole MVP is accepted.

| Scenario | Current assessment | Evidence and remaining boundary |
|---|---|---|
| Coordinator/responsibilities | PASS | Task44 plus separate Osmani/Pocock real missions, one coordinator and serial shared-source integration; no fixed team. |
| Two independent implementations | PASS | Accepted Tasks45/46 already prove separate writers and overlapping work; not repeated on dependent #638→#639. |
| Dependent activity blocked | PASS | Original setup/merge NO-GO and real Ceph/CI authority boundaries while independent preparation continued. |
| Pocock invocation/setup | PASS with attribution limit | Native setup, confirmations, synthesis and graph; later commands delegated to coordinator, not literal PO typing or unattended generic invocation. |
| Logic in authorized pilot | PASS | Waypoint exact RED/GREEN and accepted delivery; IWANT adds separate original-Pocock implementation and app/Ceph proof. |
| Independent defect review | PASS | Accepted controlled-defect Task48; final independent exact-head reviews retained separately, no inherited verdict. |
| Failed checks/missing authority | PASS in observed boundary | Local failures corrected and authority respected; successful actual CI now observed. Genuine CI failure/correction still not exercised and is not manufactured. |
| Authorized merge | PASS for Waypoint only | PR22, reviewed39a206a, merge92224ba, initial PR/main CI and PO smoke; retention exception remains accepted loss, not recovered PASS. Agent OS/IWANT main authority remains separate. |
| Restart corrected contract | PASS in observed boundary | Accepted same-session/fresh-artifact recovery plus resumed Pocock journals/durable bundles; no crash-proof live-child restoration or one process across planning/implementation claimed. |
| Selected-profile closeout | PASS within accepted boundary | Current route, full catalog mapping, real retrospective and Ready delivery exist. Independent final review at9559131 has no remaining findings; the Product Owner accepted this bounded module and authorized Agent OS documentation PR/merge. IWANT remains Ready, not merged or user-smoked; production release is excluded. |

Current decision: retain the team-execution specification and this outcome as Active authority; archive the completed execution plan. Keep #35 open. Complete the authorized documentary delivery, then Specify mobile-control and mcp-access with one shared state/commands/approvals contract and their own approval gates. Accepted sandbox proofs are not repeated. No implementation, provisioning or deployment is granted by this closeout.

## Task43: native prerequisites

This section is the historical preflight snapshot; later sections supersede its then-pending authentication/capture observations.
Observed installation: `omp/18.8.7` at the existing mise executable; Python3.12.3 and its standard-library unittest help run successfully. No dependency installation. Exact-version reference source is the existing b07a1c146d0d12cfc855a2c65d52f892ef319040 archive, not a Git checkout; its `git rev-parse` fails and is not used as runtime commit attestation. Installed version agrees with the studied version; binary-to-commit identity is not independently certified. Current Context7 docs were compared with pinned CLI/task/config docs; lifecycle statements differ and must be verified by actual capture, not assumed from current-main snippets.

Both original methodological checkouts directly return the approved HEADs: Osmani1401c8b8030e023baeebb31781a6653fe8e93026 and Pocock24fe0ef7737efae15c87225755e9f6f5965e4888. Existing source-filter/provider configuration is reused from corrected workflow-profiles fixtures without changing those originals.

Disposable worktrees `/tmp/agent-os-team-execution-proof/{osmani,pocock}` share approved base a264b6a and belong only to Agent OS. Git reports FICLONE unsupported and falls back to a plain checkout; no reflink performance or isolation claim is made. Proposed worker paths are disjoint: `fixture/{summary.py,test_summary.py,summary-return.md}` and `fixture/{pending.py,test_pending.py,pending-return.md}`. Task44 freezes the consumer contract; workers must not update shared state. Coordinator integration is serial.

Actual `omp config get <key> --json` in each workspace observes:

| Setting | Effective value |
|---|---|
| task.isolation.enabled | true |
| task.isolation.apply | false |
| task.isolation.merge | patch |
| isolation.backend | rcopy |
| task.maxConcurrency | 2 |
| task.softRequestBudget | 18 |
| task.maxRuntimeMs | 240000 |
| retry.maxRetries | 0 |
| dev.autoqa | false |

A temporary overlay and the two native project configs are the only authored runtime configuration inputs so far. Global configuration/authentication, other repositories and original raw bundles are unchanged by our edits. The selected catalogs contain25/27 configured names; actual runtime resolution/invocation is checked by Task44, not inferred from configuration alone.

`omp models openai-codex --json --no-extensions` lists the selected existing gpt-6.1-sol model with contextWindow272000. `omp usage accounts --json` metadata confirms one existing selected-provider account; only count/provider are retained, no identities/tokens copied or displayed. This is stored-login availability, not yet successful live authentication.

No new provider, key, login, paid service or spending envelope is introduced. User-authorized execution uses the existing openai-codex/gpt-6.1-sol account, low reasoning, no fallback/retry, at most two workers. Actual CLI caps are parent300s, integration240s, initial fresh recovery180s, corrected recovery150s and code reviewers180s; the initial preflight described150s recovery, so the changed configured cap is disclosed rather than silently claimed identical. Children retain240s hard timeout and18 soft requests, not an18-request hard cap. Missing existing quota/access stops inference; no billing/top-up/credential migration is authorized. Bounds are not a price estimate or proof of monetary headroom.

Confirmed fixture verification interface: `python3 -m unittest discover -s fixture -p 'test_summary.py' -v`, corresponding `test_pending.py`, and combined `python3 -m unittest discover -s fixture -p 'test_*.py' -v`. The consumer smoke renders and inspects the actual Markdown. No application build exists for Agent OS documentation; native CLI/config/help and unittest help were actually exercised.

Native rcopy materialization, child teardown/capture survival and parent-not-applied behavior remain to be observed before accepting writer results. Native isolated workspaces are checkout separation, not an immutable filesystem/network permission sandbox. If native preparation fails, the already established standard disposable worktrees are the existing alternative; sequential work cannot satisfy the parallel-writer criterion.

## Accepted sandbox boundary before the pilot

The GitHub task set remains the single tracker, with final exact-head documentary decision in Task50. Authorized sandbox observations do not replace a user-project pilot, positive Pocock progression, real CI/release or merge permission. Mission35 stays open; deployment, production, runtime migration, other-repository writes and unspecified PR/merge remain excluded.

## Task44: actual coordinator routing

Original startup failed: subprocess inherited non-TTY stdin and timed out after180s before any session directory appeared. CLI reference explicitly reads stdin to EOF; the corrected invocation uses stdin=DEVNULL. That correction, without provider/auth/runtime changes, produced both actual sessions below. The original timeout is a failed startup, not a passing run; no claim is made about unjournaled startup network effects.

Both corrected native processes exit0 with empty stderr, fixed openai-codex/gpt-6.1-sol:low and max-time150. Osmani has6 actual assistant requests; Pocock has8. Each journal shows exactly one MISSION.md write, no task spawn and no xd device call. The single foreign-skill error in each is an intentional negative case, not hidden as a tool success.

- Osmani session: sessions-osmani-routing/2026-10-10T20-30-31-108Z_01a12782-92c4-708d-b11c-e04be8e6bfe3.jsonl. Original using-agent-skills/spec-driven-development/test-driven-development URI reads succeed, paths and1401c8b HEAD match. to-spec is rejected once without fallback. Approved disposable Implement work remains eligible despite missing delivery permission; no extra universal seam gate is invented.
- Pocock session: sessions-pocock-routing/2026-10-10T20-31-41-907Z_01a12783-a753-7184-88fb-3cf45b8ab9ad.jsonl. Operator explicitly invoked ask-matt/to-spec for this inspection only; both original URI reads and24fe0ef HEAD match. spec-driven-development is rejected once. Visible11 versus registered27 is recorded; availability is not execution. No engineering docs are configured. Even with seam-approved supplied as a discriminator input, setup remains absent and synthesis blocked. No setup, foreign fallback, unwritten-spec approval gate or optional glossary/ADR creation is invented.

Both native-written missions preserve the frozen disposable contract: render_summary(profile, phase), render_pending(decisions), disjoint three-file ownership, one combined Markdown consumer seam and standard unittest. No new coordination skill is needed for the observed routing behavior; absent mission-team candidate bytes are not certified or adopted. Successful real responses now prove live authentication for these calls, not future quota/headroom.

Task44 accepts bounded routing and missing-setup discrimination only. Pocock's actual setup, unattended user-only progression, positive implementation and context-window continuity are not proven by the negative probe. The current mission remains Osmani; Pocock data values in consumer tests do not establish Pocock-method implementation. Independent approved Osmani writers may proceed while Pocock engineering progression remains blocked on its genuine prerequisites.

## Tasks45/46: real parallel isolated writers

One native task batch launched SummaryWriter and PendingWriter, both isolated:true, role team-worker with read/write/edit/bash/grep/glob only, fixed existing model, no nested task or foreign method. Native base a264b6a6fe4f40581a1331b63f0f7d66c147dfc4. Actual separate roots were /home/iingenito/.omp/wt/te59f5b680/m and /home/iingenito/.omp/wt/t46856ae46/m, verified before writes. These are native temporary Agent OS checkouts, not changes to global configuration or another product repository.

Each journal proves original Osmani router/TDD reads, source-pin verification, complete test write, actual RED because the implementation module was absent, implementation write, GREEN, direct executable smoke, owned return and one native yield. Summary11 and Pending12 assistant requests; exactly three owned writes each and no overlapping path. Summary2 and Pending3 tests pass. Native patch metadata says apply=false/Not applied; parent fixture absent before integration. Event timestamps interleave test/RED/implementation/GREEN/smoke across both workers, proving overlapping activity, not CPU simultaneity.

Canonical parent: sessions-osmani-workers/2026-10-10T20-37-33-057Z_01a12789-0301-7405-a462-876e4a90d7fc.jsonl; same-stem directory retains both complete .md/.jsonl/.patch results. After CLI exit both actual child roots no longer exist; captures remain readable. Requested backend is rcopy; observed separation/capture/teardown is not filesystem/network security confinement. Original worker tests pinned incidental Markdown structure; integration removes those pins without rewriting historical patches/returns.

## Task47: integration and corrected recovery

History-bearing native coordinator resumed the exact workers session. Both capture patches applied serially after git apply --check. Complete integration tests were written before the CLI: actual RED for absent checklist.py, then minimal argparse consumer, combined GREEN8 tests and actual CLI smoke with all unresolved decisions, both profile data values/changed phase and empty-list case. Source fixture remains disposable, not a production feature.

Merge/deploy-now request is explicitly NO-GO for missing authority while approved integration continues. Pocock missing setup after seam-approved input blocks only its own dependent progression. Same-session return records both workers and the entire corrected consumer contract, not just the last result.

Fresh native Osmani process without --resume reads complete durable returns/captures and current corrected sources; RECOVERY.md reconstructs both results, all conditions and next Task48. Fresh Pocock process correctly reports missing exact raw pointers in its MISSION. Coordinator repairs the pointers; a distinct fresh corrected process actually reads the canonical routing journal/stdout and recovers pin/foreign rejection while retaining Specify, missing setup and user-only invocation. Original missing-pointer report/raw is preserved alongside pocock-recovery-corrected.jsonl, not overwritten as a pass. No live child conversation or continuous Pocock context window is claimed.

Complete code/test/return artifacts and both RECOVERY.md files are primary proof. No real pilot, CI job, PR, merge, post-merge smoke or deployment is proven. Task47's bounded integration/recovery criterion is satisfied; full module acceptance remains separate.

## Task48: independent review and correction

Integrated disposable snapshot5f74600a7d3a0143654f49047b3d4021385fc687 precedes controlled defective headeac9df1ad167424bdc35c935fbdf5da416367fcb. Actual combined check fails three consumer assertions: the final decision disappears. A fresh native read-only reviewer, without implementer conversation or expected finding, reads original sources/base/head/diff/tests/raw and independently identifies P1 pending.py:6, decisions[:-1]. It reports NO-GO.

Minimal correction restores iteration over every supplied decision. Exact corrected code headced3ce3651129ae8e0b4615d5bf1ce76f8ac3b03 passes eight combined tests and actual CLI smoke preserving all three unresolved conditions. A distinct fresh read-only final-code reviewer examines that exact head and material correction: GO for sandbox code, NO-GO for delivery. Stale review of eac9df1, the actual earlier failing check and missing authority each remain NO-GO reasons. Primary review-initial/review-corrected prompts, journals/results and before/after check/smoke outputs are retained.

Actual GitHub inspection returns main protected=false, no rulesets, workflows0 and baseline check-runs0. github-policy.json retains responses. No CI run is fabricated or triggered; absent workflow CI is N/A for this repository, not proof of CI failure/correction elsewhere. These are existing policy observations, not permission to merge. The code snapshots are local detached Agent OS trial commits, not published production features. LSP reference query reports no server; no hidden reference migration is claimed.

## Task49: selected-profile inventories and no-merge closeout

Inventory window is approved native Tasks43–50 execution, not earlier planning. Each actual SKILL.md was compared byte-for-byte with its stated pinned Git blob. Registered names exactly match the complete native negative-resolver catalogs, not just visible prompt entries. inventory-resolution.json preserves manifest, original resolver responses, source/revision and per-entry metadata. Alias osmani-test-driven-development resolves to original test-driven-development.

EXECUTED means bounded original Osmani source selected/read and applied to an observed task, not completion of every possible workflow step. AVAILABLE_NOT_USED means registered without such execution. Pocock ask-matt/to-spec were explicitly inspected via native URI, and setup definitions directly read; none executes the engineering workflow. User-only metadata is independent of availability. CATALOGUED_UNAVAILABLE entries exist at the pin but are excluded from this project's resolved catalog, not globally broken. No source/availability row remains NOT_VERIFIED; broader behavior still has limits.

### Osmani realization inventory

All sources below belong to [addyosmani/agent-skills at1401c8b8030e023baeebb31781a6653fe8e93026](https://github.com/addyosmani/agent-skills/tree/1401c8b8030e023baeebb31781a6653fe8e93026/skills). All25 are registered and model-invocable; seven bounded executions, eighteen available/not used. Pocock is not counted as unused in this mission.

| Skill | Outcome | Source at the stated revision |
|---|---|---|
| api-and-interface-design | AVAILABLE_NOT_USED | skills/api-and-interface-design/SKILL.md |
| browser-testing-with-devtools | AVAILABLE_NOT_USED | skills/browser-testing-with-devtools/SKILL.md |
| ci-cd-and-automation | AVAILABLE_NOT_USED | skills/ci-cd-and-automation/SKILL.md |
| code-review-and-quality | EXECUTED | skills/code-review-and-quality/SKILL.md |
| code-simplification | AVAILABLE_NOT_USED | skills/code-simplification/SKILL.md |
| constraint-driven-development | AVAILABLE_NOT_USED | skills/constraint-driven-development/SKILL.md |
| context-engineering | EXECUTED | skills/context-engineering/SKILL.md |
| debugging-and-error-recovery | AVAILABLE_NOT_USED | skills/debugging-and-error-recovery/SKILL.md |
| deprecation-and-migration | AVAILABLE_NOT_USED | skills/deprecation-and-migration/SKILL.md |
| documentation-and-adrs | AVAILABLE_NOT_USED | skills/documentation-and-adrs/SKILL.md |
| doubt-driven-development | AVAILABLE_NOT_USED | skills/doubt-driven-development/SKILL.md |
| frontend-ui-engineering | AVAILABLE_NOT_USED | skills/frontend-ui-engineering/SKILL.md |
| git-workflow-and-versioning | EXECUTED | skills/git-workflow-and-versioning/SKILL.md |
| idea-refine | AVAILABLE_NOT_USED | skills/idea-refine/SKILL.md |
| incremental-implementation | EXECUTED | skills/incremental-implementation/SKILL.md |
| interview-me | AVAILABLE_NOT_USED | skills/interview-me/SKILL.md |
| observability-and-instrumentation | AVAILABLE_NOT_USED | skills/observability-and-instrumentation/SKILL.md |
| test-driven-development | EXECUTED | skills/test-driven-development/SKILL.md |
| performance-optimization | AVAILABLE_NOT_USED | skills/performance-optimization/SKILL.md |
| planning-and-task-breakdown | AVAILABLE_NOT_USED | skills/planning-and-task-breakdown/SKILL.md |
| security-and-hardening | AVAILABLE_NOT_USED | skills/security-and-hardening/SKILL.md |
| shipping-and-launch | AVAILABLE_NOT_USED | skills/shipping-and-launch/SKILL.md |
| source-driven-development | AVAILABLE_NOT_USED | skills/source-driven-development/SKILL.md |
| spec-driven-development | EXECUTED | skills/spec-driven-development/SKILL.md |
| using-agent-skills | EXECUTED | skills/using-agent-skills/SKILL.md |

### Separate Pocock product-profile inventory

All sources below belong to [mattpocock/skills at24fe0ef7737efae15c87225755e9f6f5965e4888](https://github.com/mattpocock/skills/tree/24fe0ef7737efae15c87225755e9f6f5965e4888/skills). Full pinned manifest37: registered27, excluded beta/misc10. AVAILABLE_NOT_USED rows are available; CATALOGUED_UNAVAILABLE rows are absent from the native catalog. Zero engineering-flow executions; source inspection is not setup/synthesis/retro.

| Skill | Outcome | User-only | Source at the stated revision |
|---|---|---|---|
| ask-matt | AVAILABLE_NOT_USED | yes | skills/engineering/ask-matt/SKILL.md |
| claude-handoff | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/claude-handoff/SKILL.md |
| code-review | AVAILABLE_NOT_USED | no | skills/engineering/code-review/SKILL.md |
| codebase-design | AVAILABLE_NOT_USED | no | skills/engineering/codebase-design/SKILL.md |
| diagnosing-bugs | AVAILABLE_NOT_USED | no | skills/engineering/diagnosing-bugs/SKILL.md |
| domain-modeling | AVAILABLE_NOT_USED | no | skills/engineering/domain-modeling/SKILL.md |
| git-guardrails-claude-code | CATALOGUED_UNAVAILABLE | no | skills/misc/git-guardrails-claude-code/SKILL.md |
| grill-me | AVAILABLE_NOT_USED | yes | skills/productivity/grill-me/SKILL.md |
| grill-with-docs | AVAILABLE_NOT_USED | yes | skills/engineering/grill-with-docs/SKILL.md |
| grilling | AVAILABLE_NOT_USED | no | skills/productivity/grilling/SKILL.md |
| handoff | AVAILABLE_NOT_USED | yes | skills/productivity/handoff/SKILL.md |
| implement | AVAILABLE_NOT_USED | yes | skills/engineering/implement/SKILL.md |
| implement-spec | AVAILABLE_NOT_USED | yes | skills/engineering/implement-spec/SKILL.md |
| improve-codebase-architecture | AVAILABLE_NOT_USED | yes | skills/engineering/improve-codebase-architecture/SKILL.md |
| loop-me | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/loop-me/SKILL.md |
| migrate-to-shoehorn | CATALOGUED_UNAVAILABLE | no | skills/misc/migrate-to-shoehorn/SKILL.md |
| pr | AVAILABLE_NOT_USED | no | skills/engineering/pr/SKILL.md |
| prototype | AVAILABLE_NOT_USED | no | skills/engineering/prototype/SKILL.md |
| research | AVAILABLE_NOT_USED | no | skills/engineering/research/SKILL.md |
| retro | AVAILABLE_NOT_USED | yes | skills/engineering/retro/SKILL.md |
| scaffold-exercises | CATALOGUED_UNAVAILABLE | no | skills/misc/scaffold-exercises/SKILL.md |
| setup-matt-pocock-skills | AVAILABLE_NOT_USED | yes | skills/engineering/setup-matt-pocock-skills/SKILL.md |
| setup-pre-commit | CATALOGUED_UNAVAILABLE | no | skills/misc/setup-pre-commit/SKILL.md |
| setup-ts-deep-modules | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/setup-ts-deep-modules/SKILL.md |
| tdd | AVAILABLE_NOT_USED | no | skills/engineering/tdd/SKILL.md |
| teach | AVAILABLE_NOT_USED | yes | skills/productivity/teach/SKILL.md |
| to-questionnaire | AVAILABLE_NOT_USED | yes | skills/productivity/to-questionnaire/SKILL.md |
| to-spec | AVAILABLE_NOT_USED | yes | skills/engineering/to-spec/SKILL.md |
| to-tickets | AVAILABLE_NOT_USED | yes | skills/engineering/to-tickets/SKILL.md |
| triage | AVAILABLE_NOT_USED | yes | skills/engineering/triage/SKILL.md |
| wait-what | AVAILABLE_NOT_USED | yes | skills/productivity/wait-what/SKILL.md |
| wayfinder | AVAILABLE_NOT_USED | yes | skills/engineering/wayfinder/SKILL.md |
| wizard | AVAILABLE_NOT_USED | no | skills/engineering/wizard/SKILL.md |
| writing-beats | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/writing-beats/SKILL.md |
| writing-for-agents | AVAILABLE_NOT_USED | no | skills/productivity/writing-for-agents/SKILL.md |
| writing-fragments | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/writing-fragments/SKILL.md |
| writing-shape | CATALOGUED_UNAVAILABLE | yes | skills/in-progress/writing-shape/SKILL.md |

### Route and mission-level retrospective

Osmani route: approved Specify/Plan/Tasks → original router/TDD → two actual isolated writers → serial integration/consumer QA → history-bearing and corrected file-only recovery → independent P1 review → minimal fix/eight-test GREEN/consumer smoke → exact-code-head independent re-review → motivated no-merge trial closeout. Each stage's primary pointers are in its section above. Pocock route is separate: explicitly user-invoked definition inspection → missing-setup block despite discriminator seam approval → raw-pointer repair → corrected file-only recovery, still Specify.

Osmani retrospective is the user-authorized mission-level extension, not imported Pocock retro. Observed rework: inherited stdin caused startup timeout; explicit DEVNULL fixed it. Initial Pocock mission lacked exact raw pointers; clean recovery exposed that gap and corrected fresh recovery verified the repair. Initial worker tests over-pinned Markdown presentation; integration removed those assertions and rechecked behavior. Improvements proposed: close stdin before launch, persist exact durable pointers before handoff, and review semantic test scope before capture acceptance. No global rule changes, new issues or service added.

Pocock retro remains a manual prerequisite: original user-only invocation and applicable mission setup/completion are not granted by inspection. No retrospective execution is claimed. The disposable no-merge trial closes its bounded observations only; module mission35, actual Pocock progression and live pilot/delivery remain open. Active Spec/Plan are not archived as completed product acceptance; accepted workflow-profiles history is unchanged.

## Task50: acceptance boundary and durable handoff

[Primary sandbox bundle](evidence/team-execution-sandbox.tar.gz) retains prompts, native configs/role, complete canonical and streaming journals, original/corrected negative cases, captures, current missions/recoveries, fixture code/tests/returns, local Git snapshot bundle, inventory comparison and GitHub policy responses. MANIFEST.sha256 is inside the archive. Original absolute local paths are historical provenance; archive members retain the same relative layout below /tmp/agent-os-team-execution-proof. The embedded code-snapshots.bundle preserves the three exact temporary revisions without merging them into the documentation branch.

Privacy inspection parses/scans all packaged bytes for credential/private-key patterns and structured secret fields; privacy-screen.json records exact scope/limitations. Public source text, operator-local paths, actor/session IDs and provider/model metadata remain. This is a bounded credential screen, not universal privacy/security certification. Auth storage, account identity, tokens, unrelated worktree repositories and existing accepted workflow archives are not packaged. Original startup TimeoutExpired occurred before any canonical session; its known observation is recorded separately, but original stdout/stderr were not preserved. That missing startup raw is explicitly a coverage limit, not a manufactured empty trace.

Final reviewer uses the exact published documentation head and this frozen bundle, checks original requirements/all scenarios, actual current policy/check state and byte/relative-link smoke. Its complete prompt/journal/output and verdict are preserved on the existing Task50 tracker after privacy screening. Keeping that review out of the reviewed repository snapshot avoids changing the head after review; no verdict is silently applied to a different commit.

| Specification scenario | Bounded evidence | Remaining proof |
|---|---|---|
| Choose coordinator/responsibilities | Task44 original profile/pin/phase and proportionate assignments | No fixed-team or hostile permission enforcement claim |
| Two independent implementations | Tasks45/46 actual isolated roots, owned capture, event overlap; Task47 integration | CPU simultaneity/security confinement not claimed |
| Dependent activity blocked | Missing actual merge/setup authority retained while Osmani work proceeds | Semantic NO-GO, not an immutable runtime ACL |
| Pocock invocation/setup | Explicit inspection-only native reads, foreign rejection, missing setup despite discriminator | Positive supported setup/synthesis/continuation and context continuity unresolved |
| Logic in authorized pilot | Original Osmani RED/GREEN, real yields, eight-test integration and consumer smoke in disposable fixture | Real user-project pilot requires selected repository/slice authorization |
| Independent controlled-defect review | Initial exact-head P1, actual three failing tests, minimal fix and corrected-head re-review | No production defect or different-model independence claim |
| Failed checks/missing authority | Actual local failure and stale-head/authority NO-GO; GitHub policies read | No workflow CI here; CI-job behavior in another authorized environment unproven |
| Authorized merge | No merge performed; authority correctly absent | Module-specific PR/merge authorization, checks/merge SHA/post-merge smoke missing |
| Restart complete corrected contract | History-bearing resume plus fresh Osmani and corrected fresh Pocock recovery | Live child restoration and one continuous Pocock window not proven |
| Close selected-profile mission | Full separate catalogs, route, user-extension Osmani retro, bounded no-merge closeout | Pocock user-only retro/full flow and complete module/pilot delivery remain open |

RFC-0001 control decision: KEEP native state/isolated capture, narrow project worker role, source pins, disjoint ownership, serial integration, real TDD/consumer checks and exact-head clean-context review. DELETE redundant coordinator skill/router/database/relay/always-on fixed team and speculative/advisor/retry expansion from the selected solution; no upstream tool is deleted. REPLACE inherited-open-stdin startup with explicit DEVNULL, vague result destinations with actual durable pointers, incidental wording assertions with consumer behavior, and stale review acceptance with corrected-head re-review. No new global process policy is enacted.

Historical Task50 decision: module delivery/full acceptance was NO-GO; Tasks43–50 only accepted the bounded sandbox. The real Osmani pilot now has its own subsequent authority and delivery evidence linked above; its declared raw-retention loss was explicitly accepted for bounded pilot closure on 2026-10-12. This former gate is superseded by the current accepted outcome above; the completed Plan is now archived, while mission35 stays open for the remaining MVP. The positive Pocock result is now recorded above; this historical Task50 decision is not a review of it. Workflow-profiles acceptance is unchanged. No production/deployment or new tracker is authorized by this reconciliation.
