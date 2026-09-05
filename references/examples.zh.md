# Chinese Usage Examples

Use these examples to calibrate concise Chinese answers. Adapt them to the actual request.

## Local Skill Recommendations

User: 我现在想优化一个网站的前端页面，这个任务该用哪个 skill？

Answer:

```text
推荐用：`impeccable`

原因：它专门适合优化已有网站或产品 UI，包括布局、视觉层级、响应式、交互细节和可访问性。
可能搭配：如果要从零重做页面，用 `frontend-design`；如果项目是 shadcn/Tailwind，用 `shadcn-ui`。
依据：本地已安装 skill 的说明。
```

User: 我要从零做一个漂亮的官网页面。

Answer:

```text
推荐用：`frontend-design`

原因：它适合创建新的网页、组件和前端应用，并且强调高质量视觉设计。
可能搭配：如果重点是去掉模板味，可以加 `design-taste-frontend`。
依据：本地已安装 skill 的说明。
```

User: 我有个 Next.js 项目，要加一个 shadcn 的后台侧边栏。

Answer:

```text
推荐用：`shadcn-ui`

原因：这个任务明确涉及 Next.js、Tailwind 和 shadcn 组件模式。
可能搭配：如果侧边栏做好后还要整体审美打磨，可以再用 `impeccable`。
依据：本地已安装 skill 的说明。
```

User: 我想把这段文案改得不像 AI。

Answer:

```text
推荐用：`humanizer`

原因：它专门处理 AI 味文字，适合降低套路感、空泛表达和机械句式。
依据：本地已安装 skill 的说明。
```

User: 我想做一个 PPT。

Answer:

```text
推荐用：`presentations`

原因：它适合创建、编辑或检查 PowerPoint、PPTX 和 Google Slides 类型的演示文稿。
依据：本地已安装 skill 的说明。
```

User: 我要处理一个 PDF 表单。

Answer:

```text
推荐用：`pdf`

原因：它适合 PDF 读取、生成、表单处理和视觉渲染验证。
依据：本地已安装 skill 的说明。
```

User: 我要做 Excel 数据表。

Answer:

```text
推荐用：`spreadsheets`

原因：它适合创建、编辑和分析独立的 XLSX、CSV、TSV 文件。
注意：如果你是要控制已经打开的 Excel 窗口，才用 `spreadsheets:excel-live-control`。
依据：本地已安装 skill 的说明。
```

User: 我想生成一张图片。

Answer:

```text
推荐用：`imagegen`

原因：它适合生成或编辑位图图片，比如插画、照片风格图、贴图、角色图。
依据：本地已安装 skill 的说明。
```

User: 我想写 Seedance 提示词。

Answer:

```text
推荐用：`seedance-prompt`

原因：它适合写、改、翻译和调试 Seedance 2.0 视频提示词。
如果是短提示词，用 `seedance-prompt-short`；如果是多段故事，用 `seedance-sequence`。
依据：本地已安装 skill 的说明。
```

## External Search Examples

User: 本地没有适合做 Playwright 测试的 skill，可以去 GitHub 找找吗？

Answer:

```text
可以。这个场景本地没有强匹配，我会去 GitHub/skills.sh 搜索 Playwright/testing 相关 skill，并优先检查是否有 `SKILL.md`、README、维护情况和使用热度。
依据：本地覆盖不足，需要外部搜索。
```

User: 上传前帮我看看 GitHub 上有没有类似 skill。

Answer:

```text
可以。我会搜索相近关键词，比如 `skill navigator`、`skill router`、`find skills`、`agent skill discovery`，再判断是否真的相似。
重点看：是否有有效 `SKILL.md`、项目维护情况、README、stars/安装量，以及和你的 skill 定位是否重叠。
依据：发布前外部相似性检查。
```

## Publishing Examples

User: 帮我把这个 skill 发布到 GitHub。

Answer:

```text
可以。发布前我会先检查内部 `name` 是否和仓库名一致、README 是否说明用途和安装命令、是否有必要的 reference 文件，以及 GitHub 上是否已有明显同类项目。
```

User: 这个 skill 还能怎么完善？

Answer:

```text
优先完善能提升路由稳定性的内容：中文决策树、中文示例、外部搜索质量清单、发布前检查清单。
不建议堆太多泛泛规则，否则反而会让 skill 变重。
```
