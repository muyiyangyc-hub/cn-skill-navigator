# Publishing Checklist

Use this reference when preparing a skill for GitHub or another public repository.

## Pre-Publish Checks

Before publishing or updating a skill repository, check:

- The repository name and skill `name` are aligned, or the difference is intentional.
- `SKILL.md` has valid YAML frontmatter with `name` and `description`.
- The description is specific enough to avoid attracting unrelated tasks.
- The skill body explains core behavior without becoming a full manual.
- Supporting `references/` files are linked from `SKILL.md`.
- No reference file is required for every invocation unless it is genuinely needed.
- `agents/openai.yaml` has a clear display name and short description when present.
- `README.md` explains purpose, usage examples, file structure, and installation.
- Install command uses the correct GitHub owner/repo.
- There are no placeholders such as `TODO`, `TBD`, or scaffold examples.
- The skill does not imply permission to install, publish, delete, or mutate external resources without user confirmation.

## Similarity Search

Before public release, search for similar work:

- `"<skill-name>" "SKILL.md"`
- `"<main capability>" "agent skill"`
- `"<main capability>" "skills.sh"`
- `site:github.com "<main capability>" "SKILL.md"`

Compare:

- Is this skill solving the same task or a narrower/different task?
- Does an existing skill already cover the use case better?
- Is this skill differentiated by language, workflow, target environment, or quality bar?
- Should the README mention the differentiator more clearly?

For `cn-skill-navigator`, the differentiator is:

```text
Chinese-first skill routing for Codex users, with local installed skill explanations first and GitHub/skills.sh search as a fallback.
```

## Repository Shape

Recommended minimal structure:

```text
cn-skill-navigator/
|-- README.md
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
`-- references/
    |-- local-skill-categories.zh.md
    |-- decision-tree.zh.md
    |-- examples.zh.md
    |-- external-search-checklist.md
    `-- publishing-checklist.md
```

## Release Notes Template

```text
## What's Changed

- Added <feature/reference/checklist>.
- Improved <routing/search/output behavior>.
- Clarified <boundary/safety rule>.

## Why

<Brief explanation of the user-facing improvement.>
```

## Final Verification

After publishing, read back key files from the remote repository:

- `SKILL.md`
- `README.md`
- any new reference files
- `agents/openai.yaml`

If a validator is available, run it locally. If the validator cannot run because of missing dependencies, say exactly which dependency failed and what manual checks were completed.
