---
name: cn-skill-navigator
description: Help choose the right Codex skill from local installed skills or, when local coverage is missing, search GitHub and skills.sh for suitable skills. Use when the user asks which skill to use, wants a Chinese explanation of skills, or wants to discover skills for a task.
metadata:
  short-description: Choose local or external skills
---

# CN Skill Navigator

Use this skill to turn a user's plain-language task, including Chinese requests, into practical skill recommendations.

## Reference Routing

Read only the reference files that fit the current request:

- For local installed skill explanations, Chinese categories, or overlap decisions, read [references/local-skill-categories.zh.md](references/local-skill-categories.zh.md).
- For GitHub, skills.sh, or external skill discovery, read [references/external-search-checklist.md](references/external-search-checklist.md).

## Core Behavior

When the user asks which skill to use, how to distinguish installed skills, or whether a skill exists for a task:

1. Clarify the task intent only if the request is too broad to route.
2. Prefer matching against locally installed skills first.
3. If local skills are insufficient, overlapping, or absent, search externally through GitHub and skills.sh when network access is available.
4. Recommend a small set of choices with clear boundaries, not a long catalog.
5. Explain recommendations in the user's language.
6. State whether the answer is based on local inspection, external search, or both.

Do not install a skill unless the user explicitly asks to install it.

## Local Skill Matching

Inspect installed skills before recommending local options. Useful locations include:

- `$CODEX_HOME/skills`
- `~/.codex/skills`
- plugin-provided skills listed in the active session context

For each relevant local skill, identify:

- skill name
- what it is good for
- when not to use it
- whether it overlaps with another installed skill

When names are English and the user is Chinese-speaking, translate the purpose into natural Chinese while preserving the exact skill name.

Use the local category reference when the user asks broad questions such as "我该用哪个 skill", "帮我区分 skill", or "这些 skill 都是干什么的".

## External Search

Use external search when:

- no installed skill clearly fits
- the user explicitly asks to search GitHub
- the local option is too generic
- the task is a common specialized workflow, such as testing, deployment, design systems, data extraction, API docs, or framework-specific work

Preferred search order:

1. Search skills.sh for skill packages when the Skills CLI or web access is available.
2. Search GitHub for repositories containing agent skills, using focused terms such as `agent skill <domain>`, `codex skill <domain>`, or `<framework> skill`.
3. Prefer official or reputable sources over unknown repositories.

Before recommending an external skill, check quality signals when available:

- source reputation
- install count or popularity
- repository stars
- recent maintenance
- clear README or skill description
- narrow relevance to the user's task

If these signals cannot be verified, say so plainly and mark the recommendation as tentative.

Use the external search checklist before recommending a new skill from GitHub or skills.sh.

## Recommendation Format

Keep the output concise. A good response usually includes:

- Best local match, if any
- Why it fits the request
- Important overlap or pairing advice
- External options, if local coverage is weak or the user requested search
- Exact install command only after verifying a package name
- One practical next step

Example:

```text
这个任务本地最接近的是 `frontend-design`，适合直接做页面和组件。
如果你想找更专门的 React 性能 skill，我可以再去 GitHub/skills.sh 搜索并按质量筛选。
```

## Boundaries

- Do not treat this skill as authorization to install, update, delete, or modify other skills.
- Do not recommend external skills solely from a name match.
- Do not flood the user with every possible skill.
- Do not translate or rename the actual skill folder names.
- Do not run network searches when the user only needs a clear local recommendation and local coverage is strong.
