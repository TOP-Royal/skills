# 鸿蒙 HarmonyOS 开发模板（harmonyos）

> 目标：鸿蒙应用从需求到华为应用市场上架一次成型，避免 NEXT 适配遗漏、多端差异、审核合规翻车。

---

## 固定输出物（AI 必须产出）

- 技术选型清单（ArkTS/ArkUI/Stage模型/API级别/设备类型/是否兼容Android）
- 多端适配策略（手机/平板/车机/手表/智慧屏/折叠屏：布局/交互/功能差异）
- 能力清单与权限方案（HarmonyOS 特有的 Permission/ACL/数据级别/分布式能力）
- 数据与分布式设计（AppStorage/LocalStorage/首选项/关系数据库/分布式数据/云同步）
- 发布配置（签名/HAP/HSP/AGC/元数据/隐私标签/上架材料）
- 性能基线（启动/包体/内存/帧率/功耗）与测试计划（真机/模拟器/自动化）

## 必须/禁止规则

- 必须：明确 HarmonyOS API 级别（9/11/12）与目标设备类型，NEXT 纯血鸿蒙与兼容版差异文档化
- 必须：所有权限（常规/ACL/受限）在 module.json5 声明，敏感权限有用户授权时机和拒绝引导
- 必须：数据分级标签（dataGroupId / appDistributionType / 数据级别）正确填写，隐私合规不踩红线
- 必须：多端适配至少覆盖 2 种设备类型（如手机+平板），或明确声明仅支持某类设备
- 禁止：使用 Android 私有 API 或反射调用系统服务（NEXT 上直接不可用）
- 禁止：主线程阻塞（网络/IO/复杂计算），ArkTS 必须用异步 / Promise / async-await / Worker
- 禁止：硬编码密钥/Token 进代码或资源文件，必须加密或云端下发
- 禁止：忽略流转/跨设备协同需求（鸿蒙核心差异化能力，有场景时必须设计）

---

## 1. 项目基础

- 开发语言：ArkTS（TypeScript 超集，鸿蒙主推）/ C++（高性能/图形/游戏）
- UI 框架：ArkUI（声明式，类似 SwiftUI/Compose）
- API 级别：API 9 / API 11 / API 12（NEXT 纯血）
- 目标设备：Phone / Tablet / Car / Wearable / TV / 2in1（可折叠）
- 应用模型：Stage 模型（当前主推）/ FA 模型（遗留，不推荐）
- 工程类型：Application（应用）/ Atomic Service（元服务，免安装）
- 包类型：HAP（HarmonyOS Ability Package）/ HSP（HarmonyOS Shared Package）
- 兼容策略：
  - HarmonyOS NEXT（纯血，无 Android 兼容层）
  - HarmonyOS 4.x（兼容 Android AOSP，需考虑双端代码复用）

---

## 2. 模块与导航架构

- 模块拆分：
  - entry（主模块）/ feature（特性模块）/ library（共享库）
  - 模块间通信：Ability 跳转 / UIAbility 实例管理 / EventHub
- 导航：
  - 页面路由：router.pushUrl / router.replaceUrl（API 9）/ Navigation 组件（API 11+）
  - 路由表集中管理（标准 URI：pages/xxx）
- 生命周期：
  - UIAbility：onCreate / onForeground / onBackground / onDestroy
  - Page：aboutToAppear / aboutToDisappear / onPageShow / onPageHide
  - 状态管理：@State / @Prop / @Link / @Provide/@Consume / @LocalStorageProp
- 服务：
  - ServiceExtensionAbility：后台服务
  - WorkSchedulerExtensionAbility：定时/条件任务

---

## 3. 权限与隐私合规

- module.json5 权限声明：
  - 常规权限：INTERNET / GET_NETWORK_INFO
  - 危险权限：CAMERA / READ_IMAGEVIDEO / LOCATION / MICROPHONE / BLUETOOTH
  - ACL（Access Control List）权限：READ_CONTACTS / WRITE_CONTACTS / 读取短信等（需华为审批）
