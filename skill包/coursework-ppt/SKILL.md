---
name: coursework-ppt
description: Create rigorous, source-backed coursework PowerPoint decks. Use when the user asks for 作业类 PPT, 课程作业 PPT, 小组汇报 PPT, 案例分析 PPT, 个人作业展示 PPT, course presentation decks, or any school assignment PPT that should be built from local requirements, verified sources, real data, careful argumentation, large readable typography, and controlled one-item revisions.
---

# Coursework PPT

## Operating Principle

Build coursework decks as researched academic presentation artifacts, not generic AI slides. First read, then research, then plan, then build, then verify. Prefer rigorous evidence, clear reasoning, and readable design over decorative language or template-driven output.

When a presentation plugin or skill is available, use its official workflow for editable PPTX creation, rendering, preview checks, and export.

## Required Workflow

1. **Read local materials first**
   - Inspect the current project for assignment requirements, topic notes, rubrics, teacher files, existing slides, reference PDFs, spreadsheets, and user-provided text files.
   - Extract the course, topic, audience, required structure, page range, formatting rules, group or personal task split, and any fixed wording or names.
   - Do not ask for information that is discoverable from local files.

2. **Research before planning**
   - Browse the web for authoritative, current, and traceable sources unless the user explicitly forbids browsing.
   - Prefer government agencies, official policy documents, academic papers, recognized industry reports, statistical bureaus, standards bodies, and original institution pages.
   - Record source title, publisher, date, link, and the claim or data point it supports.
   - Do not invent data, citations, report names, chart values, or fake URLs. If no reliable number is found, use a qualitative claim and explain the limitation.

3. **Plan the deck before building**
   - Propose a page-by-page structure before creating the PPTX when the request is broad or new.
   - Make the plan obey the teacher's required chapter structure exactly. If the assignment requires sections such as "现状情况、存在问题、解决办法（方案）", use those as the main chapters and place all other content within them.
   - Include each slide's claim, proof object, expected evidence, and role in the argument.

4. **Write with academic discipline**
   - Give every slide a real point, evidence, and reasoning.
   - Explain causes and mechanisms before jumping to solutions.
   - Avoid vague high-level phrases such as "赋能", "主心骨", "大动脉", "大闭环", and "全链路" unless they are concretely defined and necessary.
   - Avoid obvious AI or task-execution wording such as "严格遵照作业要求" and "根据用户要求". Use natural presentation phrasing instead, such as "本报告从现状、问题与方案三个方面展开".
   - Keep the topic boundary tight. Do not add unrelated industries, technologies, or sections just to fill pages.

5. **Design for classroom readability**
   - Use an elegant, simple, formal visual system appropriate to the subject.
   - Keep typography larger than typical AI-generated slides: titles, body text, section markers, data labels, and source notes must remain readable when projected.
   - Prefer diagrams, process flows, matrices, evidence tables, architecture maps, timelines, data cards, and comparison layouts over dense paragraphs.
   - Each slide should carry one main claim. Do not crowd the page with long prose.
   - Use real or verified visual assets when the subject needs images; otherwise favor clean editable shapes and charts.

6. **Handle citations and evidence visibly**
   - Put key sources in a readable footer or final source page.
   - Make source notes large enough to read, not tiny gray decoration.
   - Ensure every quantitative claim can be traced to a source note or source list.
   - Include a final "资料来源" slide when it improves credibility.

7. **Build and verify**
   - Export an editable `.pptx` with a meaningful topic-based filename, not `output.pptx` or `deck.pptx`.
   - Render previews or contact sheets when tooling permits.
   - Check page count, required chapter structure, topic fit, source traceability, typography, overflow, overlaps, and visual consistency.
   - Report the final file path and the verification performed.

## User Input Expectations

When the user has not provided enough detail, infer what can be discovered locally before asking. The ideal project contains:

- `作业要求.txt` or similar: course, assignment type, required structure, page or time limits, rubric, template rules, and non-negotiable content.
- `主题说明.txt` or similar: title, research object, scene boundaries, required cases or technologies, preferred tone, and design preferences.
- Optional teacher slides, rubrics, papers, reports, links, school templates, prior examples, group names, class, and student IDs.

If these are absent, proceed with a conservative assumption only when it is safe; otherwise ask a concise question that materially changes the deck.

## Revision Rule

When the user requests a follow-up change after a deck exists, treat it as a single-item edit unless they explicitly ask for broader revision. Change only the stated item, preserve all other content and layout, regenerate the PPTX, and verify the file still opens and has the expected slide count.

Examples:

- "只改封面背景" means change only the cover background.
- "把引用字号放大" means adjust only source-note typography.
- "重命名文件" means rename only the file, not slide content.

## Quality Bar

The deck should pass these checks:

- The structure follows the assignment exactly.
- Sources are real, traceable, and appropriate.
- Claims are not generic and are supported by evidence.
- The prose sounds natural for a student or academic presentation.
- Fonts are comfortably readable.
- The design is polished, simple, and consistent.
- Later edits remain narrowly scoped.
