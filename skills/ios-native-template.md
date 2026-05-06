# iOS 原生开发模板（ios-native）

> 目标：iOS 项目从需求到 App Store 上架一次成型，避免审核被拒、性能不达标、适配遗漏、签名/证书翻车。

---

## 固定输出物（AI 必须产出）

- 技术选型清单（Swift/UIKit/SwiftUI/最低版本/依赖管理）
- 模块与导航架构图（SwiftUI NavigationStack / UIKit Coordinator / VIPER/MVVM-C）
- 权限与隐私清单（Info.plist / 弹窗文案 / 后台模式 / ATT  App Tracking Transparency）
- 数据层设计（CoreData/SwiftData/UserDefaults/Keychain/网络/缓存/离线）
- 发布配置（证书/Provisioning Profile/App Store Connect/截图/元数据）
- 性能基线（启动/包体/内存/帧率/电量）与测试计划

## 必须/禁止规则

- 必须：Deployment Target 与 Xcode 版本明确，弃用 API 有替代方案
- 必须：所有权限（相机/相册/定位/蓝牙/麦克风/通知/ATT）在 Info.plist 声明用途字符串，弹窗时机合理
- 必须：后台模式（定位/音频/下载/VoIP/Processing）在 Info.plist 声明且有正当理由，审核能解释
- 必须：网络层有超时/重试/缓存策略，支持弱网/离线降级
- 禁止：主线程阻塞（网络/IO/复杂计算），必须用 async/await/GCD/OperationQueue
- 禁止：硬编码密钥进代码 plist，Keychain / 服务端下发 / Xcode 环境变量
- 禁止：使用私有 API 或非公开 SPI（审核 100% 拒）
- 禁止：忽略暗黑模式/横屏/多窗口/动态字体/旁白 VoiceOver（或显式声明不支持）

---

## 1. 项目基础

- 语言：Swift（优先）/ Objective-C（遗留桥接）
- UI 框架：SwiftUI（新，iOS 15+）/ UIKit（成熟，混合项目）/ SwiftUI + UIKit 混编
- 最低版本（Deployment Target）：
- Xcode 版本：
- 架构：MVVM / MVVM-C（Coordinator）/ VIPER / Clean Architecture / TCA（The Composable Architecture）
- 依赖管理：SPM（Swift Package Manager，优先）/ CocoaPods / Carthage
- 异步：async/await（iOS 15+）/ Combine / GCD

---

## 2. 模块与导航架构

- 模块拆分：
  - App（壳）/ Feature / Core / Data / Domain
  - 跨模块通信：协议/路由/Deep Link / App Groups（共享容器）
- 导航：
  - SwiftUI：NavigationStack（类型安全路由）/ NavigationSplitView（iPad/Mac）
  - UIKit：UINavigationController / UITabBarController / 自定义 Coordinator
  - 路由表集中管理（URL scheme / Universal Link / App Link）
- 状态管理：
  - SwiftUI：@State / @Binding / @ObservedObject / @EnvironmentObject / @StateObject
  - UIKit：RxSwift / Combine / 自定义 Observable

---

## 3. 权限与隐私合规

- Info.plist 权限声明（必须提供用途说明字符串）：
  - 相机：NSCameraUsageDescription
  - 相册：NSPhotoLibraryUsageDescription
  - 定位：NSLocationWhenInUseUsageDescription / NSLocationAlwaysUsageDescription
  - 麦克风：NSMicrophoneUsageDescription
  - 蓝牙：NSBluetoothAlwaysUsageDescription
  - 通知：UNUserNotificationCenter.requestAuthorization
  - ATT：NSUserTrackingUsageDescription（iOS 14.5+，广告归因）
- 弹窗时机：
  - 首次使用功能时触发（不要启动就弹一堆）
  - 永久拒绝后提供设置页跳转引导
- 后台模式：
  - Info.plist UIBackgroundModes：location/audio/fetch/remote-notification/processing/VoIP
  - 审核注意：VoIP 只能用于真实语音通话，禁止用于保活
- 隐私清单（Privacy Manifest，iOS 17.2+/Xcode 15）：
  - 第三方 SDK 隐私清单签名（如 Firebase/Facebook/友盟）
  - 自身 API 调用声明（磁盘/网络/进程等）
- 数据收集：
  - App Store Connect 中声明数据类型与用途
  - 儿童类别（Made for Kids）禁止广告/分析/外部链接

---

## 4. 数据层设计

- 本地存储：
  - SwiftData（iOS 17+，声明式，SwiftUI 原生）
  - Core Data（成熟，Objective-C 遗产，多线程需谨慎）
  - UserDefaults（轻量配置，禁止存敏感/大量数据）
  - Keychain（敏感数据：Token/密码/证书）
  - 文件：FileManager（缓存/文档/临时目录，iCloud 同步选项）
- 网络层：
  - URLSession（原生）/ Alamofire（高级封装）
  - 序列化：Codable / JSONDecoder / SwiftyJSON
  - 配置：超时/重试/证书绑定/请求/响应拦截
- 缓存策略：
  - 内存缓存：NSCache / 自定义 LRU
  - 磁盘缓存：URLCache / Kingfisher（图片）/ 自定义
  - 数据一致性：本地优先 / 网络优先 / 双写（明确策略）
- 离线：
  - 网络状态监听（NWPathMonitor）
  - 离线队列：请求入队 → 联网后自动重试

