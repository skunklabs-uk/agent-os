[🇮🇹 Italiano](README.it.md)

# Software Factory

**Status:** Active. This English README is the authoritative version. An [Italian translation](README.it.md) is available for convenience. Keep it aligned when updating this page. Linked documents retain their original language.

This repository defines and validates a process for AI-assisted software development.

The goal is to reduce repetitive manual work, keep decisions in the repository, and gradually automate only activities that are mature enough, verifiable, and feasible with the available tools.

## Active documents

- [`requirements/REQ-0001-software-factory.md`](requirements/REQ-0001-software-factory.md)  
  The project's original requirement.

- [`rfcs/RFC-0001-principles.md`](rfcs/RFC-0001-principles.md)  
  The founding principles that govern the project.

- [`PROMPT-HANDOFF.md`](PROMPT-HANDOFF.md): prompt and handoff classification policy and model-selection guidance for main and delegated tasks.

## Current mission

La missione #35 resta aperta. Homelab #2095 realizza un percorso upstream di
UI browser per OMP, alternativo ai tre accessi SSH e ancora in corso; non
equivale alla DoD più ampia di controllo mobile del team Agent OS. La
[capability map](CAPABILITY-MAP-agent-team.md) riporta stato e limiti. I moduli
workflow-profiles e team-execution mantengono la loro accettazione limitata.

## Documents under validation

- [`software-factory.md`](software-factory.md)  
  The Software Factory's minimal functional workflow.

- [`backlog/decision-review-process.md`](backlog/decision-review-process.md)  
  A proposed review process to validate against further use cases.

## Operating rules

Instructions for working in this repository are defined in [`AGENTS.md`](AGENTS.md).

Keep the repository lean. Introduce new documents, directories, workflows, or automation only when they address a real need and cannot be avoided or consolidated.

### Prompt, handoff, and model-selection guidance

[`PROMPT-HANDOFF.md`](PROMPT-HANDOFF.md) is the authoritative policy: each generated prompt or handoff must begin with YAML front matter, except conversational replies; it also guides model selection when the client allows it. It is a standalone native instruction file: Codex can load it as `$CODEX_HOME/AGENTS.md`, and OMP as `RULES.md` in the active agent directory, including each named profile. Use a persistent checkout and preserve existing instructions instead of replacing them. OMP task subagents do not inherit `AGENTS.md`; the native `RULES.md` is required for their coverage. The project scaffold refers to the policy but does not synchronize existing projects.

Update the persistent checkout through the repository's normal reviewed workflow; do not remove or move it while instruction paths point to it. Check each runtime's effective home and profile and verify loading in a new session after changes. Existing Codex sessions must be reopened; OMP reloads rules on a new session or `/new` or `/clear`. To remove the installation, first inspect and remove only links created for it, preserving pre-existing instructions. These instructions guide model behavior; they do not enforce it.

In the Developer Workspace, the three workers link to `/workspaces/.agent-os-prompt-policy/PROMPT-HANDOFF.md`; the shared checkout tracks `main`. Merging a PR does not update it automatically. Before advancing it, verify the approved revision, local changes and other writers; fetch and fast-forward `main` without force. Compare the policy bytes with the approved revision and verify the links and loading on the workers. Do not overwrite local changes. The shared checkout and private homes must both be available to reconstruct the links.

For a new Developer Workspace home, first apply the operator's existing personal chezmoi source, after reviewing its diff. Then reuse chezmoi with the separate native source state in `config/workspace-policy/`; it contains only these three links and does not modify the personal source. Use this procedure only on `developer-workspace-0`, `developer-workspace-worker2-0` or `developer-workspace-worker3-0`, not WSL. Ensure that the shared checkout exists at the path above and contains the approved integrated policy. Inspect the effective Codex home and OMP profiles, all parent directories and all three target paths. Resolve any parent symlink and verify that its destination is an intended writable directory; preserve the parent link. Stop for a dangling or unintended parent. Check that the personal source neither manages these target files nor uses an `exact_` parent that would remove them. This procedure covers the observed default Codex home and OMP `default` and `personal` profiles only.

The targets are `$HOME/.codex/AGENTS.md`, `$HOME/.omp/agent/RULES.md` and `$HOME/.omp/profiles/personal/agent/RULES.md`.

On the three workers, the observed interactive entry point selects `personal`. No current use of the unnamed OMP profile was observed, and a clean login shell could not select a default model; the unnamed profile is therefore outside the verified-use scope. Its link is provisioned, but loading in a clean session is not verified. If that profile becomes used, verify it separately without changing authentication or providers as part of this policy.

Create missing parent directories with mode `0700`, one level at a time without changing existing directories. Treat a dangling symlink as an existing target. Run `chezmoi --source /workspaces/.agent-os-prompt-policy/config/workspace-policy diff --include=symlinks` with **only explicit target paths verified absent**, then use the same source, target list and `--include=symlinks` for `apply`. Never apply this source without target paths or with `--force`: a normal chezmoi apply can replace an existing unmanaged file. If a target exists, leave it out and integrate the policy with its existing instructions separately; verify loading before considering that target complete. The normal personal chezmoi apply does not invoke this separate source state; repeat the targeted procedure when rebuilding a home. A recreated home also requires the shared policy checkout to be available.

