# Plan: mobile-control and mcp-access

**Status:** Draft — planning deliverable for Product Owner review; not executable task approval.
**Mission:** [Agent OS35](https://github.com/skunklabs-uk/agent-os/issues/35), sole coordinator on NOVBSCWOLaulMaU.
**Authority:** [mobile-control](../SPEC-mobile-control.md), [mcp-access](../SPEC-mcp-access.md) and the [shared provider contract](../SPEC-team-execution.md#shared-remote-consumer-contract), explicitly approved on 2026-10-12 at `f55c2b7838104770766825e57b68129b019e951e`. Team-execution is accepted and delivered by [PR51](https://github.com/skunklabs-uk/agent-os/pull/51), merge `95528e6c0013f067702496902c40051fba973e48`.
**Method:** original Osmani spec-driven-development and planning-and-task-breakdown at `1401c8b8030e023baeebb31781a6653fe8e93026`. This phase is Plan; Tasks and Implement retain their later gates.
**Tracking:** GitHub issue35 and its eventual approved native sub-issues; no tasks/todo.md or second ledger. On 2026-10-12 the open-issue list contained only35, so no mobile/MCP execution task exists to reuse. Recheck before creating any. The former team-execution plan is Archived history and is not overwritten.

## Outcome and scope

Deliver two real user journeys: control the host mission from the user's mobile browser, and delegate/inspect/interrupt it through the user's actual ChatGPT MCP surface. Both use the same provider identity, state and decisions. Acceptance is per module, then reconciled for the MVP; accepted Waypoint/Pocock proofs are not repeated. No deployment, IWANT merge, runtime replacement, new infrastructure or spending is authorized by this plan's creation or approval.

The plan deliberately qualifies existing capabilities before selecting an implementation. Unknown access or source compatibility is not converted into a success claim. Later packages are conditional paths, not permission to build an unspecified adapter. If qualification establishes that an extension is necessary, amend this plan with the exact owner repository, base, files, commands, costs and necessity evidence before approving that implementation's Tasks.

## Evidence and implementation choices

| Observation / source | Planning consequence |
|---|---|
| Accepted team-execution provides native OMP18.8.7, original skill pins, real isolated workers and independent review; [outcome](team-execution-evidence.md). | KEEP that provider baseline. No new coordinator, workflow router, fixed team, state database or replay of accepted proofs. |
| [Collab documentation atb07a1c1](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/collab.md) describes browser sharing and guest intervention but host-only commands/session transitions. | Start mobile qualification here; joining an existing session cannot by itself satisfy remote start/resume. Preserve the gap rather than accepting a desktop-assisted substitute. |
| [omp-web package at0acce624](https://github.com/ddallabenetta/omp-web/blob/0acce6240b27eb7d44d5c9b78187bd95e01270f8/package.json) declares OMP dependencies~18.1.17; compatibility with18.8.7 is unproven. | Compare only if native capability leaves a required gap. Verify compatibility before any installation; do not downgrade the qualified provider or add a second runtime silently. |
| [Official Secure MCP Tunnel documentation](https://developers.openai.com/api/docs/guides/secure-mcp-tunnels?site_locale=en), read2026-10-12, describes an outbound private connection and ChatGPT connection through a workspace-associated tunnel. | Assess this supported transport before proposing public ingress. Account/workspace entitlement, host reachability and actual use are unknown. No tunnel creation, API key, API model call or network change has been authorized. Transport alone supplies no OMP business tools. |
| [Official authentication documentation](https://developers.openai.com/plugins/build/auth), read2026-10-12, describes OAuth-based user authentication and recommends an existing identity provider. | Reuse supported authentication if available; do not invent anonymous write access or custom auth. Verify actual client/account path and candidate tool semantics before choosing integration. |
| User requires mobile device and actual ChatGPT client evidence, both still missing. | Put identity/access qualification first. Desktop emulation and server-only tests cannot close either module. |

For MCP, compare existing supported tools/integrations against the full provider contract before considering a maintained MCP adapter around OMP SDK/RPC. Native RPC is a building block, not proof of an MCP server or account access. If no reusable route covers the gaps, the smallest custom alternative requires the RFC-0001 necessity record and explicit scope approval; it is not selected now. Existing Codex remote facilities may inform the comparison but cannot silently replace the qualified OMP provider or prove OMP-native behavior.

### Focused native-source readiness findings

A separate read-only preparer checked the pinned Collab/RPC sources and the local installed path. The binary exists at `/home/iingenito/.local/share/mise/installs/oh-my-pi/18.8.7/omp`; the prior qualification records version18.8.7 and an upstream archive, not a verified binary-to-commit mapping. The original temporary source checkout is no longer present. Do not claim that a local source path or exact binary mapping has been revalidated.

At the cited pin, Collab exposes guest observation/intervention/dialogs, but `/resume` and machine commands are host-only and new/resumed sessions change rooms. The old link does not follow the new session. Thus M1 must investigate a supported start/resume route rather than repeatedly proving only joining. The production relay is not distributed for self-hosting; a development stand-in is not a production hosting solution.

[Native RPC at the same pin](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/rpc.md) supplies session operations, state and interruption over proprietary JSONL stdio, not MCP. A yielded prompt result can precede settled work. `--no-ui` suppresses dialogs; closing stdin disposes the session and pending UI. Any later bridge must prove correct decision handling, settled state and reconnection without a duplicate coordinator or accidental stdin closure. These are observed source constraints, not an adapter implementation proposal.

Read-only inspection commands, with no runtime launch or secret output:

```bash
stat /home/iingenito/.local/share/mise/installs/oh-my-pi/18.8.7/omp
curl --fail --silent --show-error https://raw.githubusercontent.com/can1357/oh-my-pi/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/collab.md
curl --fail --silent --show-error https://raw.githubusercontent.com/can1357/oh-my-pi/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/rpc.md
```

Do not log `omp collab link` capability URLs. Registry-listing commands may clean stale metadata and must not be classified as pure filesystem inspection. No such commands were run for this Plan.

## Dependencies, ownership and parallelism

```text
Approved specs + provider contract
  -> P0 shared readiness / ownership
       -> M1 mobile path qualification -> M2 mobile decisions/reconnect
       -> C1 actual-client MCP qualification -> C2 MCP long work/decisions/reconnect
  M2 + C2 (or explicit PO decision on a demonstrated MCP limit)
       -> R independent final review -> D module acceptance and closeout
```

M1 and C1 may run independently after P0; M2 never precedes M1, C2 never precedes C1. A missing MCP permission blocks its dependent path, not mobile qualification. At most two assignments run concurrently; reduce for available resource authority. Coordination/integration is one owner, not a third competing implementation lane. No fixed team.

- **Coordinator:** exclusively owns shared contract, `tasks/plan.md`, capability map, mission35 and serial integration. Provider contract changes are reviewed before consumers rely on them.
- **Mobile specialist:** owns the mobile candidate and its evidence in a separate worktree/check-out if writing. Returns exact base/head, changed files, observed device results and limits; never updates the shared plan.
- **MCP specialist:** owns the separate MCP candidate/evidence under the same rules. No access to other projects solely because a transport supports them.
- **Reviewer:** clean session, original Osmani code-review-and-quality, original requirements, exact base/head/diff and relevant raw; no implementer chat or suggested verdict. Re-review only material corrections. Application QA and access/security review are responsibilities activated by actual work, not permanent extra agents.

The present Agent OS writer reuses the isolated coordinator worktree. No owner checkout or other worktree is reset, cleaned or cherry-picked. Future executable writers receive explicit owned files and permitted repositories in approved tasks before any launch. One integrator per repository.

## Proposed work packages, not duplicate task records

These packages are the scope and ordering for the next Tasks phase, not issued/approved executable tasks. Each must become a small native task with no more than three acceptance criteria and about five changed files; split any larger implementation only after its actual surface is known.

| Package / size | Result and focused verification | Prerequisites / ownership |
|---|---|---|
| P0 — shared readiness, S | Confirm host identity/availability, exact provider/source pins, one active coordinator and read/write ownership; record actual device/browser and ChatGPT surface/account capability without secrets; identify allowed access, model/cost ceilings and a bounded synthetic mission. Classify each lane READY/BLOCKED with precise next action. | Approved Plan and readiness Task. Coordinator; existing plan/mission plus source inspection. No service start or configuration writes for discovery. |
| M1 — mobile start/resume and visibility, S–M | On the actual device, qualify native collab and any source-justified existing alternative against start/resume, correct mission/team visibility and authorization. Record authentic observations including any required host intervention. Return exact uncovered gap if native route fails; no substitute acceptance. | P0 + approved task/runtime/access limits. Mobile owner; initially evidence only, candidate config paths specified before writing. |
| C1 — actual-client MCP delegation, S–M | Verify supported client/account connection and authentication; select an existing integration/transport only after source comparison. On an approved bounded mission, observe delegation/status to the sole coordinator and rejection outside scope. A supported transport with no mission tools is incomplete. | P0 + actual account access + approved task/connection resources. MCP owner. No install, tunnel, ingress or new service before owner authorization; material extension requires amended Plan. |
| M2 — mobile intervention and reconnect, M | Exercise question/approval/rejection, steer/interrupt and disconnect with a pending decision; reconnect and resolve once. Verify touch/keyboard usability, actual execution outcome and stale/duplicate response handling. Trace every mobile acceptance scenario to real evidence. | M1 covered required path + task approval + unchanged approved shared contract. Mobile owner; tests only for new approved logic, no framework by default. |
| C2 — MCP long work and reconnect, M | Exercise a request whose work outlives the initiating call, retrieve the same mission's result, resolve an applicable pending decision and interrupt/reconnect without duplicate work. Distinguish unknown/acknowledged/completed. Trace every MCP acceptance scenario to actual client evidence. | C1 qualified route + task approval. MCP owner; no model/API spending inferred from protocol testing. |
| R — independent exact-head review, S | Reconcile both module criteria against original specs, ownership, source pins and real raw; verify unauthorized/stale decisions do not mutate another mission. Required/Critical findings return to the owning writer; review material corrections on their new head. | M2/C2 outcomes available, or precise accepted product-limit decision. Independent reviewer read-only, coordinator integrates. |
| D — bounded acceptance and closeout, S | Present actual user-device/client results and remaining limits for module acceptance; record MCP include/limit/defer decision if needed, proportional mission retro and durable outcome; archive only completed plans and update all current pointers. Deliver PR/SHA/smoke after any separately authorized merge. | R clear + applicable PO module/delivery approval. Coordinator serial writer. #35 closes only when agreed MVP criteria are met. No deploy or IWANT merge. |

## Checkpoints and executable boundaries

1. **After P0:** coordinator confirms each lane's precise prerequisites and resource authority. No invented device identity, credential migration, pilot allowance reuse or unbounded retry. Missing user input is requested once for the affected lane, with independent preparation continuing.
2. **After M1/C1:** review evidence of the actual route, decide KEEP native/reusable or document the uncovered gap. A materially new implementation, owner repository, dependency, permission or service requires a concrete amended Plan/authority before writing. A source-only negative is not a fabricated runtime failure, and not a unilateral MCP deferral.
3. **After M2/C2:** original scenarios must have actual result/revision/raw pointers. User reports remain attributed to the user; coordinator tests remain coordinator tests. Reviewer receives evidence, not an expected verdict.
4. **Before D:** verify current branch policy, checks and delivery authority on exact heads. Never inherit Waypoint CI/merge delegation for a new module, trigger preview/build/deploy by accident, or rerun paid checks without applicable permission.

Current phase checks, from this repository:

```bash
git status --short
git diff --check
git diff --check origin/main...HEAD
git diff origin/main...HEAD -- SPEC-mobile-control.md SPEC-mcp-access.md SPEC-team-execution.md CAPABILITY-MAP-agent-team.md tasks/plan.md
```

No application build/bootstrap/CI is applicable to this Markdown planning change. Verify relative links and anchors plus source consistency and independent review. Executable readiness tasks must pin the actual installed binary paths, source/config inspection commands and, before any runtime trial, the complete startup/test/cleanup commands for the selected route. Do not treat interactive `/collab` as a shell command or blindly execute upstream tunnel quickstarts. No runtime/provider launch occurs in this planning turn.

For later authorized OMP proofs retain `dev.autoqa: false`, `PI_AUTO_QA=0`, permitted provider/model, isolated workers and automatic patch application disabled. Close stdin only on the previously qualified one-shot noninteractive path; do not apply that startup workaround to a persistent RPC transport, whose stdin must remain owned and open for its intended lifetime. Runtime duration/soft request bounds must not be represented as monetary caps. Determine actual resource authority in the task before use; do not transfer the pilot's budget.

## Resource and prerequisite boundary

- **Already acquired:** specifications and shared contract approval, this planning assignment, accepted provider proof, read-only preparation and real independent documentary review.
- **Next methodological decision:** Plan approval, followed by native Task graph and execution approval. No task creation or app implementation is represented as completed here.
- **Before user trials:** actual mobile device/browser and remote network context; actual ChatGPT client/workspace supported setup; operator participation for login/device smoke. Request facts or supported operator actions, never secrets in chat.
- **Before new operational use:** exact candidate, minimal permissions/connectivity, repository owner, startup/shutdown procedure, duration/cost authority and any necessary service/network approval. These are not all assumed to be needed: first reuse what is already present and authorized.
- **Always excluded:** deploy, IWANT merge, production/AWS, unsupported ChatGPT UI automation, routine tool upgrades, reopening unrelated Homelab34, fabricated proofs or duplicate trackers.

## Risks and proportional responses

| Concrete risk | Response |
|---|---|
| Browser joins a session but cannot remotely start/resume it | Fail that scenario explicitly; compare source-supported existing alternatives before any minimal extension. |
| Actual account cannot use the selected MCP route | Preserve the observed constraint, continue mobile, request explicit include/limit/defer decision only with evidence. |
| Native guest dialog lacks required scoped-decision behavior | Test the actual provider semantics, reuse existing request identity/rejection; custom controls need demonstrated gap and scope approval. |
| A connection expires or changes mission while a decision is pending | Verify target identity and stale response behavior end-to-end; do not infer from UI reappearance. |
| Persistent host or exposure is needed | State the minimum owner change and operational cost, obtain authority before provisioning; do not turn a local proof into an unsolicited hosting project. |
| Several small adapters become a new platform | Review total components and operating burden under RFC-0001; prefer KEEP native or DELETE/REPLACE unnecessary machinery. |

## Plan acceptance and next action

Approve the dependency order, native-first qualification, ownership/parallelism and staged evidence checkpoints. This approves a plan for reaching the product criteria, not feasibility already established or unspecified custom implementation. Then create/reuse only the first ready native Tasks under35 after a fresh duplicate check, with precise bounds and later execution approval. Follow-on implementation tasks are detailed only once qualification settles their real surface; independent paths need not wait for an unrelated block.
