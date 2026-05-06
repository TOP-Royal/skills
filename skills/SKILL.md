# 2026 热门技术技能体系（基于 GitHub 趋势）

> 本套技能文档基于 2026 年 GitHub 趋势、开源社区热度及行业需求整理，涵盖当前最具价值的技术方向。
> **所有详细技能文档必须遵循 [`skill-execution-standard.md`](skill-execution-standard.md)**：固定输出物 + 必须/禁止规则 + DoD 验收清单。

## 索引

- [技能清单](#技能清单)
- [如何选择学习路径](#如何选择学习路径)
- [模板与速查（一次成型核心入口）](#模板与速查一次成型核心入口)
  - [一次成型交付编排模板](one-shot-delivery-template.md)
  - [编码前检查模板](coding-preflight-template.md)
  - [测试策略模板](testing-strategy-template.md)
  - [完成验收模板（DoD）](definition-of-done-template.md)
  - [技术调研与项目发现模板](tech-research-template.md)
  - [运维与SRE模板](sre-devops-template.md)
  - [技能体系速查（参考版）](skills-reference.md)
  - [Skill ID ↔ Template ID ↔ Trigger 映射表（唯一事实来源）](skill-id-map.md)

---

## 技能清单

| 编号 | 技能名称 | 核心关键词 | GitHub 热度 |
|------|---------|-----------|------------|
| 01 | [AI / LLM 应用开发](01-ai-llm-development.md) | LLM、RAG、Prompt Engineering、模型微调 | ⭐⭐⭐⭐⭐ |
| 02 | [Agentic AI 智能体开发](02-agentic-ai.md) | 自主智能体、多智能体协作、工具调用 | ⭐⭐⭐⭐⭐ |
| 03 | [本地 AI 部署与运维](03-local-ai-deployment.md) | Ollama、本地推理、私有化部署 | ⭐⭐⭐⭐⭐ |
| 04 | [云计算与云原生](04-cloud-computing.md) | AWS、Azure、K8s、Serverless | ⭐⭐⭐⭐⭐ |
| 05 | [数据工程与 SQL](05-data-engineering.md) | ETL、数据仓库、PostgreSQL、DuckDB | ⭐⭐⭐⭐ |
| 06 | [Python 全栈开发](06-python-fullstack.md) | FastAPI、Django、异步编程 | ⭐⭐⭐⭐⭐ |
| 07 | [网络安全](07-cybersecurity.md) | AI 安全、云安全、零信任架构 | ⭐⭐⭐⭐ |
| 08 | [前端全栈开发](08-frontend-fullstack.md) | Next.js、TypeScript、Tailwind | ⭐⭐⭐⭐⭐ |
| 09 | [MCP 协议与 AI 工具集成](09-mcp-protocol.md) | Model Context Protocol、AI 工具链 | ⭐⭐⭐⭐⭐ |
| 10 | [可视化 AI 工作流编排](10-ai-workflow-orchestration.md) | n8n、Langflow、Dify、低代码 AI | ⭐⭐⭐⭐ |

### 编程语言专项

| 编号 | 技能名称 | 核心关键词 | GitHub 热度 |
|------|---------|-----------|------------|
| 11 | [Java 开发](11-java-development.md) | Spring Boot、JVM、并发、Kotlin | ⭐⭐⭐⭐⭐ |
| 12 | [C / C++ 开发](12-c-cpp-development.md) | 系统编程、内存管理、性能优化 | ⭐⭐⭐⭐ |
| 13 | [Rust 开发](13-rust-development.md) | 所有权、并发、WASM、系统编程 | ⭐⭐⭐⭐⭐ |
| 14 | [Go 开发](14-go-development.md) | Goroutine、云原生、微服务、K8s | ⭐⭐⭐⭐⭐ |
| 15 | [JavaScript 开发](15-javascript-development.md) | ES6+、Node.js、异步、事件循环 | ⭐⭐⭐⭐⭐ |
| 16 | [CSS 开发](16-css-development.md) | Flexbox、Grid、Tailwind、动画 | ⭐⭐⭐⭐⭐ |
| 17 | [HTML 开发](17-html-development.md) | 语义化、a11y、Web Components、PWA | ⭐⭐⭐⭐ |
| 18 | [Vue 3 生态](18-vue3-ecosystem.md) | Vue 3、Nuxt、Pinia、组合式 API | ⭐⭐⭐⭐⭐ |
| 19 | [Python 语言核心](19-python-language.md) | 语法、OOP、类型系统、异步 | ⭐⭐⭐⭐⭐ |

---

## 如何选择学习路径

### 想做 AI 应用开发者
`01 → 02 → 09 → 03 → 06`

### 想做全栈工程师
`08 → 06 → 04 → 05 → 01`

### 想做 AI 基础设施工程师
`03 → 04 → 09 → 10 → 02`

### 想做数据工程师
`05 → 06 → 01 → 04 → 10`

### 想做安全工程师
`07 → 04 → 01 → 02 → 09`

### 想做 Java 后端工程师
`11 → 04 → 05 → 07`

### 想做系统级 / 高性能工程师
`12 → 13 → 14`

### 想做前端工程师
`17 → 16 → 15 → 18 → 08`

### 想做 Python 工程师
`19 → 06 → 01 → 05`

---

## 模板与速查（一次成型核心入口）

- [技能体系速查（参考版）](skills-reference.md) — 所有 Skill ID 速查 + 01-19 与模板调用关系
- [Skill ID ↔ Template ID ↔ Trigger 映射表（唯一事实来源）](skill-id-map.md) — 解决命名分裂与重复，新增/改名必须先改此表
- [技能可执行化标准](skill-execution-standard.md) — 所有详细技能必须遵循的格式：固定输出物 + 必须/禁止规则 + DoD

### 开发流程模板（强制顺序）

1. [一次成型交付编排模板](one-shot-delivery-template.md) — 总控编排：PRD → Preflight → 护栏 → 测试 → DoD
2. [产品经理能力模板](product-manager-template.md) — 用户画像/场景/竞品/价值评估/路线图/数据指标/A-B测试/商业化/风险（需求不明确时先用）
3. [设计师能力模板](designer-template.md) — 设计系统Tokens/组件状态/交互流程/响应式适配/动画规范/无障碍设计/设计还原验收（涉及UI/UX/前端还原时必须用）
4. [需求文档模板（PRD）](requirements-doc-template.md) — 原始需求 → 完整需求说明书
5. [编码前检查模板](coding-preflight-template.md) — 边界/幂等/并发/超时/观测/测试计划

### 工程护栏模板（按需触发）

- [API 设计模板](api-design-template.md)
- [数据库设计模板](db-design-template.md)
- [MySQL与关系型数据库模板](mysql-rdbms-template.md) — MySQL 表设计、索引优化、SQL规范、事务并发、迁移回滚、备份恢复
- [微服务中间件模板](microservices-middleware-template.md) — Nacos/Dubbo/Sentinel/Seata 注册发现、RPC治理、熔断限流、分布式事务、配置中心
- [Redis与缓存模板](redis-cache-template.md) — 分层缓存、key规范、一致性方案、防穿透/击穿/雪崩、部署架构与容量评估
- [消息队列模板](message-queue-template.md) — Topic设计、生产者可靠性、消费者幂等、顺序消息、死信队列、监控告警
- [支付生态模板](payment-ecosystem-template.md) — 微信/支付宝/银联/Stripe/PayPal 接入：幂等、回调验签去重、对账结算、退款、风控合规、观测告警
- [技术调研与项目发现模板](tech-research-template.md) — GitHub/Stack Overflow/Medium/Dev.to/HN/Reddit/ThoughtWorks Radar 检索高星项目，含质量评估、安全扫描、license 合规、方案对比与验证
- [运维与SRE模板](sre-devops-template.md) — CI/CD、IaC、蓝绿/金丝雀/灰度发布、SLO/SLI/Error Budget、混沌工程、容量规划、on-call
- [数据分析与BI模板](data-analyst-template.md) — 维度建模、指标体系、ETL/ELT pipeline、BI报表与可视化、数据质量监控、安全合规
- [机器学习与算法工程模板](ml-algorithm-template.md) — 推荐/搜索/预测模型：特征工程、实验管理、离线/在线评估、A-B测试、模型部署与监控、漂移检测
- [测试策略模板](testing-strategy-template.md)
- [可观测性模板](observability-template.md)
- [安全编码模板](secure-coding-template.md)

### 提交与验收

- [完成验收模板（DoD）](definition-of-done-template.md) — 提交前逐条自检
- [毕设写作技巧与模板](../毕设写作技巧与模板.md)
- [微信小程序开发模板](wechat-mini-program-template.md)
- [支付宝小程序开发模板](alipay-mini-program-template.md) — 支付宝生态：商业服务/支付/信用/会员/卡券/营销/审核/上架
- [抖音小程序开发模板](douyin-mini-program-template.md) — 抖音生态：内容/短视频挂载/直播/电商/支付/广告/内容合规
- [QQ小程序开发模板](qq-mini-program-template.md) — QQ生态：社交/游戏/娱乐/群能力/厘米秀/支付/社交裂变
- [UniApp 跨端开发模板](uniapp-cross-platform-template.md) — 一套代码编译多端（微信/支付宝/抖音/QQ/H5/App）：条件编译/封装层/原生插件/跨端测试
- [iOS 原生开发模板](ios-native-template.md) — Swift/SwiftUI/UIKit/导航/数据层/权限/隐私清单/App Store Connect 上架
- [Android 原生开发模板](android-native-template.md) — Kotlin/Jetpack Compose/导航/数据层/权限/后台/多渠道发布/性能基线
- [鸿蒙 HarmonyOS 开发模板](harmonyos-template.md) — ArkTS/ArkUI/Stage模型/多端适配/分布式流转/HAP/HSP/AGC上架
- [AI营销能力模板](ai-marketing-template.md) — AI内容生成/用户洞察分层/个性化触达/投放优化/A-B测试/营销自动化/数据归因

---

## 数据来源

- [GitHub Trending](https://github.com/trending)
- [Trendshift](https://trendshift.io/)
- [ByteByteGo Newsletter](https://blog.bytebytego.com/)
- [Pluralsight Tech Skills 2026](https://www.pluralsight.com/)
- [GitHub Octoverse 2025 Report](https://octoverse.github.com/)

---

> 持续更新中。技术变化迅速，建议结合 GitHub 实际趋势定期调整学习重点。
