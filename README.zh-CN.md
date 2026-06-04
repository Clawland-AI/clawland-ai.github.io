# Clawland 中文文档

Clawland 是一个开源 Edge AI Agent 生态，目标是在从 2 美元 MCU 到云服务器的硬件上运行可组合、可学习、可协作的 AI Agent。项目希望用低成本边缘硬件承担监测、巡检、维护和告警等重复工作，让人类负责判断、设计和处置。

本文是中文核心文档入口，面向第一次了解 Clawland 的开发者、硬件爱好者和潜在贡献者。

## 生态层级

| 层级 | 项目 | 语言 | 角色 |
| --- | --- | --- | --- |
| L0 Sensor | MicroClaw | C/Rust | 运行在 ESP32 等 MCU 上的传感器级 Agent |
| L1 Edge | PicClaw | Go | 运行在 10 美元级 Linux 边缘设备上的轻量 Agent |
| L2 Gateway | NanoClaw | Python | 区域网关和本地协调层 |
| L3 Cloud | MoltClaw | TypeScript | 云端 Fleet 管理、多 Agent 路由和编排 |

## PicClaw 做什么

PicClaw 是当前最完整的边缘 Agent 实现。它是一个 Go 单二进制程序，设计目标是低内存、快速启动、易部署。

核心能力包括：

- 连接 LLM Provider，例如 Zhipu、OpenRouter、Anthropic、OpenAI、Gemini、Groq 或兼容 vLLM 的服务。
- 执行内置工具，例如文件读写、Shell、网页搜索、定时任务、消息发送和 Gene 上报。
- 接入消息渠道，例如 Telegram、Discord、QQ、钉钉、飞书、WhatsApp 和 MaixCam。
- 通过 Gene Evolution Protocol 从运行经验中沉淀策略。
- 通过 Edge Server 向上游 Fleet 汇报节点状态和心跳。

## 快速入口

- [快速开始](QUICKSTART.zh-CN.md)
- [API 与 CLI 参考](API.zh-CN.md)
- [贡献指南](CONTRIBUTING.zh-CN.md)
- [术语表](GLOSSARY.zh-CN.md)

## 典型场景

| 场景 | 示例 |
| --- | --- |
| 数据中心巡检 | 机柜温度、烟雾、水浸、设备异常告警 |
| 水产养殖 | 溶氧、pH、温度、浊度监测，夜间增氧告警 |
| 温室管理 | 土壤湿度、温湿度、光照、CO2 趋势分析 |
| 冷链合规 | 温度、GPS、4G 上报和合规记录 |
| 设备维护 | 振动、电流、温度等预测性维护信号 |

## Build to Earn

Clawland 的贡献者机制包含两部分：

- Bounty：完成公开赏金任务并通过 review/merge 后获得一次性奖励。
- Contributor Revenue Pool：合格贡献者按季度分享 20% 的净产品收入池。

具体规则以 Clawland 组织仓库中的贡献指南和收入分享协议为准。

## License

不同子项目使用不同许可证。软件项目通常使用 Apache 2.0 或 MIT，硬件设计使用 CERN-OHL-S，Fleet 相关组件可能使用 BSL 1.1。提交贡献前请查看目标仓库的 LICENSE。

