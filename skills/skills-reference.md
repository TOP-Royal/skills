# 技能体系速查（参考版）

> 简洁技能卡片格式，适合快速查阅与 IDE Skills 配置参考。

---

## AI 与智能体

| ID | 技能名称 | 描述 |
|----|---------|------|
| `ai-llm-dev` | AI/LLM应用开发技能 | Prompt工程、RAG架构、模型微调、向量数据库、多模态处理、LangChain/LlamaIndex、OpenAI/Anthropic API调用、Embedding管理、推理优化。当你涉及大语言模型应用、知识库问答、AI功能开发时必须使用。 |
| `agentic-ai` | Agentic AI智能体技能 | 自主智能体、ReAct模式、多智能体协作、工具调用、记忆系统、计划执行、OpenClaw/AutoGPT、自我反思、环境交互、浏览器自动化。当你涉及构建能自主行动的AI代理、任务自动化、智能助手时必须使用。 |
| `local-ai` | 本地AI部署技能 | Ollama、llama.cpp、vLLM、模型量化、GGUF格式、GPU/CPU推理、私有化部署、隐私保护、离线运行、硬件选型。当你涉及本地大模型运行、私有化AI服务、数据不出域场景时必须使用。 |
| `mcp-protocol` | MCP协议技能 | Model Context Protocol、AI工具集成、Server/Client开发、Stdio/SSE传输、工具定义、资源管理、Prompt模板、Claude Desktop/Cursor集成。当你涉及AI与外部工具连接、自定义MCP Server开发时必须使用。 |
| `ai-workflow` | AI工作流编排技能 | n8n、Dify、Langflow、可视化编排、低代码AI、Prompt链、RAG管道、人机协同、API发布、Webhook触发。当你涉及无代码/低代码构建AI应用、自动化流程设计时必须使用。 |

---

## 云计算与基础设施

| ID | 技能名称 | 描述 |
|----|---------|------|
| `cloud-native` | 云计算与云原生技能 | AWS/Azure/GCP、Kubernetes、Docker、Terraform/OpenTofu、Serverless、CI/CD、GitOps、可观测性、Prometheus/Grafana、OpenTelemetry。当你涉及云平台架构、容器编排、基础设施即代码、DevOps流程时必须使用。 |
| `data-engineering` | 数据工程技能 | SQL优化、ETL/ELT、dbt、DuckDB、数据仓库建模、实时流处理、Kafka/Flink、ClickHouse、数据质量、Great Expectations、数据治理。当你涉及数据管道构建、数据分析、数据仓库设计时必须使用。 |
| `python-fullstack` | Python全栈开发技能 | FastAPI、Django、异步编程、Pydantic、SQLAlchemy、uv/ruff工具链、Celery任务队列、pytest测试、Streamlit原型。当你涉及Python后端开发、API设计、异步服务、AI应用后端时必须使用。 |
| `cybersecurity` | 网络安全技能 | AI安全、云安全、零信任架构、OWASP、渗透测试、DevSecOps、密钥管理、漏洞扫描、代码审计、合规框架。当你涉及安全架构设计、漏洞修复、安全审计、渗透测试时必须使用。 |

---

## 工程护栏（一次成型关键）