#### Classification rollout: bounded WSL behavior verification closeout

Status closed on 2026-11-13 for the bounded prompt-behavior verification requested by the user. This section owns rollout status; [PR #70](https://github.com/skunklabs-uk/agent-os/pull/70) retains implementation history, [PR #74](https://github.com/skunklabs-uk/agent-os/pull/74) the earlier reconciliation, and [PR #75](https://github.com/skunklabs-uk/agent-os/pull/75) the Arch evidence update. This closeout does not change the policy or separate model-selection guidance.

| Destination | Distribution | Loading | Observed behavior |
| --- | --- | --- | --- |
| Developer Workspace | Verified on 2026-11-09 at Agent OS `ce3dbbdd6f42cb79cf55446c23c8a516d769fd0d`, codex-skills `1f10c1d5ed8159718b3915fb9dd886aaef8366cb`; explicit home reconstruction was exercised | Codex 0.167.0 and OMP 18.18.3 `personal`, bounded evidence in #70 | Separate prompt front matter, conditional metadata, conversational exemption and actual OMP delegation observed; not enforcement |
| WSL Arch | Six managed targets were reported in the retained rollout evidence; a later local `chezmoi verify` exited 1 with a configuration warning. New-home reconstruction not exercised | Historical Codex rollout ID remains unreconciled. Historical OMP `personal` loading was reported; other profiles are not qualified | PASS for the bounded new-session prompt: separate front matter on each generated prompt and no front matter on the conversational reply. Historical Codex and OMP child failures were not repeated |
| WSL Ubuntu | Not established in this closeout | NON VERIFIABLE with the available native diagnostic: `codex debug prompt-input` output did not expose the loaded instruction-file contents. The model's self-report is not independent loading evidence | PASS for the bounded new-session response: separate front matter on each generated prompt and no front matter on the conversational reply |

Historical Arch report received from the local executor through the user: Arch WSL2 identity root, home `/root`; Codex 0.167.1 with `CODEX_HOME=/root/.codex`; OMP 18.18.8. Prior `/home/iingenito` findings do not describe this installation; that account was not found in the inspected account database. `~/.codex-work` was available but not observed in active processes. OMP `personal` was explicitly selected for verification, not established as the habitual profile. `default`, `novigo-openai`, and `novigo-litellm` targets were reported managed; actual use/loading was not demonstrated. `work` had no RULES target; the selector alone does not prove it unused.

### Arch evidence and historical limits

- Distribution (historical executor report): six regular files at `/root/.codex/AGENTS.md`, `/root/.codex-work/AGENTS.md`, `/root/.omp/agent/RULES.md`, and the `personal`, `novigo-openai`, `novigo-litellm` profile agent `RULES.md` paths. The report cites source checkout `/root/projects/personal/dotfiles`, commit `68df79feee7a1f825a9785c607019c91e308e611`, and targeted `chezmoi verify` exit 0; local changes in dotfiles `README.md` and `dot_bashrc.d/omp-profile.sh` were preserved. A later targeted `chezmoi verify` invocation exited 1 with a configuration warning and no detailed cause in the returned output. Persistence is therefore not confirmed by this closeout; a clean-home reconstruction was not run.
- Codex loading: the historical executor report says rollout session `01a1d19d-7cc3-7300-8b61-a36d79d6af50`, record 8, contains the initial classification instructions. An earlier result gave a different session ID, `01a1d19d-7cc3-7300-b3db-2c7db5262a6c`; no direct artifact readback resolved the discrepancy. This reference remains unresolved and was not reopened for this bounded closeout. The behavior rollout `01a1d19e-a8dd-7c31-9006-e5fffe7076b1`, record 15, reportedly emitted two prompts without front matter; its record 8 contained the policy and record 12 the generic two-prompt request. The earlier targeted inspection found no direct conflicting instruction; cause remains unknown.
- OMP loading: with 18.18.8, explicit `personal`, a native RPC `get_state` reportedly returned `systemPrompt` containing the classification rules. The child transcript for delegation `01a1d1ac-8a3b-7591-beb4-1f7330754c16`, `PurringYak.jsonl` record 4, reportedly contained the policy in `session_init`. Upstream v18.18.8 documentation reportedly confirms named-profile RULES resolution and task-subagent inheritance. The executor states the child output at `PurringYak.md` lacked front matter; the parent task call also returned it without adding front matter. Parent rollout record 8 had independently formatted `context` and task arguments. Record 13's additional empty-task call failed at record 15; it is not evidence of a successful second delegation.
- Codex conversation response `ricevuto` without YAML was the required conversational exemption. The historical two-prompt sample failed; it was not repeated, and the separate bounded prompt session recorded above passed. No retries or corrective prompting were performed.

The 2026-11-12 report recorded the shared consumer checkout at `ce3dbbdd6f42cb79cf55446c23c8a516d769fd0d`, Agent OS `main` at `f9de648029380a831cd79f016c7398657e55e47d`, and codex-skills at `1f10c1d5ed8159718b3915fb9dd886aaef8366cb`. Those are historical references, not current consumer readback. This closeout does not advance consumer checkouts or distribute separate model-selection guidance.

The user selected a bounded closeout based on one prompt session per WSL destination. Historical failures and unresolved loading references above are retained for provenance only; they were not repeated and are not gates for this bounded result. Ubuntu policy distribution and native loading remain outside the evidence available here. The policy guides model behavior and is not technical enforcement. No further WSL tests are part of this closeout.


## Serial Developer Workspace connection

An assignment requires permitted repositories and threads, the exact branch and head commit, and the current prompt. A single serial consumer executes the task in an isolated checkout.

Reporting and publication are separate: a change requires `publish_paths` listing the exact authorized files and a draft PR in the same repository. The parent publishes; the coordinator re-reads the SHA and diff and completes RETURN. The child does not commit, push, merge, or roll out changes.

Agent OS contains documentation and the bootstrap script [`scripts/init-project.sh`](scripts/init-project.sh), with tests in [`scripts/test-init-project.sh`](scripts/test-init-project.sh). The repository contains no GitHub Actions workflows. Tests verify the bootstrap of new projects; documentation-only changes require technical diff review and a clarity review, without running the bootstrap.

Agent OS does not distribute an HTTP application, so a web preview does not apply to the repository's documentation adoption. Diff review and RETURN are still required. This note describes the repository's adoption within the connection and does not certify completion of REQ-0001 as a whole.

For enrollment, GitOps selection, recovery, and persistent state, consult the owning sources: the [connection runbook](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md) and the [Homelab README for the runtime lifecycle](https://github.com/skunklabs-uk/homelab/blob/main/gitops/apps/developer-workspace/README.md).

## Initial scaffold for new repositories

The project scaffold lives in `templates/project/`. It contains the minimum operating rules, the documentation index, a pointer to execution state, and templates for issues, pull requests, and waves.

```text
agent-os
      │ scripts/init-project.sh
      ▼
new local project
      ├── creates directory (if needed)
      ├── git init
      ├── copies templates/project/
      └── independent project
                └── origin (optional)
```

The bootstrap provides a common starting point, not a permanent connection to Agent OS.

Reusable skills are not part of the project scaffold: their authoritative source is the [codex-skills repository](https://github.com/skunklabs-uk/codex-skills). Projects must install them through symlinks using `scripts/install-project.sh` and must not track local copies.

To create a new local project from the scaffold:

```bash
./scripts/init-project.sh /path/to/project
./scripts/init-project.sh --no-prompt /path/to/project
./scripts/init-project.sh --remote git@github.com:user/project.git /path/to/project
```

To preview what would be created without changing the destination:

```bash
./scripts/init-project.sh --dry-run /path/to/project
./scripts/init-project.sh --dry-run --remote git@github.com:user/project.git /path/to/project
```

The script creates the directory if it is missing, runs `git init` if the destination is not already an independent Git repository, and copies all files from `templates/project/`.

The destination is accepted only if it does not exist, is empty, contains only `.git`, or is a project already initialized with the same scaffold files. If contents differ or additional files exist, the script exits with `ERROR` before changing the destination.

The remote is optional. By default, no remote is configured; in an interactive terminal, the script may offer to configure `origin`. `--no-prompt` disables all questions. `--remote` configures `origin` directly with the supplied URL, without creating a remote repository or pushing. The user can also configure `origin` later with standard Git commands.

The script does not create commits or branches, push, or change global Git configuration. Existing remotes in an empty Git repository remain unchanged.

After initialization, copied files belong to the new repository. Future changes to `templates/project/` apply only to new initializations and do not automatically synchronize existing projects.

## Aligning an existing project

Do not use `init-project.sh` to overwrite a populated repository. To align a local `AGENTS.md` with the current template:

1. Read `templates/project/AGENTS.md`, the local `AGENTS.md`, and the project's `Active` sources governing the current work.
2. Compare how the rules behave, not just their wording, and preserve local constraints required by the domain.
3. Resolve factual differences or differences with a single clear correction directly.
4. When a difference changes authority, autonomy, stop conditions, or mission continuity, use `grill-with-docs` or `interview-me` to show the Product Owner the current behavior, proposed behavior, and minimal patch, and ask them to confirm the choice.
5. Apply only approved changes, without replacing the entire local `AGENTS.md` with the template.
6. Verify that each stop condition has a clear scope, a blocked task does not automatically stop the mission, and already authorized and determined next steps continue without mechanical confirmations.

The first alignment must remain manual. Automating comparison or patching makes sense only after observing several cases where the process is repeatable without losing necessary local rules.
