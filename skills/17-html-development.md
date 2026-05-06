# 技能 17：HTML 开发

> Web 的骨架，语义化与可访问性是 2026 年的核心追求。

---

## 技能概述

HTML 在 2026 年依然是 Web 开发的基石。随着 AI 生成代码的普及，写出语义正确、可访问、SEO 友好的 HTML 比过去更加重要。HTML5 持续发展，引入了更多语义元素、表单控件和 Web 组件相关能力。现代 HTML 不仅是页面结构，还包括 PWA（渐进式 Web 应用）所需的 manifest、service worker 关联，以及与 Web Components 的深度结合。

---

## 核心知识

### 1. 语义化 HTML
- **结构元素**：header、nav、main、article、section、aside、footer
- **文本语义**：h1-h6、p、blockquote、pre、code、time、mark、abbr
- **列表**：ul/ol/li、dl/dt/dd、有序列表嵌套
- **链接与导航**：a、link、nav、锚点、书签链接
- **媒体**：img、figure/figcaption、picture、video、audio、track
- **表格**：table、thead/tbody/tfoot、th（scope）、caption
- **避免**：div 滥用、无语义的 span 堆砌

### 2. 表单与交互
- **输入类型**：text/email/tel/url/number/date/datetime-local/range/color/file
- **验证属性**：required、min/max、pattern、minlength/maxlength
- **新控件**：datalist、meter、progress、output
- **表单组织**：fieldset/legend、label 关联（for/id）
- **文件上传**：accept、multiple、drag & drop API
- **表单提交**：formaction/formmethod、formnovalidate

### 3. 元数据与文档结构
- **head 元素**：title、meta charset/viewport/description/keywords
- **Open Graph**：og:title/og:description/og:image（社交媒体分享）
- **Twitter Cards**：twitter:card/twitter:title/twitter:image
- **SEO 元数据**：canonical、robots、sitemap 关联
- **图标**：favicon、apple-touch-icon、manifest.json
- **预加载**：preload、prefetch、preconnect、dns-prefetch
- **主题色**：meta name="theme-color"

### 4. Web Components 与自定义元素
- **自定义元素**：Custom Elements API（extends HTMLElement）
- **Shadow DOM**：封装样式与结构、open/closed mode
- **HTML Templates**：template 元素 + slot 插槽
- **生命周期**：connectedCallback、disconnectedCallback、attributeChangedCallback
- **框架集成**：Lit、Stencil、与 React/Vue 共存

### 5. 可访问性（a11y）
- **ARIA 属性**：role、aria-label、aria-hidden、aria-expanded、aria-live
- **键盘导航**：tabindex、focus 管理、skip links
- **屏幕阅读器**：语义标签替代 div、alt 文本、表单 label
- **颜色对比**：WCAG 2.1 AA/AAA 标准
- **焦点可见**：:focus-visible、focus 指示器
- ** landmarks**：main、nav、aside 的角色语义

### 6. PWA 与现代 Web
- **Web App Manifest**：name、short_name、icons、start_url、display
- **Service Worker**：注册、缓存策略、离线页面
- **Add to Home Screen**：安装提示、独立显示模式
- **推送通知**：Push API + Notifications API
- **后台同步**：Background Sync API

---

## 热门工具/框架

| 工具 | 用途 |
|------|------|
| **Lit** | 轻量 Web Components 框架 |
| **Stencil** | 编译型 Web Components |
| **HTMX** | 超媒体驱动交互（HTML 属性扩展） |
| **Alpine.js** | 轻量声明式 JS（HTML 属性） |
| **Astro** | 内容型网站（零 JS 默认） |
| **Eleventy** | 静态站点生成器 |
| **WAI-ARIA 规范** | 可访问性标准 |

---

## 学习路径

### 初级（1 周）
1. HTML5 语义化标签全面使用
2. 表单控件与基础验证
3. 图片与多媒体元素
4. 基本 meta 标签与 SEO

### 中级（1-2 周）
1. 可访问性：ARIA 属性、键盘导航、屏幕阅读器测试
2. Web Components：自定义元素 + Shadow DOM
3. PWA 基础：Manifest + Service Worker
4. 结构化数据：JSON-LD / Schema.org 标记

### 高级（持续）
1. 复杂 Web Components 架构（Lit/Stencil）
2. 性能优化：资源预加载、关键渲染路径
3. 多语言国际化：lang 属性、dir 属性、RTL 布局
4. 可访问性审计：axe-core、Lighthouse a11y 评分

---

## 实践项目

1. **语义化博客模板**：article、time、figure/figcaption、blockquote
2. **可访问表单**：完整 label、ARIA 属性、键盘导航、错误提示
3. **PWA 离线应用**：Manifest + Service Worker + 缓存策略
4. **自定义组件库**：Web Components + Shadow DOM + Slot
5. **SEO 优化落地页**：结构化数据、Open Graph、预加载优化

---

## 关键趋势

- **语义化优先**：AI 爬虫和搜索引擎更依赖语义标签
- **可访问性法规化**：欧盟《无障碍法案》（EAA）2025 年生效，全球跟进
- **HTMX 崛起**：HTML 属性驱动交互，减少 JS 复杂度
- **Web Components 复兴**：与框架无关的组件化方案
- **零 JS 内容网站**：Astro、Eleventy 等框架默认无 JS
- **AI 生成 HTML 质量**：语义正确性成为区分优劣的关键

---

## 参考资源

- [MDN HTML 文档](https://developer.mozilla.org/zh-CN/docs/Web/HTML)
- [HTML Living Standard](https://html.spec.whatwg.org/)
- [Web Accessibility Initiative](https://www.w3.org/WAI/)
- [A11y Project](https://www.a11yproject.com/)
- [Schema.org](https://schema.org/) - 结构化数据词汇表