| ID | 技能名称 | 描述 |
|----|---------|------|
| `api-design` | API 设计护栏技能 | 当你新增/修改 API 时必须用：明确请求/响应 schema、错误码、分页/排序、幂等、超时/重试/限流、兼容策略，并更新 OpenAPI。 |
| `db-design` | 数据库设计护栏技能 | 当你新增/修改表结构或查询时必须用：表结构、约束、索引、事务边界、并发写入策略、迁移与回滚演练，并用 EXPLAIN 验证关键查询。 |
| `mysql-rdbms` | MySQL与关系型数据库技能 | 当你涉及MySQL表设计、索引优化、SQL规范、事务与并发、迁移变更、备份恢复、性能监控时必须用：主键/字符集/引擎、索引EXPLAIN验证、SELECT*禁止、事务边界、迁移回滚、备份演练。 |
| `microservices-middleware` | 微服务中间件技能 | 当你涉及Nacos/Dubbo/Sentinel/Seata/RocketMQ等国内常用中间件时必须用：注册发现、RPC治理、熔断限流、分布式事务、配置中心、链路追踪。 |
| `redis-cache` | Redis与缓存技能 | 当你涉及缓存设计、Redis部署、缓存一致性、高并发缓存时必须用：分层缓存、key规范、一致性方案、防穿透/击穿/雪崩、部署架构与容量评估。 |
| `message-queue` | 消息队列技能 | 当你涉及Kafka/RocketMQ/RabbitMQ/Pulsar等消息系统时必须用：Topic设计、生产者可靠性、消费者幂等、顺序消息、死信队列、监控告警。 |
| `payment-ecosystem` | 支付生态技能 | 当你涉及支付/交易/退款/对账/回调/收银台/分账时必须用：幂等、验签去重、超时重试上限、对账驱动纠错、风控与合规、观测与告警。 |
| `tech-research` | 技术调研与项目发现技能 | 当你需要选型/找开源库/找架构方案/找替代品时必须用：GitHub/Stack Overflow/知名博客检索策略、项目质量评估（stars/安全/license/维护度）、方案对比与验证。 |
| `sre-devops` | 运维与SRE技能 | 当你涉及CI/CD、发布策略、容器编排、可观测性、故障演练、容量规划、on-call时必须用：IaC、蓝绿/金丝雀/灰度发布、SLO/SLI/Error Budget、混沌工程、应急响应。 |
| `data-analyst` | 数据分析与BI技能 | 当你涉及数据报表、指标定义、ETL/ELT、BI可视化、数据治理时必须用：维度建模、指标体系、pipeline设计、数据质量监控、安全与合规。 |
| `ml-algorithm` | 机器学习与算法工程技能 | 当你涉及推荐/搜索/预测/分类/聚类模型时必须用：特征工程、模型训练与实验管理、离线/在线评估、A-B测试、模型部署与监控、漂移检测。 |
| `testing-strategy` | 测试策略护栏技能 | 当你实现功能前必须用：确定 Unit/Integration/E2E/契约测试分层与质量门槛，列出正常/异常/边界用例，避免靠手测上线。 |
| `observability` | 可观测性护栏技能 | 当你上线新功能或改关键链路时必须用：结构化日志字段、核心指标与告警阈值、trace/span 划分，确保线上可定位。 |
| `secure-coding` | 安全编码护栏技能 | 当你处理外部输入/权限/敏感数据时必须用：输入校验、权限校验、脱敏、依赖扫描与常见 Web 漏洞防护，避免高危漏洞上线。 |

---

## 前端与Web

| ID | 技能名称 | 描述 |
|----|---------|------|
| `frontend-fullstack` | 前端全栈开发技能 | Next.js、React、TypeScript、Tailwind CSS、shadcn/ui、Vite、TanStack Query、Zustand、App Router、Server Actions。当你涉及现代Web前端开发、全栈应用、React生态项目时必须使用。 |
| `javascript` | JavaScript核心技能 | ES6+语法、闭包、原型链、事件循环、Promise/async-await、DOM操作、Node.js、模块化、V8引擎原理、函数式编程。当你涉及JavaScript语言特性、浏览器脚本、Node.js运行时、前端基础时必须使用。 |
| `css` | CSS开发技能 | Flexbox、Grid布局、Tailwind CSS、容器查询、响应式设计、CSS变量、动画过渡、暗色模式、性能优化、级联层。当你涉及页面样式、布局设计、动画效果、CSS架构时必须使用。 |
| `html` | HTML开发技能 | 语义化标签、表单控件、Web Components、可访问性(ARIA)、PWA、SEO元数据、结构化数据、Schema.org、Service Worker。当你涉及页面结构、SEO优化、无障碍设计、PWA开发时必须使用。 |
| `vue3-ecosystem` | Vue3生态开发技能 | Vue3组合式API、Nuxt3、Pinia、Vue Router、Vite、Element Plus、Vuetify、自定义Composables、Teleport、Suspense。当你涉及Vue3项目、SSR/SSG、企业后台系统、组件库开发时必须使用。 |

