# skills

一套“开发一次成型”的技能与工程护栏体系：用可执行模板把 **需求 → 方案 → 护栏 → 测试 → DoD** 串起来，减少返工与线上事故。

## 你能得到什么

- 把复杂开发任务拆成固定输出物：PRD、Preflight、护栏、测试策略、DoD
- 遇到不同类型任务自动触发对应模板（API/DB/安全/观测/支付/SRE/数据/算法/小程序等）
- 在提交前用 DoD 清单把常见坑挡在 PR 之外

## 快速开始（Cursor / Windsurf）

1. 将以下文件配置为全局规则（按你的 IDE 支持方式设置）：
   - `.cursorrules`
   - `.windsurfrules`
2. 开始任何开发任务时，先使用 `one-shot-delivery` 按顺序产出文档，再写代码。

## 核心入口（建议按此阅读）

- 总览入口：`skills/README.md`
- 技能速查：`skills/skills-reference.md`
- ID 唯一事实来源：`skills/skill-id-map.md`
- 可执行化标准：`skills/skill-execution-standard.md`

## 推荐工作流（强制顺序）

- `one-shot-delivery` → 交付编排（PRD/Preflight/护栏/测试/DoD）
- `coding-preflight` → 编码前检查
- 触发护栏（按需）：
  - `api-design`（接口变更）
  - `db-design` + `mysql-rdbms`（数据库变更）
  - `secure-coding`（外部输入/权限/敏感数据）
  - `observability`（上线关键链路/难定位）
  - `payment-ecosystem`（支付/回调/对账/分账）
  - `tech-research`（选型/开源引入，含 OpenSSF Scorecard Gate）
  - `sre-devops`（CI/CD、发布、演练、Incident 管理）
- `testing-strategy` → 测试分层与用例
- `definition-of-done` → 提交前验收清单（含 SDL 分阶段安全门禁）

## 目录结构

```
.
├── skills/                  # 所有可执行模板与详细技能
├── .cursorrules             # Cursor 全局规则（硬触发 + 门禁）
├── .windsurfrules           # Windsurf 全局规则（硬触发 + 门禁）
└── tech-trends-2026.md       # 2026 技术趋势参考
```

## 维护原则

- 新增/改名/废弃 ID：先改 `skills/skill-id-map.md`
- 模板必须遵循 `skills/skill-execution-standard.md`
- 所有结论应可追溯（有证据/链接/可复现步骤），避免“凭感觉”决策
