# 技能 11：Java 开发

> 企业级后端与生态巨兽，Android 与现代后端的基石。

---

## 技能概述

Java 在 2026 年依然是企业级后端开发的核心语言。Spring Boot 生态庞大且成熟，Kotlin 在现代后端和 Android 中增长明显。Java 21+ 引入虚拟线程（Project Loom）、结构化并发、模式匹配等现代特性，大幅提升了并发编程体验。微服务、云原生和大数据生态（Spark、Flink）都深度依赖 Java。

---

## 核心知识领域

### 1. Java 语言核心（Java 17-21 LTS）
- **面向对象**：封装、继承、多态、抽象类、接口、记录类（record）
- **函数式编程**：Lambda、Stream API、方法引用、Optional
- **新特性**：
  - 虚拟线程（Virtual Threads，Java 21）
  - 结构化并发（Structured Concurrency）
  - Switch 表达式 + 模式匹配（Pattern Matching for switch）
  - 密封类（Sealed Classes）
  - 文本块（Text Blocks）、var 局部变量推断
- **并发基础**：ExecutorService、CompletableFuture、Concurrent 包、锁与原子类
- **JVM 基础**：内存模型、GC（G1、ZGC、Shenandoah）、类加载机制

### 2. Spring 生态
- **Spring Boot**：自动配置、起步依赖、Actuator 监控
- **Spring Data JPA / JDBC**：数据访问、事务管理、乐观锁/悲观锁
- **Spring Security**：认证授权、OAuth2、JWT、方法级安全
- **Spring Cloud**：服务注册发现（Consul/Nacos）、配置中心、网关、熔断
- **Spring WebFlux**：响应式编程（Reactor、Mono/Flux）、非阻塞 I/O
- **Spring Batch**：大数据量批处理
- **Spring AI**：集成 LLM、RAG、向量存储

### 3. 构建工具与依赖管理
- **Maven**：POM 结构、生命周期、插件、多模块、依赖冲突解决
- **Gradle**：Groovy/Kotlin DSL、增量构建、任务图、Convention Plugin
- **版本管理**：语义化版本、BOM（Bill of Materials）

### 4. 数据持久化
- **关系型数据库**：PostgreSQL / MySQL + JDBC + 连接池（HikariCP）
- **ORM**：Hibernate / JPA、MyBatis、QueryDSL、JOOQ
- **缓存**：Caffeine（本地）、Redis（分布式）、Spring Cache 抽象
- **NoSQL**：MongoDB（Spring Data MongoDB）、Elasticsearch
- **消息队列**：Kafka / RabbitMQ / RocketMQ + Spring 集成

### 5. 测试与质量
- **JUnit 5**：单元测试、参数化测试、嵌套测试、扩展机制
- **Mockito**：Mock、Spy、Verify、ArgumentCaptor
- **集成测试**：Testcontainers（Docker 化真实依赖）、@SpringBootTest
- **断言库**：AssertJ、Hamcrest
- **覆盖率**：JaCoCo
- **代码质量**：SonarQube、Checkstyle、SpotBugs

### 6. JVM 生态与性能
- **JVM 调优**：堆内存、GC 日志分析、JFR/JMC 诊断
- **性能分析**：Async-profiler、JProfiler、VisualVM
- **监控**：Micrometer + Prometheus、OpenTelemetry Java Agent
- **原生编译**：GraalVM Native Image（启动速度、内存优化）

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **Spring Boot** | 全栈 Web 后端框架 | ⭐⭐⭐⭐⭐ |
| **Spring AI** | AI/LLM 集成框架 | ⭐⭐⭐⭐⭐ |
| **Quarkus** | 云原生 / Kubernetes 原生 | ⭐⭐⭐⭐ |
| **Micronaut** | 编译期依赖注入、低内存 | ⭐⭐⭐⭐ |
| **Kotlin** | Java 生态的现代替代 | ⭐⭐⭐⭐⭐ |
| **Vert.x** | 响应式 / 事件驱动 | ⭐⭐⭐⭐ |
| **Helidon** | Oracle 微服务框架 | ⭐⭐⭐ |

---

## GitHub 热门仓库

