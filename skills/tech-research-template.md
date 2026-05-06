# 技术调研与项目发现能力模板（tech-research）

> 目标：在技术社区与开源平台快速发现高星、高活跃、高可信度的项目与方案，避免“随手搜一个就用”导致的质量与安全隐患。

---

## 固定输出物（AI 必须产出）

- 目标站点与检索策略（按类型/语言/场景分层检索，明确排序与筛选规则）
- 候选项目清单（≥3 个，含 stars/forks/最近更新/issues 关闭率/维护者活跃度）
- 项目质量评估表（ stars 趋势、依赖树、license、安全漏洞、社区口碑）
- 供应链安全门禁（OpenSSF Scorecard 评分 + 关键 checks 达标清单）
- 方案对比与选型建议（功能覆盖、集成成本、长期维护风险、替代方案）
- 验证清单（快速 demo / 核心用例测试 / 兼容性检查 / 许可证合规）

## 必须/禁止规则

- 必须：任何引入外部库/框架/工具前，先产出候选项目清单与质量评估（禁止无评估直接引入）
- 必须：优先选择有持续维护（近 6 个月有 commit）、有明确 license、有安全审计或大厂背书的项目
- 必须：检查项目的已知 CVE / 漏洞 / 弃用声明 / 供应链攻击历史
- 必须：验证方案与自己的技术栈/版本/运行环境兼容（禁止“文档说支持就相信”）
- 禁止：只看 stars 数量就做决策（star 高≠质量好≠适合自己）
- 禁止：使用无 license、license 模糊、或 AGPL/SSPL 等强传染性 license 而不做合规评估
- 禁止：把“技术博客文章里的方案”直接当生产方案（必须追溯到原始仓库/官方文档）
- 禁止：忽略项目的 open issues / breaking changes / 即将弃用的 API

---

## 1. 目标站点与检索策略（明确站点）

### 1.1 开源项目发现

| 站点 | 用途 | 检索技巧 | 筛选标准 |
|------|------|---------|---------|
| **GitHub** | 代码仓库、issue/PR、release | `topic:xxx stars:>1000 language:python` / Trending / Awesome Lists | stars/forks/最近 commit/open issues 回复率 |
| **GitHub Trending** | 近期热门项目 | 按语言/时间窗口筛选 | 持续 ≥3 天在榜 + 有实际 release |
| **GitHub Awesome Lists** | 领域 curated 清单 | `awesome-xxx` 仓库 | 清单维护活跃、链接有效 |
| **Open Source Alternatives** | 商业软件开源替代 | opensourcealternatives.to / alternativeto.net | 社区评分 + GitHub 活跃度 |
| **Gitee（国内）** | 国内镜像/国产项目 | 按语言/标签/Star 排序 | 与 GitHub 同步情况、issue 活跃度 |

### 1.2 技术问答与方案验证

| 站点 | 用途 | 检索技巧 | 筛选标准 |
|------|------|---------|---------|
| **Stack Overflow** | 具体错误/方案/最佳实践 | `score:10..` / `answers:2..` / 带 [accepted-answer] | 高 vote + 近 2 年内更新 + 有官方文档引用 |
| **Stack Overflow Documentation** | 官方文档整合 | 直接搜索技术标签 | 与官方文档一致 |
| **GitHub Discussions** | 项目级方案讨论 | 在项目内搜索 | 维护者参与回复 |

### 1.3 技术博客与深度文章

| 站点 | 用途 | 检索技巧 | 筛选标准 |
|------|------|---------|---------|
| **Medium (medium.com)** | 技术深度文章 | `tag:technology` / publication:特定技术号 | 作者背书（大厂/核心贡献者）、文章有代码示例 |
| **Dev.to (dev.to)** | 社区技术文章 | 按标签/热榜 | 高反应（❤️+💬）、作者技术背景 |
| **Hacker News (news.ycombinator.com)** | 技术趋势/讨论 | `hn.algolia.com` 搜索 / 按 vote 排序 | 评论质量（有无核心开发者现身说法） |
| **Reddit (reddit.com/r/programming, r/webdev, r/java, r/Python, r/rust, r/golang)** | 社区真实反馈 | 按 top/week/month | 高 vote + 有实际使用经验分享 |
| **InfoQ (infoq.cn / infoq.com)** | 架构/工程实践 | 按专题/标签 | 有实际落地案例 |
| **阮一峰/张鑫旭/酷壳/美团技术团队/阿里技术/字节跳动技术团队** | 中文深度实践 | 直接搜索作者/团队 | 有生产环境数据/源码 |

