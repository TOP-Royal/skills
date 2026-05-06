# Android 原生开发模板（android-native）

> 目标：Android 项目从需求到上架一次成型，避免兼容性翻车、权限被拒、审核不过、性能不达标。

---

## 固定输出物（AI 必须产出）

- 技术选型清单（语言/架构/UI框架/依赖库/最低API级别/目标SDK）
- 模块与导航架构图（Activity/Fragment/Compose Navigation/路由表）
- 权限与隐私合规方案（清单 + 运行时申请时机 + 后台权限策略）
- 数据层设计（Room/数据库/数据存储/缓存/同步策略）
- 发布配置（签名/多渠道/ProGuard/R8/最小化/上架材料）
- 性能基线（启动时间/包体/内存/电量/帧率）与测试计划

## 必须/禁止规则

- 必须：minSdk 与 targetSdk 明确写入配置，兼容性策略文档化（哪些功能低版本降级）
- 必须：所有危险权限有运行时申请 + 拒绝引导 + 永久拒绝兜底（设置页跳转）
- 必须：后台任务（定位/下载/推送）有前台服务或 WorkManager 备案，禁止后台偷偷跑
- 必须：发布前通过 Lint + Kotlin 代码检查 + 基线测试，包体/启动/内存达标
- 禁止：主线程阻塞（网络/IO/复杂计算），必须用 Coroutine/RxJava/线程池
- 禁止：直接使用明文 HTTP（网络安全配置允许范围必须明确）
- 禁止：硬编码密钥/Token 进代码或 XML，必须加密存储或服务端下发
- 禁止：忽略暗黑模式/横屏/分屏/折叠屏适配（声明不支持需在配置中显式说明）

---

## 1. 项目基础

- 语言：Kotlin（优先）/ Java（遗留兼容）
- 构建系统：Gradle + Kotlin DSL / Gradle + Groovy
- 最低 API（minSdk）：
- 目标 API（targetSdk / compileSdk）：
- 架构：MVP / MVVM / MVI / Clean Architecture
- UI 框架：Jetpack Compose（新）/ XML + ViewBinding（遗留）/ 混合
- 依赖注入：Hilt / Koin
- 异步：Kotlin Coroutines + Flow / RxJava3

---

## 2. 模块与导航架构

- 模块拆分：
  - app（壳）/ feature_XX / core / data / domain
  - 模块间通信：隐式 Intent / Deep Link / 共享接口（禁止直接耦合）
- 导航：
  - Compose：Navigation Compose（类型安全路由）
  - XML：Navigation Component + Safe Args
  - 路由表集中管理（URL-like scheme，方便 H5/推送/外部跳转）
- 生命周期：
  - ViewModel（业务层生命周期绑定）
  - Compose：remember / LaunchedEffect / SideEffect / DisposableEffect
  - XML：LifecycleOwner 观察

---

## 3. 权限与隐私合规

- 权限清单分类：
  - 普通权限：INTERNET / ACCESS_NETWORK_STATE
  - 危险权限：CAMERA / READ_MEDIA_IMAGES / READ_CONTACTS / LOCATION
  - 特殊权限：SYSTEM_ALERT_WINDOW / WRITE_SETTINGS / MANAGE_EXTERNAL_STORAGE
- 运行时申请：
  - 申请时机：首次使用功能时（非启动时一次性要全部）
  - 拒绝处理：解释为什么需要 → 再次申请 → 永久拒绝跳转设置页
  - 禁止：授权失败直接崩溃或功能不可用无提示
- 隐私合规：
  - 隐私政策弹窗（首次启动，不同意退出）
  - 敏感信息（IMEI/MAC/已安装列表）获取必须有正当理由，Android 10+ 限制
  - 广告标识符（GAID）使用需声明

---

## 4. 数据层设计

- 本地存储：
  - Room（SQLite 封装）：实体/DAO/数据库/迁移
  - DataStore（Preferences 替代）：类型安全/异步/监听
  - 文件存储：缓存目录 vs 持久目录 / Scoped Storage（Android 10+）
- 网络层：
  - Retrofit + OkHttp + Kotlin Serialization / Gson / Moshi
  - 网络配置：超时/重试/证书绑定/日志拦截（debug  only）
- 缓存策略：
  - 内存缓存（LruCache）+ 磁盘缓存（OkHttp Cache / Room）
  - 数据一致性：本地优先 / 网络优先 / 双写（明确策略）