---

## 编程语言

| ID | 技能名称 | 描述 |
|----|---------|------|
| `java-dev` | Java开发技能 | Spring Boot、JVM调优、虚拟线程、Spring AI、并发编程、JPA/Hibernate、Spring Security、Kafka集成、微服务架构、GraalVM。当你涉及Java后端开发、企业级应用、Spring生态、Android开发时必须使用。 |
| `c-cpp-dev` | C/C++开发技能 | 系统编程、内存管理、指针、STL、CMake、并发编程、网络编程、Socket/ epoll、性能优化、嵌入式开发。当你涉及操作系统、游戏引擎、高频交易、嵌入式系统、性能敏感型软件时必须使用。 |
| `rust-dev` | Rust开发技能 | 所有权系统、借用检查、Tokio异步、Cargo包管理、WASM编译、系统编程、内存安全、并发安全、FFI互操作、零成本抽象。当你涉及系统级开发、区块链基础设施、WebAssembly、高性能网络服务时必须使用。 |
| `go-dev` | Go开发技能 | Goroutine/Channel、Gin/Echo框架、云原生、微服务、错误处理、Context管理、gRPC、标准库、测试基准、模块管理。当你涉及后端API开发、K8s生态工具、高并发服务、云基础设施时必须使用。 |
| `python-core` | Python语言核心技能 | 语法基础、OOP面向对象、魔术方法、装饰器、类型注解、asyncio异步、GIL机制、描述符元类、标准库精要、C扩展开发。当你涉及Python语言本身特性、高级用法、源码阅读、性能优化时必须使用。 |

---

## 跨端与移动端（补充方向）

| ID | 技能名称 | 描述 |
|----|---------|------|
| `cross-platform` | 跨端开发技能 | Flutter、React Native、Electron、Tauri、Capacitor、Dart/JS桥接、原生插件、平台适配、性能优化、热更新。当你涉及移动端App、桌面应用、跨平台统一开发时必须使用。 |
| `wechat-mini-program` | 微信小程序开发技能 | 原生小程序/Taro/uni-app、页面与组件设计、登录与鉴权（code换openid/session）、网络请求封装、支付/订阅消息、隐私合规与授权、分包与性能优化、发布与审核。当你涉及微信生态小程序开发与上线时必须使用。 |
| `alipay-mini-program` | 支付宝小程序开发技能 | 商业服务/生活缴费/信用能力/会员营销、my.tradePay支付/芝麻信用/花呗分期、卡券/营销工具、审核与上架。当你涉及支付宝生态小程序开发与上线时必须使用。 |
| `douyin-mini-program` | 抖音小程序开发技能 | 内容分发/短视频挂载/直播带货/电商交易、tt.pay支付/拍摄器/直播挂载/广告投放、内容合规/未成年人保护。当你涉及抖音生态小程序开发与上线时必须使用。 |
| `qq-mini-program` | QQ小程序开发技能 | 社交互动/游戏/娱乐/校园、群能力/好友互动/厘米秀/游戏中心、qq.requestPayment支付/社交裂变。当你涉及QQ生态小程序开发与上线时必须使用。 |
| `uniapp-cross-platform` | UniApp跨端开发技能 | Vue语法一套代码编译多端（微信/支付宝/抖音/QQ/H5/App）、条件编译/统一封装层/原生插件、构建发布自动化/跨端测试矩阵。当你涉及多端统一开发、降低跨平台成本时必须使用。 |
| `ios-dev` | iOS原生开发技能 | Swift/SwiftUI、UIKit、AppKit、Combine响应式、CoreData、AVFoundation、AutoLayout、Swift并发、Widget开发、Apple生态。当你涉及iPhone/iPad/Mac原生应用、Apple平台独占功能时必须使用。 |
| `android-dev` | Android原生开发技能 | Kotlin/Java、Jetpack Compose、Room数据库、Coroutine、WorkManager、RecyclerView、Material Design、Navigation组件、性能优化。当你涉及Android原生应用、Google生态集成、移动端深度定制时必须使用。 |
| `harmonyos` | 鸿蒙HarmonyOS开发技能 | ArkTS/ArkUI、Stage模型、多端适配（手机/平板/车机/手表/智慧屏/折叠屏）、分布式流转与协同、数据分级标签、HAP/HSP打包、AGC上架与审核。当你涉及鸿蒙原生应用、元服务、跨设备协同时必须使用。 |

