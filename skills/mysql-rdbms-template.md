# MySQL 与关系型数据库模板（mysql-rdbms）

> 目标：让数据库设计、查询优化、运维一次做对，避免线上性能事故和数据一致性问题。

---

## 固定输出物（AI 必须产出）

- 表结构定义（字段/类型/默认值/NULL/约束/字符集/排序规则）
- 索引设计清单（每个索引服务场景 + 最左前缀验证）
- 关键查询 EXPLAIN 结论（type/rows/key/extra）
- 事务边界与隔离级别说明
- 迁移脚本（up/down）+ 回滚演练步骤
- 备份与恢复策略（全量/增量/时间点恢复）

## 必须/禁止规则

- 必须：所有表都有主键（自增/雪花/UUID）
- 必须：关联查询有索引支撑，EXPLAIN 无 ALL/FILESORT/TEMPORARY
- 必须：批量操作有分批策略（避免大事务/长锁）
- 必须：生产变更先灰度/先备库验证
- 禁止：SELECT * 在生产代码中无明确理由使用
- 禁止：在 WHERE 中对索引字段做函数计算（导致索引失效）
- 禁止：无索引的大表直接 ALTER（pt-osc/gh-ost 或影子表）
- 禁止：密码/密钥直接明文存数据库（必须加密/哈希）

---

## 1. 数据库与表设计

- 数据库字符集：utf8mb4 / utf8mb4_unicode_ci
- 表引擎：InnoDB（必须）
- 表设计原则：
  - 字段命名：小写下划线，避免保留字
  - 类型选择：INT/BIGINT/VARCHAR/DATETIME/DECIMAL/JSON（按需）
  - 默认值策略：NOT NULL + 默认值，减少 NULL 判断
  - 软删除：deleted_at（推荐）或 status 字段

---

## 2. 索引设计

- 主键：单表自增 / 分布式雪花 / UUID（说明选择原因）
- 业务索引：
  - 单列索引 vs 复合索引（最左前缀）
  - 覆盖索引（减少回表）
- 避免：
  - 冗余索引
  - 低选择性索引（如性别 status=0/1）
  - 过多索引（写放大）
- 验证：EXPLAIN 输出预期 type=range/ref/eq_ref，Extra 无 Using filesort/Using temporary

---

## 3. SQL 规范

- 查询：
  - 明确 SELECT 字段（禁止 SELECT *）
  - WHERE 条件匹配索引最左前缀
  - 分页：游标/覆盖索引分页（深分页优化）
  - JOIN：小表驱动大表，关联字段同类型同字符集
- 写入：
  - INSERT 批量（values 多行）
  - UPDATE/DELETE 带 WHERE + LIMIT（防误删全表）
- 禁止：
  - 无 WHERE 的 UPDATE/DELETE
  - 大表上无索引的 ORDER BY / GROUP BY
  - 隐式类型转换（字符串查数字）

---

## 4. 事务与并发

- 隔离级别：READ COMMITTED（推荐）/ REPEATABLE READ
- 事务边界：
  - 尽量短，不要包网络调用/复杂计算
  - 同一事务内操作同模块数据
- 锁：
  - 乐观锁：version 字段 / updated_at
  - 悲观锁：SELECT FOR UPDATE（明确范围）
  - 死锁预防：统一加锁顺序、超时设置
- 幂等：唯一约束 / INSERT IGNORE / REPLACE INTO / ON DUPLICATE KEY

---

## 5. 迁移与变更

- 工具：Flyway / Liquibase / 手写脚本
- 脚本要求：
  - 可回滚（down 脚本或等价操作）
  - 幂等（可重复执行不报错）
  - 分批执行（大表加字段/索引用 pt-osc/gh-ost）
- 变更流程：
  - 开发环境验证
  - 测试环境验证
  - 生产灰度（先备库/小流量）

---

## 6. 备份与恢复

- 备份策略：
  - 全量：每天/每周
  - 增量：binlog 持续
  - 保留周期：
- 恢复演练：季度至少一次
- 监控：备份成功率、备份大小、恢复耗时

---

## 7. 性能与监控

- 慢查询：slow_query_log，阈值 1s
- 连接池：最大连接数、等待队列、超时
- 监控指标：
  - QPS/TPS
  - 慢查询数
  - 主从延迟
  - 连接数/活跃连接
  - 锁等待

---

## 8. 高可用（如适用）

- 架构：主从 / MGR / MHA / ProxySQL
- 读写分离：延迟阈值、强制走主库场景
- 分库分表：Sharding-JDBC / Vitess / 业务层拆分

---

## 9. 验收清单（DoD）

- [ ] 所有表有主键，字符集 utf8mb4
- [ ] 关键查询 EXPLAIN 无 ALL/FILESORT/TEMPORARY
- [ ] 迁移脚本可回滚且演练过
- [ ] 备份策略明确且恢复演练通过
- [ ] 慢查询监控与告警已配置
