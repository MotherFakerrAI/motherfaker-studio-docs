# 🤖 CopilotKit + LangGraph

> 基于 LangGraph 和 CopilotKit 的智能助手框架

[![Status](https://img.shields.io/badge/status-testing-yellow.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## 📖 目录

- [项目简介](#-项目简介)
- [技术栈](#-技术栈)
- [快速启动](#-快速启动)
- [项目结构](#-项目结构)
- [下一步扩展](#-下一步扩展)

---

## 📝 项目简介

**copilotkit-langgraph** 是一个结合 LangGraph 和 CopilotKit 的智能助手框架，提供完整的 AI 对话能力和工作流编排功能。

### 核心目标

- ✅ 集成 LangGraph 的工作流编排能力
- ✅ 使用 CopilotKit 提供 AI 对话界面
- ✅ 基于 AG-UI 协议实现可视化调试
- ✅ 提供快速启动和扩展的基础框架

### 主要功能

- 🤖 AI 对话助手
- 🔄 LangGraph 工作流编排
- 🎨 AG-UI 可视化界面
- 🔌 可扩展的工具集成

---

## 🛠️ 技术栈

| 分类 | 技术 | 说明 |
|------|------|------|
| **AI 框架** | LangGraph | 工作流编排 |
| **后端** | FastAPI | Python API 服务 |
| **前端** | Next.js | React 框架 |
| **AI 集成** | CopilotKit | AI 对话组件 |
| **协议** | AG-UI | 可视化调试协议 |

### 核心依赖

- **LangGraph** - AI 工作流编排引擎
- **FastAPI** - 高性能 Python Web 框架
- **CopilotKit** - AI 对话 UI 组件库
- **Next.js** - React 全栈框架

---

## 🚀 快速启动

### 环境要求

- Python >= 3.9
- Node.js >= 18.0.0
- npm >= 9.0.0

### 安装步骤

```bash
# 1. 克隆项目
git clone https://github.com/MotherFakerrAI/copilotkit-langgraph.git
cd copilotkit-langgraph

# 2. 安装后端依赖
cd backend
pip install -r requirements.txt

# 3. 安装前端依赖
cd ../frontend
npm install

# 4. 配置环境变量
cp .env.example .env
# 编辑 .env 文件，填入必要的 API 密钥

# 5. 启动后端服务
cd ../backend
python main.py

# 6. 启动前端服务（新终端）
cd ../frontend
npm run dev
```

### 访问应用

- **前端界面**: http://localhost:3000
- **后端 API**: http://localhost:8000
- **API 文档**: http://localhost:8000/docs

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
│   │   └── __init__.py
│   ├── requirements.txt    # Python 依赖
│   └── .env.example        # 环境变量示例
├── frontend/                # 前端应用
│   ├── src/
│   │   ├── app/            # Next.js 页面
│   │   ├── components/     # React 组件
│   │   │   └── copilot/    # CopilotKit 组件
│   │   └── lib/            # 工具库
│   ├── package.json
│   └── .env.example
├── README.md                # 项目说明
└── .gitignore
```

### 核心文件说明

| 文件 | 说明 |
|------|------|
| `backend/graph/agent_graph.py` | LangGraph Agent 定义 |
| `backend/main.py` | FastAPI 服务入口 |
| `frontend/src/components/copilot/` | CopilotKit UI 组件 |
| `frontend/src/app/` | Next.js 页面路由 |

---

## 🔮 下一步扩展

### 短期目标

- [ ] 添加更多 LangGraph 工具（搜索、计算、数据库查询等）
- [ ] 实现多 Agent 协作流程
- [ ] 添加对话历史记录功能
- [ ] 优化 AG-UI 可视化体验

### 中期目标

- [ ] 支持自定义工作流配置
- [ ] 添加用户认证和权限管理
- [ ] 集成外部 API（天气、新闻、股票等）
- [ ] 实现对话分析和统计

### 长期目标

- [ ] 支持多模态输入（图片、语音）
- [ ] 添加模型切换功能（支持不同 LLM）
- [ ] 实现工作流模板市场
- [ ] 提供云端部署方案

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

*最后更新：2026-03-08*
