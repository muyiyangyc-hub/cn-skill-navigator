# Chinese Decision Tree

Use this reference when the user gives a short Chinese task description and wants to know which skill to use.

Answer with the best match first. Mention alternatives only when they change the user's next action.

## First Question

Ask yourself: is the user trying to create something, improve something, inspect something, or find/install a capability?

## Skill Discovery and Management

| User says | Recommend | Notes |
|---|---|---|
| 这个任务该用哪个 skill | `cn-skill-navigator` | Use this skill to route the request. |
| 帮我区分这些 skill | `cn-skill-navigator` | Read local categories. |
| 有没有某类 skill | `cn-skill-navigator` + `find-skills` | Use external search only if local coverage is weak or requested. |
| 帮我安装这个 skill | `skill-installer` | Confirm the exact package before installing. |
| 帮我创建/修改一个 skill | `skill-creator` | Use for authoring skill files. |
| 帮我发布 skill 到 GitHub | `skill-creator` + publishing checklist | Check name, README, structure, and similar work. |

## Frontend and Product UI

| User says | Recommend | Notes |
|---|---|---|
| 优化网站前端页面 | `impeccable` | Best for existing UI improvement. |
| 改一下页面审美 | `impeccable` | Use for polish, hierarchy, spacing, interaction, responsive behavior. |
| 从零做一个网页/组件/应用 | `frontend-design` | Best for new UI creation. |
| 做一个 landing page | `frontend-design` | Pair with `design-taste-frontend` if visual taste is the main concern. |
| 这个页面太模板化 | `design-taste-frontend` | Strong for anti-generic redesign direction. |
| 用 shadcn 做表单/表格/侧边栏 | `shadcn-ui` | Use only when shadcn/Tailwind/Radix is relevant. |
| 帮我做 UI/UX 方案 | `ui-ux-pro-max` | Broad UX guidance; prefer narrower skills for implementation. |

## Writing and Content

| User says | Recommend | Notes |
|---|---|---|
| 这段文字太像 AI | `humanizer` | Rewrite for naturalness. |
| 帮我润色成自然表达 | `humanizer` | Keep meaning and reduce formulaic phrasing. |
| 写微信公众号文章/排版 | `wechat-publication-workflow` | Use for WeChat-specific content workflows. |

## Documents and Files

| User says | Recommend | Notes |
|---|---|---|
| 做/改 Word 文档 | `documents` | Use for docx or Google Docs-style artifacts. |
| 处理 PDF | `pdf` | Use for PDF extraction, creation, forms, and render checks. |
| 做 Excel/CSV/XLSX | `spreadsheets` | Use for standalone spreadsheet files. |
| 控制打开的 Excel | `spreadsheets:excel-live-control` | Only for live connected Excel sessions. |
| 做 PPT/幻灯片 | `presentations` | Use for PowerPoint or Slides. |

## Images, Visuals, and Media

| User says | Recommend | Notes |
|---|---|---|
| 生成/修改图片 | `imagegen` | Use for raster images. |
| 画图解释/做交互图表 | `visualize` | Use for visual explanations, simulations, charts. |
| 处理音视频文件 | `mediabunny` | Use for media file workflows. |

## Remotion Video

| User says | Recommend | Notes |
|---|---|---|
| 创建 Remotion 视频 | `remotion-create` | New Remotion project. |
| Remotion 最佳实践 | `remotion-best-practices` | General guidance. |
| Remotion 字幕 | `remotion-captions` | Caption workflow. |
| Remotion 渲染 | `remotion-render` | Rendering/export. |
| Remotion 可视化编辑 | `remotion-interactivity` | Visual Mode and editable animation. |

## Seedance 2.0

| User says | Recommend | Notes |
|---|---|---|
| 写 Seedance 提示词 | `seedance-prompt` | General prompt writing. |
| Seedance 短提示词 | `seedance-prompt-short` | Compact prompt output. |
| Seedance 多段故事 | `seedance-sequence` | Multi-clip or storyboard. |
| Seedance 续写下一段 | `seedance-continuation` | Continue from accepted footage. |
| Seedance 镜头 | `seedance-camera` | Camera movement and framing. |
| Seedance 动作 | `seedance-motion` | Body/object motion. |
| Seedance 灯光 | `seedance-lighting` | Lighting and atmosphere. |
| Seedance 风格 | `seedance-style` | Visual style and art direction. |
| Seedance 特效 | `seedance-vfx` | VFX, particles, weather, destruction. |
| Seedance 角色一致 | `seedance-characters` | Character lock and continuity. |
| Seedance 被拦截 | `seedance-filter` | Safer rewrite. |

## Default Answer Pattern

If one skill clearly fits:

```text
推荐用：`<skill-name>`

原因：<brief Chinese explanation>
依据：本地 skill 说明。
```

If two skills overlap:

```text
首选：`<skill-name>`

另外可以搭配：`<other-skill>`，当 <condition> 时再用。
```

If no local skill fits:

```text
本地没有特别贴合的 skill。建议用 `find-skills` 或让我去 GitHub/skills.sh 搜索，并按维护情况和 README 质量筛选。
```
