# HTML Creator

## English

HTML Creator is a Codex skill for creating standalone, decision-ready HTML artifacts from Markdown drafts, research notes, reports, PRDs, code-review findings, market briefs, and evidence-heavy material. It treats HTML as the presentation and decision layer while keeping source Markdown, JSON, CSV, or notes as the evidence layer when those sources already exist.

## What It Does

- Selects a page archetype such as decision brief, visual PRD, evidence report, status report, or review page.
- Turns flat source material into scannable sections, tables, evidence tiers, risks, and next actions.
- Adds a diagram layer for flows, state transitions, architecture maps, data movement, dependency maps, and screen journeys when prose would be too flat.
- Prefers self-contained HTML with inline CSS and offline-safe behavior.
- Preserves diagram source text when generated from Mermaid or another diagram DSL.

## When To Use

Use this skill when the user asks for a local HTML report, decision page, visual PRD, high-density review artifact, evidence report, or workflow/architecture explanation. Do not use it for production frontend app implementation, generic landing pages, PowerPoint, Word, PDF, or short text answers.

## Install

Copy the `html-creator/` folder from this branch into your Codex skills directory, for example `~/.codex/skills/html-creator/`.

## Quality Checks

This release was validated with the Codex skill quick validator. The updated instructions also require rendered diagram checks when a generated HTML page contains diagrams.

## 中文

HTML Creator 用于把 Markdown 草稿、研究笔记、报告、PRD、代码审查结果、市场简报和证据密集材料转换成单文件、可浏览、可决策的 HTML 展示物。它把 HTML 定位为展示层和决策层，不替代 Markdown、JSON、CSV 等源证据层。

## 本版重点

- 增加 Diagram Layer，支持流程图、状态图、系统架构、数据流、依赖图和页面旅程。
- 明确 Mermaid / SVG 处理方式：优先离线安全、可检查、可保留源码。
- 强化移动端可读性、图表渲染、标签可读性和无外部依赖检查。

## 适用场景

- 决策页、视觉 PRD、研究报告、状态报告、风险审查页。
- Markdown 太线性，无法表达选项、证据、风险、流程或架构关系。
- 需要在浏览器中阅读、归档或向管理层展示。

## 不适用场景

- 生产前端应用开发。
- 通用营销落地页。
- PPT、Word、PDF、Figma 专用输出。
- 很短的一屏文字说明。

## 发布说明

v1.1.0 增加图形表达层，让 HTML 交付物可以承载流程、状态、架构和数据流，而不是只做简单排版。
