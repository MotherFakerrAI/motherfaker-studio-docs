# 🤖 Agent 协作协议

## 协议目标

规范 MotherFaker Studio 内部 Agent 之间的协作流程，确保高效沟通和任务执行。

## Agent 角色定义

### CEO (Chief Executive Officer)
- **职责**: 需求确认、任务派发、最终决策
- **权限**: 可以向任何 Agent 派发任务
- **输出**: 任务指令、决策结果

### Coder
- **职责**: 开发实现、Bug 修复、技术实现
- **权限**: 接收 CEO 任务，执行代码开发
- **输出**: 可运行的代码、技术实现方案

### Secretary
- **职责**: 文档记录、任务追踪、进度汇报
- **权限**: 接收 CEO 任务，更新团队文档
- **输出**: 结构化文档、进度报告

### Tracker (Agent Tracker 工具)
- **职责**: 进度追踪、状态更新、通知推送
- **权限**: 记录任务状态，推送 Feishu 通知
- **输出**: 任务状态、进度统计、通知消息

## 消息传递规范

### 任务派发格式
```
## 📝 任务：{任务名称}

### 项目信息
- **项目名称**: {name}
- **GitHub**: {url}
- **技术栈**: {stack}

### 任务内容
{详细描述}

### 文档位置
{目标位置}
```

### 任务完成汇报格式
```
**任务已完成 ✓**

已更新 `{仓库名}` 仓库：
- ✅ {完成项 1}
- ✅ {完成项 2}

commit: `{commit_hash}`
```

## 状态同步机制

1. **任务记录**: Coder 开始任务时使用 Tracker 记录
2. **状态更新**: 任务完成时更新状态为 completed
3. **自动通知**: Tracker 自动推送 Feishu 通知
4. **文档归档**: Secretary 更新团队文档

## 异常处理

- **任务阻塞**: 立即上报 CEO
- **执行失败**: 记录失败原因，等待 CEO 决策
- **信息缺失**: 主动向 CEO 确认

## 版本控制

- 代码仓库：`MotherFakerrAI/{project-name}`
- 文档仓库：`MotherFakerrAI/motherfaker-studio-docs`
- 提交规范：遵循 Conventional Commits
