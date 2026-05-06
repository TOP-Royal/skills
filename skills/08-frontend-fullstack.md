# 技能 08：前端全栈开发

> 用户界面的工程化与 AI 辅助编程结合最紧密的方向。

---

## 技能概述

前端全栈开发是 2026 年工程岗位的基础盘。TypeScript 已成为前端与全栈开发的事实标准，React + Next.js 生态持续主导市场。AI 编程助手（Copilot、Cursor、Windsurf）与前端开发结合最紧密，代码生成和 UI 组件库（如 shadcn/ui）的「复制粘贴」模式正在重塑前端工作流。

---

## 核心知识领域

### 1. TypeScript 精通
- **类型系统**：泛型、条件类型、映射类型、模板字面量类型
- **高级模式**：类型守卫、 branded types、infer 推导
- **类型安全**：strict mode、noImplicitAny、严格 null 检查
- **monorepo 类型共享**：Workspace 配置、共享类型包
- **类型体操**：编译期计算、类型级编程（适度掌握）

### 2. React 生态
- **Hooks 深入**：useEffect 闭包陷阱、useMemo/useCallback 优化、自定义 Hooks
- **并发特性**：Suspense、useTransition、useDeferredValue、React Server Components
- **状态管理**：Zustand、Jotai、TanStack Query（服务器状态）
- **路由**：React Router / TanStack Router / Next.js App Router
- **表单**：React Hook Form + Zod 验证
- **组件设计**：Compound Components、Render Props、HOC（了解历史）

### 3. Next.js 全栈
- **App Router**：RSC（React Server Components）、Server Actions
- **数据获取**：fetch 缓存策略、Revalidation、ISR/SSG/SSR
- **API Routes**：Route Handlers、Middleware
- **性能优化**：Image/Font 优化、Streaming、Partial Prerendering
- **部署**：Vercel / Docker / Node.js standalone

### 4. 样式与 UI 系统
- **Tailwind CSS**：utility-first、JIT 模式、自定义设计系统
- **shadcn/ui**：无依赖组件、可复制粘贴、Radix UI 基础
- **CSS-in-JS 替代**：Tailwind > Styled-components（性能考量）
- **动画**：Framer Motion、GSAP、CSS transitions
- **响应式设计**：Mobile-first、Container Queries

### 5. 构建与工具链
- **Vite**：极速 HMR、ESM 原生、Rollup 构建
- **Turborepo / Nx**：Monorepo 构建优化
- **SWC / esbuild**：转译与打包提速
- **测试**：Vitest、Playwright（E2E）、React Testing Library
- **代码质量**：ESLint、Prettier、TypeScript strict

---

## 热门工具与框架

| 工具 | 用途 | 热度 |
|------|------|------|
| **React / Next.js** | UI 框架 / 全栈框架 | ⭐⭐⭐⭐⭐ |
| **TypeScript** | 类型安全 JS | ⭐⭐⭐⭐⭐ |
| **Tailwind CSS** | Utility-first CSS | ⭐⭐⭐⭐⭐ |
| **shadcn/ui** | 可复制组件库 | ⭐⭐⭐⭐⭐ |
| **Vite** | 构建工具 | ⭐⭐⭐⭐⭐ |
| **TanStack Query** | 服务器状态管理 | ⭐⭐⭐⭐⭐ |
| **Zustand** | 客户端状态管理 | ⭐⭐⭐⭐ |
| **Astro** | 内容型网站 | ⭐⭐⭐⭐ |
| **Vue / Nuxt** | 渐进式框架 | ⭐⭐⭐⭐ |

---

## GitHub 热门仓库

- [facebook/react](https://github.com/facebook/react) - UI 库
- [vercel/next.js](https://github.com/vercel/next.js) - React 全栈框架
- [microsoft/typescript](https://github.com/microsoft/typescript) - 类型系统
- [tailwindlabs/tailwindcss](https://github.com/tailwindlabs/tailwindcss) - CSS 框架
- [shadcn-ui/ui](https://github.com/shadcn-ui/ui) - 可复制组件
- [vitejs/vite](https://github.com/vitejs/vite) - 下一代构建工具
- [TanStack/query](https://github.com/TanStack/query) - 异步状态管理
- [pmndrs/zustand](https://github.com/pmndrs/zustand) - 轻量状态管理
- [withastro/astro](https://github.com/withastro/astro) - 内容型网站框架

---

## 学习路径

### 初级阶段（2-3 周）
1. TypeScript 基础：类型、接口、泛型
2. React 基础：Hooks、组件、Props/State
3. Tailwind CSS：Utility classes、响应式、暗色模式
4. 使用 Vite 搭建项目
5. shadcn/ui 组件库使用

### 中级阶段（3-5 周）
1. Next.js App Router：RSC、Server Actions、数据获取
2. 状态管理：TanStack Query + Zustand 组合
3. 表单处理：React Hook Form + Zod 验证
4. 路由与导航：动态路由、拦截路由、平行路由
5. 测试：Vitest + React Testing Library + Playwright

### 高级阶段（持续）
1. 性能优化：Core Web Vitals、Streaming、代码分割
2. 服务端架构：Edge Runtime、Serverless Functions
3. AI 集成：Vercel AI SDK、流式响应、生成式 UI
4. 微前端：Module Federation、独立部署
5. Monorepo：Turborepo + 共享包 + 类型安全

---

## 实践项目建议

1. **SaaS 仪表板**：Next.js + shadcn/ui + TanStack Query + 后端 API
2. **AI 聊天界面**：Vercel AI SDK + 流式消息 + 历史记录
3. **内容管理系统**：Astro / Next.js + MDX + 搜索 + 分类
4. **实时协作白板**：WebSocket + Canvas + 多人光标
5. **电商 storefront**：产品列表 → 详情 → 购物车 → 结算（全链路）

---

## 前端 + AI 结合模式

```tsx
// 流式 AI 聊天组件（Vercel AI SDK）
import { useChat } from 'ai/react'

export default function Chat() {
  const { messages, input, handleInputChange, handleSubmit } = useChat()

  return (
    <div>
      {messages.map(m => (
        <div key={m.id}>
          {m.role === 'user' ? 'User: ' : 'AI: '}
          {m.content}
        </div>
      ))}
      <form onSubmit={handleSubmit}>
        <input value={input} onChange={handleInputChange} />
        <button type="submit">Send</button>
      </form>
    </div>
  )
}
```

---

## 关键趋势

- **AI 辅助编码重塑前端**：Cursor / Windsurf / Copilot 大幅提升效率
- **RSC 改变数据获取模式**：服务端组件减少客户端 JS
- **shadcn/ui 模式流行**：无 NPM 依赖、可复制、可定制
- **Vite 替代 Webpack**：速度成为开发体验核心
- **TypeScript 全覆盖**：任何新项目都不应跳过类型安全
- **边缘渲染普及**：Vercel Edge、Cloudflare Workers 上的 SSR
- **Server Actions 简化 API**：减少显式 API 层，直接调用服务端函数

---

## 参考资源

- [Next.js 官方文档](https://nextjs.org/docs)
- [React 官方文档](https://react.dev/)
- [TypeScript 文档](https://www.typescriptlang.org/docs/)
- [Tailwind CSS 文档](https://tailwindcss.com/docs)
- [shadcn/ui 文档](https://ui.shadcn.com/)
- [Vercel AI SDK 文档](https://sdk.vercel.ai/docs)
- [Web.dev](https://web.dev/) - Google 性能与最佳实践
