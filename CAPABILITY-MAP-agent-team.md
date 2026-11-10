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
- mobile-control, mcp-access: mission35 resta aperta. Homelab #2095 autorizza
  una nuova UI browser upstream per OMP come accesso alternativo ai tre
  Developer Workspace SSH; la missione è in corso e non prova il controllo
  mobile dell'intero team Agent OS né l'accesso MCP. Deployment, sessione
  effettiva e copertura su dispositivi reali non sono ancora attestati.
  [Stato e DoD correnti](https://github.com/skunklabs-uk/homelab/issues/2095);
  [PR d'integrazione](https://github.com/skunklabs-uk/homelab/pull/2100).

The accepted workflow-profiles and team-execution outcomes and their bounded evidence remain in their module outcome sources. The completed execution plan is archived. Homelab #2095 is a related OMP workspace UI integration, not acceptance or completion of Agent OS mobile-control/mcp-access. No complete MVP acceptance, IWANT main merge, production or deployment is inferred; mission35 stays open.

## Process trace

The issue was created after interview-me/idea-refine before specification. This was an unjustified sequencing deviation, explicitly acknowledged. Recovery: approve this map, then follow Specify → Plan → Tasks → Implement per module according to Osmani's spec-driven-development. Map approval does not approve any module spec, plan, implementation, merge or deployment.

## Ambito del ritiro e stato corrente

Il 16 ottobre 2026 il Product Owner ha autorizzato la dismissione del vecchio
progetto omp-web e della sua infrastruttura dedicata, dopo il confronto con le
capacità native.
Non sono più richiesti manutenzione del fork, npm, bundle desktop, updater,
integrazione MCP dedicata o onboarding di runner per questi canali.

Quella decisione riguarda esclusivamente il vecchio fork, i relativi asset e
l'infrastruttura dedicata; non chiude la missione generale #35. L'8 novembre
2026 il Product Owner ha autorizzato in Homelab #2095 un percorso nuovo e
distinto: UI upstream mantenuta per OMP, alternativa ai tre accessi SSH.
L'autorizzazione non riattiva il vecchio fork né le sue specifiche. #2095 è
ancora aperta e non attesta deployment o uso; mission35 resta aperta per la
propria DoD più ampia. Lo stato e gli artefatti aggiornati sono linkati sopra.