---

## 5. 关键功能开发

### 5.1 推送
- APNs（Apple Push Notification service）
- 厂商通道：国内 App 需集成极光/个推/友盟等（聚合多厂商）
- 推送扩展：Notification Service Extension（富媒体/图片/自定义 UI）
- 静默推送：background fetch / content-available

### 5.2 支付
- Apple In-App Purchase（IAP，虚拟商品必须用）/ Apple Pay（实物）
- 服务端验证：App Store Server API / 收据验证
- 订阅：StoreKit 2（iOS 15+，现代 API）/ StoreKit 1
- 沙盒测试：沙盒账号配置/订阅加速（缩短周期）

### 5.3 地图与定位
- Apple Map / Google Map SDK / 高德 SDK
- 定位精度：kCLLocationAccuracyBest / kCLLocationAccuracyHundredMeters
- 后台定位：significantLocationChange / startMonitoringSignificantLocationChanges
- 地理围栏：CLCircularRegion / CLBeaconRegion

### 5.4 相机与媒体
- AVFoundation（Camera / 录音 / 编解码）
- PhotoKit（相册访问，iOS 14+ 有限访问权限）
- 播放：AVPlayer（本地/网络）/ VideoPlayer（SwiftUI）
- 直播：RTMP / WebRTC / HLS

---

## 6. 性能与体验

- 启动优化：
  - 冷启动 < 2s（低端机 iPhone SE）
  - dyld 优化：减少动态库数量 / 使用静态库 / 延迟加载
  - 主线程任务最小化
- 包体优化：
  - 资源优化：图片 Asset Catalog / App Slicing（按设备发不同资源）
  - 代码裁剪：Dead Code Stripping / Swift 编译优化
  - 多语言：按需打包
- 内存优化：
  - 图片加载：Kingfisher（缓存/降采样/生命周期）
  - 内存泄漏：Instruments / Memory Graph
  - 大对象释放：autoreleasepool / 延迟加载
- 电量优化：
  - 定位频率 / 网络批量 / 动画暂停（后台/不可见）
  - Energy Log / XCTMetric
- 渲染性能：
  - 帧率监控：CADisplayLink / Xcode Frame Debugger
  - SwiftUI：避免大面积 @State 刷新 / 使用 Equatable / 懒加载
  - UIKit：Auto Layout 性能 / 复用 Cell / 异步渲染

---

## 7. 多设备适配

- iPhone：全系列屏幕（SE → Pro Max）/ 灵动岛 / 刘海屏安全区域
- iPad：多窗口 / Split View / Slide Over / 键盘/鼠标/触控板
- Mac Catalyst / visionOS：如计划支持需提前设计
- 暗黑模式：Color Set / SF Symbols / 动态颜色
- 动态字体：支持用户设置的大字体（UIContentSizeCategory）
- 旁白 VoiceOver： accessibilityLabel / accessibilityHint / accessibilityTraits
- 旋转：支持横竖屏或锁定（Info.plist + 代码协同）

---

## 8. 测试与质量

- 单元测试：XCTest + 依赖注入（Mock）
- UI 测试：XCUITest（缓慢但覆盖全链路）/ ViewInspector（SwiftUI）
- 性能测试：XCTMetric（启动/内存/CPU/网络）
- 兼容性：
  - 多设备（iPhone SE / 标准 / Pro Max / iPad）
  - 多系统版本（Deployment Target → Latest）
  - 弱网/离线/低电量/低存储
- Beta：TestFlight（内部/外部测试）/ 蒲公英/Fir.im（国内）

---

## 9. 发布与审核

- 证书与签名：
  - Development / Distribution（App Store / Ad Hoc / Enterprise）
  - Provisioning Profile 与 Bundle ID / Capability 匹配
  - CI/CD：Fastlane（match / gym / pilot / deliver）
- App Store Connect：
  - 元数据：标题/副标题/关键词/描述/截图/视频/分级
  - 隐私标签：数据类型/用途/是否关联用户/是否用于追踪
  - 定价/内购/订阅配置
- 审核规避：
  - 无隐藏功能 / 无热更新（除 JS 逻辑外，原生代码热更新会被拒）
  - 支付合规：虚拟商品必须用 IAP
  - 账号登录：必须提供 Apple Sign In（如支持第三方登录）
  - 儿童安全：UGC 需有举报/过滤/家长控制
- 国内：
  - 如需上架国内安卓渠道，iOS 版需保持一致性（功能/品牌）

---

## 10. 验收清单（DoD）

- [ ] Deployment Target / Xcode 版本明确，弃用 API 有替代方案
- [ ] 所有权限在 Info.plist 声明用途字符串，弹窗时机合理
- [ ] 后台模式有正当理由，审核能解释，无违规保活
- [ ] 数据层：本地存储/网络/缓存方案明确，离线降级策略清晰
- [ ] 主线程无阻塞，async/await 或 GCD 已落地
- [ ] 无硬编码密钥，敏感信息存 Keychain 或服务端下发
- [ ] 无私有 API / 非公开 SPI
- [ ] 暗黑模式/横屏/动态字体/VoiceOver 已适配或显式声明不支持
- [ ] 性能基线达标：启动 < 2s（SE）、包体、内存、帧率
- [ ] 单元测试 + UI 测试通过，TestFlight Beta 验证
- [ ] App Store Connect 元数据/隐私标签/截图/内购/证书配置完整
