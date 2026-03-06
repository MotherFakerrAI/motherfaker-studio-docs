# 🤖 Agent 进度追踪工具

## 项目概述

| 项目 | 内容 |
|------|------|
| 名称 | Agent 进度追踪工具 |
| 描述 | 用于追踪各 Agent 任务执行进度的工具 |
| 仓库 | https://github.com/MotherFakerrAI/agent-tracker |
| 创建时间 | 2026-03-06 |

---

## 核心功能

- ✅ 任务记录 — 记录 Agent 执行的任务
- ✅ 状态查询 — 查询任务当前状态
- ✅ 进度展示 — 可视化展示任务进度
- ✅ Agent 统计 — 统计各 Agent 执行情况
- ✅ **Feishu 推送通知** — 任务完成/失败时自动推送群聊

---

## CLI 命令

| 命令 | 功能 |
|------|------|
| `log` | 记录新任务 |
| `status` | 查询任务状态 |
| `update` | 更新任务进度 |
| `list` | 列出所有任务 |
| `stats` | 查看 Agent 统计 |

### 通知参数

| 参数 | 功能 |
|------|------|
| `--notify` | 控制是否发送 Feishu 通知 |
| `--github-url` | 添加 GitHub 链接按钮到通知卡片 |

---

## Feishu 通知功能

### 通知触发
- 任务完成时自动推送
- 任务失败时自动推送

### 通知卡片内容
- 任务描述
- 执行 Agent
- 任务状态
- 执行耗时
- GitHub 链接按钮

### 推送效果示例
```
🤖 Agent Tracker 任务通知

任务：xxx
Agent: coder
状态：✅ completed
耗时：5m 32s
```

### 配置方式

**步骤：**
1. 复制 `.env.example` 到 `.env`
2. 填入 `FEISHU_WEBHOOK_URL`

**或使用环境变量：**
- `FEISHU_WEBHOOK_URL`

**机器人设置：**
- 自定义关键词：`Agent Tracker`
- 无需签名验证

---

## 任务状态

| 状态 | 说明 |
|------|------|
| `pending` | 待处理 |
| `running` | 执行中 |
| `completed` | 已完成 |
| `failed` | 执行失败 |

---

## 技术实现

（待补充）

---

## 优化建议

（待 brainstorm 提出）

---

## 更新日志

| 日期 | 内容 |
|------|------|
| 2026-03-06 | 初始版本创建 |
| 2026-03-06 | 新增 Feishu 推送通知功能（支持 --notify 和 --github-url 参数） |
| 2026-03-07 | 完善 Feishu 配置说明（.env 配置 + 机器人关键词设置） |
