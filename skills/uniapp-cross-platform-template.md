# UniApp 跨端开发模板（uniapp-cross-platform）

> 目标：一套代码编译到微信小程序/支付宝小程序/抖音小程序/QQ小程序/H5/App，实现真正的跨端一次成型。

---

## 固定输出物（AI 必须产出）

- 跨端目标平台清单（微信/支付宝/抖音/QQ/H5/App，明确首发和次要平台）
- 条件编译与平台差异处理方案（#ifdef / #ifndef / 平台专属目录）
- 统一组件与API封装层（抹平平台差异，提供一致接口）
- 原生插件与扩展方案（云函数/原生模块/第三方SDK集成）
- 构建与发布流水线（各平台打包/上传/审核/发布自动化）
- 性能与包体优化（主包控制/分包/资源压缩/Tree Shaking）
- 跨端测试矩阵（平台×设备×系统版本×场景）

## 必须/禁止规则

- 必须：明确首发平台和次要平台，禁止"全平台同时完美上线"的不切实际预期
- 必须：所有平台差异（API/组件/样式/支付/登录/分享）必须通过条件编译或封装层处理，禁止硬编码平台判断散落各处
- 必须：各平台支付/登录/分享走对应平台官方能力（条件编译调用不同SDK）
- 必须：主包体积严格控制（微信小程序主包 < 2MB），非必要资源延迟加载或放CDN
- 禁止：在业务代码中直接写 `if (platform === 'wx')` 等硬编码平台判断（应统一在封装层）
- 禁止：用 H5 的 DOM/BOM API 写页面（UniApp 编译到小程序时不支持）
- 禁止：未经测试就直接全平台发布（必须分平台灰度）
- 禁止：忽略各平台审核差异（同一功能在不同平台可能审核标准不同）

---

## 1. 跨端目标与策略

### 1.1 平台差异矩阵

| 能力 | 微信小程序 | 支付宝小程序 | 抖音小程序 | QQ小程序 | H5 | App |
|------|-----------|-------------|-----------|---------|----|-----|
| 登录 | wx.login | my.getAuthCode | tt.login | qq.login | 自有登录/微信H5授权 | 微信/QQ/手机号一键登录 |
| 支付 | wx.requestPayment | my.tradePay | tt.pay | qq.requestPayment | 微信支付H5/支付宝H5 | 微信/支付宝/Apple Pay |
| 分享 | wx.shareAppMessage | my.showSharePanel | tt.shareAppMessage | qq.shareToQQMiniProgram | 浏览器分享/复制链接 | 原生分享 |
| 扫码 | wx.scanCode | my.scan | tt.scanCode | qq.scanCode | 浏览器限制 | 原生扫码 |
| 推送 | 订阅消息 | 订阅消息 | 订阅消息 | 订阅消息 | Web Push | 原生推送 |

### 1.2 首发策略

- 首发 1-2 个平台，验证商业模式后再扩展
- 建议首发：微信小程序（用户基数大）或 目标用户最集中的平台
- 次要平台逐步适配：注意各平台审核周期不同

---

## 2. 技术架构

### 2.1 项目结构

```
src/
  components/          # 通用组件
  pages/               # 页面
  platforms/           # 平台专属代码
    wx/                # 微信小程序专属
    alipay/            # 支付宝小程序专属
    douyin/            # 抖音小程序专属
    qq/                # QQ小程序专属
    h5/                # H5专属
    app/               # App专属
  utils/
    platform.js        # 平台判断封装
    request.js         # 统一请求封装
    pay.js             # 统一支付封装
    login.js           # 统一登录封装
    share.js           # 统一分享封装
  App.vue
  main.js
  manifest.json        # 应用配置
  pages.json           # 页面路由
```

### 2.2 条件编译

- 模板中：`<view v-if="platform === 'wx'"></view>` 或 `#ifdef MP-WEIXIN`
- JS 中：`// #ifdef MP-WEIXIN` / `// #endif`
- CSS 中：`/* #ifdef MP-WEIXIN */` / `/* #endif */`
- 平台标识：
  - `MP-WEIXIN`：微信小程序
  - `MP-ALIPAY`：支付宝小程序
  - `MP-TOUTIAO`：抖音小程序
  - `MP-QQ`：QQ小程序
  - `H5`：H5
  - `APP`：App

### 2.3 统一封装层（核心）

```javascript
// utils/platform.js
export function getPlatform() {
  // #ifdef MP-WEIXIN
  return 'wx';
  // #endif
  // #ifdef MP-ALIPAY
  return 'alipay';
  // #endif
  // ...其他平台
}

// utils/pay.js
export function requestPayment(orderInfo) {
  // #ifdef MP-WEIXIN
  return uni.requestPayment({ provider: 'wxpay', ...orderInfo });
  // #endif
  // #ifdef MP-ALIPAY
  return uni.requestPayment({ provider: 'alipay', ...orderInfo });
  // #endif
}
```

