# 技能 19：Python 语言核心

> 语法简洁、生态庞大，AI 时代的第一编程语言。

---

## 技能概述

Python 是 2026 年最广泛使用的编程语言之一。它以简洁的语法和庞大的生态系统著称，在 AI/ML、数据科学、自动化运维、Web 后端和脚本编写等领域占据主导地位。Python 3.13+ 的性能持续优化，`uv` 和 `ruff` 等 Rust 编写的工具链正在重塑 Python 开发生态。本技能聚焦 Python 语言本身，从核心语法到高级特性，再到工程化实践。

---

## 核心知识

### 1. 语言基础
- **数据类型**：int/float/str/bool/None、list/tuple/dict/set/frozenset
- **控制流**：if/elif/else、for/while、break/continue/else（循环 else）、match/case（3.10+）
- **函数**：定义、参数（位置/关键字/默认/可变 *args/**kwargs）、匿名函数 lambda
- **作用域**：LEGB 规则、global/nonlocal、闭包
- **迭代器与生成器**：iter/next、yield/yield from、生成器表达式
- **装饰器**：函数装饰器、类装饰器、functools.wraps、带参数装饰器
- **上下文管理器**：with 语句、__enter__/__exit__、contextlib
- **推导式**：列表/字典/集合推导式、嵌套推导式

### 2. 面向对象编程
- **类与对象**：__init__、self、类属性 vs 实例属性
- **继承与多态**：单继承、多继承、MRO（方法解析顺序）、super()
- **魔术方法（Dunder Methods）**：
  - 构造/析构：__new__、__init__、__del__
  - 字符串表示：__str__、__repr__、__format__
  - 运算符重载：__eq__、__lt__、__add__、__getitem__、__call__
  - 属性访问：__getattr__、__setattr__、__getattribute__、__dir__
  - 描述符：__get__、__set__、__delete__
- **属性装饰器**：@property、@<name>.setter、@<name>.deleter
- **类方法/静态方法**：@classmethod、@staticmethod
- **数据类（dataclasses）**：@dataclass、field()、__post_init__
- **枚举**：Enum、IntEnum、auto()
- **抽象基类（ABC）**：abc 模块、@abstractmethod

### 3. 异常处理与调试
- **异常层级**：BaseException → Exception → 具体异常
- **try/except/else/finally 结构**
- **自定义异常**：继承 Exception、添加属性
- **异常链**：raise ... from ...
- **调试工具**：pdb、ipdb、pdb++、breakpoint()（3.7+）
- **日志**：logging 模块、Handler/Formatter/Filter、配置文件
- **断言**：assert、pytest 中的断言重写

### 4. 模块与包管理
- **模块系统**：import、from ... import ...、__all__、相对导入
- **包结构**：__init__.py（3.3+ 可选）、namespace packages
- **虚拟环境**：venv、virtualenv、conda、pyenv
- **现代工具链**：
  - **uv**：极速包管理 + 虚拟环境 + Python 版本管理（Astral）
  - **poetry**：依赖锁定、pyproject.toml、发布
  - **pdm**：PEP 582（局部包目录）、标准合规
  - **pip + requirements.txt**：传统方案
- **pyproject.toml**：项目元数据、构建系统、工具配置统一
- **Wheel / sdist**：分发格式、构建后端（setuptools/flit/hatchling）

### 5. 类型系统（Type Hints）
- **基础注解**：int/str/list[dict]/Optional/Union
- **typing 模块**：TypedDict、NamedTuple、Protocol、TypeVar、Generic
- **Python 3.10+ 简化**：| 替代 Union、X | None 替代 Optional[X]
- **Python 3.12**：Type Parameter Syntax（def f[T](x: T) -> T）
- **静态检查**：mypy、pyright、Pylance（VS Code）
- **运行时检查**：Pydantic、typeguard、beartype

### 6. 并发与异步
- **GIL（全局解释器锁）**：影响、规避策略
- **多线程**：threading、Queue、Lock、RLock、Semaphore、Event
- **多进程**：multiprocessing、Pool、Process、共享内存、Manager
- **asyncio**：
  - async/await 语法
  - 事件循环：asyncio.run()、get_event_loop()
  - 任务：asyncio.create_task()、TaskGroup（3.11+）
  - 同步原语：asyncio.Lock/Event/Semaphore/Queue
  - 超时：asyncio.wait_for()、timeout()（3.11+）
- **asyncio 生态**：aiohttp、aiofiles、aioredis、asyncpg

### 7. 元编程与高级特性
- **反射**：type()、isinstance()、issubclass()、getattr()、hasattr()、vars()、dir()
- **动态代码**：eval()、exec()、compile()、ast 模块
- **描述符协议**：__get__、__set__、__delete__、属性控制
- **元类（Metaclass）**：type() 工厂、__metaclass__、元类继承
- **代码生成**：Jinja2 模板生成代码、AST 转换
- **性能剖析**：cProfile、line_profiler、memory_profiler、py-spy

### 8. 标准库精要
- **collections**：Counter、deque、defaultdict、OrderedDict、ChainMap
- **itertools**：无限迭代器、组合/排列、分组
- **functools**：partial、reduce、lru_cache、singledispatch、cached_property
- **pathlib**：面向对象的文件路径（替代 os.path）
- **json / csv / pickle / tomllib**：数据序列化
- **re**：正则表达式
- **datetime / zoneinfo**：时间日期、时区处理（3.9+ zoneinfo）
- **hashlib / secrets**：哈希与安全随机
- **tempfile / shutil**：临时文件与高级文件操作
- **argparse / click / typer**：命令行参数解析

---

## 热门工具

| 工具 | 用途 |
|------|------|
| **uv** | 极速包管理 + 虚拟环境 |
| **Ruff** | 极速 linter + formatter |
| **mypy / pyright** | 静态类型检查 |
| **pytest** | 测试框架 |
| **Pydantic** | 数据验证与序列化 |
| **black / ruff format** | 代码格式化 |
| **pre-commit** | Git 钩子代码质量 |
| **tox / nox** | 多环境测试 |
| **cython / mypyc** | 编译加速 |
| **pdb / ipdb** | 调试器 |

---

## 学习路径

### 初级（2-3 周）
1. 基础语法、数据类型、控制流、函数
2. 列表、字典操作与推导式
3. 文件读写、异常处理
4. 面向对象：类、继承、魔术方法基础
5. 模块导入与 pip 使用

### 中级（3-4 周）
1. 装饰器与上下文管理器
2. 生成器与迭代器协议
3. 标准库深入：collections、itertools、functools、pathlib
4. 类型注解：基础 → typing 模块 → mypy 检查
5. 并发：threading/multiprocessing/asyncio 选择与使用
6. 日志配置与调试技巧

### 高级（持续）
1. 描述符协议与元类
2. 反射与动态代码执行
3. 性能优化：剖析、算法优化、Cython
4. 设计模式：单例、工厂、策略、观察者、装饰器模式
5. Python C 扩展 / CFFI / ctypes
6. 阅读 CPython 源码：对象模型、GIL、解释器循环

---

## 实践项目

1. **CLI 工具**：带参数解析、配置文件、日志的命令行工具
2. **自定义数据结构**：实现 LRU Cache、Trie、跳表
3. **异步爬虫**：aiohttp + asyncio + 限流 + 重试机制
4. **配置文件解析器**：支持 YAML/JSON/TOML + Schema 验证
5. **装饰器库**：缓存、重试、计时、权限检查等通用装饰器

---

## 关键趋势

- **uv + ruff 替代旧工具链**：安装速度提升 10-100 倍
- **Python 3.12/13 性能飞跃**：解释器优化、nogil 实验
- **类型注解成为标配**：PEP 484 后生态系统成熟
- **PEP 723**：单文件脚本依赖声明（uv run script.py 直接运行）
- **Pydantic v2**：Rust 重写核心，10-50 倍性能提升
- **AI 辅助 Python**：Copilot/Cursor 对 Python 支持极佳
- **Python 在 AI 中不可替代**：PyTorch、JAX、Hugging Face 生态依赖 Python

---

## 参考资源

- [Python 官方文档](https://docs.python.org/zh-cn/3/)
- [Fluent Python](https://dabeley.com/) - 高级 Python 编程
- [uv 文档](https://docs.astral.sh/uv/)
- [Ruff 文档](https://docs.astral.sh/ruff/)
- [mypy 文档](https://mypy.readthedocs.io/)
- [Real Python](https://realpython.com/) - 高质量教程
- [Python Cookbook](https://bit.ly/3PyCookbook) - 实用代码片段
