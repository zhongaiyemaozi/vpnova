# VPNova 版本与功能

这个文件用于单独展示公开安装包的版本号、构建号、新增功能、修复内容和已知问题。主页 README 会链接到这里，方便用户快速查看每个公开版本的变化。

## 当前公开版本

最新 Apple 版本：`v1.0.0-build3`

最新 Android 版本：`v1.0.0-android-build1`

下载地址：

- Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-build3
- iOS IPA：`VPNova-v1.0.0-build3-iOS.ipa`
- macOS PKG：`VPNova-v1.0.0-build3-macOS.pkg`
- tvOS IPA：`VPNova-v1.0.0-build3-tvOS.ipa`
- visionOS IPA：`VPNova-v1.0.0-build3-visionOS.ipa`
- SHA-256：见 `checksums/VPNova-v1.0.0-build3-SHA256SUMS.txt`
- Android Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-android-build1
- Android APK：`VPNova-v1.0.0-android-build1-unsigned.apk`
- Android AAB：`VPNova-v1.0.0-android-build1-unsigned.aab`
- Android SHA-256：见 `checksums/VPNova-v1.0.0-android-build1-SHA256SUMS.txt`

## v1.0.0 Android build 1

状态：已发布

### 发布类型

Android 未签名公开包。

这些包不能直接安装。安装前需要使用用户自己的 Android 签名密钥重新签名。

### 安装包

- `VPNova-v1.0.0-android-build1-unsigned.apk`
- `VPNova-v1.0.0-android-build1-unsigned.aab`

### SHA-256

```text
8fa1b3c556ae9df28f0cd96544f94e5deda19d1490fd088c25c66dac00820794  VPNova-v1.0.0-android-build1-unsigned.apk
916d3098f56315d7994c234674fb54bdf17b0f4dd58327237cff2fcbe7a842c5  VPNova-v1.0.0-android-build1-unsigned.aab
```

### 兼容性

- Android 6.0 / API 23 或更高版本
- 包名：`com.vpnova.app`
- 版本名：`1.0.0`
- versionCode：`1`
- APK 内含 `arm64-v8a`、`armeabi-v7a`、`x86`、`x86_64` 的 Android `libbox.so`

### 验证

- Android 验证已由项目所有者确认通过后进入公开打包流程
- 本地执行 `./gradlew --no-daemon :app:testDebugUnitTest :app:assembleRelease :app:bundleRelease` 通过
- Android release lint 通过
- `apksigner verify` 确认 APK 未签名

### 下载

- Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-android-build1
- Checksums：`checksums/VPNova-v1.0.0-android-build1-SHA256SUMS.txt`

## v1.0.0 build 3

状态：已发布

### 发布类型

未签名二次签名包。

Apple 平台版本号固定为 `1.0.0`，本次只递增 build 到 `3`。

### 安装包

- `VPNova-v1.0.0-build3-iOS.ipa`
- `VPNova-v1.0.0-build3-macOS.pkg`
- `VPNova-v1.0.0-build3-macOS.zip`
- `VPNova-v1.0.0-build3-tvOS.ipa`
- `VPNova-v1.0.0-build3-visionOS.ipa`

### SHA-256

```text
cc6add9756dc14db3677c9aaeaf6322a8a037e2f552940903e994347b79b140c  VPNova-v1.0.0-build3-iOS.ipa
b05d3d250bc33d5c1bb20234411db696a4e8d810a12ae8b883d56e4ab788e87d  VPNova-v1.0.0-build3-macOS.pkg
7a4bf4a68e1e1805f7581b0842ef41ebc36aeacd93c114265e8ac7d2185ec372  VPNova-v1.0.0-build3-macOS.zip
8213b12b848521b55996422c92b4cfec7f6c9712998571ca1516d99d2c2c2b16  VPNova-v1.0.0-build3-tvOS.ipa
a4428279d06150e3e90446af4c415175631b65b2c75b11b68b29a8754a006e3e  VPNova-v1.0.0-build3-visionOS.ipa
```

### 兼容性

- iOS/iPadOS 15.0 或更高版本
- macOS 13.0 或更高版本
- tvOS 17.0 或更高版本
- visionOS 1.0 或更高版本
- visionOS 当前为共享 UI/Core shell，不包含 PacketTunnel 运行时

### 下载

- Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-build3
- Checksums：`checksums/VPNova-v1.0.0-build3-SHA256SUMS.txt`

## v1.0.0 build 2

状态：已发布

### 发布类型

未签名二次签名包。

这个 IPA 不能直接安装。安装前需要使用用户自己的 Apple 证书、描述文件和 entitlements 重新签名：

- `Payload/VPNova.app`
- `Payload/VPNova.app/PlugIns/PacketTunnel.appex`
- App 内的 Frameworks / dylib，如果重签工具要求递归签名

PacketTunnel 需要签名账号具备 NetworkExtension `packet-tunnel-provider` 权限。

### 新增功能

- 节点管理：支持手动添加、URI 粘贴、二维码扫描、订阅导入
- 协议支持：Shadowsocks、VMess、VLESS、Trojan、Hysteria2、TUIC、WireGuard、SOCKS5、HTTP、HTTPS Proxy
- 代理模式：规则模式、全局代理、直连模式
- 规则引擎：`DOMAIN`、`DOMAIN-SUFFIX`、`DOMAIN-KEYWORD`、`GEOIP`、`IP-CIDR`、`FINAL`
- DNS：自定义 DNS、DNS over HTTPS
- 流量统计：实时上传/下载速度、流量用量
- 原生 iOS/iPadOS 界面：支持 iPhone、iPad、深色模式、浅色模式
- 多语言：英文和简体中文

### 兼容性

- iOS/iPadOS 15.0 或更高版本
- iPhone 和 iPad
- VPN 连接需要真实设备验证

### 已知问题

- 侧载安装效果取决于签名方式、描述文件、设备和账号权限
- NetworkExtension 能力需要正确签名和授权
- 未签名 IPA 不能直接安装

### 下载

- Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-build2
- IPA：`VPNova-v1.0.0-build2.ipa`
- SHA-256：`ca62916d4f43277eca9dc0f189c5022d9233b5bf00ad80e6bac78dfd776075ad`

## 版本记录模板

后续新增版本时，可以复制下面模板：

```md
## vX.Y.Z build N

状态：已发布 / 测试中 / 计划发布

### 新增功能

- 

### 修复

- 

### 已知问题

- 

### 下载

- IPA：
- SHA-256：
- Release：
```
