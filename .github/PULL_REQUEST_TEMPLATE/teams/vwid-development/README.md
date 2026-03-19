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

Guidance:

- Prefer the most specific template available because it improves reviewer focus.
- Use the default fallback template only when the change combines multiple categories or does not fit an existing specialized template.
- For bugfix and hotfix pull requests, include the root cause and the exact validation that proves the issue is resolved.