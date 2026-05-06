# 技能 07：网络安全

> AI 时代的新型安全挑战，云安全与 AI 安全成为核心战场。

---

## 技能概述

网络安全是 2026 年需求量持续攀升的关键技能。Pluralsight 将其列为第三大热门技能，特别强调了 AI 安全和云安全方向。随着 AI 系统深度融入企业基础设施，prompt 注入、模型窃取、对抗性攻击等新型威胁涌现；同时，云原生环境的动态性也要求安全范式从边界防御转向零信任架构。

---

## 核心知识领域

### 1. 应用安全（AppSec）
- **OWASP Top 10 / Top 10 for LLM**：注入、失效访问控制、敏感数据泄露等
- **LLM 特有漏洞**：
  - Prompt Injection（提示词注入）
  - Jailbreak（越狱）
  - Data Exfiltration via LLM
  - Insecure Output Handling
  - Training Data Poisoning
- **安全编码实践**：输入验证、输出编码、参数化查询
- **依赖安全**：SCA（软件成分分析）、漏洞扫描（Snyk、Dependabot）
- **代码审计**：静态分析（SAST）、动态分析（DAST）

### 2. 云安全
- **云共享责任模型**：IaaS / PaaS / SaaS 安全边界
- **IAM 与访问控制**：最小权限原则、RBAC、ABAC、临时凭证
- **网络安全**：VPC 设计、安全组、网络 ACL、WAF、DDoS 防护
- **数据安全**：加密（传输中 / 静态）、密钥管理（KMS）、数据分类
- **容器安全**：镜像扫描、运行时防护、Pod Security、Network Policy
- **无服务器安全**：函数权限最小化、冷启动安全、API 网关保护

### 3. 基础设施安全
- **零信任架构**：永不信任，始终验证
- **身份与访问管理**：SSO、MFA、身份联邦（OIDC / SAML）
- **密钥管理**：HashiCorp Vault、AWS Secrets Manager、证书轮换
- **配置管理**：CSPM（云安全配置管理）、CIS Benchmarks
- **漏洞管理**：扫描、评估、修复、验证闭环
- **入侵检测与响应**：SIEM、EDR、SOAR、威胁情报

### 4. AI / ML 安全
- **模型安全**：对抗性攻击（Adversarial Examples）、模型窃取、成员推断攻击
- **数据隐私**：差分隐私、联邦学习、数据匿名化
- **Prompt 安全**：输入过滤、输出审查、系统提示加固
- **供应链安全**：模型来源验证、训练数据审计
- **AI 伦理与合规**：公平性、可解释性、偏见检测
- **AI 红队测试**：自动化寻找 LLM 漏洞

### 5. 安全运营（SecOps）
- **日志与监控**：集中日志、异常检测、UEBA
- **威胁狩猎**：主动搜索威胁指标（IoC）
- **事件响应**：准备、检测、分析、遏制、根除、恢复
- **DevSecOps**：安全左移、自动化安全测试、安全即代码
- **合规框架**：SOC 2、ISO 27001、GDPR、NIST、PCI-DSS

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **HashiCorp Vault** | 密钥与机密管理 | ⭐⭐⭐⭐⭐ |
| **Trivy** | 容器镜像漏洞扫描 | ⭐⭐⭐⭐⭐ |
| **OWASP ZAP** | Web 应用动态扫描 | ⭐⭐⭐⭐ |
| **Snyk** | 依赖项 + 容器安全 | ⭐⭐⭐⭐⭐ |
| **Falco** | 运行时安全监控（K8s） | ⭐⭐⭐⭐ |
| **Wiz / Orca** | CNAPP（云原生应用保护） | ⭐⭐⭐⭐ |
| **Semgrep** | 轻量级 SAST | ⭐⭐⭐⭐ |
| **Gitleaks** | 机密泄露检测 | ⭐⭐⭐⭐ |
| **OPA / Gatekeeper** | K8s 策略即代码 | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [aquasecurity/trivy](https://github.com/aquasecurity/trivy) - 全能漏洞扫描器（容器、依赖、IaC）
- [hashicorp/vault](https://github.com/hashicorp/vault) - 密钥管理与数据保护
- [OWASP/ZAP](https://github.com/zaproxy/zaproxy) - Web 应用安全扫描
- [falcosecurity/falco](https://github.com/falcosecurity/falco) - 云原生运行时安全
- [returntocorp/semgrep](https://github.com/semgrep/semgrep) - 快速静态分析
- [gitleaks/gitleaks](https://github.com/gitleaks/gitleaks) - Git 仓库机密扫描
- [open-policy-agent/opa](https://github.com/open-policy-agent/opa) - 通用策略引擎
- [owasp/www-project-top-10-for-large-language-model-applications](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications) - LLM 应用安全风险 Top 10

---

## 学习路径

### 初级阶段（2-3 周）
1. 理解 CIA 三元组（机密性、完整性、可用性）
2. 学习 OWASP Top 10，每种漏洞亲手复现一次
3. 掌握基本网络协议与安全（TLS、DNSSEC、VPN）
4. 学习一门脚本语言用于自动化（Python / Bash）

### 中级阶段（3-6 周）
1. 云安全认证：AWS/Azure/GCP 安全专项
2. 容器与 K8s 安全：镜像扫描、RBAC、Network Policy
3. 应用安全：SAST + DAST 集成到 CI/CD
4. 密钥管理：Vault 部署与集成
5. 威胁建模：STRIDE、攻击树

### 高级阶段（持续）
1. AI 安全：Prompt Injection 防御、模型红队测试
2. 零信任架构设计与落地
3. 安全运营：SIEM 规则编写、威胁狩猎
4. DevSecOps：安全工具链自动化、安全度量
5. 合规审计：SOC 2 / ISO 27001 实施经验

---

## 实践项目建议

1. **漏洞扫描流水线**：GitHub Actions + Trivy + Semgrep，PR 自动安全检测
2. **K8s 安全加固**：CIS Benchmark 扫描、Falco 运行时告警、OPA 策略
3. **AI 安全测试平台**：自动化 Prompt Injection 测试框架
4. **零信任实验室**：Identity-Aware Proxy + mTLS + 短期凭证
5. **事件响应演练**：模拟勒索软件攻击，完整 IR 流程演练

---

## 认证路径

| 认证 | 机构 | 难度 | 方向 |
|------|------|------|------|
| Security+ | CompTIA | 入门 | 通用安全 |
| CISSP | (ISC)² | 高级 | 安全管理 |
| CEH | EC-Council | 中级 | 渗透测试 |
| AWS/Azure/GCP 安全 | 云厂商 | 中级 | 云安全 |
| CKA + CKS | CNCF | 中级 | K8s 安全 |
| OSCP | Offensive Security | 高级 | 渗透测试 |

---

## 关键趋势

- **AI 安全成为新学科**：LLM 漏洞、对抗性 AI、AI 供应链安全
- **安全左移深化**：从 DevOps 到 DevSecOps，安全测试嵌入最早阶段
- **零信任成为默认**：边界消失，身份成为新的安全边界
- **CNAPP 整合**：云安全态势管理 + 工作负载保护 + 应用安全一体化
- **AI 辅助防御**：用 AI 检测威胁、自动响应、预测攻击
- **合规压力增大**：数据隐私法规全球扩张

---

## 参考资源

- [OWASP](https://owasp.org/)
- [OWASP LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [MITRE ATT&CK](https://attack.mitre.org/)
- [Cloud Security Alliance](https://cloudsecurityalliance.org/)
- [Hack The Box / TryHackMe](https://www.hackthebox.com/) - 实战练习平台
