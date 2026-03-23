# Copilot Instructions For Pull Request Reviews

This repository is the VolkerWessels organization-level `.github` repository. It is not an application codebase. Most pull requests here change shared GitHub governance assets such as pull request templates, documentation, profile content, and ownership rules.

When reviewing pull requests in this repository, prioritize correctness of GitHub behavior, maintainability of the repository structure, and governance impact over conventional application-level concerns.

## Review Priorities

Review changes in this order:

1. GitHub behavior correctness
2. Ownership and approval model integrity
3. Consistency of documentation and template guidance
4. Repository structure compatibility with GitHub conventions
5. Content quality, clarity, and completeness

## Repository-Specific Expectations

Assume the following unless the pull request clearly changes the design intentionally:

- Pull request templates that must be selectable in GitHub should remain flat under `.github/PULL_REQUEST_TEMPLATE/`.
- Team-specific documentation may live in subfolders under `.github/PULL_REQUEST_TEMPLATE/teams/`.
- Template selection in the GitHub web UI can be preselected with the `template=<file-name>` query string.
- Automated pull request creation through CI/CD, `gh pr create`, or the GitHub API should load template file contents into the pull request body instead of assuming GitHub will switch templates automatically.
- Ownership delegation is controlled through `.github/CODEOWNERS` and only becomes enforceable when combined with branch protection or repository rulesets.
- The repository profile content under `profile/` should remain accurate, professional, and suitable for organization-wide visibility.

## What To Check In Pull Request Template Changes

When a pull request changes files in `.github/PULL_REQUEST_TEMPLATE/`, verify all of the following:

- New selectable templates are placed directly in `.github/PULL_REQUEST_TEMPLATE/` unless there is a clear and justified reason not to.
- Template file names are explicit, stable, and aligned with team naming conventions such as `cct-*` or `vwid-development-*`.
- Team-specific README files document when to use each template and how to reference that template in both interactive GitHub flows and CI/CD automation.
- The generic README in `.github/PULL_REQUEST_TEMPLATE/README.md` stays generic and does not absorb team-specific operational detail that belongs in team documentation.
- Default fallback templates exist where a team-specific template family exists.
- Added templates do not duplicate another template with only trivial wording differences.
- Template content asks for evidence that matches the change type, for example rollout, rollback, validation, risk, root cause, or release evidence where appropriate.

Flag issues when:

- A template intended for GitHub selection is moved into a nested folder.
- A team-specific convention is documented only in a generic README.
- A new template is added without a clear use case or overlaps too much with an existing template.
- CI/CD guidance implies that the GitHub API or `gh pr create` will auto-select a template by filename without explicitly providing the body content.

## What To Check In CODEOWNERS Changes

When a pull request changes `.github/CODEOWNERS`, verify all of the following:

- New governed paths are actually covered by an owner rule.
- The rule order is intentional. Remember that the last matching CODEOWNERS rule wins.
- Catch-all governance rules are not accidentally weakened by a broader later rule.
- Team-specific overrides remain narrower than the default ownership rule.
- New template families and team documentation folders have matching ownership entries.
- Team names and slugs are valid for the GitHub organization and use the correct casing and slug spelling.

Flag issues when:

- A new path is introduced without a matching ownership rule where ownership should clearly exist.
- A catch-all owner is unintentionally overridden.
- A team slug appears misspelled or inconsistent with existing naming.
- The pull request assumes CODEOWNERS alone enforces approval requirements without corresponding repository rules.

## What To Check In Documentation Changes

When a pull request changes README or markdown documentation, verify all of the following:

- The documentation reflects actual repository behavior and current file locations.
- Examples use real file names that exist in the repository.
- Guidance about template selection distinguishes between the web UI query parameter approach and CI/CD automation behavior.
- Team-specific guidance is kept in the relevant team README instead of the generic README.
- Wording is clear enough for maintainers and contributors who are not deeply familiar with GitHub template internals.

Flag issues when:

- Documentation references files, teams, or paths that do not exist.
- Generic and team-specific documentation contradict each other.
- Instructions are ambiguous about whether template selection happens through URL query parameters or by populating the PR body in automation.

## What To Check In Profile Changes

When a pull request changes content under `profile/`, verify all of the following:

- External links are correct and intentional.
- The content is appropriate for organization-wide public display.
- Branding references, images, and wording match the repository's purpose.

## Review Style

When reviewing pull requests in this repository:

- Focus on behavioral and governance risks first, not cosmetic wording preferences.
- Prefer small, precise findings that explain why a change may break GitHub behavior or governance expectations.
- If a change is structurally valid, avoid requesting unnecessary wording churn.
- Call out missing ownership, incorrect path placement, misleading automation guidance, and inconsistent template taxonomy as the highest-value findings.
- If no meaningful issues are found, say so explicitly and note any residual risk such as missing branch protection verification.

## Non-Goals For Reviews In This Repository

Do not over-index on typical application review concerns unless the pull request actually adds executable code. In most cases, performance, runtime complexity, and unit test coverage are not the primary review dimensions here.