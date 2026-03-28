# Repository Instructions

This repository publishes reusable agent skills. Keep release hygiene consistent across every change.

## Core Workflow

1. Create a branch with the `codex/` prefix for every change.
2. Make the skill or repo changes on that branch.
3. Update [CHANGELOG.md](CHANGELOG.md) under `Unreleased` before finishing the work.
4. Open a pull request into `main`. Do not rely on direct pushes to `main`.
5. After the pull request is approved and merged, cut a semantic version tag on `main`.
6. Push the tag so [.github/workflows/release.yml](.github/workflows/release.yml) publishes the GitHub release.
7. Verify the release exists and that the changelog still matches what shipped.

## Branch And Merge Rules

- Never work directly on `main`.
- Keep `main` linear. Prefer squash or rebase merge behavior that does not introduce merge commits.
- Do not bypass branch protection unless there is a concrete emergency.

## Changelog Rules

- Every user-visible repository change must be reflected in [CHANGELOG.md](CHANGELOG.md).
- Add new work to the `Unreleased` section while it is in progress.
- When tagging a release, move the shipped items from `Unreleased` into a new versioned section with the release date.
- Keep entries short and factual.

## Release Rules

- Use semantic version tags in the form `vX.Y.Z`.
- Use:
    - patch for fixes, wording updates, small repo/process improvements
    - minor for new skills, major expansions, or significant new templates/references
    - major only for breaking structural changes
- Tag from `main` after the merge is complete.
- Push the tag and confirm the automated release succeeded.

## Scope Checks

- Update [README.md](README.md) when the skill catalog, positioning, or repo usage changes.
- `CLAUDE.md` should remain a symlink to `AGENTS.md`. Update `AGENTS.md`, not the symlink target separately.
- Keep each skill's `SKILL.md` concise and keep deeper material in linked `references/` or `templates/`.
