# Spec: mobile-control

**Status:** Active — approved by the Product Owner on 2026-10-12 at `f55c2b7838104770766825e57b68129b019e951e`, together with the shared provider contract. Plan preparation authorized; implementation requires its subsequent gates.
**Module:** mobile-control.
**Parent:** [approved capability map](CAPABILITY-MAP-agent-team.md).
**Depends on:** accepted [team-execution](SPEC-team-execution.md), delivered in [PR51](https://github.com/skunklabs-uk/agent-os/pull/51).
**Mission:** [35](https://github.com/skunklabs-uk/agent-os/issues/35). English is authoritative; review with the Product Owner is in Italian.

## Objective and assumptions

The Product Owner supervises the real mission running on NOVBSCWOLaulMaU from their phone or tablet browser: start/resume work, see coordinator and specialist progress, answer questions, steer/interrupt and make scoped decisions. Success requires the actual device and reachable host; a desktop viewport or localhost demonstration is insufficient.

The approved map selects a browser, not a new native application. No browser/device identity, remote network access or existing authentication is assumed proven. Retain OMP18.8.7 and approved skill pins as the qualified baseline until a necessary change is separately assessed. This specification proposes behavior, not a new service or selected hosting architecture.

## Required behavior

1. Show which machine, repository and mission are controlled; prevent silent attachment to another mission or creation of a competing coordinator.
2. Start an authorized mission and resume an existing one through the browser, preserving method, ownership and pending prerequisites. A host-only step is a disclosed gap, not completion of remote start/resume.
3. Show coordinator and relevant specialists, current work, blocks, questions, returned artifacts and exact revisions where relevant. Delayed or disconnected state is visibly distinguished from current state.
4. Allow answers, direction changes, interruption requests and scoped approvals/rejections using the [single provider contract](SPEC-team-execution.md#shared-remote-consumer-contract). The user can distinguish acknowledgement from actual execution or stoppage.
5. On disconnection, retain pending decisions at the host; after reconnect, show their current identity/status before accepting a response. Duplicate responses, stale links and changed sessions cannot authorize unrelated work.
6. Support touch and keyboard access, legible compact layouts and visible mutation consequences. Use authentic application screenshots for evidence; keep secrets and control URLs out of public artifacts.

## Candidate support and limits

Read-only preparation examined [native collab at b07a1c1](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/collab.md): browser sharing and guest intervention exist, but host session transitions and guest command restrictions require verification. Documentation does not prove the user's remote journey. [omp-web package at0acce624](https://github.com/ddallabenetta/omp-web/blob/0acce6240b27eb7d44d5c9b78187bd95e01270f8/package.json) is another candidate; compatibility with the qualified runtime remains untested. No candidate is selected here and no install/update is authorized by specification approval.

Prefer existing native facilities that satisfy the criteria. If a required action is missing, report the precise gap and minimum justified extension during Plan; do not silently reduce the remote-control requirement. Hosting must be reachable from the actual device. A new relay, ingress, service, VM or cost requires authority in its owning repository before provisioning. Do not reopen the unrelated VM/OMX PoC merely to host this work.

## Commands and project structure

This phase is Markdown only. From the Agent OS repository:

```bash
git diff --check
git diff -- SPEC-mobile-control.md SPEC-team-execution.md CAPABILITY-MAP-agent-team.md
```

No application build/server command is applicable before runtime selection. Plan must provide exact executable commands, owned paths, access and resource limits before trials; speculative startup commands are not acceptance evidence. This root specification owns mobile requirements; the provider owns the shared contract; mission35 owns phase/decision state. No new tracker or implementation directory is created.

## Style and testing strategy

Use plain state labels, original method names and real revision identifiers. Example user-facing status, not a new API schema:

```text
Mission35 / coordinator / waiting for decision
Requested action: approve SPEC-mobile-control at <revision>
Connection: disconnected — decision outcome not yet confirmed
```

Required tests use the selected native UI on the actual phone/tablet and the user's remote connection. Record device/browser/host versions, exact candidates, observations and privacy-screened screenshots. Add code tests only if an approved extension introduces logic. Do not replace device testing with viewport emulation or replay team-execution proofs.

## Acceptance scenarios

| Scenario | Required observation |
|---|---|
| Remote start and resume | Actual device starts permitted work and resumes the same mission; no host intervention concealed. |
| Team visibility | Coordinator and specialist activity, blocks and results match host state. |
| Question and approval | User answers and approves/rejects the identified pending request; host applies it once within scope. |
| Steering/interruption | Target acknowledges the request; actual outcome is displayed without claiming instantaneous termination. |
| Reconnection | Disconnect with a pending decision, reconnect, resolve once; stale/duplicate response cannot target another mission. |
| Access and usability | Unauthorized mutation rejected; user completes the flow on touch display, including viewing evidence, without hidden controls or leaked credentials. |

Every scenario needs actual evidence before module acceptance. Product Owner smoke is recorded only when reported or observed from their device.

## Boundaries and open prerequisites

- **Always:** preserve the provider contract, source-method gates, one coordinator and existing project authority; prefer the smallest sufficient native solution.
- **Ask first:** product-scope changes, new access/costs/provisioning, owner-repository changes beyond approved scope, and deployment after smoke.
- **Never:** claim desktop testing as user-device proof, weaken authentication, expose control links/secrets, or treat specification approval as execution authority.

Specification approval and subsequent Plan continuation are acquired; readiness is current. Device/browser and remote access details are required before the actual trial, not to approve these requirements. Runtime choice, exact test commands and any minimum hosting change belong to Plan. The [current plan](tasks/plan.md) prepares the next phase; Tasks/Implement require their own approval gates.
