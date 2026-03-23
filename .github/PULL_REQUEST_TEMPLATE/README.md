# Pull Request Templates

This repository provides multiple pull request templates for the VolkerWessels organization-level `.github` repository.

Available templates:

- `cct-default.md`
- `cct-feature.md`
- `cct-operational-change.md`
- `cct-release.md`
- `cct-security-change.md`
- `cct-dependency-update.md`
- `vwid-development-default.md`
- `vwid-development-feature.md`
- `vwid-development-bugfix.md`
- `vwid-development-release.md`
- `vwid-development-dependency-update.md`
- `vwid-development-hotfix.md`

When creating a pull request in a repository that inherits community health files from this repository, GitHub will expose these templates only if that repository does not define its own pull request templates.

If you need to link directly to a specific template, use the `template` query string parameter with the file name.

Guidance:

- Teams should open pull requests with the template that best matches the type of change they are making.
- If no specialized template fits, use that team's default fallback template.
- Direct template selection can be enforced in links, for example: `?template=cct-default.md` or `?template=vwid-development-default.md`.
- Team-specific conventions are documented in the team READMEs under `teams/cct/README.md` and `teams/vwid-development/README.md`.

The template files remain flat in this folder so GitHub can discover them reliably. Team documentation is stored separately to keep this README generic.