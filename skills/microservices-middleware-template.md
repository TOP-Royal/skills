# 微服务中间件模板（microservices-middleware）

> 目标：国内 Java/Go 后端常用中间件一次设计正确：注册发现、RPC、熔断限流、分布式事务、配置中心。

---

## 固定输出物（AI 必须产出）

- 服务注册与发现架构图（Nacos/Eureka/Consul）+ 服务清单
- RPC 接口定义（Dubbo/gRPC/proto/方法签名校验）
- 熔断限流规则表（Sentinel/Hystrix：资源/QPS/异常比例/降级策略）
- 分布式事务方案（Seata：AT/TCC/Saga/Saga 状态机）+ 回滚/补偿设计
- 配置中心清单（Nacos/Apollo：动态配置项 + 灰度策略 + 回滚方案）

## 必须/禁止规则

- 必须：服务间调用有超时 + 重试 + 熔断 + 降级，禁止裸调
- 必须：分布式事务明确补偿逻辑，禁止只提“用 Seata”不画补偿流
- 必须：配置变更可灰度（先 1 台/1 集群验证再全量）
- 禁止：循环依赖（A 调 B 调 C 调 A）
- 禁止：大事务跨多个服务（事务边界尽量单服务内）
- 禁止：无版本号的 RPC 接口直接改字段（兼容策略：加字段/deprecate）

---

## 1. 服务注册与发现

- 选型：Nacos / Eureka / Consul / Kubernetes DNS
- 服务清单：
  - 服务名（spring.application.name）
  - 分组/命名空间（环境隔离）
  - 元数据（版本、区域、协议）
- 健康检查：心跳间隔、超时、实例保护阈值
- 灰度/蓝绿：元数据标签 + 网关路由权重

---

## 2. RPC 与接口治理

- 协议：Dubbo / gRPC / OpenFeign + LoadBalancer
- 接口定义：
  - proto/IDL 或 Java 接口（版本化）
  - 入参/出参（DTO，禁止透传内部实体）
  - 异常：BizException / RPC 超时 / 降级返回值
- 序列化：Hessian2 / Protobuf / JSON（性能/兼容性权衡）
- 版本策略：
  - v1/v2 并行支持
  - 字段新增：optional + 默认值
  - 字段弃用：@Deprecated + 灰度监控

---

## 3. 熔断、限流、降级（Sentinel 为例）

- 资源定义：接口级 / 方法级 / 热点参数
- 限流：QPS / 线程数 / 关联限流 / 链路限流
- 熔断：慢调用比例 / 异常比例 / 异常数
- 降级：返回默认值 / 缓存数据 / 兜底逻辑
- 热点参数限流：商品 ID / 用户 ID 防刷
- 系统保护：Load / RT / 线程数 / CPU

---

## 4. 分布式事务（Seata 为例）

- 模式选择：
  - AT：简单 CRUD，自动补偿（需 undo_log）
  - TCC：复杂业务，手动实现 try/confirm/cancel
  - Saga：长事务，状态机驱动
  - XA：强一致，性能差，谨慎使用
- 设计要点：
  - 幂等：confirm/cancel 必须幂等
  - 空回滚：try 未执行时 cancel 处理
  - 悬挂：cancel 后 try 到达处理
  - 超时：全局/分支事务超时配置
- 监控：事务状态、失败重试、人工补偿入口

---

## 5. 配置中心（Nacos/Apollo）

- 配置分层：
  - 公共配置（数据库连接池、日志级别）
  - 应用配置（业务开关、阈值）
  - 灰度配置（按 IP/集群/用户比例）
- 动态刷新：@RefreshScope / ContextRefresher
- 安全：敏感配置加密（Nacos 加密插件 / KMS）
- 回滚：配置历史版本 + 一键回滚

---

## 6. 链路追踪与监控

- Trace：SkyWalking / Jaeger / Zipkin
- 指标：Micrometer + Prometheus（QPS、RT、错误率、限流触发数）
- 告警：限流触发、熔断触发、事务超时、注册中心掉线

---

## 7. 验收清单（DoD）

- [ ] 服务间调用全链路有超时+重试+熔断+降级
- [ ] RPC 接口有版本号，变更兼容策略明确
- [ ] 分布式事务补偿逻辑可描述/可演练
- [ ] 配置变更可灰度、有历史版本可回滚
- [ ] 链路追踪能定位跨服务慢请求
