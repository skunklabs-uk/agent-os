[🇮🇹 Italiano](README.md)

# Software Factory

**Status:** Active. English translation of [README.md](README.md); the Italian page remains the authoritative source. Keep this translation aligned when updating the source. Linked documents retain their original language.

This repository defines and validates a process for AI-assisted software development.

The goal is to reduce repetitive manual work, keep decisions in the repository, and gradually automate only activities that are mature enough, verifiable, and feasible with the available tools.

## Active documents

- [`requirements/REQ-0001-software-factory.md`](requirements/REQ-0001-software-factory.md)  
  The project's original requirement.

- [`rfcs/RFC-0001-principles.md`](rfcs/RFC-0001-principles.md)  
  The founding principles that govern the project.

## Documents under validation

- [`software-factory.md`](software-factory.md)  
  The Software Factory's minimal functional workflow.

- [`backlog/decision-review-process.md`](backlog/decision-review-process.md)  
  A proposed review process to validate against further use cases.

## Operating rules

Instructions for working in this repository are defined in [`AGENTS.md`](AGENTS.md).

Keep the repository lean. Introduce new documents, directories, workflows, or automation only when they address a real need and cannot be avoided or consolidated.

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
