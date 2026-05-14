---
title: "Clawland 快速开始"
description: "如何选择 Clawland Agent、克隆仓库并完成第一次本地验证。"
---

# 快速开始

本页帮助你在最短时间内判断应该从哪个 Clawland 仓库开始，并完成一次最小可验证的贡献准备。

## 1. 选择你的 Agent

| 你手上有什么 | 建议使用 | 仓库 |
|---|---|---|
| 约 10 美元 RISC-V 边缘板 | PicClaw | `Clawland-AI/picclaw` |
| Raspberry Pi 或其他单板机 | NanoClaw | `Clawland-AI/nanoclaw` |
| ESP32 / 低功耗 MCU | MicroClaw | `Clawland-AI/microclaw` |
| 云服务器、Mac mini 或开发机 | MoltClaw / Fleet | `Clawland-AI/moltclaw`、`Clawland-AI/clawland-fleet` |

如果你只是想快速贡献，优先选择文档、skill、测试或 Fleet API 这类不依赖实体硬件的任务。

## 2. 克隆仓库

以 PicClaw 为例：

```bash
git clone https://github.com/Clawland-AI/picclaw.git
cd picclaw
```

以 skills 仓库为例：

```bash
git clone https://github.com/Clawland-AI/clawland-skills.git
cd clawland-skills
```

## 3. 跑通本地检查

不同仓库的命令可能不同。常见检查方式包括：

```bash
go test ./...
npm test
npm run build
python -m pytest
```

如果仓库当前没有完整测试脚本，请在 PR 中说明你执行过的最小验证，例如 YAML 能被解析、Markdown 链接有效、示例命令能够运行，或者核心函数有单元测试覆盖。

## 4. 选择一个小任务

优先挑选这些类型：

- 文档修复、中文翻译、Quick Start 补充
- 新增一个独立 skill
- 为现有模块补测试
- 实现一个边界清晰的小 API endpoint
- 修复一个可以复现的 bug

避免一开始就做范围很大的 dashboard、硬件设计或完整端到端系统，除非 issue 已经明确写出验收标准。

## 5. 提交贡献计划

在 issue 下留言时，建议包含：

- 你准备改哪些文件
- 你会交付什么结果
- 你不会触碰哪些范围
- 你预计如何验证

示例：

```text
I would like to work on this. I will add a focused Chinese documentation slice:
README.zh-CN, Quick Start, Contributing, and API overview. I will keep links
aligned with the existing English docs and verify the Astro build.
```

## 6. 开 PR

PR 描述建议包含：

- Summary：具体改了什么
- Validation：执行了哪些检查
- Bounty reference：如果对应赏金任务，引用 Bounty Board 或 issue

小 PR、清晰范围和可复现验证，通常比一次塞进大量无关改动更容易合并。
