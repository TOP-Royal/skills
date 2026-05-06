# 技能 18：Vue 3 生态与前端框架

> 渐进式框架代表，从简单页面到复杂 SPA 的全能选择。

---

## 技能概述

Vue 3 在 2026 年依然是中国市场和中小型项目中最受欢迎的前端框架之一。其组合式 API（Composition API）设计让逻辑复用和大型组件开发更加清晰，同时保持了对选项式 API（Options API）的向后兼容。Vue 3 的响应式系统基于 Proxy，性能大幅提升。配合 Vite 构建工具和 Nuxt 全栈框架，Vue 生态在开发体验上极具竞争力。本技能同时涵盖 Vue 生态中的核心框架和工具。

---

## 核心知识

### 1. Vue 3 基础
- **响应式系统**：ref、reactive、computed、watch/watchEffect、Proxy 原理
- **组合式 API**：setup 语法糖、生命周期钩子、provide/inject
- **模板语法**：插值、指令（v-bind/v-on/v-model/v-if/v-for/v-show/v-slot）
- **组件系统**：Props/Emits、Slots（默认/具名/作用域）、异步组件、Suspense
- **生命周期**：onMounted/onUpdated/onUnmounted/onBeforeUnmount 等
- **选项式 API**（了解）：data/methods/computed/watch/mounted

### 2. Vue 3 进阶
- **Teleport**：将组件渲染到 DOM 其他位置（模态框、提示）
- **Fragments**：多根节点组件
- **Emits 声明**：类型安全的组件事件
- **全局属性/方法**：app.config.globalProperties
- **自定义指令**：v-directive 生命周期钩子
- **插件开发**：app.use() 模式
- **渲染函数与 JSX**：h() 函数、渲染插槽

### 3. 状态管理
- **Pinia**（Vue 官方推荐）：
  - Store 定义：defineStore、State/Getters/Actions
  - 组合式 Store（Setup Stores）
  - 插件系统、持久化、devtools 支持
  - 与 Vue Router 结合：导航守卫中访问 Store
- **Vuex 4**（了解历史，新项目不推荐）

### 4. 路由（Vue Router 4）
- 路由配置：path、component、children、redirect、alias
- 导航守卫：全局/路由独享/组件内
- 路由元信息（meta）：权限控制、面包屑、页面标题
- 动态路由与路由参数
- 滚动行为控制
- 组合式 API 中使用：useRoute、useRouter
- 历史模式：Hash vs History（HTML5）

### 5. 工具链与生态
- **Vite**：极速 HMR、ESM 原生、Rollup 构建
  - 配置：vite.config.ts、插件开发
  - 环境变量：import.meta.env
  - SSR 与 SSG 支持
- **Vue CLI**（已过渡到 Vite，了解历史）
- **TypeScript 集成**：defineProps/defineEmits 类型安全、泛型组件
- **测试**：Vitest（单元）、Vue Test Utils、Playwright（E2E）
- **代码质量**：ESLint（eslint-plugin-vue）、Prettier

### 6. 服务端渲染与全栈
- **Nuxt 3**：Vue 3 全栈框架
  - 文件系统路由、自动导入（Auto Imports）
  - SSR/SSG/SPA/ISR 渲染模式
  - Server API Routes（类似 Next.js API Routes）
  - Nuxt Modules 生态：@nuxt/content、@nuxt/image、@nuxt/auth
  - Nitro 引擎：跨平台服务端（Node/Deno/Workers）
- **Quasar**：Material Design + 跨平台（Web/Electron/Mobile）
- **Vuetify 3**：Material Design 组件库（Vue 3 适配）
- **Element Plus / Ant Design Vue**：企业级组件库

### 7. Vue 生态组件库
- **Element Plus**：饿了么出品，企业后台首选
- **Ant Design Vue**：Ant Design 的 Vue 实现
- **Vuetify 3**：Material Design，跨平台支持好
- **PrimeVue**：丰富主题、国际化支持好
- **Naive UI**：字节跳动出品，TypeScript 友好
- **Quasar**：全套解决方案（UI + SSR + 跨平台）

### 8. Vue 动画与过渡
- **Transition**：单元素/组件过渡（CSS 类：v-enter-from/v-enter-active/v-enter-to）
- **TransitionGroup**：列表过渡（key 驱动）
- **JS 钩子**：beforeEnter/enter/afterEnter 等
- **第三方集成**：GSAP + Vue、Anime.js
- **KeepAlive**：组件缓存与生命周期（activated/deactivated）

