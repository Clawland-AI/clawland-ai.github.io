# Clawland 贡献指南

本文是 Clawland 组织级贡献指南的中文版本，适用于 `github.com/Clawland-AI` 下的公开仓库。具体仓库可能还有额外要求，提交前请同时阅读目标仓库的 README、CONTRIBUTING 和 PR 模板。

## 快速流程

1. Fork 目标仓库。
2. 创建功能分支：

```bash
git checkout -b feature/my-feature
```

3. 完成修改。
4. 运行测试或构建命令。
5. 使用清晰的 commit message：

```bash
git commit -m "feat(agent): add temperature sensor support for SHT40"
```

6. Push 分支并创建 Pull Request。
7. 第一次提交 PR 时，按 CLA bot 提示签署 CLA。

## 可以贡献什么

### 代码

- 修复 bug。
- 实现 enhancement。
- 处理 good first issue。
- 补充测试和 CI。

### Skills

Skill 是教 Agent 掌握领域知识的 Markdown 文件。通常是一个目录，包含 `SKILL.md`，其中有 YAML frontmatter 和正文说明。

贡献 skill 时建议包含：

- 场景说明。
- 输入/输出格式。
- 阈值、策略或控制逻辑。
- 测试数据或模拟脚本。

### 硬件套件

硬件套件贡献应包含：

- BOM。
- 接线图。
- 驱动脚本。
- PicClaw skill 配置。
- 成本分析。
- 测试报告或可复现实验步骤。

### 文档

- 改进 README。
- 编写教程。
- 翻译核心文档。
- 修复歧义、过期命令或错别字。

### 社区支持

- 在 GitHub Discussions 回答问题。
- 帮助复现和 triage issues。
- 给 PR 做建设性 review。

### Bounty

公开 bounty 任务需要先在 issue 中表达意愿并等待维护者分配。完成后提交 PR，PR 描述里应引用对应 issue。

## Commit 规范

Clawland 使用 Conventional Commits：

```text
type(scope): description
```

示例：

```text
feat(agent): add sub-agent timeout configuration
fix(channels): handle Telegram reconnection on network loss
docs(skills): add weather skill tutorial
chore(ci): update Go version to 1.24
test(tools): add exec tool safety guard tests
```

常用 type：

- `feat`
- `fix`
- `docs`
- `chore`
- `test`
- `refactor`
- `perf`
- `style`
- `ci`

## PR 要求

- 一个 PR 只解决一个功能或问题。
- 描述清楚改了什么、为什么改、如何验证。
- 引用相关 issue。
- 新功能应补测试。
- 行为变化应补文档。
- 尽量控制 PR 规模，较大变更拆成多个 PR。

## Code Review

- PR 至少需要 1 位 Core Maintainer approve。
- Reviewer 目标是在 72 小时内回应。
- 反馈应具体、建设性、可执行。

## 开发环境

### PicClaw

```bash
git clone https://github.com/Clawland-AI/picclaw.git
cd picclaw
make build
./picclaw status
```

### MoltClaw

```bash
git clone https://github.com/Clawland-AI/moltclaw.git
cd moltclaw
npm install
npm run dev
```

### Skills

```bash
picoclaw skills install /path/to/your-skill
picoclaw agent -m "test your skill functionality"
```

## 问题报告

提交 issue 时请包含：

- 复现步骤。
- 期望行为。
- 实际行为。
- 环境信息。
- 相关日志或截图。

安全漏洞不要公开发 issue，请发送邮件到 `security@clawland.dev`。

## 行为准则

所有贡献者都应遵守 Code of Conduct。保持友善、具体、建设性，并欢迎新贡献者。

