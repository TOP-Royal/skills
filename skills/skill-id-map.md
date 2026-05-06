# Skill ID ↔ Template ID ↔ Trigger 映射表（唯一事实来源）

> 目标：解决 Skill/Template/触发关键词命名分裂与重复，保证新增能力时不会引入冲突。

---

## 使用规则（门禁）

- 新增/改名/废弃任意 Skill ID 或 Template ID 时：必须同步更新本表。
- `.cursorrules` / `.windsurfrules` 中出现的 ID：必须能在本表中找到对应条目。
- `skills-reference.md` 中出现的 Template 链接：必须能在本表中找到对应条目，且文件存在。

---

## 1. Template IDs（可执行模板）

| Canonical ID | 文件 | 触发关键词（示例） | Alias（可选） |
|-------------|------|-------------------|--------------|
| `one-shot-delivery` | `skills/one-shot-delivery-template.md` | 任何开发任务（总控编排） | |
| `requirements-doc` | `skills/requirements-doc-template.md` | 需求说明书/PRD | |
| `coding-preflight` | `skills/coding-preflight-template.md` | 开写前检查/Preflight | |
| `definition-of-done` | `skills/definition-of-done-template.md` | DoD/验收/提交前自检 | |
| `product-manager` | `skills/product-manager-template.md` | 需求不明确/缺场景/缺竞品/缺价值评估 | |
| `designer` | `skills/designer-template.md` | UI/UX/交互/响应式/动画/无障碍/前端还原 | |
| `ai-marketing` | `skills/ai-marketing-template.md` | 增长运营/内容营销/广告投放/用户运营 | |
| `api-design` | `skills/api-design-template.md` | API 新增/修改 | |
| `db-design` | `skills/db-design-template.md` | DB 表/索引/查询/迁移 | |
| `mysql-rdbms` | `skills/mysql-rdbms-template.md` | MySQL 表/索引/SQL/事务/备份 | |
| `microservices-middleware` | `skills/microservices-middleware-template.md` | Nacos/Dubbo/Sentinel/Seata/RocketMQ | |
| `redis-cache` | `skills/redis-cache-template.md` | Redis/缓存一致性/穿透击穿雪崩 | |
| `message-queue` | `skills/message-queue-template.md` | Kafka/RocketMQ/RabbitMQ/Pulsar | |
| `payment-ecosystem` | `skills/payment-ecosystem-template.md` | 支付/交易/退款/对账/回调/分账 | |
| `tech-research` | `skills/tech-research-template.md` | 选型/找开源库/替代品/架构方案 | |
| `observability` | `skills/observability-template.md` | 日志/指标/追踪/告警/上线关键链路 | |
| `secure-coding` | `skills/secure-coding-template.md` | 外部输入/权限/敏感数据 | |
| `testing-strategy` | `skills/testing-strategy-template.md` | 测试策略/回归/E2E | |
| `sre-devops` | `skills/sre-devops-template.md` | CI/CD/发布策略/容器编排/SRE/故障演练 | |
| `data-analyst` | `skills/data-analyst-template.md` | BI/报表/指标/ETL/数据可视化/数据治理 | |
| `ml-algorithm` | `skills/ml-algorithm-template.md` | 推荐/搜索/预测模型/特征工程/训练部署监控 | |
| `wechat-mini-program` | `skills/wechat-mini-program-template.md` | 微信小程序/微信生态 | |
| `alipay-mini-program` | `skills/alipay-mini-program-template.md` | 支付宝小程序/芝麻信用/花呗 | |
| `douyin-mini-program` | `skills/douyin-mini-program-template.md` | 抖音小程序/短视频挂载/直播电商 | |
| `qq-mini-program` | `skills/qq-mini-program-template.md` | QQ小程序/群能力/厘米秀/游戏 | |
| `uniapp-cross-platform` | `skills/uniapp-cross-platform-template.md` | UniApp/跨端多端编译 | `uniapp` |
| `ios-native` | `skills/ios-native-template.md` | iOS原生/Swift/SwiftUI/UIKit | |
| `android-native` | `skills/android-native-template.md` | Android原生/Kotlin/Jetpack Compose | |
| `harmonyos` | `skills/harmonyos-template.md` | 鸿蒙/HarmonyOS/ArkTS/ArkUI/Stage | |
| `thesis-writing` | `毕设写作技巧与模板.md` | 毕设/论文写作 | |

---

## 2. Skill IDs（详细技能/知识域）

> 说明：Skill IDs 更偏“知识域/方向”，模板 IDs 更偏“可执行交付物”。当两者同名或易混淆时，以本表为准。

| Canonical ID | 类型 | 典型范围 | Alias（可选） |
|-------------|------|---------|--------------|
| `ios-dev` | skill | iOS 原生知识域（Swift/SwiftUI/UIKit 等） | |
| `android-dev` | skill | Android 原生知识域（Kotlin/Compose 等） | |
| `cross-platform` | skill | Flutter/RN/Electron 等跨端知识域 | |
| `harmonyos` | skill+template | 鸿蒙既是知识域也有模板（优先以模板使用） | |

---

## 3. 兼容性与废弃策略

- 当需要改名 ID 时：
  - 先在 Alias 列新增旧 ID（保持兼容）
  - 再在 `.cursorrules/.windsurfrules` 与 `skills-reference.md` 中统一切换
  - 最后再移除旧 alias（建议至少保留 1-2 个月）
