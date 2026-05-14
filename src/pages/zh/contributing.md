---
title: "Clawland 贡献指南"
description: "中文贡献流程：选任务、留言认领、提交计划、实现、验证和 PR。"
---

# 贡献指南

Clawland 欢迎代码、文档、skill、测试、硬件设计和示例项目等多种贡献。为了减少重复劳动，请先确认任务状态，再开始实现。

## 贡献流程

1. 找到一个 issue、Bounty Board 任务或文档缺口。
2. 阅读对应仓库的 README、许可证和已有 PR。
3. 在 issue 或讨论区留言，说明你想做的范围。
4. 如果是赏金任务，在 48 小时内补充简短实现计划。
5. Fork 仓库，创建分支并提交改动。
6. 运行测试或最小验证。
7. 开 PR，引用 issue 或 Bounty Board 条目。

## 认领任务时写什么

好的认领留言应该具体，而不是只写“我想做”。建议包含：

- 任务名称或 issue 编号
- 你准备改的模块
- 交付物
- 测试方式
- 预计时间

示例：

```text
I would like to work on the Chinese Documentation Translation bounty.
Plan:
- Add README.zh-CN.md and Chinese pages for Quick Start, Contributing, and API overview.
- Keep the translation natural and technical, not machine-literal.
- Update navigation links from the English docs.
- Validate with npm run build.
```

## PR 描述模板

```text
## Summary
- Add ...
- Update ...

## Validation
- npm run build
- Checked links ...

## Bounty
References the Clawland Bounty Board item: ...
```

## 收益和赏金

Clawland 的赏金任务通常会在 Bounty Board 或 issue 中列出金额和验收方式。一般流程是：

1. 在 issue 留言确认任务仍可做。
2. 提交计划，避免与其他贡献者重复。
3. 完成实现并开 PR。
4. 维护者 review、要求修改或合并。
5. PR 被接受后按项目说明处理付款。

请注意：赏金不是只开 PR 就自动付款，通常需要维护者确认范围、审核质量并合并。

## 代码质量原则

- 保持 PR 小而聚焦。
- 不要混入无关格式化。
- 为新逻辑补测试或说明验证方式。
- 不提交密钥、账号、生产配置或私有数据。
- 文档翻译要使用自然、准确的中文，不要逐词机翻。

## 沟通原则

维护者最需要看到的是可验证的结果。写清楚你做了什么、如何验证、还有哪些边界没有覆盖，就能显著降低 review 成本。