---

## 热门工具/框架

| 工具 | 用途 |
|------|------|
| **Vue 3** | 核心框架 |
| **Nuxt 3** | 全栈 SSR/SSG 框架 |
| **Pinia** | 状态管理 |
| **Vue Router 4** | 客户端路由 |
| **Vite** | 构建工具 |
| **Vitest** | 测试框架 |
| **Element Plus** | 企业组件库 |
| **Vuetify 3** | Material Design 组件库 |
| **Naive UI** | 字节跳动组件库 |
| **Quasar** | 跨平台框架 |
| **VueUse** | 组合式函数库 |
| **Headless UI / Radix Vue** | 无样式可访问组件基元 |

---

## 学习路径

### 初级（2 周）
1. Vue 3 基础：模板语法、指令、组件 Props/Emits
2. 组合式 API：ref/reactive/computed/watch/setup
3. Vue Router 4：路由配置、导航、参数传递
4. Pinia：Store 定义、State/Getter/Action
5. Vite 项目搭建与配置

### 中级（3-4 周）
1. 组合式 API 深入：生命周期、provide/inject、自定义 Composables
2. 组件设计模式：高阶组件、Renderless Components、插槽模式
3. TypeScript 集成：类型安全 Props/Emits、泛型组件
4. 动画与过渡系统
5. VueUse 常用组合式函数
6. 单元测试：Vue Test Utils + Vitest

### 高级（持续）
1. Nuxt 3 全栈开发：SSR/SSG、API Routes、Modules
2. 自定义 Composables 库开发
3. Vite 插件开发与构建优化
4. 性能优化：虚拟列表、懒加载、代码分割、Tree Shaking
5. 微前端：Module Federation / qiankun + Vue
6. Vue 3 源码阅读：响应式系统、编译器、虚拟 DOM

---

## 实践项目

1. **后台管理系统**：Element Plus + Pinia + Vue Router + 权限路由
2. **内容型博客**：Nuxt 3 + @nuxt/content + SSG + 暗色模式
3. **实时协作白板**：WebSocket + Canvas + 多人光标同步
4. **电商前台**：商品列表 → 详情 → 购物车 → 结算（完整链路）
5. **组件库开发**：基于 Headless UI 封装一套设计系统组件

---

## Vue vs React vs Svelte 选择

| 维度 | Vue 3 | React | Svelte |
|------|-------|-------|--------|
| **学习曲线** | 平缓 | 中等 | 平缓 |
| **模板语法** | 模板（HTML-like） | JSX/TSX | 模板（HTML-like） |
| **响应式** | 自动（Proxy） | 手动（useState/useEffect） | 编译期自动 |
| **生态成熟度** | 高（中国强） | 极高（全球最强） | 中等 |
| **企业后台** | Element Plus 生态强 | Ant Design / MUI | 相对弱 |
| **全栈框架** | Nuxt 3 | Next.js | SvelteKit |
| **包大小** | 中等 | 较大 | 最小（编译期优化） |
| **TypeScript** | 良好 | 极佳 | 良好 |
| **AI 辅助编码** | 良好 | 极佳（JSX 训练数据多） | 中等 |

---

## 关键趋势

- **组合式 API 成为主流**：Options API 逐渐减少，Vue 3.4+ 性能持续优化
- **Nuxt 3 全栈化**：Nitro 引擎让 Vue 服务端能力媲美 Next.js
- **Vapor Mode**：Vue 实验性编译模式（类似 Svelte，无虚拟 DOM）
- **VueUse 生态繁荣**：组合式函数库极大提升开发效率
- **无样式组件基元**：Headless UI / Radix Vue 模式流行
- **AI 辅助 Vue 开发**：Volar（VS Code 插件）+ AI 代码生成
- **跨平台方案**：Quasar + Capacitor/Cordova 做移动端

---

## 参考资源

- [Vue 3 官方文档](https://vuejs.org/guide/introduction.html)
- [Nuxt 3 文档](https://nuxt.com/docs/getting-started/introduction)
- [Pinia 文档](https://pinia.vuejs.org/)
- [Vue Router 文档](https://router.vuejs.org/)
- [VueUse 文档](https://vueuse.org/)
- [Vite 文档](https://vitejs.dev/guide/)
