# coderabbit

Central [CodeRabbit](https://coderabbit.ai) configuration for the jimisola
account's repositories
([central configuration](https://docs.coderabbit.ai/configuration/central-configuration)).

`.coderabbit.yaml` at the root of this repository applies to every repository
of the account that has no `.coderabbit.yaml` of its own. The repository
name must stay `coderabbit`.

Verified on a PR run: CodeRabbit lists "Central YAML (inherited)" as a layer for a
personal account.

## Defaults

- `chill` review profile, advisory only (no requested changes).
- Summary in the walkthrough comment; the PR body is left alone.
- Renovate, Dependabot and GitHub Actions bot PRs are not reviewed.
- Draft PRs are reviewed too. Comment `@coderabbitai review` to ask for a fresh review.
- Lockfiles are skipped.

## Repository rules

A repository that needs its own rules adds a small `.coderabbit.yaml` with
`inheritance: true` and only its own path filters and path instructions.
Scalars there win, objects merge key by key, lists combine, and
`path_instructions` match by path
([inheritance and merging](https://docs.coderabbit.ai/configuration/inheritance-and-merging)).
Without `inheritance: true` that file replaces these defaults entirely.

A repository with no file of its own takes its code guidelines (`AGENTS.md`,
`CLAUDE.md`) from this repository, not from itself. Every repository therefore
carries its own `.coderabbit.yaml`, even if it only sets `inheritance: true`.

To check what applies, comment `@coderabbitai configuration` on a PR.

A change here changes code review for every repository of the account.
