---
name: github-hygiene
description: >-
  Enforce GitHub contributor restrictions and standardized [XX] commit message
  conventions. Use whenever the task involves GitHub or Git operations—commits,
  amend, push, pull requests, branches, collaborators, repository settings, or
  workflows.
---

# GitHub Hygiene

Apply these rules for every GitHub or Git operation, regardless of repository, branch, or task context.

## When to use

Apply when the task involves any of:

- Creating or modifying GitHub repositories
- Cloning or working with Git repositories
- Creating, amending, or pushing commits
- Creating or updating pull requests
- Managing branches, workflows, collaborators, or repository settings
- Any other operation that changes or interacts with a GitHub repository

## 1. Code agent contributor restrictions

Never add the code agent as a GitHub contributor or collaborator.

Do not:

- Invite an AI/code-agent account as a repository collaborator
- Add an AI/code-agent account to a GitHub organization or repository
- Grant repository permissions to an AI/code-agent account
- Change repository permissions to make an AI/code-agent account a contributor
- Create or use a dedicated AI-agent GitHub account as the contributor identity

This applies to all AI/code-agent identities, including Cursor, Codex, ChatGPT, other AI coding agents, automated coding bots, and any account whose purpose is to represent the coding agent.

Operate using the user's existing Git/GitHub identity unless the user explicitly requests a different human identity.

## 2. Commit author and identity restrictions

Commits must not identify the code agent as the author, co-author, or generator.

Do not add AI-agent attribution to the commit subject, body, trailers, Git author metadata, or Git committer metadata.

Prohibited unless explicitly required by the user's existing repository configuration and cannot be changed safely:

```text
Co-authored-by: Cursor
Co-authored-by: Codex
Co-authored-by: ChatGPT
Generated-by: AI
Generated-by: Codex
Generated-by: Cursor
AI-generated
Generated with Cursor
Generated with Codex
Generated with ChatGPT
```

Do not intentionally configure Git identity to represent the code agent.

## 3. Commit message format

Unless the user explicitly specifies another format, every commit message must follow:

```text
[xx]xxxxx
```

Where:

- `xx` is a predefined two-letter uppercase prefix
- The prefix is enclosed in square brackets
- The prefix is immediately followed by a concise commit description
- The description explains the primary purpose of the change
- Do not add an AI-agent name, attribution, or unrelated metadata

### Allowed

```text
[FT]add user authentication
[FX]fix token expiration
[FE]update login page
[BE]add user service
[AP]add auth endpoint
[DB]add user table
[TS]add authentication tests
[RF]simplify auth middleware
[CI]update github workflow
[DC]update api documentation
```

### Forbidden

```text
update login page
AI: update login page
[AI]add authentication
[Cursor]fix login bug
[Codex]add api endpoint
[FT] Generated with Codex
Co-authored-by: Codex
```

## 4. Predefined commit prefixes

Authoritative default prefix list:

```text
[FE] Frontend
[BE] Backend
[AP] API
[DB] Database
[UI] UI
[CF] Config
[CI] CI/CD
[TS] Test
[DC] Docs
[RF] Refactor
[FX] Fix
[FT] Feature
[OP] Optimize
[SC] Security
[DP] Dependency
[CH] Chore
```

### Selection rules

Unless the user explicitly specifies another prefix:

1. Use a predefined prefix whenever possible
2. Never invent a new prefix
3. Never modify the spelling or capitalization of a predefined prefix
4. Use exactly two uppercase letters inside the brackets
5. Select the prefix based on the primary purpose of the change
6. When multiple prefixes could apply, choose the one that best represents the primary purpose

| Change type | Prefix |
| --- | --- |
| New functionality | `[FT]` |
| Bug fix | `[FX]` |
| Frontend implementation | `[FE]` |
| Backend implementation | `[BE]` |
| API changes | `[AP]` |
| Database changes | `[DB]` |
| UI-only changes | `[UI]` |
| Configuration changes | `[CF]` |
| CI/CD changes | `[CI]` |
| Tests | `[TS]` |
| Documentation | `[DC]` |
| Refactoring without behavior change | `[RF]` |
| Performance optimization | `[OP]` |
| Security-related changes | `[SC]` |
| Dependency changes | `[DP]` |
| General maintenance | `[CH]` |

