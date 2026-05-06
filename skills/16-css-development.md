# 技能 16：CSS 开发

> 从样式到设计系统，Web 视觉呈现的核心技术。

---

## 技能概述

CSS 在 2026 年已从单纯的样式描述语言发展为强大的布局和设计系统工具。现代 CSS 支持容器查询、级联层、嵌套规则、自定义属性（变量）和高级动画，配合 Tailwind CSS 等 utility-first 框架，开发者可以更高效地构建一致、响应式的用户界面。CSS 与 AI 辅助编码的结合也日益紧密——Tailwind 的原子类语法让 AI 生成代码的准确率显著提高。

---

## 核心知识

### 1. 基础与选择器
- 选择器：元素、类、ID、属性、伪类（:hover/:focus/:nth-child）、伪元素（::before/::after）
- 优先级与层叠：特异性计算、!important、级联层（@layer，CSS Cascade Layers）
- 继承：哪些属性继承、inherit/initial/unset/revert
- 盒模型：content-box vs border-box、margin、padding、border
- 颜色：hex、rgb/rgba、hsl/hsla、oklch、color-mix()

### 2. 布局系统
- **Flexbox**：主轴/交叉轴、justify-content、align-items、flex-grow/shrink/basis、gap
- **Grid**：grid-template-columns/rows、fr 单位、minmax()、auto-fit/auto-fill、区域（grid-area）
- **定位**：static/relative/absolute/fixed/sticky、z-index 与堆叠上下文
- **多列布局**：columns、column-gap、column-rule
- **子网格**：subgrid（CSS Grid Level 2）
- **容器查询**：@container（响应式基于容器尺寸而非视口）
- **逻辑属性**：margin-inline/block、border-start/end（国际化布局）

### 3. 响应式设计
- 媒体查询：@media、断点设计、mobile-first vs desktop-first
- 视口单位：vw/vh/vmin/vmax、dvw/dvh（动态视口）
- clamp()、min()、max() 函数
- 容器查询替代部分媒体查询
- 图片响应式：srcset、sizes、picture 元素

### 4. 现代 CSS 特性
- **CSS 变量**：--var、var()、局部与全局作用域
- **CSS 嵌套**：原生嵌套规则（Nesting Module）
- **CSS 自定义属性**：calc() + 变量实现动态主题
- **CSS 函数**：calc()、clamp()、min()、max()、env()、attr()
- **CSS Houdini**：Paint API、Layout API、Properties & Values API
- **@property**：注册自定义属性类型、实现动画插值

### 5. 动画与交互
- **过渡（Transition）**：property/duration/timing-function/delay
- **关键帧动画（@keyframes）**：from/to、百分比、animation 简写
- **性能优化**：transform 和 opacity 触发 GPU 加速、will-change
- **滚动驱动动画**：scroll()、view()、animation-timeline
- **CSS 视图过渡**：View Transitions API（页面切换动画）

### 6. 设计系统与工具
- **Tailwind CSS**：utility-first、JIT 模式、暗色模式、响应式前缀
- **CSS 模块**：局部作用域 CSS、防止命名冲突
- **CSS-in-JS**：Styled-components、Emotion（了解趋势，但 Tailwind 更主流）
- **PostCSS**：autoprefixer、cssnano、自定义插件
- **Sass / Less**：嵌套、变量、Mixin、继承（逐渐被原生 CSS 替代）
- **设计令牌**：颜色、间距、字体、圆角等变量化系统
- **暗色模式**：prefers-color-scheme、CSS 变量切换

---

## 热门工具/框架

| 工具 | 用途 |
|------|------|
| **Tailwind CSS** | utility-first CSS 框架（2026 主流） |
| **PostCSS** | CSS 后处理与转换 |
| **Sass** | CSS 预处理器 |
| **CSS Modules** | 作用域 CSS |
| **Styled-components** | CSS-in-JS（React） |
| **UnoCSS** | 即时原子 CSS 引擎 |
| **Open Props** | CSS 自定义属性库 |
| **Panda CSS** | CSS-in-JS 替代方案（静态提取） |

---

## 学习路径

### 初级（1-2 周）
1. 选择器优先级与盒模型
2. Flexbox 布局（居中、导航、卡片列表）
3. 基础响应式：媒体查询 + 视口单位
4. CSS 变量与简单动画

### 中级（2-3 周）
1. CSS Grid 复杂布局（仪表盘、相册、杂志布局）
2. 容器查询实战
3. CSS 嵌套与级联层
4. Tailwind CSS 使用与设计系统构建
5. 过渡与关键帧动画

### 高级（持续）
1. CSS Houdini 自定义绘制与布局
2. 滚动驱动动画与视图过渡
3. 性能优化：渲染流水线、关键渲染路径
4. 复杂设计系统：主题切换、多品牌适配
5. CSS 架构：BEM、ITCSS、CUBE CSS

---

## 实践项目

1. **响应式落地页**：Flexbox + Grid + 媒体查询 + 暗色模式
2. **仪表盘布局**：Grid 区域 + 可拖拽卡片 + 响应式侧边栏
3. **动画作品集**：CSS 关键帧动画 + 滚动驱动动画
4. **设计系统**：Tailwind 配置 + 自定义组件 + 主题变量
5. **CSS 艺术**：纯 CSS 绘制复杂图形（Clip-path、Gradient、Mask）

---

## 关键趋势

- **Tailwind CSS 统治地位**：utility-first 成为工程化项目首选
- **原生 CSS 越来越强大**：嵌套、容器查询、级联层减少预处理器需求
- **CSS-in-JS 退潮**：运行时开销问题，静态提取方案（Panda）兴起
- **设计令牌标准化**：Design Tokens 格式（W3C 社区组）
- **AI 生成 Tailwind**：原子类语法非常适合 AI 代码生成
- **视图过渡 API**：原生页面切换动画，减少 JS 动画库依赖

---

## 参考资源

- [MDN CSS 文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [Tailwind CSS 文档](https://tailwindcss.com/docs)
- [Modern CSS Solutions](https://moderncss.dev/)
- [Can I use](https://caniuse.com/) - 浏览器兼容性查询
