# 技能 04：云计算与云原生

> 企业数字化基础设施的核心，2026 年需求量最大的技能之一。

---

## 技能概述

云计算与云原生是 2026 年企业招聘需求最高的技能领域。Pluralsight 将云计算（AWS & Azure）列为 2026 年最热门技能之首。随着 AI 工作负载爆发，云平台的弹性计算、GPU 实例、Serverless 和托管服务成为基础设施标配。

---

## 核心知识领域

### 1. 主流云平台
- **AWS**：EC2、S3、Lambda、RDS、EKS、Bedrock、SageMaker
- **Azure**：VM、Blob Storage、Functions、AKS、OpenAI Service
- **Google Cloud**：Compute Engine、Cloud Storage、Cloud Run、Vertex AI
- **阿里云 / 腾讯云**：国内部署与合规
- **混合云与多云策略**：避免供应商锁定

### 2. 容器化与编排
- **Docker**：镜像构建、多阶段构建、Dockerfile 优化
- **Kubernetes**：Pod、Deployment、Service、Ingress、ConfigMap、Secret
- **Helm**：包管理与模板化部署
- **Kustomize**：声明式配置覆盖
- **容器运行时**：containerd、cri-o

### 3. Serverless 与无服务器
- **函数即服务（FaaS）**：AWS Lambda、Azure Functions、Cloud Functions
- **容器化 Serverless**：AWS Fargate、Google Cloud Run、Azure Container Instances
- **边缘 Serverless**：Cloudflare Workers、Vercel Edge、Deno Deploy
- **Serverless 数据库**：Supabase、PlanetScale、Neon

### 4. 基础设施即代码（IaC）
- **Terraform / OpenTofu**：多云资源编排（2026 年 OpenTofu 因开源争议崛起）
- **Pulumi**：用 Python/TypeScript/Go 编写基础设施
- **AWS CDK**：AWS 云开发套件
- **Nix**：可复现的开发环境构建（社区热度上升）
- **Ansible**：配置管理

### 5. 可观测性
- **指标**：Prometheus + Grafana
- **日志**：ELK Stack、Loki、CloudWatch Logs
- **链路追踪**：Jaeger、Tempo、Zipkin
- **统一标准**：OpenTelemetry（OTel）
- **告警**：PagerDuty、Opsgenie、Alertmanager

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **Kubernetes** | 容器编排标准 | ⭐⭐⭐⭐⭐ |
| **Docker** | 容器化标准 | ⭐⭐⭐⭐⭐ |
| **Terraform / OpenTofu** | 基础设施即代码 | ⭐⭐⭐⭐⭐ |
| **Helm** | K8s 包管理 | ⭐⭐⭐⭐ |
| **ArgoCD** | GitOps 持续交付 | ⭐⭐⭐⭐ |
| **Prometheus + Grafana** | 监控告警 | ⭐⭐⭐⭐⭐ |
| **OpenTelemetry** | 统一可观测性标准 | ⭐⭐⭐⭐⭐ |
| **Pulumi** | 代码化基础设施 | ⭐⭐⭐⭐ |
| **Nix** | 可复现环境 | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) - 容器编排的事实标准
- [hashicorp/terraform](https://github.com/hashicorp/terraform) / [opentofu/opentofu](https://github.com/opentofu/opentofu) - IaC 工具
- [helm/helm](https://github.com/helm/helm) - Kubernetes 包管理器
- [argoproj/argo-cd](https://github.com/argoproj/argo-cd) - 声明式 GitOps 工具
- [prometheus/prometheus](https://github.com/prometheus/prometheus) - 时序数据库与监控系统
- [grafana/grafana](https://github.com/grafana/grafana) - 可视化监控平台
- [pulumi/pulumi](https://github.com/pulumi/pulumi) - 多语言 IaC
- [NixOS/nix](https://github.com/NixOS/nix) - 可复现构建系统

---

## 学习路径

### 初级阶段（2-3 周）
1. 熟悉 AWS/Azure 基础服务（计算、存储、网络）
2. 掌握 Docker：构建、运行、推送镜像
3. 学习 Kubernetes 核心概念与基本操作
4. 使用 Terraform 部署简单云资源

### 中级阶段（3-6 周）
1. 设计高可用 K8s 集群（多可用区、自动扩缩容）
2. 实施 GitOps 工作流（ArgoCD + 应用清单）
3. 搭建完整的可观测性栈（Prometheus + Grafana + Loki + Tempo）
4. 掌握 CI/CD 管道（GitHub Actions / GitLab CI + ArgoCD）
5. 使用 Helm 管理应用生命周期

### 高级阶段（持续）
1. 多云架构设计与成本优化
2. Kubernetes 安全加固（Pod Security、Network Policies、RBAC）
3. 服务网格（Istio / Linkerd）实现 mTLS 与流量管理
4. 混合云与边缘计算架构
5. FinOps：云成本监控与优化策略

---

## 实践项目建议

1. **3 层 Web 应用部署**：VPC → EKS → RDS → ALB，完整生产架构
2. **Serverless API**：API Gateway + Lambda + DynamoDB，零运维后端
3. **GitOps 平台**：代码提交 → 自动构建 → ArgoCD 同步 → 生产部署
4. **多环境管理**：dev/staging/prod 的 Terraform workspace 管理
5. **AI 推理服务**：GPU 节点池 + K8s + vLLM + 自动扩缩容

---

## 认证路径

| 认证 | 平台 | 难度 | 价值 |
|------|------|------|------|
| AWS SAA | AWS | 中等 | ⭐⭐⭐⭐⭐ |
| AWS SAP | AWS | 困难 | ⭐⭐⭐⭐⭐ |
| CKA | CNCF/K8s | 困难 | ⭐⭐⭐⭐⭐ |
| CKAD | CNCF/K8s | 中等 | ⭐⭐⭐⭐ |
| Azure AZ-104 | Azure | 中等 | ⭐⭐⭐⭐ |
| Terraform Associate | HashiCorp | 简单 | ⭐⭐⭐⭐ |

---

## 关键趋势

- **AI 工作负载驱动云消费**：GPU 实例、模型托管服务需求暴增
- **Serverless 容器化**：从函数走向轻量级容器（Cloud Run、Fargate）
- **平台工程崛起**：内部开发者平台（IDP）成为企业标配
- **FinOps 成为必要**：云成本失控促使精细化成本管理
- **GitOps 成为部署标准**：声明式、版本化、自动化
- **Nix 渗透开发环境**：可复现环境解决「在我机器上能跑」问题

---

## 参考资源

- [Kubernetes 官方文档](https://kubernetes.io/docs/)
- [AWS 架构中心](https://aws.amazon.com/architecture/)
- [Terraform 教程](https://developer.hashicorp.com/terraform/tutorials)
- [CNCF 云原生全景图](https://landscape.cncf.io/)
- [OpenTelemetry 文档](https://opentelemetry.io/docs/)
