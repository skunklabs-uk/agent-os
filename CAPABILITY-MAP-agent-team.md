# Capability Map: Mobile-controlled IT agent team

**Status:** Approved by the user on 2026-10-10.
**Tracking:** [Agent OS issue 35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Language:** English is authoritative for these artifacts, as explicitly requested by the user. Italian review translations are provided in the conversation.

## Objective

Take an idea through clarification, design, implementation, verification, review and release with a specialized agent team that the user can supervise from a tablet or phone.

## Modules

These are functional boundaries, not a mandate for separate services, pods or always-running agents.

| Module id | Responsibility | Depends on |
|---|---|---|
| workflow-profiles | Select Osmani or Pocock; preserve upstream skill identity, workflow and approval requirements; disclose and justify deviations | — |
| team-execution | Mission coordinator, relevant specialists, independent parallel work, durable results, verification, independent review, functional acceptance, release, closeout and proportionate retrospective | workflow-profiles |
| mobile-control | Start/resume work, inspect coordinator and specialist progress, answer questions, interrupt/steer and approve from a mobile browser | team-execution |
| mcp-access | Delegate work, inspect status/results and interrupt through a compatible MCP client; determine v1 inclusion through actual feasibility analysis | team-execution |

Logical order: workflow-profiles → team-execution → mobile-control and mcp-access.
Assess MCP feasibility during specification without waiting for mobile implementation. This order does not defer MCP by default.

## Team responsibilities

The coordinator reads coordination issues, specifications and authoritative sources directly, assigns work, tracks scope/dependencies/progress, follows the selected workflow and updates the tracker. Reconcile changed instructions rather than inventing requirements. GitHub/Bitbucket access must be verified.

Relevant specialists cover PM, analysis, architecture, UX/UI, development, testing and DevOps. Independent activities may run concurrently once shared contracts are settled. The independent reviewer is distinct from implementers, uses a separate context and checks the original requirements, exact revision, diff and evidence before merge; re-review material corrections.

Analyst/QA owns functional acceptance. Invoke security/privacy expertise for relevant authentication, credentials, personal data, exposed services and permissions. Coordinator owns documentation and closeout with reviewer verification. DevOps includes reliability, observability and rollback; data/performance expertise is conditional.

Retrospectives occur after mission completion, merge, release verification when applicable and closeout, not after every task/PR. Bring one forward only for recurring problems compromising execution. Propose evidence-based improvement issues in Agent OS or the affected repository after checking duplicates; include impact, minimal change and benefit verification. Do not automatically modify authoritative rules.

Use Pocock's own retro where applicable. Verify Osmani guidance; absent upstream coverage, label the requested retrospective as a user extension without importing Pocock skills.

## Cross-cutting constraints

Prefer homelab only with proportionate implementation/operating effort. Choose a new project or Waypoint/waypoint-db after reality-check. GitHub retains durable project context. Do not automate ChatGPT UI through unsupported mechanisms or presume an MCP endpoint is usable from the user's actual client.

## Specification index

- [workflow-profiles](SPEC-workflow-profiles.md): Approved on 2026-10-10.
- team-execution, mobile-control, mcp-access: not yet specified; no corresponding specification files exist.

workflow-profiles has bounded native runtime evidence and accepted Checkpoint A; corrected delegation/recovery evidence is recorded for Task40/CheckpointB review in [workflow-profiles evidence](tasks/workflow-profiles-evidence.md). Full module acceptance and next-module work remain pending. This does not replace the Active Codex/Workspace contract.

## Process trace

The issue was created after interview-me/idea-refine before specification. This was an unjustified sequencing deviation, explicitly acknowledged. Recovery: approve this map, then follow Specify → Plan → Tasks → Implement per module according to Osmani's spec-driven-development. Map approval does not approve any module spec, plan, implementation, merge or deployment.
