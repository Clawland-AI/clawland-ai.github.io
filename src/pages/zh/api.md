---
title: "Clawland API 概览"
description: "Clawland Fleet 与 Edge API 的中文概览。"
---

# API 概览

本页是 Clawland 核心 API 的中文概览，帮助贡献者理解各类接口的职责边界。具体字段以各仓库中的代码、OpenAPI 文件或 README 为准。

## 分层关系

Clawland 通常可以理解为三层：

- Edge Node：PicClaw、NanoClaw 或 MicroClaw 运行在设备侧，负责读取传感器、执行命令、上报状态。
- Fleet Manager：云端或局域网服务，负责注册节点、接收 heartbeat、下发命令、聚合事件。
- Dashboard / Integrations：面向操作员、业务系统或第三方工具的可视化与集成层。

## 常见接口类型

| 接口 | 方向 | 作用 |
|---|---|---|
| Health | 外部到服务 | 判断服务是否存活，适合负载均衡或监控探针 |
| Status | 外部到 Edge | 获取节点当前状态、版本、运行时间和传感器摘要 |
| Message | Edge 与 Fleet 双向 | 传递普通事件、日志、传感器数据或系统消息 |
| Command | Fleet 到 Edge | 下发重启、切换模式、控制继电器、采样等命令 |
| Heartbeat | Edge 到 Fleet | 周期性报告节点在线、负载、最后采样时间和异常 |
| Event | Edge 到 Fleet | 上报告警、阈值触发、设备故障或业务事件 |

## Edge API 建议语义

典型 Edge API 可以包含：

```http
GET /api/health
GET /api/status
POST /api/message
POST /api/command
```

建议原则：

- `GET /api/health` 只返回轻量健康信息，不依赖慢外部服务。
- `GET /api/status` 返回更完整的节点状态，可以包含传感器摘要。
- `POST /api/message` 用于一般消息或事件，不应用来执行高风险命令。
- `POST /api/command` 需要明确命令类型、参数、幂等 ID 和执行状态。

## Fleet API 建议语义

Fleet Manager 侧通常需要：

- 节点注册：记录 node id、agent 类型、版本、能力和标签。
- Heartbeat 接收：更新在线状态、最后上报时间和运行指标。
- 命令队列：保存待执行命令，等待节点轮询或通过长连接下发。
- 事件聚合：把告警、传感器异常和设备故障统一进入事件流。
- 查询接口：给 Dashboard 或外部系统读取节点状态、命令状态和历史事件。

## 错误处理

API 应该返回结构化错误，至少包含：

- `code`：稳定的机器可读错误码
- `message`：面向开发者的简短说明
- `request_id`：用于排查日志

高风险命令应优先设计成可重试、可审计、可回滚或有超时保护。

## 安全边界

- 不在仓库中提交生产密钥、token、私有 URL 或真实客户数据。
- 命令接口默认不应开放到公网。
- 设备控制类命令要有权限、审计和失败保护。
- 对外示例应使用 mock、sample 或 redacted 数据。

## 给贡献者的建议

提交 API 相关 PR 时，请同时附上：

- 请求/响应示例
- 错误场景
- 最小测试或 curl 验收命令
- 对现有接口兼容性的说明
