# Agent Skills

[中文](README.md) | English

Personal Agent Skills for any agent that supports `SKILL.md` (Codex, Claude Code, GitHub Copilot, and others).

## Available skills

| Skill | Category | Purpose |
|---|---|---|
| [`github-hygiene`](skills/engineering/github-hygiene/SKILL.md) | Engineering | Git / GitHub rules: no AI contributor accounts, no AI attribution, uniform `[XX]` commit format. |
| [`more-ui`](skills/engineering/more-ui/SKILL.md) | Engineering | Fix UI grid, alignment, spacing, sizing, and responsive layout issues with minimal changes. |
| [`pure-output`](skills/writing/pure-output/SKILL.md) | Writing | Deliver only usable artifacts; never invent facts; mark DRAFT / PARTIAL / BLOCKED when high-risk information is missing. |

## Install

Install all skills:

```bash
npx skills add BranchCrypto/agent-skills
```

Install one skill:

```bash
npx skills add BranchCrypto/agent-skills --skill github-hygiene
```

The repository is private; the CLI uses your Git or GitHub CLI authentication.
