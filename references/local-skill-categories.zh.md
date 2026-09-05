# Local Skill Categories

Use this reference when the user wants Chinese explanations of installed skills, local skill selection, or help distinguishing overlapping skills.

Preserve exact skill names. Translate meanings, not identifiers.

## 高频入口

| User intent | Recommended skill | Boundary |
|---|---|---|
| 先想清楚功能、交互、行为修改方案 | `brainstorming` | Use before creative feature or behavior work when a design decision is needed. |
| 创建或修改 Codex skill | `skill-creator` | For skill structure, frontmatter, references, scripts, and validation. |
| 安装外部 skill | `skill-installer` | For installing curated or GitHub skills after user confirmation. |
| 找现成 skill 或生态能力 | `find-skills` | Good for broad discovery; pair with this navigator for Chinese routing. |
| 查询 Codex、OpenAI、模型、API、设置 | `openai-docs` | Use official docs-oriented answers. |

## 前端和 UI

| User intent | Recommended skill | Boundary |
|---|---|---|
| 从零设计网页、页面、组件、前端应用 | `frontend-design` | Creation-first. Best when building new UI. |
| 优化、审查、打磨已有页面或产品 UI | `impeccable` | Improvement-first. Best for existing interfaces. |
| 避免模板味、提升页面审美和设计质感 | `design-taste-frontend` | Strong for visual taste and anti-generic redesigns. |
| Next.js、Tailwind、shadcn/ui 组件和页面 | `shadcn-ui` | Use when project actually uses shadcn/Radix/Tailwind patterns. |
| 泛 UI/UX 指南、色彩、布局、组件、图表 | `ui-ux-pro-max` | Broad design knowledge; avoid using it when a narrower UI skill fits better. |

Suggested pairing:

- Existing website optimization: `brainstorming` then `impeccable`.
- New high-quality page: `brainstorming` then `frontend-design`.
- shadcn project: `shadcn-ui`, optionally with `impeccable` for polish.

## 文档、表格、演示

| User intent | Recommended skill | Boundary |
|---|---|---|
| Word/docx/Google Docs-style document creation or edits | `documents` | Use when document layout or comments matter. |
| PDF read, create, inspect, forms, visual verification | `pdf` | Use for PDF-specific work. |
| Excel/XLSX/CSV/TSV workbook creation or analysis | `spreadsheets` | Standalone spreadsheet files, not live Excel control. |
| Live Microsoft Excel workbook control | `spreadsheets:excel-live-control` | Only for connected live Excel sessions. |
| PowerPoint/PPTX/Google Slides decks | `presentations` | Use for slide creation, editing, or inspection. |

## 图片、写作、视觉解释

| User intent | Recommended skill | Boundary |
|---|---|---|
| Generate or edit raster images | `imagegen` | Use for bitmap image generation/editing. |
| Make AI-sounding writing more natural | `humanizer` | Use for prose rewriting or review. |
| Build visualizations, diagrams, simulations, charts in conversation | `visualize` | Use for explaining ideas visually or interactively. |

## 视频、动画、媒体

| User intent | Recommended skill | Boundary |
|---|---|---|
| Create a new Remotion video project | `remotion-create` | Use for new Remotion builds. |
| General Remotion guidance | `remotion-best-practices` | Use when unsure which Remotion sub-skill fits. |
| Remotion captions | `remotion-captions` | Caption workflows only. |
| Remotion rendering/export | `remotion-render` | Rendering and delivery. |
| Remotion Visual Mode/interactivity | `remotion-interactivity` | Editable animation and interaction constraints. |
| Remotion React markup | `remotion-markup` | Component markup and structure. |
| Remotion SaaS/video app advice | `remotion-saas` | Productized Remotion applications. |
| Multimedia handling | `mediabunny` | Audio/video file manipulation. |

## Seedance 2.0

Use `seedance-20` as the broad entry when the task is about Seedance 2.0. Choose a narrower sub-skill when the user has a specific need:

| User intent | Recommended skill |
|---|---|
| 写、改、翻译、调试 Seedance 提示词 | `seedance-prompt` |
| 短提示词、压缩、30-100 字 | `seedance-prompt-short` |
| 长故事、多段分镜、连续镜头 | `seedance-sequence` |
| 续写、延长、修复尾帧漂移 | `seedance-continuation` |
| 镜头、运动、灯光、风格、VFX | `seedance-camera`, `seedance-motion`, `seedance-lighting`, `seedance-style`, `seedance-vfx` |
| 角色一致性、服装、表情、手部 | `seedance-characters` |
| 音频、对白、口型、节奏 | `seedance-audio` |
| 被拦截、过滤、提示词太泛 | `seedance-filter`, `seedance-antislop` |
| 中英日韩西俄提示词词汇 | `seedance-vocab-zh`, `seedance-vocab-en`, `seedance-vocab-ja`, `seedance-vocab-ko`, `seedance-vocab-es`, `seedance-vocab-ru` |

## 其他个人工作流

| User intent | Recommended skill | Boundary |
|---|---|---|
| Create or repair a Codex animated pet | `hatch-pet` | Use for pet spritesheets and packaging. |
| WeChat public account publication workflow | `wechat-publication-workflow` | Use for WeChat-focused writing and formatting. |
| Create a reusable artifact template | `template-creator` | Use when the user wants a reusable template skill. |
| Plugin creation or plugin metadata | `plugin-creator` | Use for Codex plugin scaffolding. |
| Plugin discovery, permissions, or removal | `plugin-management` | Use for plugin-level management, not normal skill routing. |

## Answer Template

Use this shape for simple local recommendations:

```text
推荐用：`<skill-name>`

原因：<one or two Chinese sentences>

可能搭配：`<other-skill>`，当 <condition> 时使用。
依据：本地已安装 skill 的说明。
```

For overlapping skills, explain the split:

```text
这几个都相关，但分工不同：
`frontend-design`：从零做新页面或组件。
`impeccable`：优化已有页面和交互。
`shadcn-ui`：项目使用 shadcn/Tailwind 时处理组件实现。
```
