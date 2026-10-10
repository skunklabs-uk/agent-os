# workflow-profiles: native feasibility evidence

**Status:** Draft — corrected bounded Tasks37–39 proof and independent technical review are ready for Checkpoint B human module review. Checkpoint A remains accepted; full module acceptance is pending.
**Date:** 2026-10-10.
**Mission:** [35](https://github.com/skunklabs-uk/agent-os/issues/35).
**Current task:** [40](https://github.com/skunklabs-uk/agent-os/issues/40) — technical review completed; final human module review pending. No next-module work, full module completion, merge or deployment.
**Method:** Osmani. Tasks 37–40 were approved by the user on 2026-10-10. The user subsequently requested a fresh-context independent review and delegated the checkpoint decision to the coordinator.

The initial-environment sections preserve historical findings. Their missing-runtime blocker and restart instructions are superseded by the operator-host continuation and current handoff below.

## Scope and baseline

Initial disposable pass described below: no homelab configuration, provider credential changes, upstream skill edits or model inference calls were made. The authenticated continuation is recorded separately below. Published OMP 18.8.7 was installed locally with Bun 1.4.3, and compared with upstream revision b07a1c146d0d12cfc855a2c65d52f892ef319040.

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

## Initial restart handoff (superseded)

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

## Continuation — upstream tests and operator handoff

### Verified upstream tests

The pinned task/autoload-skills.test.ts and its unchanged helpers/session-defaults.ts were executed against published OMP 18.8.7. The published task/executor.ts matches the pinned source byte-for-byte (SHA-256 f3c0357b3dbcb8e4bc2177b5e6d942362afe72cd8c4e663c7541f69af3162fe9).

Command actually run:
```bash
./omp-tools/node_modules/.bin/bun test ./omp-tools/upstream-tests/task/autoload-skills.test.ts
```

Result: 3 pass, 0 fail, 5 assertions. Covered: each autoloaded skill injected; empty autoload injects none; skill messages precede the task prompt. Session/model functions are mocked by the upstream tests. These results do not prove real child inference, profile fidelity or mission approval behavior.

Earlier source-checkout test attempts failed during module loading, before assertions, because export/html/tool-views.generated.js was absent. Rather than building unrelated frontend assets, the unchanged test/helper files were placed in the disposable installed-package environment. No upstream implementation was patched, tests disabled or production workaround added. The test-run environment changed, not the chosen Osmani methodology. Applied debugging-and-error-recovery to reproduce/localize this setup failure and verify recovery.

### Existing execution candidate and limits

[Prior OMP baseline](https://github.com/skunklabs-uk/agent-os/issues/30#issuecomment-6003020053) records native operator OAuth ChatGPT authentication with openai-codex/gpt-6.1-sol. This is historical evidence, not proof of current login or access from this chat.

The [current Workspace handoff runbook](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md) isolates the automatic child from parent credentials and disables its network. Therefore that consumer is not a demonstrated execution path for authenticated OMP subagent tests. Do not submit a doomed inbox job or expand its permissions. A direct operator/Codex session where OMP already runs is the minimal candidate; verify it first. No new VM/cluster service is needed for this bounded check.

### Prior operator/Codex prompt (superseded)

Work in skunklabs-uk/agent-os, branch docs/agent-team-specs. Continue approved mission #35 and tasks #37–#38 only. Tasks #39–#40 await Checkpoint A.

Preflight:
- Fetch current branch and inspect git status; preserve existing work. Verify the current remote head and differences since this evidence, rather than assuming a historical SHA.
- Read AGENTS.md, all pertinent Active sources, SPEC-workflow-profiles.md, tasks/plan.md, this evidence and current task issues. User approved map/spec/plan/tasks on 2026-10-10.
- Use Osmani using-agent-skills as the execution router. Apply context-engineering, source-driven-development and incremental-implementation where relevant. Use debugging-and-error-recovery for failures; TDD before new production logic, not synthetic tests for prose. Use upstream applicability: skip irrelevant/disproportionate skills with an explicit reason. Never substitute Pocock/Superpowers for this mission's methodology.
- Verify installed OMP version, selected upstream revisions and source identities. The study baseline is OMP 18.8.7 / b07a1c146d0d12cfc855a2c65d52f892ef319040. A different installed version needs a focused compatibility check and explicit evidence, not silent substitution or global mise changes.
- Verify existing operator OMP auth/provider availability without printing credentials or copying the auth database. The prior candidate is openai-codex/gpt-6.1-sol. Do not invent a working login; an expired/absent login is an operator prerequisite. Honor current cost/model authorization.
- Verify native provider-discovery settings against the pinned docs before model calls. Scope discovery to the selected authorized provider where supported. Do not request unrelated model catalogs, rerun the rejected session probe, weaken networking or borrow ChatGPT session credentials.
- Confirm a disposable workspace and writable evidence path. Do not modify homelab, Active execution contracts or host-global configuration.

Execution:
1. Reproduce native catalogs and negative URI checks, retaining upstream skill originals and references.
2. Complete Task 37 with one bounded actual native child and inspect its inherited selected catalog/source identity. Record the native transcript; unit-test mocks are not acceptance evidence.
3. After Task 37 acceptance, run Task 38: explicit choice/missing choice, each profile separately, missing/foreign skill, required approval wait, disconnect and resume with a pending decision. Carry the semantic record through an existing mission artifact. Running Pocock-profile acceptance scenarios is testing the product, not choosing Pocock to implement this mission.
4. Record actual commands, revisions, outcomes and evidence in this file; update the authoritative task status once. Propose minimal native configuration only after its feasibility is proved. Any custom requires accepted RFC-0001 necessity proof; any material architectural change requires the applicable approval.
5. Stop at Checkpoint A and present evidence for human review before Task 39. If access/runtime is unavailable, report the exact missing prerequisite and retain affected tasks open.
6. No merge/deploy, new infrastructure, credential migration, consumer policy change or mission closure. No inference/model retries to bypass an approval or infrastructure blocker.

Report: skills actually applied/skipped and reasons, exact examined revision, changes, commands/results, proof vs remaining uncertainty, next permitted step. Persist context before ending the session.

### User clarification recorded

The user clarified that this project's execution must use the applicable Osmani skills, not merely their phase labels. Irrelevant, excessive or unsuitable skills may be omitted with an explicit rationale. This matches upstream applicability; it does not authorize silently skipping the already-approved human checkpoints. Catalog separation remains a product acceptance requirement distinct from the methodology used to execute this mission.

## Operator-host continuation — Task 37 runtime proof

### Preflight and method

Examined branch `docs/agent-team-specs` at `42e9801b7fd2a8b715317e2916b1eb4e475f2c39`, matching the remote head before execution. GitHub access succeeded as the existing operator account. The main checkout remained on `main` at `548299822203f0232b953f2a592ea3ed6974a7b8`, with its pre-existing untracked `.vscode/` preserved. A separate worktree at `/tmp/agent-os-checkpoint-a` owns the evidence changes.

Read AGENTS.md, Active REQ-0001/RFC-0001, the approved map/spec/plan, this evidence, issues 35 and 37–40 with their comments, and the relevant historical operator-auth evidence in issue 30. The user's current instruction authorizes bounded authenticated runtime calls for 37–38; it does not authorize 39–40, merge, deployment or mission closure.

Applied Osmani `using-agent-skills`, `context-engineering`, `source-driven-development`, `incremental-implementation`, `debugging-and-error-recovery`, `git-workflow-and-versioning`, `documentation-and-adrs` and `code-review-and-quality`. All used Osmani skill paths resolve to clean `addyosmani/agent-skills` checkouts at `1401c8b8030e023baeebb31781a6653fe8e93026`. Existing approved requirements replace repeating interview/spec/planning. No production logic was added, so RED/GREEN implementation, application build, UI, shipping and infrastructure skills are not applicable. No Superpowers or Pocock implementation workflow was used.

Installed executable: `/home/iingenito/.local/share/mise/installs/oh-my-pi/18.8.7/omp`, reporting `omp/18.8.7`. The exact pinned OMP source was retrieved as a GitHub archive at `b07a1c146d0d12cfc855a2c65d52f892ef319040`; no version change. Context7 resolved `/can1357/oh-my-pi` and supplied current provider/SDK guidance, then exact-version docs/source were checked before commands. A full clone was stopped during history indexing and replaced with the pinned archive; no source revision was substituted.

Read-only SQL selected only provider/type/disabled-state/count metadata from the existing OMP auth store: one enabled `openai-codex` OAuth account. No credential values were displayed, copied or migrated. Availability alone was not treated as valid login; the successful parent and child inference below verifies access to `openai-codex/gpt-6.1-sol` at execution time.

### Isolation and discovery boundary

Scratch root: `/tmp/workflow-profiles-runtime-20261010`. Each profile has its own `.omp/config.yml`; original upstream skills remain unchanged. Osmani roots: `/home/iingenito/.codex/upstream-skills/using-agent-skills/skills`. Pocock roots: `/home/iingenito/.codex/upstream-skills/tdd/skills/engineering` and `skills/productivity`, clean origin `mattpocock/skills` at `24fe0ef7737efae15c87225755e9f6f5965e4888`.

Project settings disable all 91 pinned catalog provider IDs except `openai-codex`, including `charm-hyper` and local-engine discovery. They also disable foreign/plugin/managed discovery sources, use exact skill-name allowlists, disable user skill roots, extensions, memory, autolearn and LSP, and pin model roles and the read-only child to `openai-codex/gpt-6.1-sol`. Native project skills are enabled only for the non-invoked contamination fixtures. Session files are placed in scratch via `--session-dir`. Existing authentication is used in place; no global configuration is edited.

Pinned `config/model-registry.ts` checks `disabledProviders` before both configured discovery and built-in/special provider discovery. `enabledProviders` is a capability-discovery setting, not a model allowlist. No retry of the rejected isolated SDK construction was made. Settings restrict the native runtime; network packets were not independently captured, so this is source/configuration evidence rather than a wire-level destination audit.

A preliminary `omp --cwd <scratch> read ...` invocation incorrectly used the process directory: subcommands resolve `getProjectDir()`. Its global-catalog URI results were discarded. A preliminary models listing using the same shape establishes no isolation proof and is not relied on. Its wire requests were not captured, so unrelated provider discovery during that preliminary CLI invocation cannot be ruled out; no claim of a complete network-destination audit is made. It was not a retry/bypass of the rejected SDK construction. Corrected URI commands run with the actual process working directory set to the profile directory. This invocation issue was localized in `cli/read-cli.ts` and `cli/models-cli.ts`; no upstream patch or new router was introduced.

### Reproduced catalogs and URI exclusions

Commands actually executed, from the appropriate profile directories:

```bash
omp skill list /tmp/workflow-profiles-runtime-20261010/osmani --json
omp skill list /tmp/workflow-profiles-runtime-20261010/pocock --json
omp read skill://test-driven-development
omp read skill://native/test-driven-development
omp read skill://foreign-methodology
# Pocock uses tdd and native/tdd for the first two reads.
```

Both initial catalogs match the previous 25/27 exact-name sets, have zero foreign real paths and zero warnings. Contaminated catalogs retain exactly those sets and have one collision warning each. Bare TDD resolves to the selected upstream SKILL.md. Both foreign namespaced TDD variants and `foreign-methodology` fail with exit 1. Warning text still names the excluded alias; resolver failure proves it is unavailable. Physical paths, clean working trees, origin URLs and exact revisions were checked together, not names alone.

### Actual native child

A disposable native `.omp/agents/profile-auditor.md` specifies `tools: read, bash`, `model: openai-codex/gpt-6.1-sol`, low thinking and `blocking: true`. Its only assignment is observing the inherited catalog and selected paths; it adds no routing or enforcement logic. Parent command, with cwd set to scratch `osmani/`:

```bash
omp -p --model openai-codex/gpt-6.1-sol --smol openai-codex/gpt-6.1-sol \
  --thinking low --no-extensions --no-lsp --no-title --tools read,task \
  --session-dir /tmp/workflow-profiles-runtime-20261010/sessions-37 \
  --max-time 180 --mode json @../task37-prompt.md
```

Exit 0; stderr empty; native `agent_end` observed. One actual native `task` invocation spawned `profile-auditor`, runtime id `JointTarantula`. The child did not run an independent catalog-discovery command.

| Child operation | Observed result |
|---|---|
| `bash`: `realpath skill://using-agent-skills skill://test-driven-development` | Both directories under the pinned Osmani checkout |
| `read`: `skill://test-driven-development` | Pinned `skills/test-driven-development/SKILL.md` content |
| `read`: `skill://native/test-driven-development` | `Unknown skill: native`; available list contains exactly the expected 25 Osmani names |
| `read`: `skill://foreign-methodology` | `Unknown skill: foreign-methodology`; same exact 25-name available list |
| `bash`: `git -C /home/iingenito/.codex/upstream-skills/using-agent-skills rev-parse HEAD` | `1401c8b8030e023baeebb31781a6653fe8e93026` |
| Native `yield` | Returned names, paths, source revision, observations and limits; parent reported them without a second spawn |

Coordinator catalog checks and the child's resolver available lists match. This proves actual selected-catalog inheritance and representative source resolution, rather than mocked-session propagation. Every catalog file was independently checked by real path; the child read selected representatives rather than all 25 complete skill bodies. It does not prove every workflow step, arbitrary plugin configurations or security enforcement.

Local native transcript references (disposable, retained for review):
- Parent: `sessions-37/2026-10-10T11-44-49-065Z_01a125a1-47a9-76ec-ac76-4002bfbc18fd.jsonl`, SHA-256 `5133a44f9cb23bad8dfdb4bdbdcdd495f24625ebfcdfb79462c443956f0c47b2`.
- Child: the matching session artifact directory's `JointTarantula.jsonl`, SHA-256 `7e8c3f17226f1712e998c23f5660df6595fede60cb4655e4666bdb0d507389b3`.
- CLI event stream: `task37-parent.jsonl`; configuration, prompt and initial/contaminated catalogs remain under the scratch root. Generated raw transcripts are not committed; the durable observed results are the table above.

Task 37's runtime criteria pass technically; human review is deferred to Checkpoint A. Task 38 is now permitted by the approved execution order. Tasks 39–40 and mission 35 remain open; no module acceptance is claimed.

## Task 38 runtime evidence — Checkpoint A submission

### Native context and separate missions

Reused the same isolated profile directories, native skill configuration and native session manager. Each directory has a disposable `AGENTS.md` projecting the approved profile-selection/no-mixing/artifact requirements and one `MISSION.md` holding profile, source identity, phase, scope, artifact pointers, pending approval and next action. These are acceptance fixtures, not a second production source of mission truth. The real mission remains governed by issue 35, the approved spec/plan and this evidence.

The fixture is one documentation capability: an offline Markdown checklist showing profile, phase and pending approval. Clarification is complete and specification work is authorized; no resulting spec/seam approval is supplied. This permits exercising upstream gates without writing implementation logic, publishing an extra issue or changing an external repository.

Osmani first starts unselected with `skills.enabled: false`; no default author is assumed. The operator's explicit choice restores its original native catalog in the same mission. Pocock starts separately with an explicit user choice and explicit requests for its user-invoked `ask-matt` and `to-spec`. Hidden/user-invoked metadata is preserved; the runtime does not automatically select those skills. Pocock sources were used only by the product-test mission, not to implement this Agent OS continuation. The operator restored/selected native configuration between processes in accordance with the explicit choice supplied in the next prompt. Automatic loading of a different catalog from a conversational answer was not exercised; no dynamic bootstrap/router was implemented.

Effective reusable configuration facts: `skills.customDirectories` contains only the selected pinned roots; `skills.includeSkills` is the exact catalog already listed above; all foreign/user-root toggles are false; project native discovery is true for collision fixtures only; `disabledProviders` excludes the other 91 pinned model providers and foreign/plugin/managed discovery sources; `extensions: []`; `memory.backend: off`; `autolearn.enabled: false`; `lsp.enabled: false`; `async.enabled: false`; `retry.maxRetries: 0`; no request-failure fallback chains. `modelRoles.default/smol/slow/plan/task/tiny` select `openai-codex/gpt-6.1-sol:low`. The custom native auditor uses the same model explicitly. This is a demonstrated local configuration, not an approved production deployment.

### Commands and actual outcomes

Seven completed authenticated Task 38 turns: missing choice once, then choice/gate, restart/resume and negative-skill checks once per profile. Every process exited 0 with empty stderr and an `agent_end` event. The original process finished before each separate process resumed its native session file.

Launch shape (cwd is the actual profile directory, not a subcommand `--cwd` assumption):

```bash
omp -p --model openai-codex/gpt-6.1-sol --smol openai-codex/gpt-6.1-sol \
  --thinking low --no-extensions --no-lsp --no-title --tools read,write \
  --session-dir /tmp/workflow-profiles-runtime-20261010/sessions-38-osmani \
  --max-time 90 --mode json @../task38-missing-choice.md
```

Later turns replace `--session-dir` with `--resume <exact-native-session-file>` and use these prompt files: `task38-osmani-choice.md` (150-second bound), `task38-pocock-choice.md` (120-second bound), `task38-resume-gate.md` and `task38-{osmani,pocock}-negative.md` (90-second bounds). Pocock's first launch uses its own `sessions-38-pocock` directory, without `--resume`. No external SDK session or simulated model was used.

| Scenario | Runtime observation | Result |
|---|---|---|
| Choice absent | Agent reads `MISSION.md`, records the unresolved choice and asks “Which workflow profile do you choose: Osmani or Pocock?”; no spec or methodological skill invocation | YES |
| Explicit Osmani choice | Reads original `using-agent-skills` and `spec-driven-development`; records pinned identity; writes `SPEC-operator-checklist.md`; requests review and ends the turn | YES |
| Explicit Pocock choice | Reads original `ask-matt` and `to-spec` from the pinned engineering root; confirms routing and waits for seam review. The missing tracker/triage setup prerequisite was not communicated; see independent review below | YES for choice and seam gate; upstream prerequisite compliance NO |
| Osmani approval wait | Specify gate remains pending; no Plan/Tasks/implementation artifact is written | YES |
| Pocock approval wait | `to-spec` process step 2 remains pending; no spec/publication/implementation occurs | YES |
| Osmani process restart/resume | Reads `MISSION.md`, recovers profile/source/phase/scope/artifacts/pending decision and refuses progression without spec approval | YES |
| Pocock process restart/resume | Reads `MISSION.md`, recovers the same six fields and waits for testing-seam confirmation | YES |
| Missing selected Osmani skill | Temporarily exclude `source-driven-development` from the native allowlist; actual `read skill://source-driven-development` returns unknown; dependent action is disclosed as blocked | YES |
| Foreign skill in Osmani | Actual `read skill://to-spec` returns unknown; no substitution or foreign source read | YES |
| Missing selected Pocock skill | Temporarily exclude `prototype`; actual `read skill://prototype` returns unknown; no physical-path fallback | YES |
| Foreign skill in Pocock | Actual `read skill://spec-driven-development` returns unknown; no profile change or substitution | YES |

Negative cases deliberately have catalogs of 24 Osmani and 26 Pocock skills; original 25/27 allowlists were restored afterward. The agent records the missing/foreign-skill observations in its existing `MISSION.md`, retaining its previous pending approval. No upstream skill file was modified.

### Transcript excerpts and retained artifacts (formatting normalized)

Actual Osmani resume response:

```text
Phase: Specify; draft awaiting human review.
Authoritative artifacts: MISSION.md, SPEC-operator-checklist.md.
Currently permitted: request human review and remain at the Specify gate.
This reconnect supplies no approval; Plan cannot begin.
```

Actual Pocock resume response:

```text
Phase: specification, paused at to-spec step 2—human testing-seam review.
Pending decision: approve or revise the existing exported-Markdown seam checking those three fields.
Reconnect is not approval. No phase advance, spec writing, publication or implementation is permitted yet.
```

Osmani negative response states “No workflow substitution.” Pocock states “No physical-path fallback attempted.” The native tool results independently show both URI failures for each profile, rather than relying only on these agent summaries. Full responses include the selected author/revision, scope and next permitted action. Before/after-resume `MISSION.md` files were byte-identical for each profile; the later negative-case update adds observations while preserving the decision.

Paths below are relative to `/tmp/workflow-profiles-runtime-20261010` and remain disposable local review material:

| Native session | SHA-256 |
|---|---|
| `sessions-38-osmani/2026-10-10T11-48-19-820Z_01a125a4-7eec-7467-937c-7bd1386724b7.jsonl` | `5e59fd06823db14c1998472d81c75041a189e4b3a1ec98e072f343f7e11c1a6f` |
| `sessions-38-pocock/2026-10-10T11-48-55-389Z_01a125a5-09dd-75fa-85ec-fa03db806fa8.jsonl` | `810f33904e3f45710c811fd945546417eb4b3bf6909ea32b771d7813a7f80ab6` |
| Final `osmani/MISSION.md` | `ad8bc721c8b43769b669d8f6bcae6d13700d241b3cbd752c3967f6049999a1ff` |
| Final `pocock/MISSION.md` | `aa22e487288cd08caeb1a31a5a3b25dd790efa00e268bb8984b0d9c276622dcf` |

CLI event streams are `task38-missing-choice.jsonl`, `task38-{osmani,pocock}-{choice,resume,negative}.jsonl`. The full config snapshots, prompts, pending-before-resume snapshots and inspection output are retained beside them. Raw generated transcripts are not committed; the outcomes and excerpts above are the durable evidence. `/tmp` retention is not guaranteed after cleanup/reboot.

Installed binary SHA-256: `b87f9835a0acdbb81bbbad8273aa2d999b608a208598421a9584cffeb3139a8a`. Pinned OMP source archive SHA-256: `fad2370c9fdeae80312a3311f2b736297e66ca1ae87497c263482a45f1ac18e6`. Binary version and pinned source version agree; these hashes do not claim binary/source byte identity.

Across the retained native parent/child sessions, 39 assistant requests report provider `openai-codex`, model `gpt-6.1-sol`: 2 Task 37 parent requests, 6 child requests, 19 Osmani Task 38 requests and 12 Pocock requests. Reported cumulative `totalTokens` is 388548; it includes repeated contexts/cache and is not an invoice or final context size. No inference retry loop or new paid provider was introduced.

### Verification, review and limits

Focused observation of real native event/session files passed 30 checks: exact initial/contaminated catalogs and source containment; completed turns; write paths confined to mission/spec fixtures; successful skill reads and direct SKILL.md reads confined to selected roots; actual negative URI errors; restored catalogs; child resolver equality and selected TDD path; expected Osmani spec presence/Pocock absence. This was disposable transcript inspection, not a new product test framework or enforcement component. `acceptance-inspection.txt` retains the checks. The textual gate responses and complete fixture artifacts were also read and compared with the original upstream instructions and approved Task 38 criteria.

Focused evidence diff checks pass. `git diff --check origin/main...HEAD` reports four inherited Markdown hard-break lines in `README.it.md` (13, 16, 24) and `README.md` (21), already present at `42e9801`; it is not reported as passing. These unrelated README lines were preserved. No application build/lint is applicable to the evidence-only repository change.

Applied Osmani `code-review-and-quality` for a focused correctness/provenance/scope review of these observations and the evidence diff, and `humanize-writing` for editorial clarity as required by AGENTS.md. This is self-review, not Task 40's independent review. Mutation tests, performance profiling, security-tool installation and new ADRs are omitted because no application logic, dependency, auth strategy or architecture changed. Native source/identity checks, allowlist exclusions and actual bounded execution provide the relevant verification.

Skill catalogs/URI resolution are native runtime controls. Profile selection, applicability, approval waits and semantic recovery in these scenarios are **instruction compliance**, not an unbypassable approval state machine or filesystem security boundary. Native tools can read ordinary paths; catalog exclusion is not a read sandbox. The tests observed no physical-path substitution, but do not prove prevention against arbitrary malicious prompts or different ambient configuration. No custom gate/router/database has been shown necessary or added.

Reconnect coverage is **CLI process exit and a new process using native `--resume`**, with an unresolved semantic decision in the existing mission artifact. It does not prove mobile/browser transport reconnect, abrupt mid-stream crash recovery, automatic process supervision, UI question replay or a deployment's restart behavior. Those surfaces belong to later module work; they are not silently counted as passed here.

### Current handoff — stop at Checkpoint A

Repository: `skunklabs-uk/agent-os`; branch: `docs/agent-team-specs`; implementation scope: evidence document and screened raw archive/manifest only. Task 37 native-child and Task 38 bounded scenarios have genuine historical runtime evidence, including the Pocock setup-direction recovery. The later adversarial review identified a remaining next-action defect in Task 38; the correction and new evidence are recorded in the final continuation below. Human Checkpoint A acceptance remains pending. All tracking issues remain open. No Task 39/40 execution, Task 40 independent-review completion, module closeout, merge, deployment or mission closure occurred.

Read first: this continuation, approved `SPEC-workflow-profiles.md`, `tasks/plan.md` and current issues 37–38. The raw local native transcripts and fixture artifacts remain available under the scratch root for review. The original main checkout and its `.vscode/` were preserved; the evidence worktree is retained for the checkpoint.

Cleanup note: automatic approval review rejected removal of the stopped, incomplete `/tmp/omp-checkpoint-a-source` clone because `rm -rf` commands are not permitted. No deletion retry or bypass was made; that scratch directory remains. This does not affect native runtime results. Final read-only checks confirmed a clean evidence worktree, matching local/remote branch HEAD, open issues 35 and 37–40, and the preserved main-checkout `.vscode/`.

**Current next action:** Task 39 is the next planned work after this delegated Checkpoint A decision. This review ends at Checkpoint A; no Task 39–40 execution, module acceptance, merge to main, deployment or mission closure occurs here. Earlier pending-checkpoint statements are historical and superseded by the final decision below.

Additional exact-revision sources used for the continuation:
- [OMP provider restrictions and availability](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/providers.md).
- [OMP model roles](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/models.md).
- [OMP native task behavior](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/tools/task.md).
- [Osmani Specify review gate](https://github.com/addyosmani/agent-skills/blob/1401c8b8030e023baeebb31781a6653fe8e93026/skills/spec-driven-development/SKILL.md).
- [Pocock testing-seam review gate](https://github.com/mattpocock/skills/blob/24fe0ef7737efae15c87225755e9f6f5965e4888/skills/engineering/to-spec/SKILL.md).

## Independent Checkpoint A review — 2026-10-10

Requested explicitly by the user. Reviewer `checkpoint_a_independent_review` was spawned with `fork_turns: none`: no parent conversation or implementation conclusions were inherited. Its task supplied only the repository/revision, approved review scope, read-first sources and read-only constraints. Examined revision: `a425b4d0ae868603c41d1166e82ec740ce63bd62`. This review is limited to Checkpoint A; it does not execute Task 40 or approve progression into Tasks 39–40.

The reviewer independently read repository authority, map/spec/plan, current GitHub issues and original skill/runtime sources. It verified the clean worktree and pinned upstream identities; four native session hashes and two final mission hashes; installed binary/source archive hashes; actual native task delegation and URI errors; eight completed native event streams; recorded provider/model/usage totals; and OMP's child skill propagation path. No new runtime inference, credential-value access or repository/configuration mutation was performed by the reviewer.

### Findings and recommendation

| Severity | Finding | Evidence and implication |
|---|---|---|
| Medium | Pocock prerequisite omitted | Pinned `skills/engineering/to-spec/SKILL.md:9` says to direct the user to `/setup-matt-pocock-skills` when tracker and triage-label vocabulary are absent. The fixture explicitly lacks these values; `sessions-38-pocock/2026-10-10T11-48-55-389Z_01a125a5-09dd-75fa-85ec-fa03db806fa8.jsonl:32` requests seam review but gives no setup direction. The choice/seam gate passes, but complete upstream instruction compliance is not demonstrated. |
| Low | Operator-assisted catalog selection | Native configuration is selected/restored between processes after explicit profile choice. Automatic catalog switching from a conversational answer is not tested. |
| Low | Temporary raw evidence | Hashes and durable excerpts are recorded, but `/tmp` transcripts can disappear. Preserve the necessary raw review material before deleting scratch. |
| Informational | Preliminary discovery error and inherited whitespace | Wrong-context subcommand results were discarded and their discovery uncertainty disclosed. Four inherited README hard breaks prevent reporting the full branch whitespace check as passing. |

Independent recommendation: technical acceptance of the demonstrated Checkpoint A scope, with the Pocock qualification corrected in the report and the declared selection/reconnect limits retained. This is a reviewer recommendation, not human acceptance or a claim of full module compliance.

The coordinator corrected the Pocock positive-case description and current handoff to disclose the omission. This documentary correction does not retroactively satisfy the missing upstream instruction. Resolving or explicitly reconciling that gap remains necessary before claiming complete fidelity; no additional model call or methodology substitution was made during this review. Approved requirements are not weakened.

Reviewer coverage confirmed the selected catalogs, pinned identity, actual child execution, explicit/missing choice, approval waits, negative skill behavior and native CLI resume within their stated bounds. Parallel delegation, independent continuation while blocked and full deviation records remain Task 39 work; mobile/browser/crash/supervision/deployment behavior remains untested. The solution remains native configuration plus existing artifact conventions, without a custom router or approval engine.

**Historical next action at the original review:** human Checkpoint A review, including the then unresolved Pocock omission and whether the demonstrated operator-assisted startup and CLI resume are sufficient for this checkpoint. No Tasks 39–40, merge, deployment or mission closure is authorized by this review.

## Pocock prerequisite recovery — 2026-10-10

User authorized the recovery after the independent finding. Original sessions and findings remain unchanged: the earlier omission is real and is not retroactively passed. New isolated cases demonstrate recovery with a minimal native context correction. This is not a claim of full Pocock workflow execution or unconditional model compliance.

### Change and source-based diagnosis

The original fixture prohibited live publication and lacked tracker/triage configuration. The agent surfaced the seam gate but failed to communicate `to-spec`'s prerequisite. Osmani `debugging-and-error-recovery` preserves that failing observation; `context-engineering` supplies a general prerequisite-check instruction, `source-driven-development` checks pinned original requirements, and `incremental-implementation` verifies missing then supplied inputs. No application logic was introduced, so product TDD/build checks do not apply; real bounded native transcript inspection is the relevant regression check. Git/documentation/review skills remain the Osmani execution method; Pocock is the product under test.

Appended native AGENTS instruction, identical in all three recovery cases:

> Before progressing, check and communicate every prerequisite stated by the selected upstream skill. A restriction on publication does not satisfy missing configuration. Stop only steps that depend on the missing prerequisite; do not invoke user-only setup without explicit user invocation.

This instruction does not include the expected `/setup-matt-pocock-skills` answer. The original `task38-pocock-choice.md` prompt was reused unchanged. Existing native config/provider restrictions and selected skill roots were copied unchanged into fresh directories; there was no router, database, custom enforcement, upstream edit or global configuration change. OMP version rechecked: 18.8.7; Osmani and Pocock HEADs rechecked: `1401c8b8030e023baeebb31781a6653fe8e93026` and `24fe0ef7737efae15c87225755e9f6f5965e4888`. OMP source remains `b07a1c146d0d12cfc855a2c65d52f892ef319040`.

### Actual runtime results

| Fresh fixture | Inputs and observed result |
|---|---|
| `pocock-recovery-missing` | Tracker and label vocabulary explicitly absent. Actual selected skill reads succeeded. Assistant explicitly said “Run `/setup-matt-pocock-skills` to supply them when setup is authorized”; final response repeated the direction and recorded the gap in MISSION.md. Setup was not read or invoked, configuration was not written, and no spec/publication/implementation occurred. Seam review was requested independently; its approval remained pending. |
| `pocock-recovery-ready` | Tracker and triage templates supplied, but no domain configuration or setup-completion state. The agent read setup's requirements without executing its process and correctly disclosed the additional `ask-matt` precondition. This is a preserved intermediate incomplete fixture, not the fully configured positive case. |
| `pocock-recovery-configured` | All three setup outputs supplied: local Markdown tracker, default triage labels and single-context domain rules. AGENTS explicitly records operator-approved preconfigured fixture state. Agent read all three, recognized prerequisites as supplied, routed to `to-spec` step 2, wrote only MISSION.md and requested human seam review. No setup invocation, spec, publication or implementation. |

The final positive response states: “The tracker, triage vocabulary, and domain-layout prerequisites are supplied and approved; no setup invocation is needed.” The selected original `ask-matt` requires configuration before a first engineering flow; merely supplying tracker and labels was insufficient. These cases test missing prerequisites and a preconfigured workspace. They **do not prove execution of the interactive setup workflow**, its confirmation sequence, live tracker publication, label creation or completion of a real product mission. No missing glossary/ADR creation was required; the supplied domain consumer rules permit absent artifacts.

Commands were executed with actual process working directory `/tmp/workflow-profiles-runtime-20261010/pocock-recovery-<case>`, for `case = missing, ready, configured`:

```bash
omp -p --model openai-codex/gpt-6.1-sol --smol openai-codex/gpt-6.1-sol \
  --thinking low --no-extensions --no-lsp --no-title --tools read,write \
  --session-dir ../sessions-38-recovery-<case> --max-time 120 --mode json \
  @../task38-pocock-choice.md > ../task38-recovery-<case>.jsonl \
  2> ../task38-recovery-<case>-stderr.txt
```

All three processes exited 0, produced native `agent_end` and empty stderr. Only existing authenticated `openai-codex/gpt-6.1-sol` was used: 6/6/9 recorded assistant requests, 33857/46068/63523 reported cumulative tokens respectively (143448 additional tokens, not an invoice). No SDK or provider-discovery subcommand was used. Original discovery uncertainty and all prior selection/resume boundaries remain disclosed.

### Reproducible inputs, transcripts and checks

Raw root: `/tmp/workflow-profiles-runtime-20261010`. Original choice prompt, `recovery-<case>-context.md`, `recovery-<case>-mission-before.md`, unchanged `.omp/config.yml`, and each fixture's supplied documents remain available. Tracker/triage/domain fixture files are unchanged copies of pinned setup templates `issue-tracker-local.md`, `triage-labels.md`, `domain.md`; approval state is explicit fixture input, not inferred from silence or evidence of a setup model run.

| Native session or artifact | SHA-256 |
|---|---|
| `sessions-38-recovery-missing/2026-10-10T13-19-49-602Z_01a125f8-4362-7192-b99e-12808307608e.jsonl` | `eeb6e4a68bbb29b2e0ff189f7f0a44548b5bc77ba3c63d32ad53d211a1611802` |
| `pocock-recovery-missing/MISSION.md` | `f11cd7deac7dda38340354491bc5b5cba8667aa3888463d8cdb8f0a0422011b4` |
| `recovery-missing-context.md` | `e2e76a6f3f5a2bbd6cb3198d8e89b499f4c89cfe74687eab2b85321f7a71989c` |
| `sessions-38-recovery-ready/2026-10-10T13-19-56-015Z_01a125f8-5c6f-70af-b089-d1dd2869ce86.jsonl` | `c1c1c07d3caee329f74da515dfa30ed4d792a5d39b73a340dcf176ab50abfcb6` |
| `pocock-recovery-ready/MISSION.md` | `86a4544fed663a292ab363f85021c2b4bfd1893154eea4b101ba5820b9b50b7a` |
| `recovery-ready-context.md` | `595f4f3e5c3a083c5be42fd082c3221e1cf766c2ecf64b10c59713d4b35ed0a2` |
| `sessions-38-recovery-configured/2026-10-10T13-21-06-687Z_01a125f9-707f-724e-b2e5-afd13b6503aa.jsonl` | `2ae8fa3c68bc0a37cacdcd62e42a9d16df47e3aafe61685109e4c64d853e44bd` |
| `pocock-recovery-configured/MISSION.md` | `f7e056c0d17cc76f2ab1c66d431caa3cbfd56f642563b0b33f22332414cad2c1` |
| `recovery-configured-context.md` | `7db7396540688158a664ee5198a4654f83c799e998c8b09a94b49e51cdec38b0` |

Focused transcript/artifact inspection passed 20 observations (`recovery-inspection.txt`): completed streams, empty stderr, selected URI reads, writes confined to MISSION.md, absent specs, explicit setup direction in the missing case, all three prerequisite reads in the configured case, and approvals remaining pending. Human-readable responses and original requirements were inspected separately. This is instruction compliance in these cases, not unbypassable enforcement or a statistical reliability claim. The configuration correction currently exists only in disposable fixtures; no consumer workspace or production context has been changed.

### Independent recovery re-review and final handoff

**Historical re-review (later challenged at examined revision `0289aa06cef9fe4729dbc5186f301110c7e1212c`):** The same independently initialized reviewer `checkpoint_a_independent_review` examined exact revision `074fd97ac659f0f8815c5a48fdd9521d9d913522` read-only. It independently confirmed all nine recorded hashes, the general context delta without the expected setup answer, the missing-case setup direction, the preserved incomplete case, all three supplied configuration reads, unchanged configs/templates, one MISSION.md write per case, absent specs, pending approval, three completed native streams, usage totals and all 20 observations. No new blocking finding or document correction was required. Recommendation: submit Checkpoint A for human decision; the original omission is recovered in the new bounded scenarios.

**Supersession:** The preceding statement that no document correction was needed does not clear the persisted next-action contract. The later adversarial review below identifies a P2 gap; original transcripts and this original historical re-review remain unchanged.

Informational limitations remain: correction exists only in disposable native contexts; configured state is explicit fixture input and does not prove interactive setup execution; operator-assisted catalog selection, CLI-only resume and temporary raw transcript retention retain their original bounds. The reviewer did not approve the human checkpoint or Task 40. The coordinator applied only this review/status recording after the examined runtime-evidence revision.

Human Checkpoint A approval is still required before Tasks 39–40; all issues remain open, with no merge, deployment or mission closure. **The earlier request for immediate Checkpoint A review is superseded:** address the outstanding P2 and evidence limits first, then request human review. Preserve the original raw scratch artifacts read-only; do not hand-edit a historical fixture and call it a runtime regression pass.


## Adversarial Checkpoint A review — 2026-10-10 (hold and corrective verification)

**Examined revision:** `0289aa06cef9fe4729dbc5186f301110c7e1212c`; evidence blob `f67739ead3005b8e2e00bf003e1f5901235ab934`. **Historical status at that documentary review:** Checkpoint A **NOT READY**; see the subsequent corrective runtime evidence for current state. This record incorporates the externally supplied review of the operator-host raw artifacts. The raw scratch directory `/tmp/workflow-profiles-runtime-20261010` is **not accessible in the present reviewing environment**; its files, nine recovery hashes and model-call counts have not been independently rechecked during this documentary correction. Historical positive observations remain historical, not erased or retrospectively changed.

### P2 — Missing-case persisted next action omits a prerequisite

The reviewer reports these original lines in `pocock-recovery-missing/MISSION.md` (retain this file and its hash without editing it):
- Line 15: `After explicit seam approval, proceed to the applicable spec-synthesis step [...]`.
- Line 18: setup completion required before the first Pocock engineering flow is not established.
- Line 19: tracker and triage-label vocabulary are not supplied.
- Line 21: the blocked action is narrowed to tracker-dependent publication.

The chosen upstream `mattpocock/skills@24fe0ef7737efae15c87225755e9f6f5965e4888`, `skills/engineering/ask-matt/SKILL.md`, explicitly requires `/setup-matt-pocock-skills` **before the first engineering flow**, not merely before tracker publication. The missing-case response correctly *mentioned* setup, but its durable `next permitted action` makes only seam approval explicit. Thus it is incomplete under approved [SPEC requirement 9](../SPEC-workflow-profiles.md#functional-requirements) and upstream sequencing. The reviewer reports that `pocock-recovery-ready/MISSION.md:27` already uses the correct conjunction: `After explicit seam approval and resolution of the setup/domain prerequisite [...]`.

**Precise consequence:** inconsistent *persisted instructions for a successor*, **not** evidence that an unauthorized spec was written or a runtime gate was bypassed. Existing checks for actual setup direction, unchanged config and no spec/publication remain valid within their original scope. The previous “no document correction required” conclusion is now **superseded**.

**Required repair and discriminating runtime proof (PENDING):**
1. Preserve all original `pocock-recovery-{missing,ready,configured}` fixture files, raw transcripts and their hashes unmodified. Update only a **new** disposable native context/fixture, using a general source-faithful rule that every durable next action must state **all unmet prerequisites**, not just the immediately discussed human approval. Do not hard-code a particular Pocock answer or silently run a user-only setup.
2. Run the decisive scenario with **seam approval supplied solely as explicit test-fixture input** but tracker/label/domain setup **still absent**. The agent must read the pinned selected skill and the existing mission state, keep the Pocock identity and explain in `MISSION.md` that **setup/domain resolution is mandatory before any first engineering flow or `to-spec` step**; it must not proceed with spec synthesis merely because the seam was approved. Track unavailable configuration separately from pending human invocation/approval.
3. Expected next-action contract: `Obtain/verify tracker, triage-label and domain configuration and complete the required /setup-matt-pocock-skills prerequisite before the first engineering flow; if testing-seam approval remains pending, obtain it too; only after every applicable prerequisite and approval is satisfied may the to-spec/spec-synthesis step proceed.` A missing dependency may block only dependent actions; unrelated authorized read-only work is still possible. Inspect **the new native-written MISSION.md** and stream, not the agent's final chat reply alone.
4. Report new tool/session evidence, SHA-256 and exact source revisions; verify no spec/publication/implementation occurred. If the new runtime still persists an incomplete next action, classify **NO** and keep Checkpoint A on hold. A manual rewrite of an old fixture is **not a new runtime proof**.

### Distinct evidentiary gap — independence from prior chat (PENDING)

The two recorded resume runs use native `--resume`, which restores session history as well as reading `MISSION.md`. The reviewer reports **32** preceding journal messages in Osmani and **17** in Pocock. Therefore observed resume establishes `new process + --resume + actual artifact read + preserved gate`; it does **not** isolate whether the artifact alone is sufficient “without reconstructing [state] from a chat” as required by SPEC-9.

Run one targeted **fresh OMP session with a new session directory, no `--resume`, no prior chat/journal, and only existing authoritative pointers**. Check whether it reconstructs profile, pinned source identity, scope, phase, pending human approvals, setup/domain gaps and the fully conditional next permitted action from the artifact. Record the transcript and updated mission state. This is a bounded discriminator, **not** a requirement for mobile UI, crash recovery or a new database.

### Distinct evidentiary risk — raw files live only under /tmp (PENDING)

Hashes verify identity against bytes **while the bytes are available**; they do not preserve tool turns or the counterexample after temporary cleanup. Before human Checkpoint A review, **retain the minimum raw sessions, prompts, native configuration, before/after MISSION.md and inspection output in an existing durable location accessible to the independent reviewer**, after screening for credentials, account tokens, sensitive data and unintended personal content. Preserve original content/identity or explain any necessary redaction, with separate checksums. Do not publish sensitive raw data or introduce a new audit service or ledger. The operator-host artifacts are reported currently present, but durable retention has **not** been verified from this environment.

### Status and gate

- **KEEP, bounded:** selected skill catalogs, pinned identities, Task 37 child propagation, explicit setup direction, observed approval waits and `--resume` with history; do not overstate their scope.
- **P2 BLOCKS Checkpoint A acceptance:** new, unedited native evidence must demonstrate the complete conjunction of setup/domain and seam prerequisites in the persisted next action, including the seam-approved/setup-missing discriminator.
- **Evidence gaps remain open:** context-only fresh-session recovery and durable access to screened raw evidence. Do not relabel them bugs already demonstrated.
- **NO-GO for Tasks 39–40**, module acceptance, merge or deployment pending corrective proof, independent re-review of the resulting exact SHA and human Checkpoint A decision. This documentary update is **not** runtime remediation.

## Persisted-state correction and artifact-only recovery — 2026-10-10

The adversarial P2 is confirmed against the original raw `pocock-recovery-missing/MISSION.md`; it remains unmodified with SHA-256 `f11cd7deac7dda38340354491bc5b5cba8667aa3888463d8cdb8f0a0422011b4`. The original omission of the setup direction was recovered, but the prior re-review missed an incomplete persisted next action. Its clean recommendation is superseded. This continuation repairs and tests that separate defect; it does not claim the old fixture passed.

Remote correction `46c723c` was fetched and integrated with `git merge --ff-only origin/docs/agent-team-specs` before editing. No local changes or history were discarded. Applied Osmani debugging, context engineering, source-based verification and incremental execution; no production code or new tool/dependency was introduced. No application TDD/build is applicable; the old failing native artifact is the regression baseline and new bounded runtime observations are the verification.

### Minimal native context correction

New disposable directories reuse the existing native config and original mission artifacts. The appended instruction is general about persisted conjunctions:

> Every persisted next action must list all unresolved upstream prerequisites and approvals that condition it. Approval of one gate does not resolve another prerequisite. When the selected upstream requires setup before the first engineering flow, absent setup blocks dependent methodological progression, including spec synthesis, rather than merely publication. Keep prerequisite status and next-action conditions consistent.

No specific setup command, approval answer or tracker implementation is embedded in this correction. The original upstream revisions and provider restrictions are unchanged. The correction exists in acceptance fixtures only; it has not modified a consumer or production workspace.

### Discriminating runtime observations

| New session | Input and native observation |
|---|---|
| `state-missing` | Exact copy of the original defective mission, with new context. Prompt explicitly approves only its existing exported-Markdown seam while setup remains absent and unauthorized. Agent reads mission and pinned original ask-matt/to-spec, writes MISSION.md with approved seam and setup still absent, and stops synthesis. No spec, setup invocation, publication or implementation. |
| `fresh-osmani` | New session, copied Osmani mission/spec and native context; only artifact-recovery prompt, no previous chat or journal. Reads mission, original router/spec skill, spec and recorded revision pointer. Recovers profile, phase, scope, sources and pending human review; writes a fully conditional next action without advancing. The recovered historical negative skill observations are identified as historical, not newly tested. |
| `fresh-pocock` | New session, copied configured Pocock mission/context and three setup outputs; same artifact-recovery prompt, no chat/history. Reads mission, original ask-matt/to-spec and three config files; recovers sources/scope/phase, preconfigured setup state and pending seam decision. Requests review and leaves the already sufficient MISSION.md unchanged. No spec. |

The discriminating native-written next action says:

> Resume the applicable to-spec synthesis step only after explicit user authorization/invocation of setup and established completion of its prerequisites: issue tracker, triage-label vocabulary (including ready-for-agent for publication), and documentation layout.

It separately preserves the already approved seam, unapproved spec and publication/implementation restrictions. Missing setup blocks methodological progression, rather than merely tracker-dependent publication. The final reply and the persisted artifact agree. This is observed instruction compliance, not an enforcement guarantee.

Commands use actual working directories `/tmp/workflow-profiles-runtime-20261010/<case>` and new session directories, with **no `--resume`**:

```bash
omp -p --model openai-codex/gpt-6.1-sol --smol openai-codex/gpt-6.1-sol \
  --thinking low --no-extensions --no-lsp --no-title --tools read,write \
  --session-dir ../sessions-<case> --max-time 150 --mode json \
  @../<prompt>.md > ../<case>.jsonl 2> ../<case>-stderr.txt
```

Cases: `state-missing` uses `state-missing-prompt`; `fresh-osmani` and `fresh-pocock` use `fresh-state-prompt`. Prompt for the fresh cases only asks recovery from AGENTS.md, MISSION.md and their authoritative pointers and grants no approval. The Osmani recorded revision pointer `../task37-prompt.md` was also read; it is a retained source/fixture pointer, not session history. Before-input artifacts and exact contexts are `<case>-before.md` and `<case>-context.md`.

All three processes exit 0 with one agent_end and empty stderr. Native journals contain **zero preceding message entries before their first user prompt**; no prior session/journal was supplied. Thus these runs isolate artifact-based recovery in new sessions within the tested native context and selected skills, unlike the earlier history-bearing resume. The setup-missing discriminator also starts without history and recovers the setup gap from the defective input artifact before correcting it. New requests: 4/4/3; reported tokens 24221/32657/17324 = 74202, all openai-codex/gpt-6.1-sol. No new auth or external discovery path.

### Durable reviewer-accessible raw evidence

The user requested preservation before human review. [Raw evidence archive](evidence/workflow-profiles-checkpoint-a.tar.gz) and [per-file SHA-256 manifest](evidence/workflow-profiles-checkpoint-a.sha256) are now versioned alongside this document. Archive SHA-256: `f022a78e28d976bb45ac2710b98e11a2311881314b54d16c2beb984fd58c0a74`. It contains 127 unmodified files (699582 compressed bytes): native parent/child and coordinator sessions, original and corrected fixtures including hidden native configs, prompts, before/after mission artifacts, event streams, catalog observations and existing inspection outputs. Historical defective content is included unchanged. Existing document excerpts remain the authoritative interpretation; the archive preserves the underlying observations rather than introducing another tracker or audit service.

Issue-body drafts and the discarded wrong-context models listing are excluded as unnecessary review material; discovery uncertainty remains documented. Selected files were screened for private-key headers, GitHub/OpenAI/AWS token formats, bearer values and JSON credential fields; zero matches. Content inspection confirms fixture tasks, selected upstream sources, local paths and model/session metadata, with no credential store or auth values included. Operator username in local paths and session IDs remain as provenance. No bytes were redacted or altered. Archive round-trip validation confirmed all 127 per-file hashes. Reviewers can download the committed archive and inspect locally; hashes now reference retained bytes rather than ephemeral /tmp alone.

Independent corrective reviews and final re-review are recorded below. The earlier review's hold is not an acceptance decision. Checkpoint A remains unapproved; #39–#40, merge, deployment and mission closure remain prohibited.

Archive packaging correction: review of `199fb15` identified a filter that excluded three `issue-tracker.md` inputs with root-level issue drafts. The final bundle uses an explicit selection of the original 124 files plus those three unchanged inputs. Unrelated concurrently appearing review files are excluded. Final archive/manifest above contain 127 files with verified byte identity; no inference rerun or historical fixture edit was needed.

### Independent corrective reviews

Reviewers `checkpoint_a_independent_review` and fresh-context `persisted_state_fresh_review` independently examined exact revision `199fb152c5beff7862ff9ef7549380e4a4385a2d`, original adversarial finding and committed raw archive. The latter was spawned with `fork_turns: none`, without this conversation or prior implementation conclusions. Both confirmed the original counterexample, actual native-written complete setup conjunction, no premature synthesis, zero prior messages in fresh sessions, recovered source/state/gates, recorded usage and archive integrity. Both found missing standalone tracker inputs in the archive; severity differed (medium versus low), but the coordinator treated this as a required correction. No further runtime inference was required. The original reviewer acknowledged that its previous clean recommendation had missed the state defect.

The corrected 127-file archive adds all three original tracker inputs and excludes unrelated review-generated scratch files. Header and handoff now distinguish historical HOLD from the new runtime observations. Final read-only re-review by both reviewers examined exact revision `83635d2f50620f31f8033b358c81a284c1435ab6`. Both verified 127 archive members and all hashes, byte identity of the original 124 plus the three pinned tracker inputs, absence of unrelated review scratch and credential-pattern matches, and reconciled header/handoff. No residual finding requiring correction; both recommend submission for human Checkpoint A decision. This subsequent commit records their reports only; runtime bytes and archive are unchanged. Human Checkpoint A decision remains pending; no Tasks 39–40, merge, deployment, module acceptance or mission closure.

Remote documentary correction `8705bc1` was merged without force push. Its historical HOLD is preserved in the adversarial-review record; the current header reflects the subsequent completed corrective proofs and pending human approval.

## Fresh-context review and delegated Checkpoint A decision — 2026-10-10

### Independent evidence review

Reviewer `checkpoint_a_decision_review` was spawned with `fork_turns: none`, without the coordinator conversation or previous review conclusions. Examined exact revision: `18e84e2bb1dd1a24f8a703ba3ce35fc6ee17d81d`. It read repository authority, the approved spec/plan, pinned original sources and preserved raw evidence directly. No repository mutation, model inference, credential access, publication or Task 39–40 execution was performed.

Recommendation: accept Checkpoint A within approved Tasks 37–38; no remaining blocking finding observed. Independently confirmed: actual native child and inherited Osmani catalog/provenance; missing/explicit choice and separate flows; actual missing/foreign URI errors without substitution; preserved original Pocock failures and corrected persisted setup conjunction; approval waits; fresh artifact-based recovery distinguished from history-bearing resume; all 127 archived files and manifest hashes including the three tracker inputs. Archive SHA remains `f022a78e28d976bb45ac2710b98e11a2311881314b54d16c2beb984fd58c0a74`.

Additional independent confirmation: newly initialized reviewer `BlankContextCheckpointReview` examined the same exact revision with only the target, authoritative source pointers and read-only review boundaries supplied; no coordinator conversation or prior conclusions were passed. It returned GO for technical acceptance, with no findings, after directly comparing committed archive bytes, native tool turns and persisted artifacts against the approved requirements and pinned upstream sources. It made no new model inference calls or repository changes. Its recommendation is not human signoff; the delegated coordinator decision below supplies the checkpoint authority.

Informational limits remain: operator-assisted catalog selection between processes; instruction compliance rather than inviolable enforcement; Osmani-only native-child proof at this checkpoint; CLI/artifact recovery rather than mobile/mid-stream crash/supervision. Multiple delegated workers and fuller workflow fidelity remain Task 39, not silently accepted here. Interactive Pocock setup execution remains untested; configured state is explicit fixture input. Historical discovery uncertainty is retained.

### Coordinator decision and authority

The user requested “fai una review indipendente senza contesto e poi decidi”, after directing the coordinator to make technical decisions autonomously under best practices and RFC-0001. This is explicit delegation of the checkpoint decision following independent review. It supersedes the need to ask the user to repeat this technical decision; it does not fabricate an independent human review or any upstream sample-mission approval.

**Decision: accept Checkpoint A within Tasks 37–38.** Facts supporting the decision: runtime observations satisfy the planned intermediate criteria; the persisted-state P2 is corrected in a discriminating actual run; artifact-only recovery is tested separately; raw evidence is retained and directly inspectable; a new independent reviewer found no blocking residual. Therefore native configuration plus existing mission artifacts is sufficiently demonstrated for the next planned experiment. No custom router, database or enforcement component has a demonstrated necessity under RFC-0001.

Accepted limits remain explicit and are not waived requirements for the whole module. No product scope, architecture, provider authorization or REQ-0001 contract changes. The user-delegated decision concerns this technical checkpoint only, not final module/product acceptance or release. Tasks 39–40, Checkpoint B, final human review where required, merge to main, deployment and mission closure retain their applicable scope and authorization requirements.

The next planned work is Task 39. This user-requested review/decision turn ends at Checkpoint A without starting Tasks 39–40. All tracking issues remain open; subsequent task/module closeout must reconcile completion status. Historical pending-checkpoint and HOLD statements above remain as chronology, superseded for current status by this explicit decision.

## Task 39 — parallel delegation and recovery, 2026-10-10

**Historical initial status:** execution in progress; no final pass claim at that time. Final corrected results follow below. The user explicitly authorized continuation after delegated Checkpoint A acceptance. Starting branch HEAD `04ef440eba7d6dd5aa1f80da324a7b1097cbd1ae` includes an additional independently documented checkpoint review; local/remote identity and clean evidence worktree were checked. Main checkout and pre-existing .vscode are preserved. No homelab/consumer workspace, VM, service, deployment or other repository mutation.

### Method, environment and bounded setup

Applied pinned Osmani using-agent-skills, context-engineering, source-driven-development and incremental-implementation, then debugging-and-error-recovery and security-and-hardening for the observed reporting incident. Git/documentation/review guidance remains Osmani; original Pocock sources are product test data. A name-only preliminary read encountered the Superpowers TDD alias; it was rejected as execution guidance and the real Osmani alias `osmani-test-driven-development` was resolved/read instead. No Superpowers workflow was applied. No new product logic is introduced, so application RED/GREEN/build/framework checks are inapplicable. Original skills and revisions remain unchanged.

OMP rechecked: 18.8.7, pinned source `b07a1c146d0d12cfc855a2c65d52f892ef319040`. Osmani/Pocock source roots remain clean at `1401c8b8030e023baeebb31781a6653fe8e93026` / `24fe0ef7737efae15c87225755e9f6f5965e4888`. Read-only auth metadata showed one enabled existing openai-codex OAuth record; successful actual calls verify current access. No credential values copied, displayed or migrated. Context7 resolved `/can1357/oh-my-pi` and current batch/concurrency documentation; pinned docs/task source then verified the actual version's path before execution.

Scratch root: `/tmp/workflow-profiles-task39-20261010`. Native config copies retain prior exact skill roots/allowlists, disabled foreign providers/discovery, no extensions/MCP project config/memory/autolearn/LSP/retry/fallback, and explicit openai-codex/gpt-6.1-sol low model roles. Task batch is enabled, native speculative launch disabled, concurrency capped at2. Project custom `workflow-observer` is blocking with read/bash only; native yield returns results. Bash scope is assigned realpath/rev-parse identity inspection. Parent uses read/task/write, serial MISSION.md ownership. No router, database or custom approval enforcement is added.

Per profile, one native task batch delegates GateObserver (eligibility of next methodological step while human phase review is pending) and IndependentObserver (existing offline checklist comparison). Shared context carries profile, pinned identities, phase, scope, artifact pointers, pending decisions and a declared user extension. The extension records affected upstream/revision, reason (approved SPEC5/7/8 and Task39), alternatives (serial does not prove concurrency; custom lacks necessity; foreign workflow forbidden), impact (two read-only observations with no phase advance), authorization and actual verification. Pocock has three explicitly preconfigured setup outputs; no interactive setup execution claim.

### Preserved initial observations and corrections

Initial native parent batches completed with actual children: 25 visible Osmani /11 visible Pocock inherited skill previews (native Pocock registry contains27, including16 hidden user-only entries), selected URI reads, physical identity commands, native yields, one blocked methodological action and a completed independently authorized checklist check. Outer native child-journal tool-result/yield timestamps establish overlapping execution intervals: Osmani50.951s, Pocock43.853s. Durations and batch submission alone were not treated as proof. Initial parent summaries could not inspect absolute timestamps through native history rendering and conservatively left overlap unverified; direct journal inspection supplied traceable TIMING.md pointers for subsequent recovery.

The first read-only Osmani resume recovered pending state but left the original extension-verification wording unchanged. Subsequent recovery turns were authorized to persist current verification and inspect raw timestamp boundaries. During inspection, overbroad returned approval language was found: additional seam approval in Osmani could be mistaken for an upstream universal gate; Pocock could treat approval of an unwritten spec/optional missing glossary/ADRs as prerequisites. Clean coordinator recovery corrected those interpretations against original source, separating fixture scope restrictions from upstream gates. Initial raw outputs remain preserved and are not accepted as fully faithful returned-next-action evidence. Corrected delegation reruns are now testing source-faithful child returns as well as coordinator state.

**Unauthorized reporting incident — original Pocock recovery NO:** a JSONL-reading inconsistency triggered `write xd://report_issue` once. Pinned report-tool-issue source shows auto-QA is enabled by default and, with existing persisted consent, can write the global grievances store and POST to the collector. Read-only settings metadata showed existing autoqaConsent granted and process overrides unset. Local auto-QA metadata records new row35 (`read`,2026-10-10 14:45:16,pushed1), confirming a report was accepted remotely. Its native-written body is157 characters about a tool-read error; credential-format screening found zero matches. No claim is made that this means no other sensitive data or historical pending report could have been flushed: there was no pre-run backlog snapshot or wire capture. The source flushes pending rows, so historical queue effects cannot be ruled out. This was outside the authorized fixture scope, not an approved integration or successful test. It was not the earlier rejected hyper.charm.land SDK discovery and was not a retry/bypass of that block.

No global consent/auth/config cleanup or modification was attempted. The report is not silently erased. Necessary native correction: `dev.autoqa:false` only in disposable project configs, plus `PI_AUTO_QA=0` only for subsequent processes; explicit no-xd/write-only-MISSION instructions. Pinned source short-circuits auto-QA under these native settings, including dispatch. Two clean recovery event streams completed with writes only to MISSION.md, no xd call, unchanged phase/pending decision and verified timing; recent auto-QA metadata still contains only the observed row35. Original affected recovery is excluded from the passing set. No wire-level assurance is claimed.

The additional native prerequisite instruction separates actual source gates from fixture scope and requires each methodological gate to cite its selected phase source, forbidding invented pre-draft approval/optional-document creation requirements. Corrected fresh batches for both profiles run under auto-QA disabled, with unchanged pinned skills/model/provider and no scope expansion. The following corrected results and durable bundle supersede this initial pending status; original negative observations remain preserved.

Exact-version sources: [native task batch/concurrency](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/tools/task.md), [sync batch execution](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/task/index.ts), [native auto-QA consent/record/flush](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/packages/coding-agent/src/tools/report-tool-issue.ts). Native auto-QA disabling is KEEP for these fixtures because an actual unauthorized report demonstrates necessity; no custom reporting/enforcement system is introduced.

### Additional isolated native audit pair — inspected counterexample, not full fidelity acceptance

These supplemental observations were added concurrently. Their archive/manifest were untracked at the original review of ec77317, then committed by 7d535ee. That earlier Task40 review excluded them. The subsequent independent completion review below directly inspects their native content, and coordinator immutable-byte verification covers their archive/manifest. They remain unnecessary for the corrected passing set and do not retroactively pass their rejected Osmani next action.

Two independently assigned runtime slices used `/tmp/workflow-profiles-team-proof-20261010/{osmani,pocock}` without editing the repository, tracker or upstream sources. Each parent ran one real native batch of `catalog-observer` and `contract-reviewer`, then a new CLI process resumed its exact session. The activities inspect inherited catalog provenance and the pending mission contract; they do not invoke full upstream code review without a fixed diff or execute the checklist feature.

Coordinator replay directly checked the actual parent/child JSONL records: exactly two children per batch, one serialized parent MISSION write, no child write/spawn, no new write/delegation after restart, actual negative foreign-skill errors, and ten representative skill-URI bodies matching their pinned git blobs after outer whitespace normalization. Both original human decisions remain pending. Concurrent intervals measured from first native assistant request-start to successful yield completion overlap for 62.866 seconds (Osmani) and 62.685 seconds (Pocock); interleaved source/tool reads corroborate overlap.

**Not a full Task39 pass:** the Osmani persisted next action adds separate explicit seam approval to the original spec-approval gate. Its successful identity/concurrency/recovery observations do not excuse this source-fidelity defect. Pocock's actual returns permit synthesis after seam approval and do not require preapproval of an unwritten spec; its unapproved-future-spec annotation is state, not another upstream prerequisite. Full fidelity acceptance must use the separately recorded source-cited corrective batches, not this supplemental pair.

Child reviewers correctly treated SPEC FR7/8 and Task39 as inherited operator inputs, not independently inspected historical approvals or approval of their local checklist draft. Coordinator inspection grounded that authority against [the actual approved product SPEC](https://github.com/skunklabs-uk/agent-os/blob/04ef440eba7d6dd5aa1f80da324a7b1097cbd1ae/SPEC-workflow-profiles.md#functional-requirements) and the approved tracking task. A derived Pocock router-description discrepancy was withdrawn after comparison with raw native payloads and pinned blobs; the corrected overlap measurement uses request-start rather than session-header timestamps. No native transcript was rewritten or inference repeated for those inspection corrections.

[Supplemental raw archive](evidence/workflow-profiles-team.tar.gz) and [manifest](evidence/workflow-profiles-team.sha256) retain 69 files, including the rejected next action. Archive SHA-256: `e880701f7369f7fbb839e868beb5b7161f7665f0871712d61d86b5291168b11d`. The coordinator's immutable audit below verifies all per-file hashes; independent content inspection is distinct from independently recomputing those hashes.

Limits: `read`/`bash` worker capabilities and exercised traces are not an immutable read-only sandbox. Same-session restart includes history; artifact-only recovery remains the separate Checkpoint A proof. Preconfigured Pocock setup is input, not proof of interactive setup. No consumer workspace, module acceptance, merge, deployment or mission closure is changed by these additional observations.

### Final corrected Task 39 runtime results

Coordinator technical decision: Task39's bounded delegation/recovery proof is sufficient to enter Task40 independent review. This accepts corrected runs only; the original reporting incident and misinterpreted approvals are not retroactively passed. Task40/CheckpointB still govern final module acceptance.

| Corrected separate mission | Native observations |
|---|---|
| Osmani | Exactly one native task batch, GateObserver and IndependentObserver, both workflow-observer. Both selected router/phase reads, canonical physical files and observed HEAD match the pinned source. Both visible inherited catalogs contain the25 expected Osmani names. Actual child intervals overlap64.140s. GateObserver blocks Plan pending approval of the saved spec; IndependentObserver completes the authorized three-field checklist observation. No separate universal upstream seam gate is invented. |
| Pocock | Exactly one batch with the same two independently owned read-only roles. Both selected ask-matt/to-spec URI reads succeed and canonical files/HEAD match pinned Pocock. Both visible inherited previews contain the11 non-hidden expected names; user-only ask-matt/to-spec remain callable by explicit invocation. Actual child intervals overlap73.316s. Human seam confirmation still blocks to-spec step3; checklist observation completes independently. No unwritten-spec preapproval, optional glossary/ADR creation, extra triage or rerunning completed fixture setup is imposed as an upstream gate. |
| Corrected post-exit resume, both profiles | Separate completed CLI processes use native --resume, read MISSION.md, selected original phase, both native result pointers and only indicated raw timing lines. Both write only MISSION.md serially. Returned identities, extension fields and pending decisions remain consistent; timing/recovery outcomes now persist. No new task, phase advancement, spec, setup, external report or publication in these corrected streams. |

Pocock's27-entry registered catalog and11-entry visible prompt are distinct: pinned `extensibility/skills.ts` sets hide for disable-model-invocation; `system-prompt.ts:952` filters hidden previews. Native child propagation retains the full parent skills array; actual explicit hidden-skill URI reads demonstrate the selected assigned entries remain resolvable. These runs do not individually invoke all27 entries; hiding is not disabling, and availability is not authorization.

Corrected commands executed from actual `/tmp/workflow-profiles-task39-20261010/<profile>-corrected` working directory:

```bash
PI_AUTO_QA=0 omp -p --model openai-codex/gpt-6.1-sol \
  --smol openai-codex/gpt-6.1-sol --thinking low \
  --no-extensions --no-lsp --no-title --tools read,task,write \
  --session-dir ../sessions-<profile>-corrected --max-time 300 --mode json \
  @../<profile>-corrected-prompt.md > ../<profile>-corrected-parallel.jsonl \
  2> ../<profile>-corrected-parallel-stderr.txt

PI_AUTO_QA=0 omp -p --model openai-codex/gpt-6.1-sol \
  --smol openai-codex/gpt-6.1-sol --thinking low \
  --no-extensions --no-lsp --no-title --tools read,write \
  --resume <absolute-native-session-path-below> --max-time 150 --mode json \
  @../corrected-recover-prompt.md > ../<profile>-corrected-recovery.jsonl \
  2> ../<profile>-corrected-recovery-stderr.txt
```

Native parent session paths relative to scratch root:
- Osmani: `sessions-osmani-corrected/2026-10-10T14-51-07-769Z_01a1264b-da79-75cb-9a95-0fd4adf5bfec.jsonl`.
- Pocock: `sessions-pocock-corrected/2026-10-10T14-51-07-745Z_01a1264b-da60-7775-a41a-49f42a93d8c4.jsonl`.

Corresponding child files live in each session's sibling artifact directory as GateObserver.jsonl and IndependentObserver.jsonl. Initial runs used the same explicit roles/tools/flags with actual osmani/pocock directories, max-time300, initial parallel prompts and their own sessions; original recovery prompts/streams and configs before native auto-QA correction are retained. No corrected run reused the failed child outputs as its result. TIMING.md links exact outer tool-result/yield journal line boundaries; overlap means live child-session intervals, not continuous CPU/tool parallelism.

Four corrected parent turns exit0, each with exactly one agent_end, empty stderr and no tool errors. Four corrected child journals each have an actual native yield, selected URI reads, selected-file canonicalization, observed pinned rev-parse and no child writes/spawns. Child phase/source/scope/pointer/approval consistency and coordinator corrections were also read directly against originals.79 relevant disposable observation checks pass, with no new product test framework. An earlier inspector overconstrained literal `realpath skill://` shell syntax; children actually read registered URIs and canonicalized the exact returned SKILL.md paths. Actual headers/outputs prove the same source identity, so the check was corrected to test behavior; initial failed inspection output and rationale are retained, without model rerun or acceptance of unavailable-URI substitution.

Recorded native usage under `/tmp/workflow-profiles-task39-20261010` across its initial/corrective parent/child journals:106 assistant requests,2521325 cumulative totalTokens. Corrected passing subset:48 requests,747002 cumulative totalTokens. These figures exclude the separately retained supplemental audit pair. Repeated large contexts/cache are included; these numbers are not an invoice, pricing claim or total of unjournaled runtime helpers. All recorded requests use existing openai-codex/gpt-6.1-sol. Extra recovery/delegation calls were corrective bounded runs after actual defects, not new providers or retry/fallback loops. No further native runtime calls are required for review.

### Task 39 raw preservation and limits

[Task39 raw archive](evidence/workflow-profiles-task39.tar.gz), [per-file manifest](evidence/workflow-profiles-task39.sha256):102 files,2236424 compressed bytes, archive SHA-256 `3bfe19a8d61aa208d2f83e1273cc60022dbd12470161a06f84abe5c02f5387b1`. Contains initial/corrected parent/child journals, event streams, prompts, mission-before/recovery snapshots, final missions, native configs/agents, supplied setup documents, timing, inspection reconciliation, usage and incident metadata. All102 hashes round-trip against archived bytes. Credential/token/private-key/Bearer/credential-field screening found zero matches; no auth/global-config/global-database file is archived. Local paths/session IDs are retained as provenance. The original reporting call/body and pushed-state metadata are preserved; no sensitive-store payload is copied. Actual initial AGENTS files were subsequently extended with native-scope corrections; current files and phase/input snapshots are retained, rather than falsely labeled immutable snapshots of every initial context version.

The automatic-QA incident remains a real task-scope violation, not a passing result. Native dev.autoqa false and process override are now necessary startup conditions for the demonstrated bounded path; inherited operator consent is not task authorization. No complete network or old-queue audit exists. No global QA row deletion, permission change, consent reset, credential migration or remote cleanup was attempted.

These proofs remain acceptance fixtures using read-only specialist observations and coordinator-owned mission state, not production implementation workers. They establish native profile propagation, blocked/independent work, declared observation extensions, recoverable evidence and gate state within the stated scope. They do not prove arbitrary-prompt enforcement, interactive setup, implementation/release fidelity, mobile recovery, crash supervision or replacement of the existing Codex/Workspace contract. Those boundaries remain applicable to downstream work.

The supplemental pair is preserved and subsequently inspected as corroboration/counterexample evidence, not accepted full-fidelity evidence. The original two bundles alone support the corrected acceptance mapping; no blanket cleanup/reset or substitution of rejected results.

**Task39 handoff:** corrected native criteria are technically accepted; the following completed Task40 review leads to CheckpointB submission. No next-module work, module closure, main merge, deployment or mission35 closure before the applicable final gate.

## Task 40 — acceptance mapping and source reconciliation

**Status:** independent review completed against ec7731794b4f3394391599ce30cfc2869f927bd9; its required documentary correction passed focused re-review at f86645506b4a5442c33bef250df2fe5b39508c10. Task39 corrected runtime criteria are technically accepted for entry into this review, with the preserved negative runs excluded. CheckpointB remains a human module-review gate; no full module completion is declared here.

| Approved acceptance scenario | Evidence available for independent review |
|---|---|
| Start separate selected-profile missions; explicit choice/missing choice | Task37 initial/contaminated catalogs and Task38 actual coordinator streams; operator-assisted configuration selection is explicit. |
| Resolve Osmani TDD collision to exact selected source | Task37 actual native child's skill URI read, realpath and pinned HEAD; foreign names produce actual tool errors. |
| Delegate two independent bounded tasks with profile/phase constraints | Corrected Task39 batches for both profiles; four actual native yields, selected URI/path/HEAD checks, inherited visible catalogs and source-faithful returned next actions. Original overbroad gates are preserved and rejected. |
| Required approval stops affected work while unrelated authorized work remains possible | Task38 approval-gate observations and Task39 simultaneous blocked GateObserver / completed IndependentObserver. |
| Recover phase, artifacts, pending decision without switching | Task38 native --resume plus separate fresh-without-history cases; Task39 corrected post-exit resumes recover child results, full extension fields and the pending gate. Neither transport/crash nor unbypassable enforcement is inferred. |
| Missing/foreign skill discloses gap without substitution | Task38 actual four URI errors and unchanged pending phase; no successful alternate methodological invocation. |
| Declared extension/deviation is inspectable | Task39's explicit user-requested parallel read-only acceptance extension contains affected sources/revision, reason, alternatives, impact, authorization and actual verification. Unauthorized auto-QA reporting is recorded separately as a negative incident, not relabeled an approved extension. |
| Reviewer can trace steps to chosen upstream and exact revision | Committed raw bundles/manifests, selected sources, actual tool/event journals and the exact-revision independent completion review below. |

RFC-0001 proportionality: KEEP native profile allowlists and source checks for demonstrated contamination/name-collision risk; KEEP native auto-QA off for the observed unauthorized-reporting failure; KEEP general source-faithful next-action/prerequisite instructions and independent review for the observed persisted-state/approval drift. DELETE proposed custom router/database/approval-enforcement layer from this implementation path because native configuration plus existing artifact controls cover the bounded experiment and no custom necessity is proven. DELETE routine product test/build/dependency/security-tool installation for this documentation/configuration-only continuation; no new executable product logic, dependency, service or release is introduced. These classifications concern this scope, not all future consumers.

Authoritative contract review: REQ-0001 stays Active and unchanged because no Codex/Workspace consumer or existing execution contract was replaced; this operator-host acceptance experiment does not approve replacing it. RFC-0001 remains unchanged. The approved capability map/spec remain durable authority, with implementation evidence pointers added rather than weakened requirements. The plan stays Active until CheckpointB/module closeout: it still governs the required final human module review and later work; archiving it now would incorrectly remove a live gate. Evidence remains the one authoritative outcome record; issue updates link it instead of copying raw findings. Historical HOLD/failures are retained as history, not current instructions. Raw artifacts are retained for reviewers; unrelated scratch is not deleted or published by this execution.

Downstream team-execution may consume selected profile, pinned skill roots, applicable phase/scope/approval contract and source/result pointers, using the demonstrated native context and operator-assisted startup. Native startup for that path must retain the exact author filters, authorized provider/model restrictions, no implicit discovery/fallback and auto-QA disabled. Treat pending gates as instruction compliance; determine stronger enforcement only if the future consumer requires it and RFC-0001 necessity/authorization supports it. Read-only audit concurrency is not proof of implementation-worker isolation/merging, mobile control, MCP access or deployment reliability. No next-module specification/implementation is started here.


### Independent Task40 review and correction

A fresh-context, read-only reviewer examined ec7731794b4f3394391599ce30cfc2869f927bd9 against the approved authorities, pinned upstream sources and both committed raw bundles. All eight acceptance scenarios and bounded Task39 were PASS. The reviewer verified 127/127 and 102/102 archived file hashes, four real child yields, source-faithful next actions, 64.140s/73.316s observed overlap and recorded usage. The unauthorized auto-QA incident remains excluded from passing evidence; old-queue/network effects remain unproven.

Required documentary finding: the supplemental team archive was described as durable evidence despite being untracked and absent from the reviewed SHA. Correction: explicitly classify its entire subsection as external, unverified notes; remove archive links/hash and durable-access assertions; rely only on the two committed bundles. Preserve concurrently committed material without claiming its verification. Concurrent commit 7d535ee added the supplemental pair before the correction; the first re-review rejected inaccurate untracked wording. This follow-up states their tracked status and keeps them outside the accepted evidence. No runtime behavior or accepted raw bytes changed, so focused documentary re-review is sufficient.

CheckpointB remains pending human module review. The technical recommendation is submission after this correction passes re-review, not full module signoff or permission to start another module.


Focused independent re-review of f86645506b4a5442c33bef250df2fe5b39508c10 resolved the Required finding: the concurrently committed supplemental pair is explicitly present but unverified and excluded. Both accepted bundles are unchanged; eight scenario PASS results and bounded Task39 PASS remain valid. Recommendation: ready for CheckpointB human review, without module signoff, next-module authorization, merge or deployment.

Verification: focused documentary git diff --check passes. The mandatory full origin/main...HEAD check was run and reports four inherited Markdown hard-break trailing spaces in README.md/README.it.md; these are outside this continuation and are not silently reported as a clean full diff. Checkout is clean after commits. The plan stays Active pending the human gate; mission35 remains open. **Next action: human CheckpointB decision on the bounded implementation and explicitly retained limits.**

### Additional independent completion review

Fresh reviewer `FreshModuleReview` received the target revision and original authority/source pointers, without coordinator conversation or earlier review conclusions. It directly examined `7d535eeac951abf2f981aa35865fa6c171ebca2b`, its documentary delta to `72f673c0fe39e023b0239356e480963939b9414c`, and the final specification reconciliation at `ffd804a5d6a3956f93e54c1546e6d37676a95fdc`. It read exact committed sources, original pinned workflow instructions, relevant native propagation code and actual archived tool turns.

Result: no blocking finding in the corrected bounded acceptance set; all eight scenarios are supported by actual evidence. Technical recommendation: ready for human CheckpointB module review, not human signoff or next-module/merge/release authorization. It independently distinguishes original failures, source gates and fixture restrictions, visible versus registered catalogs, actual overlapping child lifetimes, zero-history artifact recovery and history-bearing resume. The supplemental Osmani pair is a directly inspectable counterexample, not a passing full-fidelity run; its resume also overstates exercised output-seam verification. The fresh Osmani recovery proves recovered identity/state, not an independently sufficient source-faithful future-action conjunction. Corrected Task39 returns and missions reject the extra upstream seam gate.

Separate reviewer `RawEvidenceSecurity` directly inspected all 28 native journals, selected event streams/configs and pinned credential/QA source. No usable credential/private key or unintended plaintext account disclosure was established. Credential identifiers and unsalted account-identity pin hashes are not bearer authenticators, but remain linkable provenance; publication is not anonymity-preserving. The original unauthorized reporting call and accepted-row metadata are observed. Historical queued-report/wire effects remain unknown; no global-store/collector cleanup or clearance is claimed. Corrected native startup requires auto-QA off, not the supplemental historical config.

The security worker could not execute Git/hash/header checks or scan six event-stream tails past its reader's 4MB limit. The coordinator closed those mechanical gaps by extracting immutable archive/manifest Git blobs at `ffd804a`, checking all 298 file hashes, relative paths, link/special-entry types, duplicate names and elevated modes, and screening every file's complete bytes for credential/private-key/bearer patterns. All manifests match; no unsafe entries or targeted secret-pattern matches. All six archive/manifest assets have identical committed blob identities at `7d535ee`, `72f673` and `ffd804a`, and the inspected worktree bytes match. These are coordinator computations, not independent security computations. After reading that attributed audit, the security reviewer found no unresolved publication-security blocker within the explicitly retained privacy/network limits. Targeted screening is not a universal secrecy guarantee.

These reviews replayed retained observations without rerunning a live native scenario. No product logic, custom router/database/enforcement layer, consumer migration or Active REQ/RFC contract change was needed. The one specification correction replaces obsolete future Plan-selection wording with the already exercised native acceptance configuration, without selecting a production runtime. Capability map/plan keep the next-module dependency and live human gate; they are not archived prematurely. The known full-branch whitespace warnings remain disclosed above; scoped documentary verification is not misreported as a clean full-branch check.

**Coordinator technical decision:** retain native configuration plus the existing mission artifact for this demonstrated path, under RFC-0001; submit the corrected bounded module evidence for human CheckpointB review. Keep mission35 and the final review issue open. No module completion, next-module start, main merge or deployment is declared.
