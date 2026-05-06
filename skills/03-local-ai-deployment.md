# 技能 03：本地 AI 部署与运维

> 隐私、成本与控制权驱动下的本地 AI 革命。

---

## 技能概述

本地 AI 部署是 2026 年最具影响力的趋势之一。Ollama、Open WebUI 和 OpenClaw 等项目标志着开发者希望在自有硬件上运行 AI。隐私顾虑、API 成本，以及对深度定制的渴望推动了这场运动。现在，一条命令就能启动功能完整的 AI 平台。

---

## 核心知识领域

### 1. 本地模型运行基础
- GGUF 格式与量化原理（Q4_K_M、Q5_K_M、Q8_0）
- 模型加载与内存管理
- 上下文窗口与 VRAM 计算
- CPU vs GPU 推理权衡
- Apple Silicon (Metal) / CUDA / ROCm 后端

### 2. 模型服务化
- REST API 封装（OpenAI 兼容格式）
- 批处理与并发请求管理
- 流式响应（Server-Sent Events）
- 负载均衡与横向扩展
- 模型预热与缓存策略

### 3. 推理优化
- **量化**：INT8 / INT4 / FP16 精度权衡
- **KV Cache 优化**：PagedAttention（vLLM）
- **投机解码**（Speculative Decoding）
- **连续批处理**（Continuous Batching）
- **模型分片与流水线并行**

### 4. 硬件选型与配置
- GPU 显存计算（模型参数 × 精度系数）
- 消费级显卡推荐（RTX 4090、Mac Studio M2 Ultra）
- 多卡部署（NVLink / PCIe 桥接）
- 边缘设备部署（Jetson、Raspberry Pi + NPU）
- 云实例选型（Spot 实例、GPU 集群）

### 5. 私有化部署架构
- 单机部署 vs 集群部署
- Docker / Kubernetes 化部署
- 反向代理与 TLS 终止
- 身份认证与访问控制
- 日志监控与告警

---

## 热门工具与框架

| 工具 | 用途 | GitHub Stars |
|------|------|-------------|
| **Ollama** | 本地大模型管理（最简单易用） | 120k+ |
| **llama.cpp** | C/C++ 高性能本地推理 | 70k+ |
| **vLLM** | 生产级高吞吐推理引擎 | 40k+ |
| **SGLang** | 结构化生成优化推理 | 10k+ |
| **Text Generation Inference (TGI)** | Hugging Face 推理服务 | 10k+ |
| **Open WebUI** | 本地 ChatGPT 替代界面 | 80k+ |
| **koboldcpp** | 游戏/创意写作优化 | 5k+ |

---

## GitHub 热门仓库

- [ollama/ollama](https://github.com/ollama/ollama) - 一条命令运行本地大模型（Go 编写）
- [ggerganov/llama.cpp](https://github.com/ggerganov/llama.cpp) - 纯 C/C++ 推理，支持所有平台
- [vllm-project/vllm](https://github.com/vllm-project/vllm) - PagedAttention 实现高吞吐
- [open-webui/open-webui](https://github.com/open-webui/open-webui) - 自托管的 ChatGPT 风格界面
- [sgl-project/sglang](https://github.com/sgl-project/sglang) - 结构化生成与并行采样
- [huggingface/text-generation-inference](https://github.com/huggingface/text-generation-inference) - 生产级文本生成服务

---

## 学习路径

### 初级阶段（1 周）
1. 安装 Ollama，下载并运行 Llama 3 / Mistral
2. 熟悉 `ollama run`、`ollama list`、`ollama pull` 命令
3. 通过 REST API 与本地模型交互
4. 体验 Open WebUI，搭建本地 ChatGPT 替代品

### 中级阶段（2-3 周）
1. 学习 GGUF 量化，比较不同量化级别的质量与速度
2. 使用 llama.cpp 在低端硬件上运行大模型
3. 部署 vLLM 实现高并发 API 服务
4. 配置多模型加载与路由（根据任务选择模型）
5. Docker 化部署整个推理栈

### 高级阶段（持续）
1. 构建 Kubernetes 上的弹性推理集群
2. 实现推理服务的自动扩缩容（HPA + GPU 指标）
3. 优化长上下文场景（100K+ tokens）的显存使用
4. 模型热更新与 A/B 测试部署
5. 多模态模型本地部署（视觉理解 + 文本生成）

---

## 实践项目建议

1. **家庭 AI 服务器**：用旧 PC / NUC 搭建家庭 AI 中心，全家共享
2. **离线文档分析**：完全内网环境，分析敏感文档不出域
3. **本地编程助手**：配合 Continue.dev / Cursor 使用本地代码补全
4. **边缘 AI 网关**：工厂/零售店现场部署，毫秒级响应
5. **模型即服务（内部）**：为公司各部门提供内部 API，替代 OpenAI API

---

## 硬件配置参考

| 用途 | 推荐配置 | 可运行模型 |
|------|---------|-----------|
| 个人学习 | MacBook Pro M3 (18GB) | 7B-8B 量化 |
| 开发测试 | RTX 4090 (24GB) | 70B Q4 或 13B FP16 |
| 小型团队 | 2× RTX 4090 或 A6000 | 70B FP16 / 多并发 13B |
| 生产部署 | 4× A100 80GB | 405B 量化 / 多并发 70B |
| 边缘设备 | Jetson Orin Nano 8GB | 3B-7B 量化 |

---

## 关键趋势

- **本地优先运动**：隐私与成本驱动下，本地部署成为默认选项
- **消费级硬件可运行 70B+**：量化技术让大模型走进个人电脑
- **与云端混合**：关键任务本地处理，复杂任务云端回退
- **一体化平台**：Ollama + Open WebUI 提供开箱即用体验
- **企业私有化**：金融、医疗等行业要求数据不出域

---

## 参考资源

- [Ollama 官方文档](https://github.com/ollama/ollama/tree/main/docs)
- [vLLM 文档](https://docs.vllm.ai/)
- [llama.cpp 参数说明](https://github.com/ggerganov/llama.cpp/blob/master/examples/main/README.md)
- [Hugging Face 量化指南](https://huggingface.co/docs/transformers/main/en/quantization)
- [本地 LLM 硬件指南](https://www.reddit.com/r/LocalLLaMA/)
