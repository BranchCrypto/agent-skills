# Agent Skills

[中文](README.md) | [English](README.en.md)

个人 Agent Skills 集合，适用于支持 `SKILL.md` 的 agent（Codex、Claude Code、GitHub Copilot 等）。

## 包含的 skills

| Skill | 类别 | 用途 |
|---|---|---|
| [`github-hygiene`](skills/engineering/github-hygiene/SKILL.md) | 工程 | Git / GitHub 操作规范：禁止 AI 账号成为贡献者、禁止 AI 署名、统一 `[XX]` commit 格式。 |
| [`more-ui`](skills/engineering/more-ui/SKILL.md) | 工程 | 以最小改动修复 UI 栅格、对齐、间距、尺寸与响应式布局问题。 |
| [`pure-output`](skills/writing/pure-output/SKILL.md) | 写作 | 只交付可用成品；不编造事实，缺失高风险信息时标注 DRAFT / PARTIAL / BLOCKED。 |

## 安装

安装全部 skills：

```bash
npx skills add BranchCrypto/agent-skills
```

只安装其中一个：

```bash
npx skills add BranchCrypto/agent-skills --skill github-hygiene
```

仓库为私有，CLI 会使用你的 Git / GitHub CLI 身份认证。

## 目录结构

```text
skills/
  engineering/
    github-hygiene/SKILL.md
    more-ui/SKILL.md
  writing/
    pure-output/SKILL.md
```
