# Spec: workflow-profiles

**Status:** Approved by the user on 2026-10-10.
**Module:** workflow-profiles.
**Parent:** [approved capability map](CAPABILITY-MAP-agent-team.md).
**Tracking:** [issue 35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Language:** English is authoritative by explicit user instruction; the Italian conversation version is a review translation.

## Objective

Let the user choose Osmani or Matt Pocock when starting a mission, then keep the coordinator and every specialist on that author's workflow. Make the selected profile, current phase, applicable approval requirements and any deviation inspectable and recoverable after reconnection.

This specifies behavior and a contract. It does not select the runtime, UI, hosting or MCP transport.

## Assumptions and verified context

- Selection applies to a mission, not to the entire installation. Different missions may use different profiles.
- Resuming a mission preserves its profile. A deliberate change requires human approval and explicit reconciliation of artifacts/approvals; no silent switching.
- Repository authority, user decisions and economic limits remain applicable to either profile.
- Reuse skills from codex-skills and their upstream sources; do not copy or edit originals to hide differences.
- The verified import manifest pins Osmani to 1401c8b8030e023baeebb31781a6653fe8e93026 and Pocock to 24fe0ef7737efae15c87225755e9f6f5965e4888. Do not silently substitute upstream HEAD.
- Osmani's imported alias osmani-test-driven-development retains internal name test-driven-development, which collides with Superpowers. Name alone is insufficient identity.
- This module can be satisfied by existing configuration and authoritative instructions if runtime tests prove them sufficient. No custom router is presumed necessary.

## Functional requirements

1. Before executing methodological work, obtain an explicit profile choice or recover the already-approved choice. If absent, ask instead of choosing a default.
2. Resolve a skill by author/repository, pinned revision and path. The active methodological catalog contains only the chosen author's skills and necessary upstream references. External MCP tools and runtime facilities are not methodological skills.
3. Follow upstream applicability rules, ordering, artifacts and human-review gates. A workflow is not a universal checklist: conditional skills run only when relevant; required gates cannot be silently skipped.
4. For Osmani, use using-agent-skills as its router and follow interview-me → idea-refine → spec-driven-development → planning-and-task-breakdown when applicable, then the upstream build/verify/review/ship guidance. For Pocock, use its own routing and originating spec/tickets/implementation/review instructions. Reading the other author's sources to evaluate this module is research, not invoking their workflow.
5. Give delegated agents the selected profile, exact sources, current phase, approved scope and artifact pointers. Validate their methodological skill identity when results return.
6. Record deviations explicitly: affected upstream instruction/revision, concrete reason, alternatives, impact, authorization and verification. Distinguish user-requested extensions from upstream behavior. Never relabel another author's skill as an extension of the chosen flow.
7. Independent review and mission-level retrospective are required team behaviors requested by the user. Map them to the selected upstream where supported; otherwise declare a user extension. No Pocock retro is invoked in an Osmani mission.
8. On missing skills, incompatible invocation or unmet gates, stop only the affected action, describe the gap and continue independent authorized work. No fallback to another methodology.
9. Preserve sufficient durable context to explain the current phase and next permitted action without reconstructing them from a chat. Reuse the authoritative mission artifact; no extra database or ledger is required by this spec.

## Provider boundary

team-execution consumes: selected profile; exact upstream references; current phase; approved scope/artifact pointers; applicable pending approvals; declared extensions/deviations.
It returns the performed step, skill identities, evidence and proposed next step for consistency review.

This is a semantic contract, not a JSON/API design. mobile-control and mcp-access must not define competing copies of mission profile/state.

## Tech stack and commands

This draft is a Markdown behavioral specification in Agent OS. The runtime/configuration representation and runtime verification commands remain to be selected in Plan after approval, using verified native capabilities.

For a local checkout with origin/main and the specification branch:
```bash
git diff --check origin/main...HEAD
git diff origin/main...HEAD -- CAPABILITY-MAP-agent-team.md SPEC-workflow-profiles.md
```
Build, lint, application test and dev-server commands are not applicable to this documentation-only artifact. They must be added to the plan for any executable implementation; no unverified commands are invented.

## Project structure and style

- CAPABILITY-MAP-agent-team.md: approved boundaries and specification index.
- SPEC-workflow-profiles.md: this module's behavioral source.
- Existing requirements/ and rfcs/: governing sources; this draft does not overwrite them.
- Implementation/configuration/test paths: choose in Plan after reuse analysis.

Use stable kebab-case ids and Markdown tables/lists, preserving upstream identifiers. Example semantic record, not a runtime schema:
```text
profile: osmani
source: addyosmani/agent-skills@1401c8b8030e023baeebb31781a6653fe8e93026
skill-path: skills/spec-driven-development/SKILL.md
phase: Specify
next-action: request-spec-approval
```

## Testing strategy and success criteria

No synthetic tests that merely repeat prose. Verify configuration and actual runtime behavior with bounded scenarios after implementation:

- [ ] Start one mission per profile: only the chosen author's methodological skills are available/invoked, with exact source identity recorded.
- [ ] Resolve the TDD name collision to Osmani's source in an Osmani mission; never load Superpowers as a substitute.
- [ ] Delegate two independent bounded tasks under one profile; returned steps retain that profile and its phase constraints.
- [ ] Attempt progression past a required approval: the affected action waits, while unrelated authorized work remains possible.
- [ ] Resume after disconnect: recover profile, phase, authoritative artifacts and pending decision without switching.
- [ ] Attempt an unavailable or foreign skill: disclose the gap instead of silently substituting.
- [ ] Inspect a declared extension/deviation: reason, source, authorization and verification are present.
- [ ] A reviewer can trace executed methodological steps to the chosen upstream and the exact examined revision.

The test framework depends on the selected implementation. These scenarios are acceptance requirements, not evidence that OMP already satisfies them.

## Boundaries

Always: use approved mission scope and repository authority; verify exact upstream identities; keep profiles separate; honor applicable human gates; disclose gaps/deviations; reuse existing storage/configuration.

Ask first: change a mission's profile, bypass an upstream gate, materially alter scope/product/architecture or introduce consequences outside existing authorization.

Never: mix methodological catalogs, silently update pinned sources, fabricate approvals/runtime evidence, invoke the other author's workflow as a hidden fallback, or merge/deploy without required approval.

## Open questions and approval scope

Plan must determine whether native OMP discovery/configuration can isolate catalogs for coordinator and children and preserve phase/approval context without custom code. If not, compare alternatives and demonstrate necessity before proposing custom. Runtime suitability is not yet established.

Before execution changes the existing Codex/Developer Workspace contract, reconcile REQ-0001 and other affected Active sources. This module does not itself replace that architecture.

Approval accepts this module's behavioral requirements and boundaries. It does not approve a runtime, custom implementation, plan, source migration, merge or deployment.

## Sources

- [Osmani router](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/using-agent-skills/SKILL.md).
- [Osmani spec workflow](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/spec-driven-development/SKILL.md).
- [Pocock engineering catalog](https://github.com/mattpocock/skills/blob/24fe0ef7737efae15c87225755e9f6f5965e4888/skills/engineering/README.md).
- [Import identities](https://github.com/skunklabs-uk/codex-skills/blob/main/config/global-skill-upstreams.tsv), read on 2026-10-10, blob 7fcc32d29bc19f655a8fbad5486b6212f8c4baf0.
- [AGENTS.md](AGENTS.md), [REQ-0001](requirements/REQ-0001-software-factory.md), [RFC-0001](rfcs/RFC-0001-principles.md).
