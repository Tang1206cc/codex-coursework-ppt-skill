# coursework-ppt

中文 | [English](#english)

## 中文

这是一个用于“制作严谨、可溯源、适合课堂展示的课程作业 PowerPoint”的 Codex skill。它适合课程作业 PPT、小组汇报、案例分析、个人展示、课堂答辩、研究型汇报等需要先读材料、再查资料、再组织论证、最后生成可编辑 `.pptx` 的场景。

核心目标很明确：用户提供作业要求、主题材料、课程或老师给出的结构规范后，Codex 使用本 skill 先核验本地资料，再检索权威来源，规划每页 PPT 的论点、证据和展示方式，然后制作一份结构清楚、字号可读、来源可追踪、适合课堂投影的演示文稿。它不是普通的“套模板生成 PPT”，而是把作业型 PPT 当作一个有论证、有材料、有格式边界的学术展示任务来完成。

对了，其实你可以直接把仓库链接给 Codex，让它自己安装。安装完成后，先别着急开始使用，你可以说：“我想使用这个 skill，我需要准备哪些文件给你？”

## Skill 信息

- Skill 名称：`coursework-ppt`
- Skill 路径：`skill包/coursework-ppt`
- 入口文件：`skill包/coursework-ppt/SKILL.md`
- 界面配置：`skill包/coursework-ppt/agents/openai.yaml`
- 中文展示名：`作业类 PPT`

## 适合什么任务

适合使用本 skill 的任务包括：

- 根据课程作业要求制作 PowerPoint 汇报稿。
- 根据老师给出的章节结构制作小组汇报或个人展示。
- 制作案例分析 PPT、课程调研 PPT、行业分析 PPT、政策分析 PPT、课堂答辩 PPT。
- 将本地资料、PDF、Word、表格、已有笔记或老师课件整理成有逻辑的演示文稿。
- 为 PPT 中的数据、政策、报告、案例和关键判断补充真实可追踪来源。
- 需要较大字号、清晰版式、适合投影阅读的课堂展示稿。
- 对已经生成的 PPT 做单点修改，例如“只改封面背景”“只放大引用字号”“只重命名文件”。

不适合使用本 skill 的任务包括：

- 想要快速生成没有材料依据的通用模板 PPT。
- 需要编造数据、虚构参考文献、伪造报告名称或补充不存在的案例。
- 需要制作商业宣传页、品牌发布会、纯视觉海报型 PPT，而不是课程作业或学术展示。
- 没有主题、没有作业要求，并且也不允许 Codex 进行必要资料检索的任务。
- 希望 Codex 大幅偏离老师要求的章节结构或随意重做已经确认的内容。

## 用户调用时应提供哪些材料

为了让 skill 工作稳定，建议用户一次性提供或说明以下材料：

| 材料 | 是否必需 | 说明 |
| --- | --- | --- |
| 作业要求 | 强烈建议 | 课程名、作业类型、老师要求、评分标准、页数或汇报时长、必须包含的章节、格式要求等。可以是 `.txt`、Word、PDF、图片或老师课件。 |
| 主题说明 | 必需 | PPT 的主题、研究对象、案例范围、行业或课程背景、希望重点回答的问题。主题越明确，结构和材料筛选越稳定。 |
| 本地参考材料 | 建议 | 课程资料、课堂笔记、老师给的阅读材料、已有 Word 文稿、PDF 报告、Excel 数据、旧 PPT、分工材料等。Codex 会先读本地资料。 |
| 固定信息 | 视情况需要 | 小组成员、姓名、学号、班级、课程名、老师姓名、日期、学校或学院信息等封面或署名需要的内容。缺失时不应编造。 |
| 输出要求 | 建议 | 指定输出文件名、保存目录、是否需要 PDF 或预览图、是否要沿用某个模板或视觉风格。默认应生成新的可编辑 `.pptx`。 |
| 检索边界 | 建议 | 是否允许联网检索、优先使用哪些来源、是否只能使用用户提供材料、是否需要中文来源或英文来源。默认会检索权威且可追踪来源。 |
| 修改范围 | 适用于返工 | 如果是修改已有 PPT，请明确“只改什么”。本 skill 默认遵守单点修订原则，不会顺手重写其他页面。 |

最理想的输入组合是：

1. 一份明确的作业要求。
2. 一份清楚的主题说明。
3. 一批可读取的本地课程材料或参考资料。
4. 一句话说明输出文件名、页数范围、是否允许联网检索。

## Codex 会输出什么

一次完整任务中，Codex 通常应交付：

- 一个可编辑的 `.pptx` 文件，文件名应体现主题，而不是 `output.pptx` 或 `deck.pptx`。
- 必要时提供 PDF、页面预览图或接触表，用于检查版式和投影可读性。
- 清楚说明使用了哪些本地材料和网络来源。
- 说明完成了哪些检查，例如页数、章节结构、字号、溢出、重叠、来源可追踪性等。
- 如果某些数据没有找到可靠来源，应说明限制，而不是编造数字或引用。

## 推荐调用方式

用户可以直接在 Codex 中这样说：

```text
Use $coursework-ppt to create a rigorous, source-backed coursework presentation.

作业要求：/path/to/作业要求.txt
主题说明：/path/to/主题说明.txt
参考材料：/path/to/课程资料文件夹
输出：/path/to/课程汇报_主题名.pptx

要求：
1. 先读取本地材料，再检索权威来源。
2. 按老师要求的章节结构制作。
3. PPT 字号要适合课堂投影。
4. 最终说明使用的来源和完成的检查。
```

中文调用示例：

```text
请使用 $coursework-ppt 帮我完成这次课程作业 PPT。

作业要求文件：/path/to/作业要求.pdf
主题说明文件：/path/to/主题说明.txt
课程材料目录：/path/to/材料/
输出文件：/path/to/作业类PPT_最终版.pptx

注意：
- 章节必须按老师要求来，不要自己另起结构。
- 数据和政策内容要有真实来源。
- 每页只表达一个主要观点，字号要清楚。
- 做完后请说明检查了哪些内容。
```

更简短的调用也可以：

```text
用 $coursework-ppt 做这个课程汇报 PPT。要求在 A.pdf，主题在 B.txt，材料都在 materials 文件夹，输出到 final.pptx。允许联网查资料，引用要真实。
```

返工时建议这样说：

```text
请使用 $coursework-ppt 修改这个已有 PPT：只把所有引用来源字号放大，其他内容和布局不要动。
```

## Skill 的工作流程

本 skill 的标准流程如下：

1. 读取本地材料：检查当前项目中的作业要求、主题说明、评分标准、老师文件、已有 PPT、PDF、Word、表格和用户提供的文本材料。
2. 提取任务边界：确认课程、主题、受众、页数或时长、固定章节、格式要求、成员信息、必须使用或不能使用的内容。
3. 检索权威来源：在用户没有禁止联网时，优先查找政府机构、官方政策、学术论文、行业报告、统计机构、标准组织或原始机构页面。
4. 记录证据链：记录来源标题、发布机构、日期、链接，以及该来源支持的观点、数据或案例。
5. 规划页面结构：在任务较宽泛或新建 PPT 时，先规划每页的主张、证据对象、展示方式和在整体论证中的作用。
6. 编写学术化内容：每页保留一个主要观点，围绕“观点 - 证据 - 分析”展开，避免空泛口号和明显 AI 任务执行话术。
7. 设计课堂可读版式：使用简洁正式的视觉系统，优先使用图表、流程图、矩阵、数据卡片、时间线、对比布局和结构图，而不是堆砌长段落。
8. 处理引用和来源：关键来源应放在页脚或资料来源页，字号应可读，所有定量说法都应能追踪到来源。
9. 生成可编辑 PPTX：输出有主题含义的 `.pptx` 文件，必要时配合官方 presentation 工具链渲染预览。
10. 验证和交付：检查章节结构、页数、主题贴合度、来源真实性、文字溢出、元素重叠、字号可读性和整体一致性，并在最终回复中说明结果。

## 写作和证据原则

本 skill 最重要的原则是“先证据，后表达”。默认禁止：

- 编造数据、年份、报告名称、引用、链接或机构名称。
- 在没有依据时补充看似专业的结论。
- 为了凑页数加入无关行业、无关技术或无关案例。
- 使用“赋能”“主心骨”“大动脉”“大闭环”“全链路”等空泛表达，除非已经具体定义。
- 使用“严格遵照用户要求”“根据用户要求制作”等明显 AI 执行痕迹。
- 在用户只要求单点修改时，顺手重排、重写或改变其他页面。

默认允许：

- 将本地材料重新组织为更清楚的汇报逻辑。
- 为观点补充真实、权威、可追踪的公开来源。
- 把长段落改写为适合 PPT 的短句、结构图、表格或数据卡片。
- 根据课程主题选择更合适的正式视觉风格。
- 在缺少可靠数字时使用定性表述，并说明数据限制。
- 在信息不足且无法从本地材料判断时，向用户提出简短问题。

## 质量检查

交付前应尽量完成以下检查：

- 作业结构：是否严格符合老师要求的章节、页数、主题范围和呈现顺序。
- 论证质量：每页是否有明确主张、证据和分析，而不是只有标题和空话。
- 来源真实性：关键数据、政策、报告、案例是否有真实可访问来源。
- 引用可读性：页脚来源或资料来源页是否字号足够，是否能看清来源名称和年份。
- 课堂可读性：标题、正文、图表标签、数据标签是否适合投影阅读。
- 版式稳定性：是否存在文字溢出、元素重叠、图表遮挡、页面拥挤或留白失衡。
- 文件可用性：最终 `.pptx` 是否可编辑，文件名是否清楚，必要时是否生成预览或 PDF。
- 返工范围：如果是后续修改，是否只改了用户指定的项目。

## 目录结构

```text
codex skill_作业类PPT制作/
├── README.md
└── skill包/
    └── coursework-ppt/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## 安装和使用提示

这个仓库的核心 skill 文件夹是：

```text
skill包/coursework-ppt
```

如果需要安装到 Codex 的 skills 目录，通常应将该文件夹复制到 Codex 的 skills 位置，使 Codex 能识别其中的 `SKILL.md`。安装后，在新会话中可通过 `$coursework-ppt` 显式调用，也可以在用户提出“作业类 PPT、课程汇报 PPT、小组展示、案例分析 PPT”等请求时由 Codex 自动触发。

为了提高成功率，用户调用时应尽量使用明确文件路径，不要只说“资料都在附件里”或“帮我做个 PPT”。尤其是文件夹里同时有 Word、PDF、Excel、旧 PPT、老师课件和参考资料时，明确指出哪个是作业要求、哪个是主题说明、哪些是参考材料，会显著提升结果稳定性。

## 已知限制

- 本 skill 不能替代用户确认课程要求；如果老师要求不完整或互相矛盾，Codex 需要先澄清。
- 网络来源可能随时间变化，重要数据和政策应优先使用官方或权威来源，并在制作时现场核验。
- 扫描版 PDF、图片课件或低清截图可能需要 OCR，识别质量会影响材料提取。
- 某些学校模板、字体或母版样式在无界面环境下可能无法完全复刻，需要渲染预览检查。
- 如果用户禁止联网检索，PPT 的证据范围会受限于本地材料，不应编造外部数据。
- 本 skill 负责帮助制作课程作业展示稿，不负责保证分数、替代课堂答辩、伪造研究或规避学术诚信要求。

## 交付结果应包含

一次合格的最终回复通常应包含：

- 最终 `.pptx` 文件路径。
- 使用的本地材料和主要网络来源。
- 是否遵守老师要求的章节结构。
- 已完成的检查，例如页数、字号、溢出、重叠、来源追踪和预览渲染。
- 仍需用户确认的事项，例如封面信息、成员名单、老师特殊要求或无法核验的数据。

---

## English

This is a Codex skill for creating rigorous, source-backed coursework PowerPoint presentations. It is designed for class assignments, group presentations, case studies, personal coursework reports, classroom defenses, and research-style presentations that require Codex to read local materials, verify sources, plan the argument, and produce an editable `.pptx`.

The core goal is simple: the user provides assignment requirements, topic materials, and any course or instructor structure; Codex uses this skill to inspect the local files first, research authoritative sources, plan each slide's claim and evidence, and then build a readable classroom presentation with traceable citations. This is not a generic template-based slide generator. It treats a coursework deck as an academic presentation artifact with evidence, reasoning, and clear boundaries.

By the way, actually you can directly give the repository link to Codex and let it install by itself. After installation, do not rush into the task immediately. You can say, "I want to use this skill. What files do I need to prepare for you?"

## Skill Information

- Skill name: `coursework-ppt`
- Skill path: `skill包/coursework-ppt`
- Entry file: `skill包/coursework-ppt/SKILL.md`
- Interface config: `skill包/coursework-ppt/agents/openai.yaml`
- Display name: `作业类 PPT`

## What This Skill Is For

Use this skill for tasks such as:

- Creating PowerPoint decks from coursework requirements.
- Building group or individual class presentations from an instructor-defined structure.
- Producing case-study, course research, industry analysis, policy analysis, or classroom defense decks.
- Turning local PDFs, Word files, spreadsheets, notes, existing slides, or course materials into a structured presentation.
- Adding real and traceable sources for data, policies, reports, cases, and key claims.
- Creating classroom-readable slides with larger typography and clear layouts.
- Making narrow follow-up edits to an existing deck, such as changing only the cover background or enlarging only citation text.

This skill is not intended for:

- Generating generic slide templates without evidence or source materials.
- Inventing data, references, report titles, URLs, or case details.
- Creating commercial marketing decks, launch decks, or purely visual poster-like slides instead of coursework presentations.
- Working with no topic, no assignment requirements, and no permission to do necessary research.
- Ignoring the instructor's required chapter structure or broadly redesigning content that the user only asked to edit narrowly.

## What Users Should Provide

For best results, users should provide or clearly identify these materials:

| Material | Required | Notes |
| --- | --- | --- |
| Assignment requirements | Strongly recommended | Course name, task type, instructor requirements, rubric, page count or presentation length, required chapters, and formatting rules. This may be a text file, Word document, PDF, image, or instructor slide. |
| Topic brief | Required | Presentation topic, research object, case boundary, industry or course context, and the main question the deck should answer. |
| Local reference materials | Recommended | Course readings, notes, instructor materials, existing drafts, PDFs, reports, spreadsheets, old slides, or group work materials. Codex should read local materials first. |
| Fixed metadata | Sometimes required | Group members, name, student ID, class, course, instructor, date, school, department, or other cover information. Missing required metadata should be requested, not invented. |
| Output requirements | Recommended | Output file name, destination folder, whether PDF or preview images are needed, and whether a template or visual style should be followed. The default should be a new editable `.pptx`. |
| Research boundaries | Recommended | Whether web research is allowed, preferred source types, whether only user-provided materials may be used, and whether sources should be Chinese, English, or both. |
| Revision scope | For follow-up edits | For an existing deck, specify exactly what should change. This skill defaults to narrow edits and preserves unrelated content and layout. |

The ideal input set is:

1. A clear assignment requirement file.
2. A concise topic brief.
3. Readable local course materials or references.
4. A short instruction for output file name, slide count range, and whether web research is allowed.

## What Codex Should Output

A complete task should usually deliver:

- An editable `.pptx` file with a topic-based file name, not `output.pptx` or `deck.pptx`.
- PDF, slide previews, or contact sheets when useful for checking layout and readability.
- A clear note about which local materials and web sources were used.
- A summary of checks completed, such as slide count, required structure, typography, overflow, overlaps, and source traceability.
- A limitation note when no reliable number or source can be found, instead of invented data.

## Recommended Prompts

Example:

```text
Use $coursework-ppt to create a rigorous, source-backed coursework presentation.

Assignment requirements: /path/to/requirements.txt
Topic brief: /path/to/topic.txt
Reference materials: /path/to/course-materials
Output: /path/to/coursework_topic_final.pptx

Requirements:
1. Read local materials first, then research authoritative sources.
2. Follow the instructor's required chapter structure.
3. Use typography suitable for classroom projection.
4. Report the sources used and the checks completed.
```

Chinese example:

```text
请使用 $coursework-ppt 帮我完成这次课程作业 PPT。

作业要求文件：/path/to/作业要求.pdf
主题说明文件：/path/to/主题说明.txt
课程材料目录：/path/to/材料/
输出文件：/path/to/作业类PPT_最终版.pptx

注意：
- 章节必须按老师要求来，不要自己另起结构。
- 数据和政策内容要有真实来源。
- 每页只表达一个主要观点，字号要清楚。
- 做完后请说明检查了哪些内容。
```

Short prompt:

```text
Use $coursework-ppt for this class presentation. Requirements are in A.pdf, topic is in B.txt, materials are in the materials folder, and output should be final.pptx. Web research is allowed; citations must be real.
```

Follow-up edit prompt:

```text
Use $coursework-ppt to revise this existing deck: only enlarge all citation text. Do not change any other content or layout.
```

## Workflow

The skill follows this workflow:

1. Read local materials: Inspect assignment requirements, topic notes, rubrics, instructor files, existing slides, PDFs, Word documents, spreadsheets, and user text files.
2. Extract task boundaries: Identify the course, topic, audience, slide count or presentation length, fixed chapters, formatting rules, member information, and non-negotiable wording.
3. Research authoritative sources: Unless the user forbids browsing, prioritize government agencies, official policies, academic papers, industry reports, statistical bureaus, standards bodies, and original institution pages.
4. Record evidence: Track source title, publisher, date, link, and the claim or data point each source supports.
5. Plan the deck: For broad or new tasks, plan each slide's claim, evidence object, presentation form, and role in the argument before creating the PPTX.
6. Write academically: Give each slide a clear point, evidence, and reasoning. Avoid empty buzzwords and obvious AI task-execution phrasing.
7. Design for classroom readability: Use a simple formal visual system, with diagrams, process flows, matrices, data cards, timelines, comparisons, and structured visuals instead of dense paragraphs.
8. Handle citations visibly: Put key sources in readable footers or a final source slide. Every quantitative claim should be traceable.
9. Build an editable PPTX: Export a meaningfully named `.pptx`, using the official presentation workflow when available.
10. Verify and deliver: Check required structure, slide count, topic fit, source traceability, typography, overflow, overlaps, and visual consistency.

## Evidence and Writing Rules

The most important rule is: evidence first, expression second. By default, Codex must not:

- Invent data, years, report names, citations, URLs, or institution names.
- Add professional-sounding claims without evidence.
- Add unrelated industries, technologies, or cases just to fill slides.
- Use vague buzzwords unless they are concretely defined and necessary.
- Use obvious AI phrasing such as "strictly following the user request" in the deck.
- Broadly rewrite or redesign other slides when the user requested a single narrow edit.

By default, Codex may:

- Reorganize local materials into a clearer presentation argument.
- Add real, authoritative, and traceable public sources.
- Convert long prose into slide-friendly short text, diagrams, tables, or data cards.
- Choose a formal visual style that fits the course topic.
- Use qualitative wording and disclose limitations when no reliable number is found.
- Ask a concise question when required information is missing and cannot be inferred from local materials.

## Quality Checks

Before delivery, Codex should complete as many of these checks as possible:

- Assignment structure: required chapters, slide count, topic scope, and presentation sequence.
- Argument quality: each slide has a clear claim, evidence, and analysis.
- Source authenticity: key data, policies, reports, and cases have real accessible sources.
- Citation readability: source notes or the source slide are large enough to read.
- Classroom readability: titles, body text, chart labels, and data labels work for projection.
- Layout stability: no text overflow, overlaps, blocked charts, overcrowding, or awkward whitespace.
- File usability: the final `.pptx` is editable and meaningfully named; previews or PDFs are generated when useful.
- Revision scope: for follow-up edits, only the requested item was changed.

## Repository Structure

```text
codex skill_作业类PPT制作/
├── README.md
└── skill包/
    └── coursework-ppt/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## Installation and Usage Notes

The actual skill folder is:

```text
skill包/coursework-ppt
```

To install it into Codex, copy that folder into the Codex skills directory so Codex can discover its `SKILL.md`. After installation, users can call it explicitly with `$coursework-ppt`, or Codex may invoke it automatically when the request asks for a coursework PPT, class presentation, group report, or case-analysis deck.

For reliable results, users should provide explicit file paths instead of saying only "the files are attached" or "make a PPT for me." This is especially important when a folder contains Word documents, PDFs, spreadsheets, old slides, instructor materials, and reference files at the same time.

## Known Limitations

- This skill cannot replace user confirmation of course requirements. If instructor requirements are incomplete or contradictory, Codex should clarify them.
- Web sources can change over time. Important data and policies should be verified live from authoritative sources during production.
- Scanned PDFs, image-only slides, or low-resolution screenshots may require OCR, and OCR quality affects extraction.
- Some school templates, fonts, or slide master styles may not reproduce perfectly in a headless environment and should be checked through rendered previews.
- If the user forbids web research, evidence is limited to local materials and Codex should not invent external data.
- This skill helps create coursework presentations. It does not guarantee grades, replace oral defense, fabricate research, or bypass academic integrity requirements.

## Expected Delivery

A good final response from Codex should include:

- Final `.pptx` file path.
- Local materials and main web sources used.
- Whether the instructor's required chapter structure was followed.
- Checks completed, such as slide count, typography, overflow, overlaps, source traceability, and rendered preview checks.
- Any remaining items for the user to confirm, such as cover metadata, group members, instructor-specific rules, or unverifiable data.