---

## 全局一次成型模板（强烈建议每次写代码都用）

| ID | 模板 | 用途 |
|----|------|------|
| `one-shot-delivery` | [一次成型交付编排模板](one-shot-delivery-template.md) | 你只写一次“原始需求”，AI 按固定顺序输出：PRD → Preflight → API/DB/安全/观测（按需）→ 测试策略 → DoD。 |
| `coding-preflight` | [编码前检查模板](coding-preflight-template.md) | 开写前把输入/输出/边界/幂等/并发/超时/观测/测试计划一次问清，避免返工。 |
| `definition-of-done` | [完成验收模板（DoD）](definition-of-done-template.md) | 提交前逐条自检：功能、API契约、迁移回滚、可观测性、测试、性能与安全。 |
| `product-manager` | [产品经理能力模板](product-manager-template.md) | 从开发视角补全产品思维：用户画像/场景/竞品/价值评估/路线图/数据指标/A-B测试/商业化/风险。需求不明确时先用它，再出PRD。 |
| `designer` | [设计师能力模板](designer-template.md) | 从开发视角补全设计能力：设计系统Tokens/组件状态/交互流程/响应式适配/动画规范/无障碍设计/设计还原验收。涉及UI/UX/前端还原时必须用。 |
| `ai-marketing` | [AI营销能力模板](ai-marketing-template.md) | AI驱动的营销全链路：内容生成/用户洞察与分层/个性化触达/投放优化/A-B测试/营销自动化/数据归因。涉及增长运营/内容营销/广告投放/用户运营时必须用。 |
| `requirements-doc` | [需求文档模板（PRD）](requirements-doc-template.md) | 你只写一次“原始需求”，AI 按 PRD 结构补齐：范围、流程、功能点、数据契约、NFR、验收标准、测试与发布回滚。 |
| `wechat-mini-program` | [微信小程序开发模板](wechat-mini-program-template.md) | 小程序需求一次写清：页面/组件/登录鉴权/支付/隐私合规/性能/发布审核，避免上线返工。 |
| `alipay-mini-program` | [支付宝小程序开发模板](alipay-mini-program-template.md) | 支付宝生态：商业服务/支付/信用/会员/卡券/营销/审核/上架一次成型。 |
| `douyin-mini-program` | [抖音小程序开发模板](douyin-mini-program-template.md) | 抖音生态：内容/短视频挂载/直播/电商/支付/广告/内容合规/未成年人保护一次成型。 |
| `qq-mini-program` | [QQ小程序开发模板](qq-mini-program-template.md) | QQ生态：社交/游戏/娱乐/群能力/厘米秀/支付/社交裂变/未成年人防沉迷一次成型。 |
| `uniapp-cross-platform` | [UniApp 跨端开发模板](uniapp-cross-platform-template.md) | 一套代码编译多端（微信/支付宝/抖音/QQ/H5/App）：条件编译/统一封装层/原生插件/构建发布/跨端测试矩阵。 |
| `ios-native` | [iOS 原生开发模板](ios-native-template.md) | Swift/SwiftUI/UIKit/生命周期/导航/数据层/权限/隐私清单/发布审核/App Store Connect 一次成型。 |
| `android-native` | [Android 原生开发模板](android-native-template.md) | Kotlin/Jetpack Compose/导航/数据层/权限/后台/多渠道发布/性能基线一次成型。 |
| `harmonyos` | [鸿蒙 HarmonyOS 开发模板](harmonyos-template.md) | ArkTS/ArkUI/Stage模型/多端适配/分布式流转/HAP/HSP/AGC上架/权限/数据分级一次成型。 |
| `payment-ecosystem` | [支付生态模板](payment-ecosystem-template.md) | 微信/支付宝/银联/Stripe/PayPal等真实支付接入：幂等、回调验签去重、对账结算、退款、风控合规、观测告警。 |
| `tech-research` | [技术调研与项目发现模板](tech-research-template.md) | GitHub/Stack Overflow/Medium/Dev.to/HN/Reddit/ThoughtWorks Radar 检索高星项目，含质量评估、安全扫描、license 合规、方案对比与验证。 |
| `sre-devops` | [运维与SRE模板](sre-devops-template.md) | CI/CD、IaC、蓝绿/金丝雀/灰度发布、SLO/SLI/Error Budget、可观测性、混沌工程、容量规划、on-call。 |
| `data-analyst` | [数据分析与BI模板](data-analyst-template.md) | 维度建模、指标体系、ETL/ELT pipeline、BI报表与可视化、数据质量监控、数据安全与合规。 |
| `ml-algorithm` | [机器学习与算法工程模板](ml-algorithm-template.md) | 推荐/搜索/预测模型：特征工程、实验管理、离线/在线评估、A-B测试、模型部署与监控、漂移检测。 |
| `api-design` | [API 设计模板](api-design-template.md) | API 一次设计正确：schema、错误码、分页、幂等、超时/重试/限流、兼容策略 + OpenAPI 更新。 |
| `db-design` | [数据库设计模板](db-design-template.md) | 表结构/索引/事务/迁移回滚一次搞定，并用 EXPLAIN 验证关键查询。 |
| `mysql-rdbms` | [MySQL与关系型数据库模板](mysql-rdbms-template.md) | MySQL表设计、索引优化、SQL规范、事务并发、迁移回滚、备份恢复、性能监控。 |
| `microservices-middleware` | [微服务中间件模板](microservices-middleware-template.md) | Nacos/Dubbo/Sentinel/Seata注册发现、RPC治理、熔断限流、分布式事务、配置中心。 |
| `redis-cache` | [Redis与缓存模板](redis-cache-template.md) | 分层缓存、key规范、一致性方案、防穿透/击穿/雪崩、部署架构与容量评估。 |
| `message-queue` | [消息队列模板](message-queue-template.md) | Topic设计、生产者可靠性、消费者幂等、顺序消息、死信队列、监控告警。 |
| `testing-strategy` | [测试策略模板](testing-strategy-template.md) | 先定测试分层与用例，再写代码；避免上线靠手测。 |
| `observability` | [可观测性模板](observability-template.md) | 日志/指标/追踪/告警四件套，确保线上可定位。 |
| `secure-coding` | [安全编码模板](secure-coding-template.md) | 输入校验、权限、脱敏、依赖扫描、常见漏洞防护。 |
| `thesis-writing` | [毕设写作技巧与模板](../毕设写作技巧与模板.md) | 按“绪论/相关技术/需求分析/实现/测试/总结”结构生成论文内容，包含摘要模板、字数分配、图表规范、避坑清单与快速检查表。 |

