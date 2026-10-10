# Spec: team-execution

**Status:** Draft — Specify phase; user review required before Plan.
**Module:** team-execution.
**Parent:** [approved capability map](CAPABILITY-MAP-agent-team.md).
**Dependency:** [workflow-profiles](SPEC-workflow-profiles.md), accepted in its documented bounded scope.
**Tracking:** [mission35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Method:** Osmani at1401c8b8030e023baeebb31781a6653fe8e93026. Pocock is a separately selected product profile, not this specification's execution method.
**Language:** English is authoritative by user instruction; product-owner summaries are in Italian.

## Objective

Give the user one mission coordinator who can turn approved work into verified, reviewable changes using only the relevant specialists. Reduce repetitive handoffs while preserving the chosen author's workflow, product decisions, exact reviewed revision and separate deployment authorization.

The preferred deliverable is reusable coordination guidance as a skill; a smaller project-level prompt is acceptable when it satisfies the same outcomes. Native runtime configuration and existing skills come first. No additional coordinator artifact is justified merely because a candidate already exists.

## Confirmed inputs and limits

- The approved capability map places this module after workflow-profiles and before mobile-control/mcp-access.
- The workflow-profiles [outcome](tasks/workflow-profiles-evidence.md#accepted-outcome-and-closeout) proves native profile propagation, read-only observation concurrency and bounded gate/recovery behavior. It does not prove isolated implementation workers, full delivery, mobile/MCP, interactive setup or inviolable enforcement.
- User clarifications in [mission35](https://github.com/skunklabs-uk/agent-os/issues/35#issuecomment-6098056024) require proportional specialist selection, clean-context review, functional acceptance, documentary closeout and mission-level retrospective.
- The [preparatory candidate assessment](https://github.com/skunklabs-uk/agent-os/issues/35#issuecomment-6099400149) describes mission-team v0.3, not approved implementation. Its ZIP is not a repository artifact inspected in this phase. Its reported hashes/content are assessment provenance, not a fresh local validation or adoption decision.
- OMP18.8.7 atb07a1c146d0d12cfc855a2c65d52f892ef319040 remains the investigated candidate. Plan must verify the actual runtime/version and compatibility before choosing commands or relying on capabilities.
- The Active REQ-0001 Codex/Developer Workspace contract remains unchanged. This module cannot silently migrate that consumer or authorize other repositories.

## Functional requirements

1. **One accountable coordinator.** Read original mission requirements, Active authority and current tracker decisions directly. Record goal, scope, selected profile/pin, phase, acceptance criteria, artifacts, ownership, pending decisions and the next permitted action in the existing authoritative mission record. Distinguish observed facts, deductions and missing prerequisites. Do not infer current work from filenames or timestamps.
2. **Relevant specialists.** Assign analysis/functional acceptance, architecture, tech lead/development, UX/UI, QA and DevOps only where the task needs them. Security/privacy, data and performance expertise are conditional on actual risk. A role is a responsibility, not a mandatory always-running agent. A small hotfix must not automatically create a new spec, checkpoint or specialist team beyond applicable rules.
3. **One workflow per mission.** Carry the selected upstream, exact real sources and phase rules into each assignment. Use only that author's methodological skills. Coordination guidance is an explicitly justified integration layer, not another methodology or replacement for using-agent-skills/ask-matt. Missing, unavailable or foreign skills produce a disclosed gap, never another author's fallback.
4. **Actual invocation and setup.** Verify what the runtime permits for user-invoked skills, including a user-only coordination candidate. Profile selection is not blanket authorization to invoke every step. For Pocock, missing first-engineering setup must be communicated through /setup-matt-pocock-skills and block all dependent progression, including after seam approval. Persist exact remaining user actions and invocation evidence. Preserve original phase/context rules; do not promise unattended progression the selected source/runtime does not support.
5. **Work graph and ownership.** Reuse the profile's selected tracker/artifact for tasks, dependencies and acceptance; no parallel ledger. State worker inputs, permitted writes, base revision, result destination and integration responsibility. Parallelize only independent work after shared contracts are settled. Prefer separate worktrees/checkouts for independent writers; serialize shared contracts and integration. If safe writer isolation is unavailable, report the limitation and use an honest sequential path rather than claiming parallel implementation.
6. **Real workers and durable returns.** Use actual runtime agents where available, not simulated reviews or invented parallelism. Return changed paths/revisions, actual checks, evidence, unresolved findings and source-faithful next actions. The coordinator validates profile/phase/scope consistency before integrating results; elapsed duration alone does not prove overlapping execution.
7. **Implementation and acceptance.** Apply the selected author's TDD before new executable logic. Preserve RED/GREEN observations and approved seams where required. Analyst/QA checks the original functional need and error paths, not only passing technical tests. Document-only work does not fabricate TDD or application builds. Integration repeats the smallest checks affected by combined changes.
8. **Independent review.** A reviewer does not implement the reviewed work and starts with a separate context, without implementer conversation or inherited verdict. Supply original requirements, Active sources, source pins, exact base/head/diff and evidence; clean context is not missing context. Require an examined SHA, actual checks, severity-ranked findings and explicit limitations. Resolve blocking findings and re-review material corrections on the final head. A model or role name alone does not prove independence.
9. **Checks and delivery authority.** Read actual required checks and branch policy on the exact final revision. Fix genuine failures within scope, repeat relevant verification and obtain the applicable review. No merge on failed/unknown required checks, a stale reviewed head or missing authorization. No workflow CI means N/A with a concrete explanation, not invented green CI. Retry paid/broken CI only under RFC-0001's cost rules. Explicit existing delegation can cover PR and merge without another mechanical confirmation; it cannot silently replace a gate required by the selected source or product authority.
10. **Separate deployment.** After an authorized merge, report PR, exact merge SHA and a proportionate smoke test. Deployment requires a distinct explicit user OK after the smoke test. Neither continue nor merge grants production permission. A documentation delivery must not invent a deployed application to satisfy this step.
11. **Recovery with pending decisions.** Recover identity, phase, source/artifact pointers, worker results, ownership and every unresolved prerequisite from authoritative artifacts. The next action names the conjunction of required approvals/setup/invocation/scope conditions. Distinguish same-session resume from artifact-only fresh recovery; do not rely on a prior chat for a stronger claim. Interrupted worker/process liveness is a separate measured behavior, not inferred from saved files. Preserve Pocock context-window constraints and disclose any unsupported recovery step.
12. **Retrospective and closeout.** At mission completion, after merge/release verification when applicable or a motivated no-merge closeout, review evidenced mistakes/rework/manual interventions. Invoke Pocock's own retro through its supported user invocation; the Osmani mission retrospective is the explicit user-requested extension, not an imported Pocock skill. Earlier retrospectives require recurring problems that compromise execution. Propose changes/issues only for significant evidenced gaps and with required authority, after duplicate checks. Never edit global process rules automatically.
13. **Complete selected-profile inventory.** At closeout derive the inventory from the current pinned upstream manifest plus the actual resolved runtime catalog. Record each selected-profile skill's source/revision and one evidence-backed outcome. Proposed compact outcomes: EXECUTED, AVAILABLE_NOT_USED, CATALOGUED_UNAVAILABLE, NOT_VERIFIED. Record runtime availability/invocation restrictions separately so availability is not confused with execution. Catalogue beta/misc entries honestly rather than assuming all are usable. Excluded-author skills are not unused skills. Render the actual route with evidence pointers in the existing closeout location; do not create another permanent catalog/tracker. Reuse upstream-reference diagrams where suitable; derived pictures are not process authority.

## Native-first decision boundary

Plan compares native OMP context/configuration plus the existing mission artifact and selected upstream skills against a minimal project prompt and the mission-team candidate. For any added artifact, record the actual uncovered coordination failure, alternatives, impact and minimum necessary content. KEEP native facilities where sufficient; DELETE redundant coordination machinery. A justified reusable skill must be classified and tested as coordination/integration, including its invocation metadata and profile isolation. No custom router, database, policy engine, relay or persistent service is selected here.

Ownership is decided only after that comparison. Agent OS owns the approved specification/mission. A global skill would belong in its owning skills repository only under separately approved implementation scope; the candidate assessment does not authorize that write. Pilot implementation likewise requires an explicitly selected, authorized repository and slice. No new repository, service, VM or homelab change is authorized by this specification.

## Commands and project structure

This phase changes Markdown only. Existing executable checks:

```bash
git diff --check origin/main...HEAD
git diff origin/main...HEAD -- SPEC-team-execution.md CAPABILITY-MAP-agent-team.md
```

There is no application build, test or dev-server command for this specification. Plan must verify exact-version runtime commands and native isolation/authorization settings before executable trials. Do not invent SDK startup/provider discovery or repeat the rejected hyper.charm.land path. Any authenticated proof uses existing operator login without displaying/copying credentials; missing login is an operator prerequisite, not a request for secrets in chat.

- SPEC-team-execution.md: this module's behavioral specification.
- CAPABILITY-MAP-agent-team.md: module boundary/dependency index.
- tasks/workflow-profiles-evidence.md: accepted provider-module outcome and native startup constraints.
- requirements/ and rfcs/: governing Active authority.
- Existing mission issue/profile tracker: authoritative work state and eventual closeout; future plan/task/evidence paths selected only in their approved phase.

## Style and contract example

Use kebab-case module/task identifiers, original upstream skill names and exact revisions. Keep model/runtime observations distinct from methodological requirements. Example semantic handoff, not a new mandatory runtime schema:

```text
module: team-execution
profile: osmani
phase: implement
base: <actual-git-sha>
worker-scope: <owned-paths-and-acceptance>
pending: <all-unresolved-prerequisites>
next-permitted-action: <action-with-explicit-conditions>
result: <artifact-and-check-pointers>
```

## Acceptance scenarios and verification strategy

| Scenario | Required observable evidence |
|---|---|
| Start a mission and choose relevant responsibilities | One selected profile/pin, original requirement and proportionate role assignments; no fixed seven-agent ceremony. |
| Implement two independent small tasks | Actual separate writers, explicit ownership/base, observed overlapping work, integration and relevant checks; no shared-file conflict hidden as success. |
| One dependent activity is blocked | A real approval/setup/invocation prerequisite stops it while authorized independent work proceeds; next action preserves all open conditions. |
| Exercise Pocock invocation and missing setup | Actual supported user invocation, disclosed setup prerequisite and restart behavior; no foreign fallback or automated user-only step inferred from initial choice. |
| Introduce executable logic in the authorized pilot | Selected-method RED/GREEN evidence, actual worker return, integrated result and analyst/QA acceptance. Documentation-only cases state why TDD does not apply. |
| Reviewer finds a controlled defect | Real clean-context review of original requirement/exact SHA; correction, relevant check and independent re-review of final head. |
| Checks fail or authorization is missing | Correct NO-GO on affected delivery; eventual genuine green checks in an authorized environment or explicit blocker, never CI bypass or artificial production failure. |
| Merge an authorized delivery | PR/head/base/review/check/merge evidence and exact SHA; user smoke instructions; no deployment before separate user OK. |
| Restart with worker results and a pending decision | Separate same-session and fresh-artifact observations recover full corrected contract; missing prerequisite cannot be reconstructed only from chat. |
| Close the selected-profile mission | One authoritative complete inventory/route with evidence-backed states, source-faithful retrospective and reconciled/archived documents. No automatic issue farm or other-profile unused inventory. |

Use small real acceptance slices and actual native transcripts, selected-source identity checks and repository verification. Preserve originals and corrected observations in durable reviewer-accessible material after privacy inspection. Unit/regression tests cover new executable logic; tools/framework are chosen from the authorized pilot's existing stack, not added for ceremony. Runtime inference, CI execution and repository writes require their existing spending/permission authority. No live model or CI run is authorized merely by this Draft.

## Boundaries

**Always:** read original authority; retain one selected method; verify identities and actual actions; preserve all pending prerequisites; use proportionate specialists/checks; serialize integration; record exact reviewed/tested revisions; use native auto-QA-off and authorized-provider restrictions from the accepted dependency before runtime tests.

**Ask first:** change selected profile or product scope, bypass an upstream gate, add architecture/persistent services, change authentication/permissions, write to another repository, incur new costs, choose a pilot with material operational consequences, or deploy. Technical choices already approved, local and reversible are autonomous.

**Never:** simulate agents/review/CI, mix methodological families, migrate credentials, modify global operator configuration, expand consumer permissions, retry blocked external discovery, erase failed raw proof, merge on stale/failing required checks, or treat chat as the only durable record.

## Approval scope and remaining decisions

This specification proposes the behavior to approve, not an implementation choice. The specific native/prompt/skill approach, exact ownership/pilot and executable commands are Plan decisions after approval; no attachment is required to approve these product requirements. The four closeout outcome labels are proposed vocabulary, not evidence already collected.

Review this Draft before Plan. Approval of it alone does not authorize implementation, other-repository writes, deployment, migration or spending outside existing limits. The user-authorized continuation enables Specify; prior workflow-profiles merge authority does not automatically approve this new module's later phase gates.

## Primary sources

- [Osmani specification workflow](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/spec-driven-development/SKILL.md).
- [Osmani skill router](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/using-agent-skills/SKILL.md).
- [Pocock routing/setup/context rules](https://github.com/mattpocock/skills/blob/24fe0ef7737efae15c87225755e9f6f5965e4888/skills/engineering/ask-matt/SKILL.md) and [user-invoked retro](https://github.com/mattpocock/skills/blob/24fe0ef7737efae15c87225755e9f6f5965e4888/skills/engineering/retro/SKILL.md), read as product sources only.
- [OMP native task documentation](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/tools/task.md); documented features remain candidates until the affected real path is verified.
- [AGENTS](AGENTS.md), [REQ-0001](requirements/REQ-0001-software-factory.md), [RFC-0001](rfcs/RFC-0001-principles.md).
