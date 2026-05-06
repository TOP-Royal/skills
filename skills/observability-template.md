# 可观测性模板（observability）

> 目标：让问题能被快速定位（谁、何时、哪里、为什么）。

## 固定输出物（AI 必须产出）

- 日志字段表（字段名/含义/是否必填/脱敏策略）
- 指标清单（计数 + 延迟直方图 + 关键业务指标）
- Trace 方案（span 划分 + 关键属性）
- 告警阈值（错误率/P95/队列堆积等）

## 必须/禁止规则

- 必须：所有请求贯穿 request_id 或 trace_id
- 必须：错误码可聚合统计（不要只靠文本 message）
- 禁止：日志输出敏感信息（token/密码/证件号/手机号明文）

---

## 1. 日志（Logs）

- 日志格式：结构化（JSON）
- 必备字段：
  - request_id / trace_id
  - user_id（如有）
  - resource_id / order_id（关键业务 ID）
  - latency_ms
  - error_code
- 禁止：输出 token/密码/身份证/手机号明文

---

## 2. 指标（Metrics）

- 计数：success_total / error_total
- 延迟：latency_ms histogram（p50/p95/p99）
- 资源：CPU、内存、连接池、队列堆积
- 业务指标：下单成功率、支付成功率等

---

## 3. 追踪（Tracing）

- 是否使用 OpenTelemetry
- Span 划分：入口 → DB → 下游 HTTP → MQ publish
- 关键属性：route、http.status_code、db.statement（注意脱敏）

---

## 4. 告警（Alerts）

- 错误率告警阈值：
- P95 延迟告警阈值：
- 关键队列堆积告警：

---

## 5. 验收清单（DoD）

- [ ] 线上能按 request_id 追到完整链路
- [ ] 常见错误有明确错误码 + 对应告警
- [ ] 至少一个核心看板（成功率、延迟、吞吐）