> 每个技能的详细学习路径、工具链、实践项目请查看对应编号的 `.md` 文件。
> 例如：`ai-llm-dev` 详细内容在 `01-ai-llm-development.md`

---

## 其他高频技术方向（扩展覆盖）

| ID | 技能名称 | 描述 |
|----|---------|------|
| `message-queue` | 消息队列技能 | Kafka、RabbitMQ、RocketMQ、Pulsar、消息可靠性、顺序性、死信队列、幂等消费、流处理。当你涉及异步解耦、事件驱动、高并发削峰时必须使用。 |
| `nosql-cache` | NoSQL与缓存技能 | Redis、MongoDB、Elasticsearch、ClickHouse、缓存一致性、缓存穿透/击穿/雪崩、数据分片、持久化策略。当你涉及高并发缓存、文档存储、搜索引擎、列式分析时必须使用。 |
| `microservices` | 微服务架构技能 | 服务拆分、服务发现、配置中心、熔断限流、分布式事务、Saga/TCC、API 网关、gRPC/Protobuf、链路追踪。当你涉及服务化改造、分布式系统、大规模团队协作时必须使用。 |
| `devops-sre` | DevOps与SRE技能 | CI/CD、GitOps、IaC、监控告警、SLI/SLO、混沌工程、蓝绿/金丝雀发布、故障演练、容量规划。当你涉及持续交付、系统稳定性保障、自动化运维时必须使用。 |
| `graphql` | GraphQL与API聚合技能 | Schema 设计、Resolver、DataLoader、N+1 防护、订阅、Federation、与 REST 共存策略、类型安全。当你涉及多端数据聚合、BFF层、复杂查询接口时必须使用。 |
| `data-science-ml` | 数据科学与ML工程技能 | Pandas/NumPy、Scikit-learn、特征工程、模型训练、MLflow、模型部署、A/B测试、数据版本管理。当你涉及数据分析、机器学习模型、推荐系统、预测模型时必须使用。 |
| `blockchain` | 区块链开发技能 | 智能合约、Solidity、Web3.js/ethers.js、共识机制、钱包集成、NFT、DeFi、Gas优化、安全审计。当你涉及区块链应用、Web3 DApp、智能合约开发时必须使用。 |
| `game-dev` | 游戏开发技能 | Unity、Unreal Engine、Godot、游戏物理、渲染管线、网络同步、ECS架构、资源管理、性能剖析。当你涉及游戏客户端、游戏引擎、实时多人对战时必须使用。 |
| `embedded-iot` | 嵌入式与物联网技能 | RTOS、ESP32/Arduino、MQTT、CoAP、边缘计算、传感器融合、低功耗设计、固件OTA、工业协议。当你涉及智能硬件、IoT设备、嵌入式系统、工业自动化时必须使用。 |