- 数据分级标签：
  - module.json5：appDistributionType（app_gallery / enterprise / none）
  - dataGroupId（数据共享组，企业/同账号设备共享）
  - 数据级别：restricted / general / public
- 用户授权：
  - 弹窗时机：首次使用功能时触发
  - 拒绝引导：永久拒绝后提供设置页跳转（ability.want 跳转设置）
- 隐私合规：
  - 隐私声明弹窗（首次启动，不同意则退出或限制功能）
  - 个人信息保护法：收集最小必要原则，不收集 IMEI/Android ID 等不可重置标识
  - 广告标识符：OAID 使用需声明

---

## 4. 数据层设计

- 本地存储：
  - AppStorage：全局 UI 状态（应用级）
  - LocalStorage：页面级状态
  - 首选项（Preferences）：轻量键值对（类似 SharedPreferences）
  - 关系数据库（RDB）：SQLite 封装，支持 SQL
  - 对象关系映射（ORM）：AppDataPersistence / @ObjectLink
  - 文件存储：沙箱目录 / 公共目录（需授权）
- 网络层：
  - @ohos.net.http：原生 HTTP
  - 第三方库：axios 鸿蒙版 / 自研封装
  - 配置：超时/重试/证书绑定
- 缓存策略：
  - 内存缓存：AppStorage / LocalStorage / 自定义 LRU
  - 磁盘缓存：文件缓存 / RDB 缓存表
- 分布式数据：
  - DistributedData：同账号多设备数据同步（需配置 dataGroupId）
  - 云同步：华为云数据库（AGC Cloud DB）
- 离线：
  - 网络状态监听（netConnection）
  - 离线队列：请求入队 → 联网后自动重试

---

## 5. 多端适配

- 设备类型差异：

| 设备 | 屏幕特性 | 交互方式 | 适配策略 | 功能差异 |
|------|---------|---------|---------|---------|
| Phone | 小屏竖屏 | 触摸 | 响应式断点 | 基础功能 |
| Tablet | 大屏横竖 | 触摸+键盘 | 双 pane / 侧边栏 | 增强功能 |
| Car | 横屏固定 | 触摸+语音 | 大按钮 / 语音优先 | 驾驶模式限制 |
| Wearable | 极小圆/方屏 | 触摸+旋转 | 极简界面 | 核心功能 |
| TV | 大屏远距 | 遥控器 | 焦点导航 / 大字体 | 视频/控制为主 |
| 2in1 | 折叠/展开 | 触摸+键盘+笔 | 分屏 / 多窗口 | 桌面级功能 |

- 布局策略：
  - 响应式：GridRow/GridCol / BreakpointSystem
  - 自适应：百分比 / 拉伸 / 隐藏 / 均分
  - 资源限定词：language / region / resolution / device-type
- 交互差异：
  - 车机：语音交互（ASR/TTS）优先，减少手动输入
  - 手表：手势 / 表冠 / 语音，信息极简
  - TV：遥控器焦点 / 方向键 / 返回键处理

---

## 6. 分布式与流转能力

- 跨设备协同（鸿蒙核心差异）：
  - 流转（Continue）：应用在手机启动，无缝流转到平板/车机
  - 跨设备调用：StartAbilityByCall / 跨设备 ServiceExtension
  - 分布式软总线：发现 / 连接 / 传输（设备组网）
- 设计原则：
  - 有跨设备场景时必须在需求阶段明确流转设备类型和数据同步范围
  - 禁止：为流转而流转，无实际场景硬加分布式能力
- 数据同步：
  - DistributedData（同账号）/ 华为云（跨账号）
  - 冲突解决策略：Last-Write-Wins / 业务层合并

---

## 7. 关键功能开发

