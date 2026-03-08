# 📚 LearnLoop 学习伴侣

> 基于 LangGraph + CopilotKit 的学习监督助手

[![Status](https://img.shields.io/badge/status-MVP-yellow.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## 📖 目录

- [项目概述](#-项目概述)
- [核心功能](#-核心功能)
- [技术架构](#-技术架构)
- [快速启动](#-快速启动)
- [其他模块](#-其他模块)

---

## 📝 项目概述

**LearnLoop** 是一个基于 CopilotKit AG-UI 和 LangGraph 的学习监督助手，帮助用户设定学习目标、规划学习路径、跟踪学习进度，并通过成就系统激励持续学习。

### 核心价值

- 🎯 帮助用户明确学习目标
- 📅 自动拆解为可执行的每日任务
- ✅ 打卡监督机制
- 🏆 成就系统激励持续学习

---

## 🎯 核心功能

| 功能 | 说明 |
|------|------|
| **学习目标设定** | 用户输入想要学习的主题或技能 |
| **学习路径规划** | 自动拆解为 4 周学习计划 |
| **每日打卡** | 用户完成每日任务后打卡 |
| **连续打卡统计** | 记录连续学习天数 |
| **进度报告** | 生成学习进度总结 |
| **成就系统** | 达成里程碑获得徽章（如 7 天徽章） |

### 功能流程图

```
用户输入学习目标
       ↓
LangGraph 规划 4 周学习路径
       ↓
每日推送学习任务
       ↓
用户打卡 → 更新进度 → 检查成就
       ↓
生成进度报告
```

---

## 🛠️ 技术架构

| 分层 | 技术 | 说明 |
|------|------|------|
| **后端** | Python + LangGraph + FastAPI | AI 工作流编排 + API 服务 |
| **协议** | AG-UI (CopilotKit) | 可视化调试协议 |
| **前端** | Next.js 14 + CopilotKit React | 用户界面 |

### 核心依赖

- **LangGraph** - AI 工作流编排引擎
- **FastAPI** - 高性能 Python Web 框架
- **CopilotKit** - AI 对话 UI 组件库
- **Next.js 14** - React 全栈框架

---

## 🚀 快速启动

### 环境要求

- Python >= 3.9
- Node.js >= 18.0.0
- npm >= 9.0.0

### 后端启动

```bash
cd backend
pip install -r requirements.txt
python main.py
```

**后端服务地址**: http://localhost:8000

### 前端启动

```bash
cd frontend
npm install
npm run dev
```

**前端服务地址**: http://localhost:3000

---

## 🔮 其他模块

### 决策导航仪

**复杂决策辅助工具**

帮助用户在面临复杂决策时：
- 梳理决策因素
- 分析各选项优劣
- 提供决策建议

### 创意孵化器

**从想法到执行计划**

帮助用户将创意转化为可执行的计划：
- 创意记录与整理
- 可行性分析
- 执行步骤拆解
- 资源需求评估

---

## 📁 项目结构

```
copilotkit-langgraph/
├── backend/                 # 后端服务
│   ├── main.py             # FastAPI 入口
│   ├── graph/              # LangGraph 工作流定义
│   │   ├── __init__.py
│   │   └── agent_graph.py  # Agent 图定义
│   ├── tools/              # 工具函数
│   └── requirements.txt    # Python 依赖
├── frontend/                # 前端应用
│   ├── src/
│   │   ├── app/            # Next.js 页面
│   │   ├── components/     # React 组件
│   │   └── lib/            # 工具库
│   └── package.json
└── README.md                # 项目说明
```

---

## 📚 参考资源

- [LangGraph 官方文档](https://langchain-ai.github.io/langgraph/)
- [CopilotKit 官方文档](https://docs.copilotkit.ai/)
- [FastAPI 文档](https://fastapi.tiangolo.com/)
- [Next.js 文档](https://nextjs.org/docs)
- [AG-UI 协议](https://github.com/ag-ui-protocol)

---

## 👥 团队

- **MotherFaker Studio** - https://github.com/MotherFakerrAI

---

*最后更新：2026-03-09*