### 1.4 趋势与权威报告

| 站点 | 用途 | 检索技巧 |
|------|------|---------|
| **ThoughtWorks Technology Radar** | 技术趋势/采纳建议 | 按 quadrant 筛选（Adopt/Trial/Assess/Hold） |
| **Gartner Hype Cycle** | 技术成熟度 | 按年份/领域 |
| **State of JS / State of CSS / Stack Overflow Developer Survey** | 生态真实使用率 | 官方年度报告 |
| **JetBrains Developer Ecosystem Survey** | 工具链/语言趋势 | 官方年度报告 |

### 1.5 安全与合规核查

| 站点 | 用途 |
|------|------|
| **Snyk Advisor (snyk.io/advisor)** | 包安全性/维护度/社区健康 |
| **OSV (osv.dev)** | 开源漏洞数据库 |
| **GitHub Security Advisories** | 仓库级 CVE |
| **npm audit / pip-audit / cargo audit** | 依赖漏洞扫描 |
| **OpenSSF Scorecard** | 项目安全评分 |
| **SNYK Vuln DB** | 已知漏洞 |

---

## 2. 检索策略（分场景）

### 2.1 找“开箱即用”的开源库/框架

1. **GitHub 搜索**：`topic:react-component stars:>5000 language:TypeScript` → 按最近更新排序
2. **Awesome Lists**：`awesome-react` → 找到 curated 的分类列表
3. **Snyk Advisor**：验证安全性与维护度
4. **快速筛选**：
   - 最近 commit < 6 个月
   - contributors > 3（防单点维护者失联）
   - closed issues / total issues > 70%
   - 有明确 license（MIT/Apache-2.0/BSD）

### 2.2 找“特定问题”的解决方案

1. **Stack Overflow**：`score:10.. [spring-boot] "connection pool"` → 看 accepted answer + 最高 vote
2. **GitHub Issues**：在目标仓库搜 `is:issue "your error message"` → 看是否已修复/ workaround
3. **Reddit / HN**：搜真实使用者的踩坑经验
4. **官方文档**：验证方案是否官方推荐（禁止只看博客不验证官方）

### 2.3 找“架构/设计模式”参考

1. **GitHub 大型项目**：搜 `spring-petclinic`、`realworld`、`system-design-primer`
2. **Awesome Lists**：`awesome-system-design`、`awesome-architecture`
3. **大厂技术博客**：搜具体案例（如“美团订单系统架构”）
4. **GitHub 组织**：`github.com/google`、`github.com/netflix`、`github.com/uber` 的公开项目

### 2.4 找“替代品”或“迁移方案”

1. **AlternativeTo**：按功能/平台找替代
2. **GitHub 仓库对比**：对比 stars/issues/PR/文档完整性
3. **Breaking Changes / Migration Guide**：在官方仓库搜 `MIGRATION.md` / `CHANGELOG.md`

---

## 3. 项目质量评估表（每个候选项目必填）

| 维度 | 检查项 | 合格标准 | 当前值 |
|------|--------|---------|--------|
| **活跃度** | 最近 commit | ≤ 6 个月 | |
| | 最近 release | ≤ 12 个月 | |
| | contributors | ≥ 3（核心） | |
| | issue 回复率 | ≥ 70% closed / 30 天内有 maintainer 回复 | |
| **健康度** | stars / forks | stars > 500（小工具）/ > 2000（框架） | |
| | 依赖更新 | 核心依赖无严重 CVE | |
| | 测试覆盖 | 有 CI / 有测试徽章（可选加分） | |
| **安全** | 已知 CVE | 0 高危 / 有中危需评估影响 | |
| | OpenSSF Scorecard | ≥ 5.0（越高越好） | |
| | Snyk 健康度 | ≥ 80 | |
| **合规** | License | MIT / Apache-2.0 / BSD（优先） | |
| | | GPL/AGPL/SSPL（需法务评估） | |
| | | 无 License（禁止直接商用） | |
| **文档** | README 完整度 | 有快速开始/示例/配置/贡献指南 | |
| | API 文档 | 有在线文档或 typedoc/jsdoc | |
| | Changelog | 有版本变更记录 | |
| **集成** | 兼容性 | 与目标语言/框架/版本兼容 | |
| | 包体/性能 | 不显著增加构建时间或运行时开销 | |