### 7.1 推送
- 华为 Push Kit：推送服务 / 通知扩展
- 推送配置：AGC 后台 / 证书 / Topic / 标签
- 抵达率：厂商通道 + 应用自启动权限（需引导用户开启）

### 7.2 支付
- HMS IAP（华为应用内支付）：虚拟商品
- 支付宝/微信支付：实物商品
- 服务端验证：订单查询 / 防掉单

### 7.3 地图与定位
- 华为 Map Kit / 定位服务
- 定位精度：GPS / 网络 / 混合
- 地理围栏：进入/退出/驻留

### 7.4 相机与媒体
- Camera Kit：拍照 / 录像 / 预览
- 媒体库：Picker（系统选择器，推荐）/ 自研相册（需授权）
- 音视频：AVPlayer（播放）/ MediaCodec（编解码）

---

## 8. 性能与体验

- 启动优化：
  - 冷启动 < 2s（中端机）
  - 延迟加载 / 异步初始化 / 预加载
- 包体优化：
  - HAP 包：裁剪无用资源 / 多设备分包（HAP 按设备类型拆分）
  - 图片：WebP / SVG / 分辨率限定词
- 内存优化：
  - 大图加载：采样 / 缓存 / 生命周期绑定
  - 状态管理：避免过度使用 @State 导致全局刷新
- 渲染性能：
  - ArkUI 布局优化：减少嵌套 / 使用 Column/Row 替代 Flex 过度嵌套
  - 列表：List + LazyForEach（虚拟滚动）
  - 帧率监控：使用 PerformanceMonitor
- 功耗优化：
  - 定位频率控制 / 后台任务约束 / 动画暂停

---

## 9. 测试与质量

- 单元测试：OHUnit / Jest-for-ArkTS
- UI 测试：UiTest / Hypium（自动化框架）
- 兼容性：
  - 多设备：Phone / Tablet / 模拟器
  - 多 API：API 9 / 11 / 12
  - 多分辨率 / 横竖屏 / 暗黑模式
- 流转测试：两台真机流转 / 模拟器流转
- Beta：AGC 内测 / 灰度发布

---

## 10. 发布与上架

- 签名：
  - 调试签名（自动）/ 发布签名（.p12 + .csr，华为 AppGallery Connect）
  - HAP 签名：私钥本地 / 公钥 AGC
- HAP/HSP：
  - 多 HAP 按需下发（按设备类型拆分）
  - HSP 共享包：多 HAP 共享代码/资源
- AGC（AppGallery Connect）：
  - 元数据：名称/图标/截图/视频/描述/分类/隐私声明
  - 上架材料：隐私政策 / 软著 / ICP备案（如涉及网络服务）
- 审核规避：
  - 无 Android 兼容层调用（NEXT）
  - 权限使用与声明一致
  - 支付合规：虚拟商品用 HMS IAP
  - 元服务限制：免安装，功能轻量，不可替代完整应用

---

## 11. 验收清单（DoD）

- [ ] API 级别与目标设备类型明确，NEXT 与兼容版差异文档化
- [ ] 所有权限在 module.json5 声明，敏感权限有授权时机和拒绝引导
- [ ] 数据分级标签（dataGroupId / appDistributionType / 数据级别）正确填写
- [ ] 多端适配至少覆盖 2 种设备类型，或明确声明仅支持某类设备
- [ ] 无 Android 私有 API 或反射调用（NEXT 环境）
- [ ] 主线程无阻塞，异步方案（Promise/async-await/Worker）已落地
- [ ] 无硬编码密钥，敏感信息加密存储或云端下发
- [ ] 有跨设备场景时流转和数据同步方案已设计，无场景则明确说明
- [ ] 性能基线达标：启动 < 2s、包体、内存、帧率
- [ ] 单元测试 + UI 测试 + 兼容性测试（多设备/API/分辨率）通过
- [ ] AGC 元数据/隐私声明/签名/上架材料完整