- [spring-projects/spring-boot](https://github.com/spring-projects/spring-boot) - 企业级应用开发标准
- [spring-projects/spring-ai](https://github.com/spring-projects/spring-ai) - Spring 生态的 AI 集成框架
- [quarkusio/quarkus](https://github.com/quarkusio/quarkus) - Kubernetes 原生 Java 框架
- [micronaut-projects/micronaut-core](https://github.com/micronaut-projects/micronaut-core) - 现代 JVM 全栈框架
- [eclipse-vertx/vert.x](https://github.com/eclipse-vertx/vert.x) - 工具包用于在 JVM 上构建响应式应用
- [JetBrains/kotlin](https://github.com/JetBrains/kotlin) - Android + 服务端现代语言
- [google/guava](https://github.com/google/guava) - Google 核心 Java 工具库

---

## 学习路径

### 初级阶段（3-4 周）
1. Java 基础语法 + OOP + 集合框架（List/Map/Set/Queue）
2. Stream API + Lambda + Optional 函数式编程
3. Maven/Gradle 构建工具
4. Spring Boot 基础：REST API + JPA + H2/PostgreSQL
5. JUnit 5 + Mockito 单元测试

### 中级阶段（4-6 周）
1. Spring Security：JWT 认证、OAuth2、RBAC
2. Spring Data JPA 高级：关联映射、分页、Specifications、QueryDSL
3. 缓存策略：Caffeine + Redis 二级缓存
4. 消息队列：Kafka/RabbitMQ 集成
5. 并发编程：CompletableFuture、虚拟线程、Reactor（WebFlux）
6. Docker 化部署 + Spring Boot 分层镜像

### 高级阶段（持续）
1. 微服务架构：Spring Cloud Gateway + Consul/Nacos + 熔断
2. JVM 调优与 GC 分析
3. GraalVM Native Image 编译与优化
4. 响应式全栈：WebFlux + R2DBC + Redis Reactive
5. Spring AI：LLM 集成、RAG、向量数据库
6. 事件驱动架构：CQRS + Event Sourcing + Axon Framework

---

## 实践项目建议

1. **电商订单系统**：Spring Boot + JPA + Redis + Kafka + 支付回调
2. **权限管理系统**：RBAC + JWT + OAuth2 + 前后端分离
3. **实时数据看板**：WebFlux + SSE + MongoDB + 大屏展示
4. **AI 问答服务**：Spring AI + pgvector + OpenAI API + RAG
5. **分布式任务调度**：XXL-JOB / PowerJob + 分片执行 + 监控

---

## Kotlin 并行路线

| 对比维度 | Java | Kotlin |
|---------|------|--------|
| **语法简洁** | 较冗长 | 更简洁（数据类、默认参数、扩展函数） |
| **空安全** | 无原生支持 | 编译期空安全 |
| **协程** | 虚拟线程（新） | 原生协程（成熟） |
| **Android** | 可用但非首选 | Google 官方推荐 |
| **Spring Boot** | 完全支持 | 完全支持，代码更简洁 |
| **互操作性** | - | 100% 与 Java 互操作 |

---

## 关键趋势

- **虚拟线程普及**：Java 21 虚拟线程让高并发编程大幅简化，逐步替代线程池模式
- **Spring AI 崛起**：Spring 官方推出 AI 框架，Java 开发者构建 LLM 应用门槛降低
- **云原生框架竞争**：Quarkus/Micronaut 在云原生场景挑战 Spring Boot 地位
- **Kotlin 持续增长**：Android + 后端双场景，Google 和 JetBrains 强力推动
- **GraalVM 落地**：原生编译从实验走向生产，Serverless 和容器场景受益
- **JVM 语言多元化**：Scala（大数据）、Groovy（脚本/Gradle）、Clojure（函数式）共存

---

## 参考资源

- [Spring 官方文档](https://spring.io/projects)
- [Spring AI 文档](https://docs.spring.io/spring-ai/reference/)
- [Java 官方教程](https://docs.oracle.com/javase/tutorial/)
- [Baeldung](https://www.baeldung.com/) - Java + Spring 高质量教程
- [Kotlin 官方文档](https://kotlinlang.org/docs/)
- [Quarkus 文档](https://quarkus.io/guides/)
