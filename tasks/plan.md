# Implementation Plan: workflow-profiles

**Status:** Archived — execution completed; Checkpoint B explicitly approved by the user on 2026-10-10. Retained only as execution history, not current instructions.
**Scope:** [approved module spec](../SPEC-workflow-profiles.md).
**Tracking:** [Agent OS issue 35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Method:** Osmani planning-and-task-breakdown at 1401c8b8030e023baeebb31781a6653fe8e93026.
**Language:** English is authoritative.

Current accepted outcome, durable limits and the user's conditional merge authorization are recorded in [workflow-profiles evidence](workflow-profiles-evidence.md#accepted-outcome-and-closeout). The approved module spec remains the behavioral authority; this completed plan does not authorize another module, deployment or production runtime replacement.

## Outcome

Demonstrate that a mission and its delegated agents retain one chosen workflow, exact upstream identities and applicable approval gates across execution and reconnection. Prefer native OMP configuration and existing authoritative mission artifacts. This plan covers workflow-profiles only; mobile UI, MCP, hosting and the complete specialist team belong to their respective modules.

## Evidence and proposed approach

OMP revision b07a1c146d0d12cfc855a2c65d52f892ef319040 documents skill include/exclude filters, custom directories and explicit SDK skill lists. Children receive the parent session's skills. Differing name collisions preserve variants under namespaces; hiding a skill does not disable it. Agent autoloadSkills references parent skills by name and silently ignores unknown names.

Therefore, test exact source identity and the final resolved catalog, rather than assuming directory aliases or hidden entries provide separation. Try native configuration first. Explicit SDK skill selection is an existing fallback capability to evaluate, not approval to build a custom router.

Approval gates and durable phase state are a separate hypothesis: skill filtering alone does not prove them. Distinguish instruction compliance from runtime enforcement in the evidence.

## Ordered work packages

### 1. Native feasibility — Small

Inspect pinned discovery/configuration and child-session behavior; reproduce a catalog for each profile in a disposable environment.

Acceptance: only the selected author's methodological sources resolve, including namespaced variants; the Osmani TDD collision resolves to its pinned source; report unsupported behavior explicitly.

Verification: capture resolved names, physical paths and revisions for coordinator and child. This inspection does not require model calls.

Likely paths: upstream read-only sources; tasks/workflow-profiles-evidence.md.

### 2. One mission per profile — Medium

Use native configuration and the existing mission artifact to carry profile, sources, phase, scope, pending approvals and declared extensions. Exercise Osmani and Pocock separately.

Acceptance: a mission starts with an explicit choice, resumes with the same choice and stops an affected step at a required approval or missing/foreign skill.

Verification: bounded runtime transcripts for both profiles, disconnect/resume and negative cases. Record actual invocations, not merely successful discovery.

Likely paths: tasks/workflow-profiles-evidence.md; minimal native configuration/context files, selected after package 1 (no more than five files per task).

### Checkpoint A

Review packages 1–2 evidence. If native facilities fail, compare configuration changes, explicit SDK selection and alternative runtime support by effort and coverage. Request approval for any material architecture change before proceeding. Do not silently weaken the approved requirements.

### 3. Delegation and recovery — Medium

Delegate two independent bounded tasks using the same approved mission contract; check returned identities and phase constraints. Verify a blocked action does not prevent unrelated authorized work.

Acceptance: both children retain the profile and exact skill provenance; resume preserves pending decisions; deviations/extensions record source, reason, alternatives, impact, authorization and verification.

Verification: child transcripts and recovered mission artifact. Parallelize the independent test activities only after the shared contract is settled.

Likely paths: the same minimal configuration/context files and evidence document. No new state database is presumed.

### 4. Independent review and closeout — Small

Have a reviewer outside the implementation context compare the exact revision, approved spec and evidence. Correct findings and re-review material changes.

Acceptance: every spec scenario has evidence or an explicit unresolved failure; documentation identifies limitations and the next module's dependency; affected Active sources are reconciled before changing the Codex/Developer Workspace contract.

Verification: reviewer report with examined SHA and evidence links, followed by user review. Merge and deployment remain separate approvals.

Likely paths: tasks/workflow-profiles-evidence.md; existing authoritative files only if an approved reconciliation is necessary, in separately scoped tasks.

### Checkpoint B

Review packages 3–4 and all acceptance scenarios before declaring the module complete. No completion claim while required runtime evidence is missing.

## Task index

1. [Task 1: task: verify native workflow profile isolation ](https://github.com/skunklabs-uk/agent-os/issues/37)
2. [Task 2: task: verify profile selection gates and resume ](https://github.com/skunklabs-uk/agent-os/issues/38)
3. [Task 3: task: verify delegated workflow fidelity and recovery ](https://github.com/skunklabs-uk/agent-os/issues/39)
4. [Task 4: task: independently review workflow profiles and closeout ](https://github.com/skunklabs-uk/agent-os/issues/40)

Tasks37–40 were approved on 2026-10-10 and completed in the accepted bounded scope. Their historical checkpoints were tracked in Tasks38 and40; tasks are closed after PR41 integration. Parent mission35 stays open for the remaining modules.

## Tasks gate and tracking

The separate Plan → Tasks gate was completed on 2026-10-10. Checkpoint A was accepted after fresh-context independent review; the subsequent continuation authorized Task39. The user explicitly approved Checkpoint B after independent review of `201fcaa` and authorized documentary closeout and a conditional merge. The [current outcome record](workflow-profiles-evidence.md#accepted-outcome-and-closeout) preserves evidence, integration status, limits and the deployment/runtime boundary; old pending-gate statements in this archived plan are historical.

The coordination tracker is GitHub issue35; the linked detailed issues above are the single task tracker. Do not duplicate their checklists in tasks/todo.md. No existing incomplete plan or task list is overwritten.

## Verification environment and commands

Use an isolated checkout/test environment, not the production homelab. Establish the supported pinned OMP installation and focused commands during native feasibility; record exact commands before executable work. Do not invent installation/build/test commands.

Documentation checks in a local checkout:
```bash
git diff --check origin/main...HEAD
git diff origin/main...HEAD -- CAPABILITY-MAP-agent-team.md SPEC-workflow-profiles.md tasks/plan.md
```

No application build is required for the planning artifact. Model/provider access and any spending must comply with existing authorization and repository limits; unavailable access is a disclosed test prerequisite, not fabricated evidence.

## Risks and decisions

| Risk | Response |
|---|---|
| Namespace or provider leakage | Inspect final catalogs and physical sources; test coordinator and children. |
| Instructions appear to enforce gates but do not | Test blocked progression and report the enforcement level. |
| Resume loses authoritative context | Exercise reconnection with an unresolved approval. |
| Runtime choice conflicts with Active REQ-0001 | Reconcile before changing the existing architecture. |
| Prototype grows into custom orchestration | Apply the repository's necessity test; obtain approval for material changes. |

Homelab suitability and actual mobile MCP compatibility will be assessed in the appropriate module specifications; this plan does not decide or defer their inclusion.

## Historical plan approval

The sequence and native-first feasibility approach were approved before execution. The original plan approval alone did not authorize custom orchestration, source migration, merge, deployment or spending outside existing limits. Later module acceptance and conditional merge authority are recorded in the current outcome source.

## Primary references

- [Osmani planning skill](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/planning-and-task-breakdown/SKILL.md).
- [OMP skill discovery](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/skills.md).
- [OMP SDK skill configuration](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/examples/sdk/04-skills.ts).
- [OMP agent discovery](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/task-agent-discovery.md).
