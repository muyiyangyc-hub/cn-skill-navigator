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

## GitHub Repository Setup

For a public skill repository, check the GitHub page itself:

- Repository name is short, lowercase, and matches the install command.
- Description explains the main user-facing value in one sentence.
- Visibility matches the user's intent, usually public for shared skills.
- README renders correctly on the repository homepage.
- Default branch contains the final `SKILL.md`.
- Repository topics are useful when the user wants discoverability, for example `codex`, `skill`, `agent-skills`, `chinese`, `skills`.
- The repository does not expose secrets, local paths, private notes, tokens, or user-specific data.

If GitHub repository settings cannot be changed by the available tools, tell the user which settings they may adjust manually.

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

## Install Verification

When possible, verify installation from the published repository:

```bash
npx skills add <owner>/<repo> -g
```

Then check that:

- The installed skill appears in the next session's skill list.
- The `name` in `SKILL.md` is the expected invocation name.
- Linked references are included after install.
- A simple routing request gives the expected recommendation.

If installing into the user's real global skill directory would overwrite a local development copy, avoid doing it automatically. Explain the risk and ask before proceeding.

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

## Update Workflow

For an existing GitHub skill repository:

1. Read the current remote file before updating it.
2. Use the current blob SHA when replacing an existing file through the GitHub contents API.
3. Create new files only when the path does not already exist.
4. Do not run parallel update/delete operations on the same path.
5. After upload, read the changed files back from GitHub and verify the expected content is visible.

## Final Verification

After publishing, read back key files from the remote repository:

- `SKILL.md`
- `README.md`
- any new reference files
- `agents/openai.yaml`

If a validator is available, run it locally. If the validator cannot run because of missing dependencies, say exactly which dependency failed and what manual checks were completed.

For this project, the known validation fallback is:

```text
If `quick_validate.py` fails because Python lacks `yaml`, manually verify frontmatter, required files, reference links, README structure, and remote file contents.
```