---

## 4. 方案对比与选型建议

- 产出格式：
  | 项目 | 功能覆盖 | 集成成本 | 维护风险 | 社区 | 推荐场景 |
  |------|---------|---------|---------|------|---------|
- 选型原则：
  - **Adopt**（成熟采纳）：高活跃度 + 大厂背书 + 大量生产案例
  - **Trial**（试点尝试）：中等活跃度 + 有明确路线图 + 你愿意承担迁移成本
  - **Assess**（评估观察）：新兴但有潜力 + 无严重漏洞 + 有核心团队
  - **Hold**（暂缓观望）：低维护 / 高漏洞 / license 风险 / 与现有栈冲突大

---

## 4.1 供应链安全门禁（OpenSSF Scorecard Gate）

> 目的：把“高星”变成“可被安全接纳”的依赖；在引入前给出可量化门槛。

- 门槛建议（可按团队风险等级调整）：
  - Scorecard 总分：≥ 6.0（核心依赖）/ ≥ 5.0（非核心依赖）
  - 必须满足的关键 checks（低于门槛则禁止引入，或必须写豁免理由）：
    - Branch Protection（分支保护）
    - Code Review（强制评审）
    - Maintained（维护度）
    - Security Policy（安全策略/漏洞上报渠道）
    - Vulnerabilities（已知漏洞跟踪）
    - Pinned Dependencies（依赖固定/lockfile）
    - Token Permissions（CI Token 最小权限）

- 输出格式（每个候选项目必填）：

| 项目 | Scorecard 分数 | 未通过 checks | 风险说明 | 是否可接入 | 备注/豁免 |
|------|----------------|---------------|----------|------------|----------|
| | | | | | |

---

## 5. 验证清单（引入前必须做）

- [ ] 在隔离环境（Docker/VM/沙箱）中跑通官方 quickstart
- [ ] 验证核心用例（你的场景中最关键的 1-3 个功能点）
- [ ] 检查与现有依赖的兼容性（版本冲突 / 许可证冲突）
- [ ] 跑安全扫描（`npm audit` / `pip-audit` / `cargo audit` / `snyk test`）
- [ ] 检查 license 是否允许你的使用场景（商用 / 分发 / 修改）
- [ ] 查看 open issues 中是否有你场景下的已知 bug / 未实现功能
- [ ] 评估迁移成本：如果 6 个月后项目弃用，你的替换成本是多少？

---

## 6. 信息溯源与可靠性判断

- **高可信**：官方仓库 README / 官方文档 / 官方博客 / 核心维护者发言
- **中可信**：Stack Overflow 高 vote 答案（有官方文档链接）/ 大厂技术博客（有数据/源码）
- **低可信**：个人博客无更新 / Medium 无作者背景 / 纯翻译搬运 / 无代码示例
- **禁止**：把“某篇文章说”当最终依据，必须追溯到官方仓库或官方文档验证

---

## 7. 验收清单（DoD）

- [ ] 候选项目清单 ≥ 3 个，均来自明确站点（GitHub/Stack Overflow/知名博客）
- [ ] 每个候选项目已填质量评估表（活跃度/健康度/安全/合规/文档/集成）
- [ ] 已知 CVE / 安全漏洞已核查（OSV/Snyk/GitHub Security Advisories）
- [ ] 供应链安全门禁已完成（OpenSSF Scorecard 分数 + 关键 checks 达标；如不达标需豁免理由）
- [ ] License 合规已确认，无高风险许可证未经评估
- [ ] 核心用例已在隔离环境验证通过
- [ ] 与现有技术栈的兼容性已确认，无不可解决的版本冲突
- [ ] 方案对比表已产出，有明确选型建议（Adopt/Trial/Assess/Hold）
- [ ] 信息已溯源到官方仓库/官方文档，非仅凭博客文章
