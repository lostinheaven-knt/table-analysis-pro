# Publishing Notes

This repository is structured as an AgentSkill-style package.

## Release checklist

Before packaging or publishing:

- confirm `SKILL.md` frontmatter is valid
- keep `SKILL.md` focused and concise
- make sure every referenced file actually exists
- remove stale placeholders
- keep resource files directly useful
- ensure there are no symlinks in the package

## Current package contents

- `SKILL.md`
- `README.md`
- `LICENSE`
- `requirements.txt`
- `references/*.md`
- `scripts/README.md`

## Packaging intent

This repo is currently documentation-first.
If a local packaging tool is available later, package the skill from the repository root.

## Versioning suggestion

Use simple semver-style tags:

- `v0.1.0` — first publishable draft
- `v0.2.0` — meaningful content or reference expansion
- `v1.0.0` — stable, field-tested release
