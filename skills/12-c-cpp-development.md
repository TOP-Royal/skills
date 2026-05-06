# 技能 12：C / C++ 开发

> 系统编程与高性能计算的基石。

---

## 技能概述

C/C++ 在 2026 年依然是系统编程、游戏开发、嵌入式和高性能计算的核心。C++20/23 引入协程、模块、概念等现代特性。Rust 的崛起推动 C++ 社区加强安全检查。C 语言在嵌入式和操作系统开发中不可替代。

---

## 核心知识

### C 语言
- 指针与内存模型、结构体与联合体
- POSIX API、进程/线程、Socket 编程
- 内存管理：malloc/free，常见内存错误
- Linux 内核模块与驱动开发

### C++ 核心
- 面向对象：类、继承、多态、虚函数
- STL：vector/map/set/algorithm/iterator
- 智能指针：unique_ptr/shared_ptr/weak_ptr
- 模板与泛型：函数模板、类模板、SFINAE、Concepts（C++20）
- 现代特性：auto/lambda/移动语义/结构化绑定/协程
- 并发：thread/mutex/condition_variable/future/原子操作
- RAII 与异常安全

### 内存与性能
- 手动内存管理、内存池、自定义分配器
- 编译器优化：O2/O3/LTO/PGO
- 缓存友好性、SIMD（SSE/AVX/NEON）、零拷贝
- 性能分析：perf、Valgrind、AddressSanitizer

### 工具链
- 编译器：GCC、Clang/LLVM、MSVC
- 构建：CMake（标准）、Meson、Bazel、Ninja
- 包管理：vcpkg、Conan
- 调试：GDB、LLDB、Valgrind

---

## 热门框架/库

| 工具 | 用途 |
|------|------|
| CMake | 跨平台构建 |
| vcpkg / Conan | 包管理 |
| Boost | 准标准库 |
| Qt | GUI 框架 |
| Google Test / Catch2 | 测试 |
| fmt / spdlog | 格式化/日志 |
| nlohmann/json | JSON |
| OpenCV | 计算机视觉 |
| Google Benchmark | 微基准测试 |
| flatbuffers / capnproto | 零拷贝序列化 |

---

## 学习路径

### 初级（3-4 周）
1. C 基础 + 指针深入
2. C++ OOP + STL 容器与算法
3. 智能指针与 RAII
4. CMake 构建系统

### 中级（6-8 周）
1. 模板与泛型编程
2. 并发编程（thread/mutex/future/async）
3. 网络编程（Socket + epoll/select）
4. 调试与性能分析工具

### 高级（持续）
1. C++20/23：协程、概念、模块
2. 模板元编程与编译期计算
3. SIMD、缓存优化、锁-free 编程
4. 内核编程 / 嵌入式开发

---

## 实践项目

1. **HTTP 服务器**：线程池 + epoll 并发模型
2. **内存分配器**：高效内存池替代 malloc
3. **JSON 解析器**：手写递归下降解析器
4. **游戏引擎基础**：ECS 架构 + 2D 物理碰撞
5. **Linux 驱动**：字符设备驱动开发

---

## 关键趋势

- C++20/23 协程改变异步编程模式
- Rust 倒逼 C++ 加强内存安全（C++26 Contracts）
- vcpkg/Conan 解决依赖管理痛点
- AI 基础设施底层大量 C++（PyTorch、ONNX Runtime）
- 游戏引擎（UE5、Godot）持续使用 C++
- 自动驾驶 / 车联网 ROS2 大量 C++ 代码

---

## 参考资源

- [cppreference.com](https://en.cppreference.com/)
- [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/)
- [CMake 文档](https://cmake.org/documentation/)
