# workflow-profiles: native feasibility evidence

**Status:** Draft — partial execution evidence, not module acceptance.
**Date:** 2026-10-10.
**Mission:** [35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Current task:** [37](https://github.com/skunklabs-uk/agent-os/issues/37); catalog and URI checks passed, child runtime proof remains outstanding.
**Method:** Osmani. Tasks 37–40 approved by the user on 2026-10-10; Checkpoint A has not been reached.

## Scope and baseline

Disposable local execution only. No homelab configuration, provider credential changes, upstream skill edits or model inference calls were made. Published OMP 18.8.7 was installed locally with Bun 1.4.3, and compared with upstream revision b07a1c146d0d12cfc855a2c65d52f892ef319040.

The published discovery implementation and CLI catalog implementation are byte-identical to the pinned checkout:
- extensibility/skills.ts SHA-256: 50892b528c20ab1fc901dad90e3900f05433d64767710e288d1821c96f50ea85.
- cli/skill-list.ts SHA-256: 7276feecb8c5cba43d4de27a1f5a6add6fb9f8af4b21f80a46971014945a3ee4.

Upstream checkouts:
- Osmani: 1401c8b8030e023baeebb31781a6653fe8e93026.
- Pocock: 24fe0ef7737efae15c87225755e9f6f5965e4888.

## Native configuration exercised

Separate disposable working directories held .omp/config.yml. No tracked production configuration was introduced. All foreign user/project skill toggles were false; native user skills were false. customDirectories pointed to Osmani skills/, or Pocock skills/engineering and skills/productivity. includeSkills contained exact frontmatter names from the selected roots, not a wildcard.

The contaminated variant enabled native project skill discovery and added two non-invoked fixtures: a differing TDD skill with the same raw name and an unrelated foreign-methodology skill. The same include allowlist was retained. Native custom-directory precedence and final-name inclusion filtering were exercised.

Catalogs are bounded to these roots. This does not prove safe discovery in arbitrary plugin/project configurations, automatic author verification, or skill applicability compliance.

## Results

| Check | Osmani | Pocock |
|---|---|---|
| Initial catalog | 25 expected, 25 resolved | 27 expected, 27 resolved |
| Missing/unexpected entries | 0 / 0 | 0 / 0 |
| Physical paths outside chosen upstream | 0 | 0 |
| Initial discovery warnings | 0 | 0 |
| Hidden entries | 0 | 16, reflecting upstream user-invoked metadata |
| Catalog after foreign fixture/collision | 25, no foreign entries | 27, no foreign entries |
| Bare TDD URI | Pinned Osmani SKILL.md | Pinned Pocock engineering/tdd/SKILL.md |
| Foreign namespaced TDD URI | Unknown skill: native | Unknown skill: native |
| Unrelated foreign URI | Unknown skill: foreign-methodology | Unknown skill: foreign-methodology |

Collision warnings describe native/test-driven-development or native/tdd as available, but final allowlist filtering removes them: actual URI resolution rejected both. Warning text is not evidence of final reachability.

Osmani catalog:
api-and-interface-design, browser-testing-with-devtools, ci-cd-and-automation, code-review-and-quality, code-simplification, constraint-driven-development, context-engineering, debugging-and-error-recovery, deprecation-and-migration, documentation-and-adrs, doubt-driven-development, frontend-ui-engineering, git-workflow-and-versioning, idea-refine, incremental-implementation, interview-me, observability-and-instrumentation, performance-optimization, planning-and-task-breakdown, security-and-hardening, shipping-and-launch, source-driven-development, spec-driven-development, test-driven-development, using-agent-skills.

Pocock catalog:
ask-matt, code-review, codebase-design, diagnosing-bugs, domain-modeling, grill-me, grill-with-docs, grilling, handoff, implement, implement-spec, improve-codebase-architecture, pr, prototype, research, retro, setup-matt-pocock-skills, tdd, teach, to-questionnaire, to-spec, to-tickets, triage, wait-what, wayfinder, wizard, writing-for-agents.

Every Osmani file resolved under the pinned osmani-study/skills/<name>/SKILL.md. Pocock files resolved under its pinned engineering/productivity roots. Catalog availability does not authorize invoking all skills or ignore user-only applicability.

## Commands actually executed

Working directory: /workspace/scratch/3f8497f0c0ba.

```bash
npm install --prefix /workspace/scratch/3f8497f0c0ba/omp-tools bun@1.4.3 @oh-my-pi/pi-coding-agent@18.8.7
git clone --depth 1 https://github.com/can1357/oh-my-pi.git omp-study
git -C omp-study rev-parse HEAD
git clone https://github.com/addyosmani/agent-skills.git osmani-study
git -C osmani-study checkout --detach 1401c8b8030e023baeebb31781a6653fe8e93026
git clone https://github.com/mattpocock/skills.git pocock-study
git -C pocock-study checkout --detach 24fe0ef7737efae15c87225755e9f6f5965e4888
PI_CODING_AGENT_DIR=/workspace/scratch/3f8497f0c0ba/profile-probe/state ./omp-tools/node_modules/.bin/bun ./omp-tools/node_modules/@oh-my-pi/pi-coding-agent/src/cli.ts skill list /workspace/scratch/3f8497f0c0ba/profile-probe/osmani --json
PI_CODING_AGENT_DIR=/workspace/scratch/3f8497f0c0ba/profile-probe/state ./omp-tools/node_modules/.bin/bun ./omp-tools/node_modules/@oh-my-pi/pi-coding-agent/src/cli.ts skill list /workspace/scratch/3f8497f0c0ba/profile-probe/pocock --json
```

Both listing commands ran before and after contamination. URI checks used the published SkillProtocolHandler.resolve(parseInternalUrl(uri), {skills}) against each actual returned contaminated catalog, following the upstream test pattern. This was a disposable observation script, not new production logic or a repository test framework.

Raw local catalog SHA-256:
- Osmani initial: 3614bc84db853731d0a751ce2e0f035c55e40faa3ec7eb2900657f996d531a44.
- Osmani contaminated: f9e67531e04e19ffc50292f16dd50b198c3218dcd871a3859e718abd170963e0.
- Pocock initial: 75bb65611685cc82bc746ec09f1d7895f718286c1ee141d796299abdcbe0fbfa.
- Pocock contaminated: 15b0a47fb3be428f68d3db4354b16cb0e21c71f7480b51f6e5b93e0fc72e92c1.

Hashes identify transient output; the durable results and reconstruction instructions are recorded above.

## Child propagation: inspected, not runtime-proven

At the pinned source:
- task/structured-subagent.ts resolveAutoloadSkills copies session.skills; autoload matches by name and silently drops missing names.
- task/executor.ts supplies skills: options.skills to child createAgentSession.
- sdk.ts uses explicitly provided skills instead of discovery; skillsReloadable is false when options.skills is provided.

This supports the native approach but does not replace an actual spawned child transcript. Delegation and returned-step checks remain pending.

## Blocked session probe and required environment

An SDK no-inference probe reported availableAuthenticatedModels: 0 from a newly created isolated auth store and registry. No host credential stores were inspected. This is evidence about the disposable environment only.

Session construction then attempted an external request to hyper.charm.land. Automatic approval review rejected the operation because the destination/payload were outside the established local probe. No retry or bypass was attempted. Source inspection identifies Charm Hyper as a model gateway with public catalog discovery; sdk.ts can perform online-if-uncached discovery during model fallback. The exact rejected wire payload was not observed, so no claim about its transmitted data is made.

Continuation requires an authorized OMP execution environment/provider and bounded model choice. Do not expand network access merely to complete a catalog check. Use documented native provider settings and verify their effects before session execution; never repurpose credentials from this ChatGPT session.

## Restart handoff

In the authenticated execution environment:
1. Read current AGENTS.md, Active REQ-0001/RFC-0001, approved SPEC-workflow-profiles.md, tasks/plan.md and issues 35, 37–40. Verify actual branch/revision and existing working tree.
2. Preserve the Osmani execution workflow. Reading Pocock sources is research/test setup, not switching the current mission's methodology.
3. Reproduce the native catalogs and URI exclusions above with exact upstream revisions. Verify the final catalog by physical identity, not name only.
4. Finish Task 37 by observing the native child's inherited catalog with bounded execution; record commands/transcript and limits.
5. Execute Task 38's separate-profile scenarios using existing approved provider access/cost limits. Reuse mission artifacts; no custom router/database without accepted necessity proof.
6. Present Checkpoint A evidence for human review before Task 39. Do not merge, deploy, close mission 35 or declare module completion.
7. If runtime remains unavailable, keep affected tasks open, preserve findings here and continue independent authorized source inspection only.

## Method trace and remaining checks

Used Osmani context-engineering, incremental-implementation and source-driven-development. TDD applicability was examined: no production logic was written, so no RED/GREEN code change or synthetic prose tests were introduced. Native discovery and URI runtime checks protect the approved catalog contract.

No methodological substitution or approval-gate deviation was used. The session-probe blocker and missing provider prerequisite are disclosed, not treated as passes. No custom orchestration has been justified or added.

Remaining: actual child execution; explicit profile choice; missing/foreign skill behavior during an agent turn; approval gate behavior; disconnect/resume; parallel delegation; returned provenance; independent review and module closeout. No Task 37 closure or Checkpoint A acceptance yet.

## Primary sources

- [OMP skills](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/skills.md).
- [Native catalog command](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/cli/skill-list.ts).
- [Skill URI handler](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/internal-urls/skill-protocol.ts).
- [Task session executor](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/task/executor.ts).
- [OMP SDK](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/sdk.ts).
