# 技能 09：MCP 协议与 AI 工具集成

> Anthropic 主导的开放协议，正在成为连接 AI 与外部世界的事实标准。

---

## 技能概述

MCP（Model Context Protocol）是 2026 年最具变革性的新兴协议之一。由 Anthropic 提出并开源，它定义了一种标准方式让 AI 模型与外部工具、数据源和服务进行交互。Pluralsight 将 MCP 列为 2026 年第二大热门技能。Dify、Cursor、Windsurf、Claude Desktop 等主流工具已原生支持 MCP，GitHub 上 MCP 相关项目快速增加。

---

## 核心知识领域

### 1. MCP 协议基础
- **架构模型**：Host（宿主应用）→ Client（连接管理）→ Server（工具提供方）
- **传输层**：stdio（本地进程）、SSE（HTTP Server-Sent Events）
- **消息格式**：JSON-RPC 2.0 子集
- **生命周期**：初始化 → 能力协商 → 请求/通知 → 关闭
- **安全模型**：权限控制、沙箱执行、用户确认

### 2. MCP 原语（Primitives）
- **Tools（工具）**：AI 可调用的函数（类似 Function Calling）
  - 工具定义：名称、描述、JSON Schema 参数
  - 工具调用：name + arguments → result
- **Resources（资源）**：AI 可读取的数据源
  - URI 标识：`file://`、`db://`、`api://`
  - MIME 类型：text/plain、application/json、image/*
- **Prompts（提示模板）**：预定义的提示词模板
  - 参数化模板、可组合提示
- **Sampling（采样）**：Server 请求 LLM 生成内容
  - 让工具服务端也能使用 AI 能力

### 3. MCP Server 开发
- **SDK 选择**：Python SDK、TypeScript SDK、Java SDK、Go SDK
- **Server 实现**：
  - 基于 stdio：命令行工具形式，本地运行
  - 基于 SSE：HTTP 服务，可远程访问
- **工具注册**：装饰器模式或显式注册
- **错误处理**：标准错误码、人类可读消息
- **进度报告**：长时间操作的通知机制

### 4. MCP Client 集成
- **Client 配置**：Server 发现与连接管理
- **能力协商**：Tools / Resources / Prompts / Sampling 能力声明
- **工具选择**：AI 模型决定何时调用哪个工具
- **并行调用**：多工具同时执行
- **结果处理**：工具结果注入 AI 上下文

### 5. 生态系统与工具链
- **官方 Registry**：MCP 官方工具目录
- **社区 Servers**：文件系统、数据库、Git、浏览器、API 集成
- **Inspector**：调试 MCP 连接的工具
- **认证与授权**：OAuth、API Keys、环境变量
- **配置管理**：JSON/YAML 配置文件、环境隔离

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **MCP Python SDK** | 开发 Python MCP Server | ⭐⭐⭐⭐⭐ |
| **MCP TypeScript SDK** | 开发 TS/JS MCP Server | ⭐⭐⭐⭐⭐ |
| **Claude Desktop** | MCP Host（原生支持） | ⭐⭐⭐⭐⭐ |
| **Cursor** | MCP Host（IDE 集成） | ⭐⭐⭐⭐⭐ |
| **Dify** | 生产级 AI 平台 + MCP | ⭐⭐⭐⭐ |
| **Windsurf** | MCP Host（Cascade 集成） | ⭐⭐⭐⭐ |
| **MCP Inspector** | 调试 MCP 连接 | ⭐⭐⭐⭐ |
| **n8n MCP 节点** | 工作流 + MCP 集成 | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [modelcontextprotocol/python-sdk](https://github.com/modelcontextprotocol/python-sdk) - Python 官方 SDK
- [modelcontextprotocol/typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk) - TypeScript 官方 SDK
- [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) - 官方参考 Server 实现集合
- [modelcontextprotocol/specification](https://github.com/modelcontextprotocol/specification) - 协议规范
- [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) - 调试工具
- [cline/cline](https://github.com/cline/cline) - VS Code 插件（支持 MCP）
- [OpenClaw 等 AI 助手项目] - 大量使用 MCP 扩展能力

---

## 学习路径

### 初级阶段（3-5 天）
1. 阅读 MCP 协议规范（Architecture + Core Concepts）
2. 在 Claude Desktop 上配置并使用官方 MCP Servers（文件系统、Git）
3. 体验工具调用流程：AI 决定 → 调用工具 → 获取结果 → 生成回答
4. 理解 Tools、Resources、Prompts 三种原语的区别

### 中级阶段（1-2 周）
1. 使用 Python/TypeScript SDK 开发自定义 MCP Server
2. 实现工具：连接数据库查询、调用内部 API、操作文件
3. 配置 Cursor / Windsurf 使用自定义 MCP Server
4. 处理错误、进度报告、长时间运行任务
5. 学习 SSE 传输模式，部署远程 MCP Server

### 高级阶段（持续）
1. 设计企业级 MCP Server 架构（认证、审计、限流）
2. 实现复杂的 Resource 系统（文件系统 + 数据库 + API 统一抽象）
3. 开发 Sampling 能力，让 Server 也能请求 AI
4. 构建 MCP Server 的 Registry / 发现机制
5. 将 MCP 集成到现有产品（内部工具平台、RAG 系统）

---

## 实践项目建议

1. **数据库查询助手 MCP**：自然语言 → SQL 查询 → 结果表格
2. **Git 仓库分析 MCP**：提交历史、代码统计、变更分析
3. **Jira / Linear 项目管理 MCP**：查询任务、创建 Issue、更新状态
4. **内部 API 网关 MCP**：统一封装公司微服务为 AI 可调用的工具
5. **本地文件知识库 MCP**：文档索引、语义搜索、自动摘要

---

## MCP Server 示例（Python）

```python
from mcp.server import Server
from mcp.types import Tool, TextContent
import sqlite3

app = Server("sqlite-assistant")

@app.list_tools()
async def list_tools() -> list[Tool]:
    return [
        Tool(
            name="query_database",
            description="执行 SQLite 查询",
            inputSchema={
                "type": "object",
                "properties": {
                    "sql": {"type": "string", "description": "SQL 查询语句"}
                },
                "required": ["sql"]
            }
        )
    ]

@app.call_tool()
async def call_tool(name: str, arguments: dict) -> list[TextContent]:
    if name == "query_database":
        conn = sqlite3.connect("data.db")
        result = conn.execute(arguments["sql"]).fetchall()
        conn.close()
        return [TextContent(type="text", text=str(result))]
    raise ValueError(f"Unknown tool: {name}")
```

---

## 关键趋势

- **MCP 成为 AI 工具连接标准**：类似 USB-C，统一了 AI 与外部世界的接口
- **生态系统快速扩张**：从几十个官方 Servers 到数百个社区 Servers
- **IDE 深度集成**：Cursor、Windsurf、VS Code 插件原生支持
- **企业采用加速**：将内部系统封装为 MCP Server，让 AI 安全访问
- **Prompt 模板标准化**：通过 MCP 共享高质量的提示模板
- **采样能力双向化**：不仅是 AI 调用工具，工具也能请求 AI

---

## 参考资源

- [MCP 官方文档](https://modelcontextprotocol.io/)
- [MCP 协议规范](https://spec.modelcontextprotocol.io/)
- [Python SDK 文档](https://github.com/modelcontextprotocol/python-sdk)
- [TypeScript SDK 文档](https://github.com/modelcontextprotocol/typescript-sdk)
- [官方 Servers 集合](https://github.com/modelcontextprotocol/servers)
- [Anthropic MCP 博客](https://www.anthropic.com/news/model-context-protocol)
