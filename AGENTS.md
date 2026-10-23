# Repository guidance

## Purpose

This repository is the canonical source for BranchCrypto's Agent Skills.

## Skill design

- Keep each skill independently installable.
- Use `SKILL.md` for decisions and steps. Put conditional detail in linked references.
- Keep skill directory names identical to the `name` in each frontmatter.
- Do not add scripts, tests, or documents a skill does not need.

## Repository structure

- `skills/engineering/` contains engineering and Git/GitHub workflows.
- `skills/writing/` contains writing and content-output skills.
- `skills/in-progress/` contains skills that are not yet ready for installation.
- `skills/deprecated/` contains retired skills kept for reference.

## Delivery

- Keep the primary checkout on `main`.
- Commit with the format defined by `github-hygiene`.
- Never add an AI account as a contributor and never add AI attribution to commits.
