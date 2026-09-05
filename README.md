# CN Skill Navigator

A Chinese-first Codex skill for choosing the right skill for a task.

It helps Codex explain installed skills in plain Chinese, recommend the best local skill for a request, and search GitHub or skills.sh when the local skill set is not enough.

## What It Does

- Matches a user's Chinese or English task description to locally installed Codex skills
- Explains overlapping skills with clear boundaries
- Searches external sources such as GitHub and skills.sh when no local skill fits
- Recommends only a small set of relevant options
- Avoids installing or modifying skills unless the user explicitly asks

## When To Use

Use this skill when you ask things like:

- "这个任务该用哪个 skill?"
- "帮我区分一下这些 skill 的用途。"
- "有没有适合做前端优化的 skill?"
- "本地没有的话，帮我去 GitHub 上找找。"

## Install

```bash
npx skills add muyiyangyc-hub/cn-skill-navigator -g
```

## Files

- `SKILL.md`: Core skill instructions
- `agents/openai.yaml`: Codex UI metadata

## Notes

This skill is intentionally lightweight. It is a navigator, not a package manager. It can recommend local or external skills, but installation should happen only after the user confirms it.
