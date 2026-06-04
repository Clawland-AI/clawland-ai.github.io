# Clawland 快速开始

本文用 PicClaw 作为入门路径。PicClaw 是 Clawland 的 L1 Edge Agent，适合在 Linux 边缘设备、Raspberry Pi、RISC-V 开发板或普通服务器上运行。

## 1. 构建 PicClaw

```bash
git clone https://github.com/Clawland-AI/picclaw.git
cd picclaw
make build
```

构建完成后，二进制文件会出现在 `build/` 目录。也可以运行：

```bash
make build-all
```

这会为 Linux、macOS、amd64、arm64、riscv64 等目标构建产物。

## 2. 初始化

```bash
picoclaw onboard
```

初始化流程会创建本地配置和工作区。默认工作区在：

```text
~/.picoclaw/
```

## 3. 配置 LLM Provider

最小配置只需要选择一个 provider 并设置 API key。例如使用 Zhipu：

```json
{
  "agents": {
    "defaults": {
      "model": "glm-4.7",
      "max_tokens": 8192
    }
  },
  "providers": {
    "zhipu": {
      "api_key": "YOUR_API_KEY"
    }
  }
}
```

支持的 provider 包括 Zhipu、OpenRouter、Anthropic、OpenAI、Gemini、Groq，以及自托管 vLLM endpoint。

## 4. 运行 Agent

一次性提问：

```bash
picoclaw agent -m "What is 2+2?"
```

交互模式：

```bash
picoclaw agent
```

启动网关模式：

```bash
picoclaw gateway
```

网关模式会同时启用消息渠道、cron、edge 心跳和相关后台服务。

## 5. 启用 Edge Server

示例配置：

```json
{
  "edge": {
    "enabled": true,
    "port": 9090,
    "node_id": "dc-rack-a1",
    "node_name": "Datacenter Rack A1",
    "cloud_endpoint": "http://nanoclaw:8080",
    "cloud_token": "...",
    "heartbeat_seconds": 30
  }
}
```

启用后，PicClaw 会暴露：

- `GET /healthz`
- `GET /api/v1/status`
- `POST /api/v1/command`

并按配置向上游 Fleet Manager 发送心跳。

## 6. 安装 Skills

查看内置 skills：

```bash
picoclaw skills list
```

安装内置 skills：

```bash
picoclaw skills install-builtin
```

从 Git 仓库安装：

```bash
picoclaw skills install <git-url>
```

## 7. 数据中心监测 Demo

内置 `datacenter-monitoring` skill 可用于本地模拟：

```bash
python3 skills/datacenter-monitoring/scripts/mock-sensor.py --all --summary
python3 skills/datacenter-monitoring/scripts/mock-sensor.py --rack A1 --spike
python3 skills/datacenter-monitoring/scripts/mock-sensor.py --rack B2 --fail
```

完整部署说明见 PicClaw 仓库中的 `skills/datacenter-monitoring/DEPLOY.md`。

## 8. 常见问题

### Web search 报 API configuration error

没有配置 Brave Search API key 时这是正常现象。申请 key 后写入 `tools.web.search.api_key`。

### Telegram 提示 getUpdates 冲突

同一个 Telegram bot token 只能由一个 `picoclaw gateway` 实例轮询。停止其他实例后重试。

### Provider 内容过滤

部分模型服务会触发内容过滤。可以换一种表达，或切换到其他 provider/model。

