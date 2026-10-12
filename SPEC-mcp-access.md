# Spec: mcp-access

**Status:** Active — approved by the Product Owner on 2026-10-12 at `f55c2b7838104770766825e57b68129b019e951e`, together with the shared provider contract. Plan preparation authorized; implementation requires its subsequent gates.
**Module:** mcp-access.
**Parent:** [approved capability map](CAPABILITY-MAP-agent-team.md).
**Depends on:** accepted [team-execution](SPEC-team-execution.md), delivered in [PR51](https://github.com/skunklabs-uk/agent-os/pull/51).
**Mission:** [35](https://github.com/skunklabs-uk/agent-os/issues/35). English is authoritative; review with the Product Owner is in Italian.

## Objective and assumptions

Use the Product Owner's actual ChatGPT client/account to delegate authorized work to the coordinator on NOVBSCWOLaulMaU, inspect progress/results and request interruption through supported MCP capabilities. Determine v1 inclusion from observed feasibility; do not defer MCP simply because mobile work exists.

Availability in this account/client, supported authentication, network reachability and long-operation behavior are currently **unverified**. A working server, SDK/RPC endpoint or another MCP client is not proof that this user can use the flow. No unsupported ChatGPT UI automation or silent switch to another client is permitted.

## Required behavior

1. Expose only the operations needed to delegate within approved repository/scope, inspect mission and specialist status/results, answer applicable pending questions/decisions and request interruption. Preserve the [single provider contract](SPEC-team-execution.md#shared-remote-consumer-contract); a consumer cannot invent its own mission or approval ledger.
2. Confirm the exact destination machine and mission. Delegation to an existing mission reuses its coordinator; no duplicate task solely because a request or connection is retried.
3. Make long work observable after the initiating request returns or times out. Return a stable reference whose status/results can be retrieved; distinguish unknown outcome from failed work, and request acknowledgement from completed interruption.
4. Authenticate the authorized operator, limit accessible repositories/operations and reject unauthenticated or out-of-scope mutations. Never transfer operator credentials into chat or publish them with evidence.
5. Display exact pending action and consequences before applying a scoped decision. Maintain source-specific user-only invocation and approval rules; MCP transport does not waive them.
6. Recover after client reconnection without losing unresolved decisions or applying them twice. Surface an unsupported capability explicitly instead of pretending it succeeded.

## Feasibility during Specify

The existing read-only investigation identifies native OMP SDK/RPC as candidate building blocks, not an existing qualified MCP integration. The [qualified OMP source](https://github.com/can1357/oh-my-pi/tree/b07a1c146d0d12cfc855a2c65d52f892ef319040) and maintained MCP solutions must be compared against the actual client requirements before architecture selection. No new framework, custom server, persistent service or hosting choice is selected by this document.

| Required fact | Current evidence | Consequence |
|---|---|---|
| Actual ChatGPT client/account supports the required MCP operations | Not yet observed | Check the actual account/client and current official documentation; another client is insufficient. |
| Authentication and host reachability | No actual client-to-host MCP proof | Verify supported transport/auth and the minimum owner-authorized exposure before connecting. |
| Long operations, status/results and interruption | Native runtime facilities are candidates only | Exercise the full route on a harmless bounded mission after approval of executable scope. |
| Approval and reconnect behavior | Required provider behavior, not a proven client feature | Test real pending decisions, duplicate responses and reconnection. |

These gaps prevent a feasibility PASS and any implementation claim. Specification approval authorizes Plan preparation, not a decision to exclude MCP. If the actual client cannot support a required capability, preserve the observed reason and present an explicit include/limit/defer decision to the Product Owner before closing the module. Read-only feasibility can continue without waiting for mobile implementation; authenticated trials or new access require their applicable authority.

## Commands and project structure

This phase changes Markdown only. From the Agent OS repository:

```bash
git diff --check
git diff -- SPEC-mcp-access.md SPEC-team-execution.md CAPABILITY-MAP-agent-team.md
```

No server/build/test command can honestly be specified until the candidate and owner repository are selected. Plan must resolve exact versions, commands, owned paths, test resources and cost limits before executable trials. This root specification owns MCP requirements; team-execution owns the common contract; mission35 owns phase/decision state. No implementation folder, new repository or duplicate tracker is created.

## Style and testing strategy

Use explicit outcomes and exact mission references. Example semantic result, not a fixed wire schema:

```text
mission: <existing-owner-reference>
request: interruption acknowledged
observed-state: still running
pending: <unresolved-owner-decision>
```

Use actual supported client calls and bounded synthetic data in the approved test environment. Record client/account capability without secrets, host/runtime/candidate versions, request/result identity and observed behavior. Protocol/unit tests are added only for approved new logic; they cannot replace the end-to-end client test. Keep unknown, blocked, rejected, acknowledged and completed outcomes distinct.

## Acceptance scenarios

| Scenario | Required observation |
|---|---|
| Client connection | User's actual ChatGPT client authenticates to the authorized host surface; unsupported account/client limitation is evidenced. |
| Delegation | Permitted request reaches the sole coordinator with correct repository, scope and method; out-of-scope request is rejected. |
| Long work | Initial call returns or times out; the same mission's current progress and final result remain retrievable without duplicate execution. |
| Questions/decisions | Applicable pending request is identified, shown and resolved once within source-method authority. |
| Interruption | Request reaches the right mission; acknowledged and actual stopped/completed states are distinguished. |
| Reconnection | Current state and pending decisions recover; stale/replayed responses do not authorize another operation. |
| v1 decision | Actual feasibility evidence supports inclusion; any limitation or deferral is explicitly accepted by the Product Owner. |

## Boundaries and open prerequisites

- **Always:** use supported client interfaces, preserve the common contract and project gates, compare reusable maintained solutions before proposing custom code.
- **Ask first:** new access, costs, network exposure/provisioning, consumer permission changes, product-scope reduction or MCP deferral, and deployment after smoke.
- **Never:** automate the ChatGPT UI through unsupported mechanisms, claim a server test proves client support, reuse pilot spending limits, or deploy on specification approval.

Specification and shared-contract approval are acquired. The [current plan](tasks/plan.md) proceeds through delegated readiness and the later scoped execution gates. The actual client/account capabilities and permitted connectivity remain trial prerequisites; do not request secrets in chat. No implementation is selected, and MCP remains in scope until an explicit evidence-based decision changes it.