- 同步与后台：
  - WorkManager：可延迟、有保证、约束条件（网络/电量/充电）
  - 前台服务：定位/下载/播放（必须通知栏常驻）
  - AlarmManager：精确时间任务（Android 12+ 限制）

---

## 5. 关键功能开发

### 5.1 推送
- Firebase Cloud Messaging（海外）/ 厂商推送（国内：华为/小米/OPPO/vivo/魅族）
- 多厂商聚合：极光/个推/友盟 / 自建路由
- 抵达率：厂商通道 + 自建长连接兜底

### 5.2 支付
- Google Play Billing / 国内：支付宝/微信支付/华为支付
- 服务端验证：支付回调 + 主动查询（防掉单）
- 订阅管理：续期/取消/恢复/价格变动

### 5.3 地图与定位
- Google Maps（海外）/ 高德/百度（国内）/ 华为地图（鸿蒙设备）
- 定位精度：GPS / 网络 / 混合，后台定位需前台服务
- 地理围栏：功耗评估（不要密集围栏）

### 5.4 相机与媒体
- CameraX（推荐）/ Camera2（高级定制）
- 媒体选择器：PhotoPicker（Android 13+）替代自研相册
- 视频：ExoPlayer（播放）/ MediaCodec（编解码）

---

## 6. 性能与体验

- 启动优化：
  - 冷启动 < 2s（低端机）
  - 延迟初始化（IdleHandler / 异步初始化 / 懒加载）
  - SplashScreen API（Android 12+）
- 包体优化：
  - R8 混淆 + 资源压缩
  - 动态功能模块（Dynamic Feature）/ ABI 分包（arm64-v8a / armeabi-v7a）
  - 大图压缩（WebP / AVIF）/ 字体子集化
- 内存优化：
  - 大图加载（Coil / Glide）：采样/缓存/生命周期绑定
  - 内存泄漏检测：LeakCanary（debug）/ Profiler
  - 后台限制：App Standby / Doze / Background Restrictions
- 电量优化：
  - 定位频率控制 / 网络批量请求 / 动画暂停（后台不可见）
  - 使用 Battery Historian 分析
- 渲染性能：
  - 帧率监控：Choreographer / Profile GPU Rendering
  - 掉帧根因：布局层级 / 过度绘制 / 主线程阻塞

---

## 7. 测试与质量

- 单元测试：JUnit5 + MockK + Turbine（Flow 测试）
- UI 测试：Compose Test / Espresso
- 兼容性测试：
  - 多分辨率（ldpi → xxxhdpi）
  - 多系统版本（minSdk → targetSdk 典型机）
  - 折叠屏/平板/分屏/横屏
- Monkey 测试：稳定性 + 崩溃率
- 基线测试：启动时间 / 内存峰值 / 包体 / 帧率

---

## 8. 发布与上架

- 签名：
  - 发布密钥（.jks）独立保存，CI/CD 使用环境变量/加密文件
  - 密钥轮换（Android 9+ 支持）
- 混淆与加固：
  - R8 混淆规则（-keep 白名单）
  - 加固：腾讯乐固 / 网易易盾 / 360（国内）/ Google Play App Signing（海外）
- 多渠道：
  - 国内：华为/小米/OPPO/vivo/应用宝/豌豆荚/360（渠道号/元数据区分）
  - 海外：Google Play / Samsung Galaxy Store / Amazon
- 上架材料：
  - 图标/截图/视频/描述/隐私政策/分级问卷/内容分级
  - 国内：ICP备案/软著/版号（游戏）/隐私协议

---

## 9. 验收清单（DoD）

- [ ] 技术选型与 minSdk/targetSdk 已明确，兼容性降级策略文档化
- [ ] 所有危险权限有运行时申请 + 拒绝引导 + 永久拒绝兜底
- [ ] 后台任务（定位/下载/推送）使用前台服务或 WorkManager，无违规后台行为
- [ ] 数据层：Room/DataStore 方案明确，网络超时/重试/缓存策略清晰
- [ ] 主线程无阻塞，异步方案（Coroutine）已落地
- [ ] 无硬编码密钥，敏感信息加密存储或服务端下发
- [ ] 暗黑模式/横屏/分屏/折叠屏已适配或明确声明不支持
- [ ] Lint + 单元测试 + UI 测试通过，Monkey 无崩溃
- [ ] 性能基线达标：启动 < 2s（低端）、包体、内存、帧率
- [ ] 上架材料齐全（签名/混淆/加固/渠道/隐私政策/截图）
