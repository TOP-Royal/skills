# 技能 15：JavaScript 开发

> Web 世界的通用语言，从浏览器到服务器到嵌入式无处不在。

---

## 技能概述

JavaScript 在 2026 年依然是 Web 开发的基础语言，同时通过 Node.js、Deno、Bun 扩展到了服务端、CLI 工具和嵌入式领域。虽然 TypeScript 在工程化项目中占据主导，但 JavaScript 的底层理解对于前端开发、Node.js 运行时和浏览器引擎调试仍然不可或缺。ES2024/2025 持续引入新特性，语言本身在快速进化。

---

## 核心知识

### 1. 语言基础
- **数据类型**：原始类型（string/number/boolean/null/undefined/symbol/bigint）+ 引用类型（Object/Array/Function）
- **类型转换**：隐式转换规则、== vs ===、truthy/falsy 值
- **作用域**：函数作用域、块级作用域（let/const）、词法作用域、闭包
- **执行上下文**：this 绑定规则（默认/隐式/显式/new）、箭头函数的 this
- **原型链**：__proto__、prototype、Object.create、instanceof
- **事件循环**：宏任务（macrotask）、微任务（microtask）、Promise 队列
- **错误处理**：try/catch/finally、Error 类型、自定义 Error

### 2. ES6+ 现代特性
- 解构赋值、展开运算符、模板字符串
- Promise / async / await、Promise.all / Promise.race / Promise.allSettled
- 模块化：ES Modules（import/export）vs CommonJS（require/module.exports）
- 迭代器与生成器（Generator）、for...of
- Map / Set / WeakMap / WeakSet
- 可选链（?.）、空值合并（??）、逻辑赋值（||= / &&= / ??=）
- 顶层 await、at() 方法、Object.hasOwn()
- ES2024/2025：Array grouping、Promise.withResolvers、Temporal API

### 3. 函数式编程
- 一等函数、高阶函数、纯函数
- 闭包应用：模块模式、柯里化、偏函数应用
- 数组方法：map/filter/reduce/find/some/every/flat/flatMap
- 函数组合：pipe / compose
- 不可变数据：Immutable.js（了解）、Spread 复制、结构化克隆

### 4. 浏览器环境与 DOM
- DOM 操作：选择器、元素创建与修改、事件监听
- 事件机制：冒泡、捕获、事件委托、自定义事件
- BOM：window、location、history、navigator、localStorage/sessionStorage
- 网络请求：Fetch API、XMLHttpRequest、AbortController
- Web API：WebSocket、Web Workers、Service Workers、Notifications
- 性能：requestAnimationFrame、Intersection Observer、Resize Observer

### 5. Node.js 运行时
- 模块系统：CommonJS vs ES Modules、package.json 配置
- 事件驱动：EventEmitter、Stream API（Readable/Writable/Duplex/Transform）
- 文件系统：fs/promises、Path、Buffer
- 网络：net、http/https、cluster 模块
- 进程管理：child_process、worker_threads、cluster
- 包管理：npm / yarn / pnpm 对比与选择
- 环境管理：nvm / fnm

### 6. 异步编程深入
- 回调地狱与解决方案
- Promise 链式调用与错误传播
- async/await 语法糖与内部机制
- 并发控制：限制并发数、p-map、p-limit
- 取消与超时：AbortController、Promise.race + setTimeout

---

## 热门工具/框架

| 工具 | 用途 |
|------|------|
| **Node.js / Deno / Bun** | 运行时 |
| **Express / Fastify / Koa** | Web 框架 |
| **React / Vue / Svelte** | 前端框架 |
| **Next.js / Nuxt / SvelteKit** | 全栈框架 |
| **Jest / Vitest** | 测试框架 |
| **Playwright / Puppeteer** | 浏览器自动化 |
| **ESLint / Prettier** | 代码质量 |
| **Webpack / Vite / Rollup** | 构建工具 |
| **Lodash / Ramda** | 工具库 |
| **Axios / undici** | HTTP 客户端 |

---

## 学习路径

### 初级（2 周）
1. JS 基础语法、数据类型、运算符
2. 控制流、函数、作用域、闭包
3. 数组与对象操作
4. DOM 基础操作与事件
5. ES6+ 核心特性

### 中级（3-4 周）
1. 异步编程：Promise、async/await、事件循环深入
2. 原型链与面向对象
3. 模块化开发与工具链
4. Node.js 基础：HTTP 服务、文件操作、npm
5. 测试：Jest / Vitest 单元测试

### 高级（持续）
1. 函数式编程范式
2. 浏览器渲染原理与性能优化
3. 网络协议：HTTP/1.1、HTTP/2、HTTP/3、WebSocket
4. 安全：XSS、CSRF、CSP、同源策略
5. V8 引擎原理：隐藏类、内联缓存、垃圾回收

---

## 实践项目

1. **待办应用**：DOM 操作 + localStorage + 事件委托
2. **CLI 工具**：Node.js + Commander.js + 文件处理
3. **实时聊天**：WebSocket + Node.js 服务端
4. **爬虫**：Puppeteer / Playwright 无头浏览器
5. **自定义 Promise 库**：手写 Promise.all/race/resolve/reject

---

## 关键趋势

- **TypeScript 成为工程标配**：但 JS 底层理解仍不可或缺
- **Bun 挑战 Node.js**：更快的运行时，但生态成熟度待观察
- **Deno 2 稳定**：内置 TS 支持、权限模型、标准库
- **ES 标准持续演进**：Temporal API、Records & Tuples（提案）
- **AI 辅助 JS 开发**：大量前端代码由 AI 生成，调试能力更重要
- **Web 平台新 API**：WebGPU、File System Access、Popover API

---

## 参考资源

- [MDN JavaScript 指南](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide)
- [JavaScript.info](https://javascript.info/)
- [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS)
- [Node.js 官方文档](https://nodejs.org/docs/latest/api/)
- [ES2024 新特性](https://github.com/tc39/proposals)
