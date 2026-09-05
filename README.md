# CN Skill Navigator

面向中文用户的 Codex skill 导航器，用来判断一个任务应该调用哪个 skill。

它会先用中文解释本地已安装 skill 的用途和边界，再在本地能力不够时搜索 GitHub 或 skills.sh，帮助用户发现更合适的外部 skill。

English: A Chinese-first Codex skill for choosing the right skill for a task. It explains installed skills in plain Chinese, recommends the best local skill for a request, and searches GitHub or skills.sh when the local skill set is not enough.

## What It Does

- 用中文把英文 skill 名称解释清楚
- 根据中文或英文任务描述匹配本地已安装的 Codex skills
- 区分用途相近的 skill，比如 `frontend-design`、`impeccable`、`shadcn-ui`
- 使用中文决策树和示例，让常见任务的推荐更稳定
- 本地没有强匹配时，搜索 GitHub 和 skills.sh
- 推荐外部 skill 前检查质量信号
- 提供发布 skill 前的检查清单
- 只推荐少量真正相关的选项
- 除非用户明确要求，不安装、不删除、不修改其他 skill

English:

- Matches a user's Chinese or English task description to locally installed Codex skills
- Explains overlapping skills with clear boundaries
- Uses Chinese decision trees and examples for common routing decisions
- Searches external sources such as GitHub and skills.sh when no local skill fits
- Checks quality signals before recommending external skills
- Includes a publishing checklist for preparing skill repositories
- Recommends only a small set of relevant options
- Avoids installing or modifying skills unless the user explicitly asks

## When To Use

适合在这些场景使用：

- "这个任务该用哪个 skill?"
- "帮我区分一下这些 skill 的用途。"
- "有没有适合做前端优化的 skill?"
- "本地没有的话，帮我去 GitHub 上找找。"
- "上传前帮我查一下有没有相似的 skill。"
- "帮我检查这个 skill 发布前还缺什么。"

## Quick Examples

```text
用户：我现在想优化一个网站的前端页面，这个任务该用哪个 skill？
推荐：`impeccable`
```

```text
用户：我要从零做一个漂亮的官网页面。
推荐：`frontend-design`
```

```text
用户：本地没有的话，帮我去 GitHub 上找找。
推荐：先检查本地覆盖，再按质量信号搜索 GitHub / skills.sh。
```

## Install

```bash
npx skills add muyiyangyc-hub/cn-skill-navigator -g
```

After installing, you can ask:

```text
用 `$cn-skill-navigator` 判断这个任务该用哪个 skill。
```

## Structure

- `SKILL.md`: Core routing behavior and reference selection
- `references/local-skill-categories.zh.md`: Chinese categories for common local Codex skills
- `references/decision-tree.zh.md`: Chinese task-to-skill decision tree
- `references/examples.zh.md`: Chinese examples and answer templates
- `references/external-search-checklist.md`: GitHub and skills.sh search rules, quality checks, and output template
- `references/publishing-checklist.md`: Pre-publish checks for skill repositories
- `agents/openai.yaml`: Codex UI metadata

## Notes

This skill is intentionally a navigator, not a package manager. It can recommend local or external skills, but installation should happen only after the user confirms it.

这个 skill 的核心定位是“导航”和“解释”，不是替用户自动安装或管理所有 skill。
