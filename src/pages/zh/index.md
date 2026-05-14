---
title: "Clawland 中文文档"
description: "Clawland 边缘 AI Agent 生态的中文文档入口。"
---

# Clawland 中文文档

**用低成本硬件构建边缘 AI Agent，并通过开源贡献获得回报。**

Clawland 是一个开源边缘 AI Agent 生态，目标是让从 2 美元微控制器到云服务器的设备都能承担监测、巡检、告警和自动化控制任务。它把不同成本、性能和运行位置的硬件组织成一套分层 Agent 系统，让开发者可以从小型传感器节点一路扩展到云端 Fleet Manager。

## 适合谁

- 想把 AI Agent 部署到真实硬件上的开发者
- 想做传感器监测、农业水产、冷链、设备巡检或安全看护的团队
- 想通过开源任务、赏金任务和长期贡献参与 Clawland 生态的人
- 想用 Go、TypeScript、Python、C 或 Rust 构建边缘系统的人

## 文档导航

- [快速开始](./quick-start/)：选择 Agent、安装仓库、跑通最小示例。
- [贡献指南](./contributing/)：了解如何选任务、提交 PR、参与赏金和收入共享。
- [API 概览](./api/)：了解 Fleet、Edge、Message、Status 和 Health 等核心接口的职责。

## Agent 家族

| Agent | 适合硬件 | 主要语言 | 典型用途 |
|---|---|---|---|
| PicClaw | 约 10 美元 RISC-V 板 | Go | 轻量边缘节点、传感器网关、本地控制 |
| NanoClaw | Raspberry Pi / 单板机 | Python | 区域网关、复杂数据处理、Python 生态集成 |
| MicroClaw | ESP32 等 MCU | C / Rust | 超低成本传感器节点、MQTT 上报、OTA |
| MoltClaw | 云服务器或 Mac mini | TypeScript | Fleet Manager、云端路由、仪表盘和编排 |

## 贡献与收益

Clawland 的 Build to Earn 模式鼓励开发者通过 issue、PR、文档、硬件设计和 skill 贡献参与生态。公开赏金任务通常会在 Bounty Board 或 GitHub issue 中说明范围、验收方式和支付路径。参与前建议先在对应 issue 留言确认任务仍可认领，再提交计划和 PR。

## 下一步

第一次参与建议按这个顺序走：

1. 读 [快速开始](./quick-start/)。
2. 选择一个与你熟悉语言匹配的 Agent。
3. 在 GitHub 上查看 good first issue 或 Bounty Board。
4. 留言说明你要做的范围和 48 小时内的实现计划。
5. 提交小而完整的 PR，并附测试或验收说明。
