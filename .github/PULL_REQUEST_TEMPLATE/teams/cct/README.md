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

Guidance:

- Prefer the most specific template available because it produces better review context.
- Use the default fallback template only when the change spans multiple categories and no single specialized template fits.
- Include concrete validation evidence for any change that affects shared services, deployment pipelines, or security posture.