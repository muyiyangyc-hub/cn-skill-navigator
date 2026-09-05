# External Search Checklist

Use this reference before recommending a skill from GitHub, skills.sh, or another external source.

## When To Search

Search externally when one of these is true:

- No installed skill clearly fits the user's task.
- Installed skills are too broad for a specialized workflow.
- The user explicitly asks to search GitHub, skills.sh, or the web.
- The task depends on a fast-moving tool, framework, or platform where newer skills may exist.
- The user is considering publishing a skill and wants to check for similar work first.

Do not search externally when a strong local match is enough and the user only asked which installed skill to use.

## Search Queries

Use focused queries. Good patterns:

- `"<domain>" "SKILL.md" "agent skill"`
- `"<domain>" "Codex skill"`
- `"<domain>" "skills.sh"`
- `"agent skills" "<domain>" GitHub`
- `site:github.com "<skill idea>" "SKILL.md"`

For Chinese-first skills, also search English equivalents because most public skills use English names:

- `skill navigator`
- `skill router`
- `find skills`
- `agent skill discovery`
- `codex skill manager`

## Quality Signals

Before recommending an external skill, check as many of these as practical:

- The repository actually contains a valid `SKILL.md`.
- The `description` clearly matches the user's task.
- The source is reputable or has a clear maintainer.
- The repository has meaningful stars, forks, installs, or community usage.
- The skill appears maintained recently.
- The README explains installation and intended use.
- The skill scope is narrow enough to be useful.
- It does not request unnecessary permissions or perform surprising side effects.

If quality signals are weak or unavailable, label the recommendation as tentative.

## Recommendation Levels

Use these labels when comparing external options:

- Strong match: clear `SKILL.md`, relevant description, maintained, reputable source.
- Possible match: relevant idea but incomplete quality signals.
- Not recommended: vague scope, missing skill file, stale or unclear project, or risky behavior.

## Output Template

```text
我找到了这些相近选择：

1. `<repo-or-skill>` - Strong match
   适合：<task>
   质量信号：<stars/install count/maintainer/README>
   安装：`npx skills add <package> -g`

2. `<repo-or-skill>` - Possible match
   适合：<task>
   注意：<missing quality signal>

我的建议：<choose one or say local skill is enough>
```

## Boundaries

- Do not install, update, delete, or publish anything from a search result unless the user explicitly asks.
- Do not recommend a repository merely because its name sounds close.
- Do not hide uncertainty. If the evidence is incomplete, say so.
- Do not claim a skill is the best available unless search coverage and quality signals support that claim.
