# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Status

Repository is freshly bootstrapped — no solution or projects yet. When code is added, extend this file
with build/test commands (e.g. `dotnet build`, `dotnet test --filter "FullyQualifiedName~Name"`) and
an architecture overview.

## Branching workflow (GitFlow without `develop`)

- `main` is the only long-lived branch; it must stay releasable. It is protected on GitHub:
  no direct pushes, no force-push, no deletion, linear history.
- Branch from `main` using prefixes: `feature/<name>`, `fix/<name>`, `hotfix/<name>`, `chore/<name>`,
  optional `release/<version>` for stabilization. Never create a `develop` branch.
- Merge back through a pull request (squash or rebase; merge commits disabled). Remote branches are
  deleted automatically after merge.
- Releases: annotated tag `vX.Y.Z` on `main` (`git tag -a v1.2.3 -m "..." && git push origin v1.2.3`).

## Code review

For C#/.NET code review, refactoring advice, or library audits, use the user-level skill
`dotnet-code-quality-review` (installed in `~/.claude/skills/dotnet-code-quality-review-skill`, not
vendored into this repo).
