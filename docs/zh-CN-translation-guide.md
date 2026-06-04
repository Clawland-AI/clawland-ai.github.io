# Clawland Chinese Translation Style Guide

This guide keeps Simplified Chinese documentation consistent across Clawland
repositories. It supports the Chinese Documentation Translation bounty by giving
reviewers and contributors a shared terminology and quality checklist.

## Goals

- Use natural Simplified Chinese for developers and hardware builders.
- Preserve the meaning of the English source without literal machine-style phrasing.
- Keep product names, repository names, commands, code, URLs, and API paths stable.
- Make bounty, contribution, and safety language clear enough for first-time contributors.

## Core Terms

| English | Simplified Chinese | Notes |
|---|---|---|
| AI Agent | AI Agent | Keep the mixed term because it is already common in developer docs. |
| edge AI | 边缘 AI | Use for the general technical category. |
| Edge Node | Edge Node / 边缘节点 | Keep `Edge Node` in API tables; use `边缘节点` in prose when readability matters. |
| Fleet Manager | Fleet Manager | Keep as a product or component name. |
| Dashboard | Dashboard / 仪表盘 | Keep `Dashboard` for component names; use `仪表盘` for UI descriptions. |
| MessageBus | MessageBus | Keep exact code identifier. |
| heartbeat | heartbeat / 心跳 | Keep `heartbeat` in API names; use `心跳` in explanatory prose. |
| command | 命令 | Use for device or fleet control actions. |
| status | 状态 | Use for node state, health, and runtime summaries. |
| sensor | 传感器 | Use consistently for hardware readings. |
| skill | skill | Keep lowercase `skill` when referring to Clawland skill files. |
| bounty | 赏金任务 | Prefer `赏金任务` over only `赏金` in contributor-facing docs. |
| Build to Earn | Build to Earn | Keep the program name in English, then explain in Chinese if needed. |
| revenue share | 收入分成 | Use for contributor revenue-sharing docs. |
| open source | 开源 | Use in prose; keep license names in English. |
| Quick Start | 快速开始 | Use for documentation titles and navigation. |
| Contributing Guide | 贡献指南 | Use for documentation titles and navigation. |
| API docs | API 文档 | Keep `API` uppercase. |
| BOM | BOM | Keep uppercase and explain as `物料清单` on first use if needed. |
| wiring diagram | 接线图 | Use for hardware kit docs. |
| firmware | 固件 | Use for MCU and board software. |
| OTA update | OTA 更新 | Keep `OTA` uppercase. |
| mock data | mock 数据 | Use for examples that are not real production data. |
| redacted data | 脱敏数据 | Use when private data has been removed. |

## Product And Repository Names

Do not translate product or repository names:

- Clawland
- PicClaw
- NanoClaw
- MicroClaw
- MoltClaw
- clawland-fleet
- clawland-skills
- clawland-kits

Use the exact spelling shown in upstream repositories. If an English source uses
both `PicoClaw` and `PicClaw`, keep the spelling from the repository or issue
being translated and avoid mixing both spellings in the same page.

## Tone

- Prefer concise developer Chinese over marketing-style copy.
- Use active voice where possible: `提交 PR` instead of `PR 被提交`.
- Keep requirements direct: `必须`, `需要`, `建议`, and `避免` are clearer than vague wording.
- Avoid exaggerated claims that are not in the English source.
- Translate contributor-facing money language carefully. Do not imply that opening
  a PR guarantees payment; say that payment depends on maintainer review,
  acceptance, and the project payout process.

## Markdown And Code Rules

- Keep code fences unchanged unless the source command is intentionally translated.
- Do not translate package names, import paths, API routes, environment variables,
  file names, branch names, or repository names.
- Keep Markdown heading levels aligned with the English source.
- Keep relative links valid after moving a page into a Chinese route.
- Translate link text when it is normal prose, but keep external product names unchanged.
- Preserve warning, note, and checklist structure so reviewers can compare sections quickly.

## Review Checklist

Before opening a Chinese documentation PR, verify:

- Native-quality Simplified Chinese, not direct machine translation.
- Terminology matches the table above.
- Commands, API paths, code identifiers, and repository names are unchanged.
- Markdown renders without broken heading hierarchy or table formatting.
- Links point to existing pages or clearly marked future pages.
- Bounty and revenue-share wording does not promise automatic payment.
- Any production secrets, private URLs, customer names, or real tokens are absent.

## Suggested PR Validation

Use the checks that fit the repository:

```bash
npm run build
```

For Markdown-only repositories without a build script, include a short manual
validation note in the PR:

```text
Validation:
- Checked Markdown tables and links in the changed Chinese docs.
- Preserved code fences, commands, API paths, and repository names.
- Reviewed terminology against docs/zh-CN-translation-guide.md.
```
