# Clawland 文档站

这是 [clawland-ai.github.io](https://clawland-ai.github.io) 的源码仓库，用来承载 Clawland 项目的公开文档、快速开始、贡献说明和 API 概览。

Clawland 是一个面向边缘设备的开源 AI Agent 生态。它让从 2 美元微控制器到云服务器的硬件都能运行不同层级的 Agent，用低成本硬件承担监测、巡检、告警和自动化运维任务。

## 中文文档入口

- [中文首页](./src/pages/zh/index.md)
- [快速开始](./src/pages/zh/quick-start.md)
- [贡献指南](./src/pages/zh/contributing.md)
- [API 概览](./src/pages/zh/api.md)

## 本地开发

本仓库包含 Astro 站点配置：

```bash
npm install
npm run dev
```

打开开发服务器输出的本地地址即可预览。

旧版 Jekyll 说明仍保留在英文 README 中；如果项目后续统一到 Astro，建议以 `package.json` 中的脚本为准。

## 许可证

文档内容使用 CC BY-SA 4.0 授权。
