# 技能 01：AI / LLM 应用开发

> 基于 GitHub 2026 年热度最高的 AI 开源项目整理。

---

## 技能概述

AI / LLM 应用开发是 2026 年最热门的技术方向。GitHub Octoverse 2025 报告显示，AI 相关仓库数量超过 430 万，LLM 项目同比增长 178%。本技能涵盖从调用大模型 API 到构建生产级 RAG 系统的完整能力。

---

## 核心知识领域

### 1. 大语言模型基础
- Transformer 架构原理（注意力机制、编码器/解码器）
- 主流模型家族：GPT-4o、Claude 4、Gemini 2.5、Llama 4、DeepSeek V4
- 上下文窗口与长文本处理（1M+ tokens）
- Token 计算与成本控制

### 2. Prompt Engineering
- 零样本 / 少样本提示
- Chain-of-Thought (CoT) 思维链
- ReAct 模式（推理 + 行动）
- 结构化输出（JSON Mode / Function Calling）
- 提示词模板管理与版本控制

### 3. RAG（检索增强生成）
- 文档分块策略（固定长度、语义分块、递归分块）
- Embedding 模型选择（OpenAI、Cohere、开源模型）
- 向量数据库：Pinecone、Milvus、Weaviate、pgvector
- 重排序（Re-ranking）与混合检索
- 查询改写与扩展

### 4. 模型微调
- LoRA / QLoRA 高效微调
- 全参数微调 vs 参数高效微调
- 指令微调数据集构建
- 评估指标：BLEU、ROUGE、人类评估

### 5. 多模态 AI
- 文本 + 图像理解（GPT-4V、Claude Vision）
- 文本生成图像（Stable Diffusion、DALL-E、Flux）
- 文本生成语音 / 语音转文本
- 视频理解与生成

---

## 热门工具与框架

| 工具 | 用途 | GitHub Stars |
|------|------|-------------|
| **LangChain** | LLM 应用开发框架 | 100k+ |
| **LlamaIndex** | RAG 与数据连接框架 | 50k+ |
| **PydanticAI** | 类型安全的 AI Agent 框架 | 新兴 |
| **Vercel AI SDK** | 前端 AI 交互组件库 | 20k+ |
| **Ollama** | 本地模型运行 | 120k+ |
| **vLLM** | 高性能推理引擎 | 40k+ |
| **Hugging Face Transformers** | 开源模型库 | 150k+ |
| **Unsloth** | 高效模型微调 | 25k+ |

---

## GitHub 热门仓库

- [langchain-ai/langchain](https://github.com/langchain-ai/langchain) - LLM 应用开发的事实标准框架
- [run-llama/llama_index](https://github.com/run-llama/llama_index) - RAG 应用首选框架
- [ollama/ollama](https://github.com/ollama/ollama) - 本地运行大模型最简单的方式
- [vllm-project/vllm](https://github.com/vllm-project/vllm) - 高吞吐推理引擎
- [unslothai/unsloth](https://github.com/unslothai/unsloth) - 2 倍速微调，70% 显存节省
- [vercel/ai](https://github.com/vercel/ai) - React/Vue/Svelte 的 AI 流式 UI 组件

---

## 学习路径

### 初级阶段（1-2 周）
1. 熟悉 OpenAI / Anthropic API 调用
2. 掌握 Prompt Engineering 基础技巧
3. 用 LangChain 构建简单问答应用
4. 了解 Embedding 和向量搜索概念

### 中级阶段（2-4 周）
1. 构建完整的 RAG 系统（文档上传 → 分块 → 向量化 → 检索 → 生成）
2. 使用 LlamaIndex 连接多种数据源（数据库、API、PDF）
3. 实现 Function Calling / Tool Use
4. 学习模型评估与 A/B 测试

### 高级阶段（持续）
1. 使用 LoRA 微调开源模型（Llama、Mistral）
2. 构建多模态应用（图像理解 + 文本生成）
3. 优化推理性能（量化、批处理、缓存）
4. 设计多 Agent 协作系统

---

## 实践项目建议

1. **智能客服机器人**：RAG + 企业知识库，支持多轮对话
2. **代码审查助手**：分析 PR diff，自动生成审查意见
3. **文档自动生成器**：根据代码注释生成 API 文档
4. **多语言翻译工具**：结合 Embedding 的术语一致性翻译
5. **AI 会议纪要**：语音转录 → 摘要 → 行动项提取

---

## 关键趋势

- **开源模型追赶闭源**：DeepSeek-V3 证明开源模型可媲美顶级闭源模型
- **本地部署普及**：Ollama 等工具让本地 AI 一键启动
- **视觉化构建**：Langflow、Dify 让非工程师也能搭建 AI 流程
- **多模态成为标配**：文本、图像、音频、视频统一处理

---

## 参考资源

- [LangChain 官方文档](https://python.langchain.com/)
- [LlamaIndex 文档](https://docs.llamaindex.ai/)
- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [Hugging Face 课程](https://huggingface.co/learn)
- [OpenAI API 文档](https://platform.openai.com/docs)