---

## 3. 核心能力跨端封装

### 3.1 登录

- 统一接口：`login()`
- 内部条件编译调用各平台 `uni.login()`
- 服务端统一处理：接收 code + platform 标识 → 分发到不同平台的 auth 服务

### 3.2 支付

- 统一接口：`pay(orderInfo)`
- 内部条件编译调用 `uni.requestPayment({ provider: 'wxpay'|'alipay'|'toutiao' })`
- 服务端需支持多平台支付配置（商户号/AppID/密钥）

### 3.3 分享

- 统一接口：`share(shareInfo)`
- 各平台分享内容格式不同（标题/图片/路径），在封装层做适配
- App 端可调用原生分享（微信/QQ/系统分享面板）

### 3.4 页面跳转

- `uni.navigateTo` / `uni.redirectTo` / `uni.reLaunch`（跨平台通用）
- 注意：小程序有页面栈限制（10层），H5/App 无限制

---

## 4. 原生能力与扩展

### 4.1 原生插件

- UniApp 插件市场：搜索平台适配插件
- 自定义原生插件：Android（AAR）/ iOS（Framework）
- 云函数：UniCloud（服务端逻辑，跨平台通用）

### 4.2 第三方SDK

- 统计：友盟+ / 神策 / GrowingIO（条件编译初始化）
- 地图：高德（全平台支持较好）
- 推送：个推 / 极光（App 端）/ 各平台订阅消息（小程序端）

---

## 5. 构建与发布

### 5.1 打包配置

- `manifest.json`：各平台 AppID/权限/功能开关
- `vue.config.js`：Webpack 配置优化
- 分包配置：`pages.json` 中 `subPackages`

### 5.2 自动化发布

- HBuilderX 云打包 / CLI 打包
- CI/CD：
  - 代码提交 → 自动构建各平台 → 上传代码到各平台开发者后台
  - 微信小程序：miniprogram-ci
  - 支付宝：小程序 IDE CLI
  - 抖音：字节小程序 CLI
  - App：云打包 / 本地打包

### 5.3 灰度策略

- 分平台灰度：先发布微信小程序 → 稳定后再发支付宝/抖音
- 分版本灰度：同一平台内，先 10% 用户 → 50% → 全量

---

## 6. 性能与包体优化

- 主包控制：
  - 微信小程序主包 < 2MB（UniApp 编译后可能偏大，需优化）
  - 使用分包：`subPackages`
  - 图片/字体放 CDN，本地只留必要资源
- Tree Shaking：
  - 按需引入组件库（如 uView / ThorUI）
  - 移除未使用的页面和组件
- 启动优化：
  - 首页预加载 `preloadRule`
  - 减少首页渲染节点数
  - 骨架屏
- 运行时优化：
  - `v-if` vs `v-show` 合理使用
  - 长列表使用 `uni-list` 虚拟滚动
  - 图片懒加载

---

## 7. 跨端测试矩阵

| 平台 | 设备 | 系统 | 必测场景 |
|------|------|------|---------|
| 微信小程序 | iPhone / Android | iOS / Android | 登录/支付/分享/下拉刷新 |
| 支付宝小程序 | iPhone / Android | iOS / Android | 芝麻信用/会员/卡券 |
| 抖音小程序 | iPhone / Android | iOS / Android | 视频播放/挂载/直播 |
| QQ小程序 | iPhone / Android | iOS / Android | 群能力/游戏/分享 |
| H5 | Chrome / Safari / 微信内置浏览器 | - | 响应式/支付/分享 |
| App | iPhone / Android | iOS / Android | 原生推送/扫码/定位 |

- 自动化测试：
  - 单元测试：Jest + Vue Test Utils
  - E2E：Appium（App）/ miniprogram-automator（小程序）

---

## 8. 验收清单（DoD）

- [ ] 目标平台清单明确（首发+次要），各平台 AppID 已申请
- [ ] 所有平台差异通过条件编译或统一封装层处理，无散落硬编码
- [ ] 登录/支付/分享/扫码等核心能力已跨端封装并全平台测试通过
- [ ] 主包体积达标（微信小程序 < 2MB），非必要资源已放CDN或分包
- [ ] 性能达标：首屏 < 1.5s、列表滚动流畅、图片加载无白屏
- [ ] 跨端测试矩阵已执行，各平台核心场景无异常
- [ ] 各平台审核材料已准备（营业执照/行业资质/隐私政策，按平台要求）
- [ ] 灰度发布策略明确，禁止未经测试直接全平台全量发布
