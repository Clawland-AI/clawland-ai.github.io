# API 与 CLI 参考

本文整理 Clawland/PicClaw 当前公开文档中的核心接口和命令，便于中文开发者快速查阅。

## CLI 命令

| 命令 | 说明 |
| --- | --- |
| `picoclaw onboard` | 初始化配置和工作区 |
| `picoclaw agent -m "..."` | 一次性对话 |
| `picoclaw agent` | 进入交互式 Agent 模式 |
| `picoclaw gateway` | 启动网关模式，包含 channels、cron、edge 和 heartbeat |
| `picoclaw status` | 查看配置状态 |
| `picoclaw cron list` | 列出定时任务 |
| `picoclaw cron add` | 添加定时任务 |
| `picoclaw skills list` | 列出已安装 skills |
| `picoclaw skills install <url>` | 从 Git 仓库安装 skill |
| `picoclaw skills install-builtin` | 安装全部内置 skills |
| `picoclaw gene list` | 查看本地 genes 及置信度 |
| `picoclaw gene stats` | 查看 gene pool 统计 |
| `picoclaw gene export` | 导出 genes JSON |
| `picoclaw version` | 查看版本 |

## Edge Server API

启用 `edge.enabled` 后，PicClaw 会作为 L1 edge node 暴露基础 HTTP API。

### `GET /healthz`

健康检查接口，用于本机探活、容器编排、上游 Fleet 监测。

### `GET /api/v1/status`

返回节点状态，通常包括节点标识、运行状态、心跳信息、gene 统计等摘要信息。具体字段以当前实现为准。

### `POST /api/v1/command`

接收来自上游 Fleet Manager 的命令。适用于远程触发检测、调整阈值、执行预定义 skill 或发送控制指令。

## 内置工具

| Tool | 说明 |
| --- | --- |
| `read_file` | 读取文件内容 |
| `write_file` | 创建或覆盖文件 |
| `edit_file` | 基于搜索替换修改文件 |
| `append_file` | 追加文件内容 |
| `list_dir` | 列出目录内容 |
| `exec` | 执行 Shell 命令 |
| `spawn` | 启动后台进程 |
| `web_search` | 搜索网页 |
| `web_fetch` | 抓取并提取网页内容 |
| `message` | 通过配置的渠道发送消息 |
| `cron` | 创建或管理定时任务 |
| `report_gene` | 向 Gene Evolution 系统上报经验 |

## 消息渠道

| Channel | 配置项 | 备注 |
| --- | --- | --- |
| Telegram | `token`, `allow_from` | 推荐渠道；配合 Groq 可支持语音消息 |
| Discord | `token`, `allow_from` | 需要启用 MESSAGE CONTENT INTENT |
| QQ | `app_id`, `app_secret` | QQ Open Platform |
| DingTalk | `client_id`, `client_secret` | 钉钉内部应用 |
| Feishu | `app_id`, `app_secret`, `encrypt_key`, `verification_token` | 飞书/Lark bot |
| WhatsApp | `bridge_url` | 通过 WhatsApp bridge |
| MaixCam | `host`, `port` | 直接连接硬件 |

## Gene Evolution Protocol

PicClaw 的 CGEP 通过运行经验改进监测策略：

1. 从传感器数据、memory 和每日记录中提取 signals。
2. 将 signals 与 gene pool 匹配，把高分 genes 注入 LLM system prompt。
3. 处理完成后，把经验 solidify 为 capsules。
4. 成功的新策略可生成 genes。
5. 高置信度 genes 可发布到 Fleet，供其他节点复用。

内置 signal 类型包括：

- `sensor_error`
- `threshold_breach`
- `cross_sensor_anomaly`
- `new_pattern_detected`
- `response_too_slow`
- `strategy_proven`
- `unknown_situation`
- `time_pattern`

## 配置片段

### Provider

```json
{
  "providers": {
    "openrouter": {
      "api_key": "YOUR_API_KEY"
    }
  }
}
```

### Telegram

```json
{
  "channels": {
    "telegram": {
      "enabled": true,
      "token": "123456:ABC-DEF...",
      "allow_from": ["YOUR_USER_ID"]
    }
  }
}
```

### Gene

```json
{
  "gene": {
    "strategy": "balanced",
    "auto_publish": true,
    "min_confidence": 0.7,
    "min_verified_by": 3
  }
}
```

