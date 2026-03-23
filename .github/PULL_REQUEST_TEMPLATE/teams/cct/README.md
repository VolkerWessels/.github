# CCT Pull Request Templates

Use the CCT template that best matches the operational or delivery context of the change.

Recommended usage:

- `cct-default.md`: fallback when none of the specialized templates below clearly fits
- `cct-feature.md`: feature delivery or implementation work
- `cct-operational-change.md`: infrastructure, platform, CI/CD, or configuration work
- `cct-release.md`: coordinated releases or deployment-focused pull requests
- `cct-security-change.md`: hardening, access changes, secret rotation, or vulnerability remediation
- `cct-dependency-update.md`: package, module, image, or platform dependency updates

Template reference examples:

- `?template=cct-default.md`
- `?template=cct-operational-change.md`
- `?template=cct-security-change.md`

How to call a specific template:

- Interactive GitHub web flow: open the repository compare or new pull request URL and append the `template` query parameter with the exact file name, for example `?template=cct-operational-change.md`.
- Deep-linking from documentation or portals: publish links that already contain the `template=<file>` query string so contributors land on the correct PR form.
- CI/CD or automation flow: when a pipeline, script, or bot creates the pull request through `gh pr create` or the GitHub API, load the desired template file and use its contents as the pull request body. The API creates the PR body, but it does not switch templates in the same way as the web UI query parameter.

CI/CD example approach:

- Select the template file based on the pipeline context, for example release branches use `cct-release.md` and dependency update jobs use `cct-dependency-update.md`.
- Read `.github/PULL_REQUEST_TEMPLATE/<template-file>` in the automation step.
- Submit that content as the PR body in `gh pr create --body-file ...` or the equivalent GitHub REST API field.

Guidance:

- Prefer the most specific template available because it produces better review context.
- Use the default fallback template only when the change spans multiple categories and no single specialized template fits.
- Include concrete validation evidence for any change that affects shared services, deployment pipelines, or security posture.
- If you need deterministic template selection in automation, choose the template file explicitly in the workflow logic rather than relying on a reviewer to pick one manually.