---

## 可执行化标准与调用关系

> **所有详细技能文档（01-19 及新增）必须遵循 [`skill-execution-standard.md`](skill-execution-standard.md)**：固定输出物 + 必须/禁止规则 + DoD。

### 01-19 编号技能 ↔ 模板调用关系

| 编号技能 | 开发时必联动的模板 |
|---------|-----------------|
| 01 AI/LLM、02 Agentic AI、03 Local AI、09 MCP、10 AI Workflow | `requirements-doc` → `secure-coding`（API Key/模型安全） → `testing-strategy`（模型评估用例） |
| 04 Cloud、06 Python Fullstack、08 Frontend Fullstack、11 Java、14 Go | `coding-preflight` → `api-design`（如有接口） → `db-design`（如有 DB） → `testing-strategy` → `observability` → `definition-of-done` |
| 05 Data Engineering | `coding-preflight` → `db-design` → `testing-strategy`（数据质量测试） → `observability`（数据管道监控） |
| 07 Cybersecurity | `secure-coding`（核心） → `testing-strategy`（渗透/安全测试） → `definition-of-done` |
| 12 C/C++、13 Rust | `coding-preflight` → `testing-strategy`（内存安全/并发测试） → `definition-of-done` |
| 15 JavaScript、16 CSS、17 HTML、18 Vue3 | `coding-preflight` → `testing-strategy`（E2E/组件测试） → `definition-of-done` |
| 19 Python Core | `coding-preflight` → `testing-strategy` → `definition-of-done` |

### 通用调用口诀

> **任何开发任务**：`one-shot-delivery` → 01-19 技能（产出固定输出物） → 护栏模板（按需） → `definition-of-done`
