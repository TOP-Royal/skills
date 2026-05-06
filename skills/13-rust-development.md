# 技能 13：Rust 开发

> 系统编程的新贵，安全与性能的完美平衡。

---

## 技能概述

Rust 在 2026 年已成为系统编程和高性能后端的首选新贵。Linux 内核逐步接纳 Rust，云端原生工具链（如 uv、ruff、vector）大量使用 Rust 编写。Rust 的所有权系统从根本上消除了内存安全漏洞，使其成为 C/C++ 的安全替代者。同时，Rust 的零成本抽象和并发安全模型让它在高性能网络服务、数据库、区块链和 WebAssembly 领域快速扩张。

---

## 核心知识

### 1. 所有权与借用
- 所有权规则：每个值有且只有一个所有者
- 借用（Borrowing）：不可变借用 &T、可变借用 &mut T
- 生命周期（Lifetime）：编译期验证引用有效性
- 智能指针：Box、Rc、Arc、RefCell、Mutex、RwLock
- Copy / Clone / Drop trait

### 2. 类型系统与模式
- 枚举（Enum）与模式匹配（match）
- Option<T> 与 Result<T, E>：无 null 的错误处理
- 泛型与 Trait：接口定义、Trait 对象、关联类型
- 类型推断与类型别名
- Never 类型（!）与发散函数

### 3. 并发与异步
- 线程：std::thread、JoinHandle、通道（mpsc）
- 异步编程：async/await、Future、Pin
- Tokio：异步运行时（任务调度、IO、定时器）
- 并发原语：Mutex、RwLock、Semaphore、Barrier（标准库 + parking_lot）
- Send 与 Sync trait：编译期线程安全保证

### 4. 内存管理
- 所有权系统自动管理内存，无 GC
- 堆分配：Box、Vec、String
- 栈分配与栈展开（stack unwinding）
- unsafe Rust：原始指针、FFI、内部可变性
- 自定义分配器

### 5. 宏与元编程
- 声明宏（macro_rules!）
- 过程宏（Procedural Macros）：派生宏、属性宏、函数宏
- 编译期计算：const fn、const 泛型

### 6. 生态与工具链
- Cargo：包管理、构建、测试、文档
- Rustup：工具链管理
- Clippy：Lint 工具
- Rustfmt：代码格式化
- Crates.io：包注册中心
- 测试：单元测试、集成测试、文档测试、benchmark（criterion）

---

## 热门框架/库

| 工具 | 用途 |
|------|------|
| **Tokio** | 异步运行时 |
| **Axum / Actix-web** | Web 框架 |
| **Tonic** | gRPC 框架 |
| **Diesel / SQLx** | ORM / 类型安全 SQL |
| **Serde** | 序列化/反序列化 |
| **Rayon** | 数据并行 |
| **PyO3** | Python 扩展开发 |
| **WASM-bindgen** | WebAssembly 绑定 |
| **Crossbeam** | 并发工具库 |
| **Bevy** | 游戏引擎 |
| **Leptos** | 全栈 Web 框架（Rust 原生） |
| **Yew** | WebAssembly 前端框架 |

---

## 学习路径

### 初级（2-3 周）
1. 所有权、借用、生命周期（Rust Book 第 1-10 章）
2. 结构体、枚举、模式匹配
3. 错误处理：Result、? 运算符、panic
4. 集合类型：Vec、HashMap、String
5. Cargo 项目管理与基本测试

### 中级（3-5 周）
1. 泛型与 Trait 系统
2. 生命周期深入与高级 Trait 用法
3. 智能指针与内部可变性
4. 多线程编程与并发模式
5. 异步编程：async/await + Tokio
6. 宏基础与过程宏了解

### 高级（持续）
1. unsafe Rust：FFI、原始指针、与 C/C++ 互操作
2. 性能优化：零拷贝、内存布局、SIMD
3. 嵌入式 / 裸机 Rust（no_std）
4. WebAssembly 开发
5. 编译器插件与自定义工具链
6. 大型项目架构与模块化设计

---

## 实践项目

1. **CLI 工具**：仿 ripgrep 的文件搜索工具
2. **HTTP API 服务**：Axum + SQLx + PostgreSQL
3. **聊天服务器**：WebSocket + Tokio + 广播
4. **Python 扩展**：PyO3 开发高性能计算模块
5. **WASM 前端应用**：Yew / Leptos 构建浏览器应用
6. **数据库客户端**：实现简单 Redis 客户端协议

---

## 关键趋势

- **Linux 内核接纳 Rust**：2026 年更多内核模块用 Rust 重写
- **云端原生工具链 Rust 化**：uv、ruff、vector 等证明 Rust 工具性能优势
- **WebAssembly 主力语言**：Rust → WASM 是最成熟的编译路径
- **区块链基础设施**：Solana、Polkadot、NEAR 核心 Rust 开发
- **安全替代 C/C++**：操作系统、浏览器引擎、数据库逐步引入 Rust
- **Rust 前端崛起**：Leptos、Dioxus 等全栈 Rust 框架成熟
- **AI 辅助学习**：所有权系统仍是学习曲线，但 AI 工具降低入门门槛

---

## 参考资源

- [The Rust Programming Language (The Book)](https://doc.rust-lang.org/book/)
- [Rust by Example](https://doc.rust-lang.org/rust-by-example/)
- [Tokio 文档](https://tokio.rs/tokio/tutorial)
- [This Week in Rust](https://this-week-in-rust.org/)
- [Rustlings](https://github.com/rust-lang/rustlings) - 交互式练习
