# 技能 06：Python 全栈开发

> AI 时代的瑞士军刀，后端开发、数据工程、AI 应用的首选语言。

---

## 技能概述

Python 是 2026 年最不可或缺的编程语言。它不仅是 AI / 数据科学的绝对主导语言，也是后端开发、自动化脚本和云基础设施的核心工具。Pluralsight 将 Python 列为第五大热门技能，GitHub 上 Python 仓库数量持续领先。Python 3.13+ 的性能优化和新工具链（uv、ruff）正在重塑生态。

---

## 核心知识领域

### 1. Python 核心与进阶
- **现代语法**：类型注解、match/case、walrus operator、async/await
- **性能优化**：多线程 vs 多进程、asyncio、GIL 与无 GIL（Python 3.13+）
- **内存管理**：垃圾回收、弱引用、__slots__
- **元编程**：装饰器、描述符、上下文管理器
- **包管理**：uv（极速）、poetry、pdm（现代替代 pip）

### 2. Web 后端开发
- **FastAPI**：异步、类型安全、自动文档（OpenAPI）
- **Django**：全功能框架、ORM、Admin、生态成熟
- **Flask**：轻量灵活、微服务首选
- **异步服务器**：Uvicorn、Hypercorn、Gunicorn + Uvicorn workers
- **WebSocket**：实时通信、Socket.io

### 3. API 设计与开发
- **RESTful API**：资源建模、HTTP 方法、状态码、版本控制
- **GraphQL**：类型系统、Resolver、N+1 问题、Strawberry / Ariadne
- **gRPC**：Protobuf、流式通信、高性能内部 API
- **认证授权**：OAuth 2.0 / OIDC、JWT、API Keys
- **API 文档**：OpenAPI 3.0、Swagger UI、Redoc

### 4. 数据库交互
- **SQLAlchemy 2.0**：ORM + Core，声明式映射
- **Django ORM**：快速开发、迁移系统
- **异步数据库**：asyncpg（PostgreSQL）、aiomysql、Tortoise ORM
- **NoSQL**：Motor（MongoDB）、Redis-py、Beanie
- **向量数据库**：Chroma、Qdrant、Weaviate、pgvector

### 5. 测试与质量
- **pytest**：单元测试、fixture、参数化
- **测试类型**：单元、集成、端到端（Playwright / Selenium）
- **覆盖率**：pytest-cov、Codecov
- **代码质量**：Ruff（lint + format）、Black、isort、mypy
- **CI/CD**：GitHub Actions、pre-commit hooks

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **FastAPI** | 现代异步 Web 框架 | ⭐⭐⭐⭐⭐ |
| **Django** | 全功能 Web 框架 | ⭐⭐⭐⭐⭐ |
| **SQLAlchemy** | ORM / SQL 工具包 | ⭐⭐⭐⭐⭐ |
| **Pydantic** | 数据验证与序列化 | ⭐⭐⭐⭐⭐ |
| **uv** | 极速 Python 包管理器 | ⭐⭐⭐⭐⭐ |
| **Ruff** | 极速 Python linter + formatter | ⭐⭐⭐⭐⭐ |
| **pytest** | 测试框架 | ⭐⭐⭐⭐⭐ |
| **Celery** | 分布式任务队列 | ⭐⭐⭐⭐ |
| **Streamlit / Gradio** | 快速 ML/AI 原型 UI | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [tiangolo/fastapi](https://github.com/tiangolo/fastapi) - 现代、高性能 Web 框架
- [pydantic/pydantic](https://github.com/pydantic/pydantic) - 数据验证与配置管理
- [django/django](https://github.com/django/django) - 全功能 Web 框架
- [sqlalchemy/sqlalchemy](https://github.com/sqlalchemy/sqlalchemy) - SQL 工具包和 ORM
- [astral-sh/uv](https://github.com/astral-sh/uv) - 极速 Python 包管理器（Rust 编写）
- [astral-sh/ruff](https://github.com/astral-sh/ruff) - 极速 Python linter（Rust 编写）
- [pytest-dev/pytest](https://github.com/pytest-dev/pytest) - 测试框架
- [celery/celery](https://github.com/celery/celery) - 分布式任务队列
- [streamlit/streamlit](https://github.com/streamlit/streamlit) - ML/数据应用 UI 框架

---

## 学习路径

### 初级阶段（2-3 周）
1. 巩固 Python 基础 + 类型注解
2. 学习 FastAPI 构建 REST API
3. 掌握 Pydantic 数据模型
4. 使用 SQLAlchemy 进行数据库操作
5. 学会写 pytest 单元测试

### 中级阶段（3-5 周）
1. 异步编程：asyncio + FastAPI + asyncpg
2. API 认证：OAuth 2.0 + JWT 实现
3. 任务队列：Celery + Redis 处理后台任务
4. Docker 化部署：Dockerfile + docker-compose
5. 代码质量：Ruff + mypy + pre-commit 配置

### 高级阶段（持续）
1. 微服务架构：gRPC / REST 服务间通信
2. 性能调优：性能分析（cProfile / py-spy）、缓存策略
3. 事件驱动：消息队列（Kafka / RabbitMQ）集成
4. AI 集成：LLM API 调用、向量数据库、RAG 系统
5. 云原生：K8s 部署、Helm Chart、CI/CD 管道

---

## 实践项目建议

1. **任务管理系统**：FastAPI + PostgreSQL + JWT + 前端
2. **实时聊天应用**：WebSocket + Redis + 消息持久化
3. **内容推荐 API**：用户行为 → 向量嵌入 → 相似度计算 → 推荐
4. **异步爬虫系统**：Celery + 代理池 + 数据清洗 + 存储
5. **AI 文档问答**：上传 PDF → 解析 → 向量化 → 问答 API

---

## Python 现代工具链（2026 推荐）

```bash
# 安装 uv（替代 pip + virtualenv + pip-tools）
curl -LsSf https://astral.sh/uv/install.sh | sh

# 创建项目
uv init myproject
cd myproject
uv add fastapi pydantic sqlalchemy asyncpg

# 代码质量
uv add --dev ruff mypy pytest

# Ruff 替代 Black + isort + flake8
ruff check .
ruff format .
```

---

## 关键趋势

- **uv + ruff 重塑工具链**：Rust 编写的新一代工具，速度提升 10-100 倍
- **FastAPI 成为标准**：Pydantic v2 性能飞跃，async 原生支持
- **类型注解普及**：mypy / Pydantic 成为生产代码标配
- **AI 原生开发**：Python 是 LLM 应用开发的事实标准语言
- **Django 依然强大**：企业级项目首选，Admin 是独特优势
- **无 GIL Python**：3.13+ nogil 实验，多线程并行性能质变

---

## 参考资源

- [FastAPI 官方文档](https://fastapi.tiangolo.com/)
- [Pydantic 文档](https://docs.pydantic.dev/)
- [SQLAlchemy 2.0 教程](https://docs.sqlalchemy.org/en/20/tutorial/)
- [Python 官方文档](https://docs.python.org/3/)
- [uv 文档](https://docs.astral.sh/uv/)
- [Ruff 文档](https://docs.astral.sh/ruff/)
- [Real Python](https://realpython.com/) - 高质量教程