## 5. User-specified prefix has priority

The predefined prefix list is the default, not an absolute restriction.

If the user explicitly specifies a different commit prefix or commit format, follow the user's explicit instruction.

Example: user says `Use [HOT] for this commit.` → use `[HOT]fix production issue`.

- Do not replace the user's explicitly requested prefix with a predefined prefix
- If the user does not specify a prefix, use the predefined list
- If the user specifies only the description, select the appropriate predefined prefix

## 6. Commit description

The description after the prefix should be:

- Concise and specific
- Written in English unless the user explicitly requests another language
- Focused on the actual change
- Free of AI-agent attribution

Preferred:

```text
[FX]fix expired access token handling
[FT]add password reset endpoint
[FE]update account settings page
[RF]simplify request validation
```

Avoid:

```text
[FX]fix stuff
[FT]changes
[RF]update code
[BE]AI generated backend changes
```

## 7. Commit scope

Prefer one logical change per commit when practical.

When a task contains multiple unrelated changes:

- Do not fabricate a single misleading commit description
- Prefer separate commits when practical
- Select the prefix independently for each commit
- Keep each commit message representative of its actual contents

If the user explicitly requests a single commit, follow that instruction and choose the prefix that best represents the primary purpose of the combined change.

## 8. Pre-commit validation

Before creating a commit, verify:

**Identity**

- Git author is the user's configured identity
- Git committer is not an AI/code-agent identity
- No AI-agent attribution will be added

**Message**

1. Starts with a valid prefix
2. Uses a predefined prefix unless the user explicitly specified another
3. Uses exactly two uppercase letters for a default prefix
4. Prefix is enclosed in `[]`
5. Contains a concise description after the prefix
6. Does not mention Cursor, Codex, ChatGPT, AI agent, or similar agent identity
7. Does not contain prohibited attribution trailers

**GitHub permissions**

Before changing repository permissions or collaborators:

- Verify the target is not an AI/code-agent identity
- Never grant contributor or collaborator access to the code agent

## 9. Push and GitHub operations

Before pushing commits:

- Ensure commit messages comply with this skill
- Ensure commits do not contain prohibited AI attribution
- Ensure the code agent has not been added as a GitHub contributor
- Do not modify GitHub permissions merely to facilitate agent operation

If an existing commit violates these rules and the user asks to push it, fix the violation before pushing when doing so is safe and consistent with the user's requested workflow.

For commits already pushed to a shared/public branch, do not rewrite history automatically. Ask the user before:

```text
git commit --amend
git rebase
git reset --hard
git push --force
git push --force-with-lease
```

## 10. Pull requests

When creating or updating a pull request:

- Do not identify the code agent as a contributor
- Do not add AI-agent attribution unless explicitly requested by the user
- Keep the PR title and description focused on the actual changes
- Follow the repository PR template when one exists
- Do not modify repository permissions to create or update a PR

## 11. Conflict resolution

If another repository-level instruction, project rule, or user instruction conflicts with this skill:

1. Follow the higher-priority instruction
2. If the user explicitly specifies a commit prefix or commit format, follow the user's explicit request
3. Otherwise, use the predefined prefix list and commit format in this skill
4. Never add the code agent as a GitHub contributor

Do not silently invent an alternative rule.

## 12. Final enforcement checklist

Before completing any GitHub-related task:

```text
[ ] Code agent was not added as a GitHub contributor.
[ ] Code agent was not added as a GitHub collaborator.
[ ] Git author is not an AI-agent identity.
[ ] Git committer is not an AI-agent identity.
[ ] Commit message follows [xx]xxxxx by default.
[ ] Default prefix comes from the predefined list.
[ ] User-specified prefix takes priority over the predefined list.
[ ] Commit message contains no AI-agent attribution.
[ ] Commit trailers contain no AI-agent attribution.
[ ] GitHub operations do not unnecessarily modify repository permissions.
```
