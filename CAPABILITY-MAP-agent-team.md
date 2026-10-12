# Capability Map: Mobile-controlled IT agent team

**Status:** Active — approved by the user on 2026-10-10.
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

- [workflow-profiles](SPEC-workflow-profiles.md): Active behavioral authority; bounded module acceptance is recorded in the outcome source below.
- [team-execution](SPEC-team-execution.md): Active specification; approved temporary task set has [bounded native execution evidence and complete selected-profile inventories](tasks/team-execution-evidence.md). The sandbox's exact-head final review is [Task50](https://github.com/skunklabs-uk/agent-os/issues/50). The subsequent real Osmani pilot is merged and closed with an explicitly accepted evidence-retention exception; [the owning closeout decision](https://github.com/skunklabs-uk/waypoint-db/issues/20#issuecomment-6116611891) records its outcome and limits. The separate [positive Pocock delivery](tasks/team-execution-evidence.md#positive-pocock-delivery--iwant523) is now observed on IWANT#523. The independent final review at9559131 has no remaining findings; the Product Owner accepted the bounded module and authorized Agent OS documentation PR/merge on 2026-10-12.
- [mobile-control](SPEC-mobile-control.md) and [mcp-access](SPEC-mcp-access.md): Active specifications approved on 2026-10-12 atf55c2b7, together with the shared remote-consumer contract in the provider specification. The [Plan](tasks/plan.md) now proceeds to readiness and bounded local qualification under the Product Owner’s continuation delegation; Task52 owns the first concrete scope. No application implementation or hosting choice is selected by this readiness.

The user explicitly approved workflow-profiles at Checkpoint B after independent review. [Accepted outcome, evidence and limitations](tasks/workflow-profiles-evidence.md#accepted-outcome-and-closeout) remain unchanged. team-execution Spec/Plan/Tasks43–50 approval covers temporary proof only; native isolated writers, integration, corrected recovery and exact-code-head independent review now have bounded evidence. The real Osmani pilot subsequently delivered waypoint-db PR22, with successful initial PR/main CI and Product Owner smoke; its accepted raw-retention exception does not turn the retention failure into a PASS. [Current evidence and authority](tasks/team-execution-evidence.md#direct-product-owner-acceptance-and-current-authority) record the positive IWANT#523 Pocock delivery, independent final review and explicit bounded module acceptance. The completed execution plan is archived. Next: complete Task52 readiness, then advance only concrete authorized mobile/MCP slices through the selected-method gates. No Active Codex/Workspace replacement, complete MVP acceptance, IWANT merge, production or deployment is inferred; mission35 stays open.

## Process trace

The issue was created after interview-me/idea-refine before specification. This was an unjustified sequencing deviation, explicitly acknowledged. Recovery: approve this map, then follow Specify → Plan → Tasks → Implement per module according to Osmani's spec-driven-development. Map approval does not approve any module spec, plan, implementation, merge or deployment.
