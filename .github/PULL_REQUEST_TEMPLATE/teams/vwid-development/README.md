# VWID Development Pull Request Templates

Use the VWID Development template that best matches the delivery or maintenance scenario.

Recommended usage:

- `vwid-development-default.md`: fallback when none of the specialized templates below clearly fits
- `vwid-development-feature.md`: feature work or product enhancement
- `vwid-development-bugfix.md`: non-urgent defect corrections
- `vwid-development-hotfix.md`: urgent production fixes or incident-driven changes
- `vwid-development-release.md`: coordinated releases or deployment-focused pull requests
- `vwid-development-dependency-update.md`: library, framework, tooling, or platform dependency updates

Template reference examples:

- `?template=vwid-development-default.md`
- `?template=vwid-development-bugfix.md`
- `?template=vwid-development-release.md`

How to call a specific template:

- Interactive GitHub web flow: open the repository compare or new pull request URL and append the `template` query parameter with the exact file name, for example `?template=vwid-development-bugfix.md`.
- Deep-linking from internal tools or release notes: point users to a PR URL that already includes `template=<file>` so the correct template is preselected.
- CI/CD or automation flow: when a pipeline, script, or bot creates the pull request through `gh pr create` or the GitHub API, read the chosen template file and submit that content as the PR body. The automation path should treat the template as source content, because the API does not select UI templates by query parameter.

CI/CD example approach:

- Map workflow conditions to template files, for example hotfix pipelines use `vwid-development-hotfix.md` and dependency bots use `vwid-development-dependency-update.md`.
- Read `.github/PULL_REQUEST_TEMPLATE/<template-file>` during the workflow.
- Pass that file to `gh pr create --body-file ...` or send it as the `body` field through the GitHub REST API.

Guidance:

- Prefer the most specific template available because it improves reviewer focus.
- Use the default fallback template only when the change combines multiple categories or does not fit an existing specialized template.
- For bugfix and hotfix pull requests, include the root cause and the exact validation that proves the issue is resolved.
- If the PR is created from CI/CD, make the template decision in the workflow logic so the resulting PR body is predictable and consistent.