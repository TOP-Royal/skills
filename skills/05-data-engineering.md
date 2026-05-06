# 技能 05：数据工程与 SQL

> 数据是 AI 时代的石油，数据工程师是管道建设者。

---

## 技能概述

SQL 和数据分析能力在 2026 年依然是最稳定、最基础、最不可替代的技能。无论 AI 如何发展，企业都需要从原始数据中提取洞察、构建数据管道、维护数据仓库。Pluralsight 将 SQL 列为 2026 年第四大热门技能，数据工程方向需求持续高涨。

---

## 核心知识领域

### 1. SQL 精通
- **基础查询**：SELECT、JOIN、子查询、窗口函数
- **高级分析**：CTE（递归 CTE）、PIVOT/UNPIVOT、排名函数
- **性能优化**：执行计划、索引设计、查询重写
- **数据库设计**：范式与反范式、ER 建模、分区策略
- **方言差异**：PostgreSQL、MySQL、SQL Server、BigQuery、Snowflake

### 2. 数据仓库与 OLAP
- **维度建模**：星型/雪花模型、事实表/维度表
- **ETL/ELT 管道**：抽取、转换、加载的最佳实践
- **现代数据栈**：dbt + Snowflake/BigQuery + Fivetran/Airbyte
- **数据湖**：S3 + Delta Lake / Iceberg / Hudi
- **湖仓一体**：Databricks、Starburst

### 3. 实时数据处理
- **流处理框架**：Apache Kafka、Flink、Spark Streaming、ksqlDB
- **事件驱动架构**：CDC（变更数据捕获）、Event Sourcing
- **消息队列**：Kafka、RabbitMQ、Pulsar、Redis Streams
- **实时分析**：ClickHouse、Apache Druid、Pinot

### 4. 数据质量与治理
- **数据验证**：Great Expectations、Soda Core、dbt tests
- **数据血缘**：OpenLineage、DataHub、Amundsen
- **数据目录**：数据发现、元数据管理
- **隐私合规**：GDPR、CCPA、数据脱敏与匿名化
- **数据质量监控**：异常检测、SLA 定义

### 5. 现代分析数据库
- **DuckDB**：嵌入式分析型数据库，本地数据分析爆发
- **ClickHouse**：列式 OLAP，高性能实时分析
- **Apache Druid**：实时摄取 + 亚秒查询
- **StarRocks / Doris**：国产高性能 MPP 数据库

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **dbt** | 数据转换（T in ELT） | ⭐⭐⭐⭐⭐ |
| **Apache Airflow** | 工作流编排 | ⭐⭐⭐⭐⭐ |
| **DuckDB** | 本地分析数据库 | ⭐⭐⭐⭐⭐ |
| **Apache Kafka** | 流处理平台 | ⭐⭐⭐⭐⭐ |
| **Apache Spark** | 大规模数据处理 | ⭐⭐⭐⭐ |
| **Airbyte** | 开源数据集成 | ⭐⭐⭐⭐ |
| **Great Expectations** | 数据质量验证 | ⭐⭐⭐⭐ |
| **ClickHouse** | 列式 OLAP | ⭐⭐⭐⭐ |
| **Flink** | 实时流处理 | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [duckdb/duckdb](https://github.com/duckdb/duckdb) - 嵌入式分析数据库，2026 年现象级项目
- [dbt-labs/dbt-core](https://github.com/dbt-labs/dbt-core) - 数据转换的标准工具
- [apache/airflow](https://github.com/apache/airflow) - 数据管道工作流编排
- [apache/kafka](https://github.com/apache/kafka) - 分布式流处理平台
- [apache/spark](https://github.com/apache/spark) - 统一分析引擎
- [airbytehq/airbyte](https://github.com/airbytehq/airbyte) - 开源 ELT 连接器
- [ClickHouse/ClickHouse](https://github.com/ClickHouse/ClickHouse) - 列式数据库管理系统
- [great-expectations/great_expectations](https://github.com/great-expectations/great_expectations) - 数据质量验证框架

---

## 学习路径

### 初级阶段（2-3 周）
1. 精通 SQL：从基础查询到窗口函数、CTE
2. 学习 PostgreSQL 作为基准数据库
3. 理解数据库设计原则与索引优化
4. 熟悉至少一种 BI 工具（Metabase / Superset / Tableau）

### 中级阶段（3-5 周）
1. 学习 dbt，实现版本控制的数据转换
2. 使用 Airflow 编排 ETL 管道
3. 掌握数据仓库建模（星型/雪花模型）
4. 了解数据湖概念（Parquet、Delta Lake）
5. 使用 DuckDB 进行本地数据分析

### 高级阶段（持续）
1. 设计实时数据处理架构（Kafka + Flink/Spark）
2. 实现数据质量监控与数据治理框架
3. 湖仓一体架构落地
4. 大规模数据迁移与同步方案
5. AI 数据管道：特征工程、向量数据存储、训练数据管理

---

## 实践项目建议

1. **电商数据分析平台**：从订单数据到销售洞察的完整 pipeline
2. **实时用户行为分析**：Kafka → Flink → ClickHouse → 实时看板
3. **dbt 数据仓库**：使用 dbt + DuckDB/PostgreSQL 构建维度模型
4. **日志分析系统**：ELK → SQL 查询接口，替代 expensive SaaS
5. **AI 训练数据管道**：原始数据 → 清洗 → 特征工程 → 向量存储

---

## SQL 学习资源推荐

| 资源 | 类型 | 说明 |
|------|------|------|
| SQLBolt | 在线练习 | 交互式基础 SQL |
| Mode Analytics | 教程 + 数据集 | 实战导向 |
| LeetCode Database | 刷题 | 面试准备 |
| Use The Index, Luke! | 书籍/网站 | 索引与性能优化 |
| dbt Learn | 官方课程 | dbt 最佳实践 |
| DuckDB 文档 | 官方文档 | 现代分析 SQL |

---

## 关键趋势

- **DuckDB 现象级崛起**：嵌入式分析替代传统大数据栈用于中小规模
- **ELT 取代 ETL**：先加载后转换，利用目标数据库算力
- **dbt 成为标准**：数据转换的版本控制与测试
- **实时化需求**：从 T+1 走向分钟/秒级延迟
- **AI 数据管道**：为 LLM 训练、RAG、特征工程的数据准备
- **数据网格（Data Mesh）**：去中心化数据架构

---

## 参考资源

- [DuckDB 官方文档](https://duckdb.org/docs/)
- [dbt 文档](https://docs.getdbt.com/)
- [Airflow 文档](https://airflow.apache.org/docs/)
- [Modern Data Stack Ecosystem](https://moderndatastack.xyz/)
- [Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp)
