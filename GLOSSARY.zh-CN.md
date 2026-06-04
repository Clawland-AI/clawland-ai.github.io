# Clawland 术语表

本文统一中文文档中的核心术语，避免同一概念被翻译成多个版本。

| English | 中文建议 | 说明 |
| --- | --- | --- |
| Agent | Agent / 智能体 | 首次出现可写作“Agent（智能体）”，后续保留 Agent |
| Edge AI | 边缘 AI | 在靠近设备和现场的位置运行 AI |
| Fleet | Fleet / 节点集群 | 多个 Claw 节点的统一管理视角 |
| Skill | Skill / 技能 | Markdown 形式的领域知识包，建议保留英文 Skill |
| Gene | Gene / 策略基因 | CGEP 中可复用的监测或处理策略 |
| Capsule | Capsule / 经验胶囊 | 从运行经验固化出的结构化记录 |
| MessageBus | MessageBus / 消息总线 | 内部模块通信机制 |
| Provider | Provider / 模型服务提供方 | LLM 服务来源 |
| Channel | Channel / 消息渠道 | Telegram、Discord、飞书等接入渠道 |
| Gateway | Gateway / 网关 | 负责汇聚、转发和协调的节点 |
| Edge Server | Edge Server / 边缘服务 | PicClaw 暴露给上游 Fleet 的 HTTP 服务 |
| Heartbeat | 心跳 | 周期性状态上报 |
| Bounty | Bounty / 赏金任务 | 完成后经 review/merge 支付奖励的任务 |
| Contributor Revenue Pool | 贡献者收入池 | 按季度分配给合格贡献者的净收入池 |
| BOM | 物料清单 | 硬件套件所需零件列表 |
| Wiring diagram | 接线图 | 传感器、开发板和供电连接图 |

## 产品名

产品名不翻译：

- Clawland
- PicClaw
- PicoClaw
- NanoClaw
- MicroClaw
- MoltClaw
- Clawland Fleet

## 风格约定

- 命令、路径、配置项、API endpoint 保持英文原样，例如 `picoclaw gateway`、`~/.picoclaw/config.json`、`GET /healthz`。
- 产品承诺类描述避免夸张化翻译，优先使用准确、可验证的表达。
- 技术缩写首次出现时可补充中文解释，例如 LLM（大语言模型）。
- 代码块、JSON key、环境变量和链接不翻译。

