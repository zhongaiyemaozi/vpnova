# VPNova 安装指南

这份文档说明如何安装 VPNova 公开发布的 Apple 安装包和 Android 安装包。

由于 VPNova 暂不通过 App Store 或 Google Play 发布，安装过程取决于你自己的签名、侧载或设备管理方式。

## 下载地址

请从官方 GitHub Releases 下载：

- 最新版本：https://github.com/zhongaiyemaozi/vpnova/releases/latest
- 全部版本：https://github.com/zhongaiyemaozi/vpnova/releases

建议只从以上地址下载安装包，不要安装来源不明的二次分发包。

## 安装前准备

你需要：

- iPhone、iPad、Mac、Apple TV、Apple Vision 或 Android 设备
- 对应平台的系统版本：iOS/iPadOS 15.0+、macOS 13.0+、tvOS 17.0+、visionOS 1.0+ 或 Android 6.0+
- 对应平台的最新 VPNova 安装包
- 可用的签名、重签名或侧载工具
- 自己的代理节点、订阅链接或配置 URI

VPNova 不内置代理服务器，也不提供免费节点。

## Apple 平台：AltStore

1. 在电脑和 iOS 设备上安装 AltStore。
2. 从 GitHub Releases 下载最新 VPNova IPA。
3. 在 iOS 设备上打开 AltStore。
4. 进入 `My Apps`。
5. 点击 `+`。
6. 选择下载好的 VPNova IPA。
7. 等待安装完成。
8. 打开 VPNova，并按系统提示允许添加 VPN 配置。

如果使用免费 Apple ID，AltStore 安装的 App 通常需要定期刷新签名。

## Apple 平台：Sideloadly

1. 在电脑上安装 Sideloadly。
2. 使用 USB 连接 iPhone 或 iPad。
3. 从 GitHub Releases 下载最新 VPNova IPA。
4. 将 IPA 拖入 Sideloadly。
5. 使用 Apple ID 或开发者账号签名。
6. 开始安装。
7. 如果 iOS 提示信任开发者，请到系统设置中完成信任。
8. 打开 VPNova，并按系统提示允许添加 VPN 配置。

## Apple 平台：Apple Configurator

1. 在 Mac 上安装 Apple Configurator。
2. 使用 USB 连接 iPhone 或 iPad。
3. 下载已签名的 VPNova IPA。
4. 在 Apple Configurator 中选择设备。
5. 添加并安装 IPA。
6. 打开 VPNova，并允许 VPN 配置。

## Apple 平台：Xcode

这个方式主要适合开发者或测试人员。

1. 使用 USB 连接 iPhone 或 iPad 到 Mac。
2. 打开 Xcode。
3. 进入 `Window` -> `Devices and Simulators`。
4. 选择目标设备。
5. 安装已签名的 VPNova IPA。
6. 在设备上打开 VPNova，并允许 VPN 配置。

## Android：签名 APK 后安装

公开 Android APK 是未签名包，文件名类似：

```text
VPNova-v1.0.0-android-build1-unsigned.apk
```

它不能直接安装。你需要先使用自己的 Android 签名密钥签名，再安装到设备。

示例流程：

```sh
apksigner sign \
  --ks your-release-key.jks \
  --out VPNova-v1.0.0-android-build1-signed.apk \
  VPNova-v1.0.0-android-build1-unsigned.apk

apksigner verify --verbose VPNova-v1.0.0-android-build1-signed.apk
adb install VPNova-v1.0.0-android-build1-signed.apk
```

也可以下载 `.aab` 后使用 Android Studio、bundletool 或自己的发布流程生成签名 APK。请不要公开分享你的 `.jks`、keystore 密码或签名配置。

## 首次启动

安装完成后：

1. 打开 VPNova。
2. 添加代理节点或订阅链接。
3. 选择当前使用的节点。
4. 选择规则、全局代理或直连模式。
5. 点击连接。
6. 按系统提示允许添加 VPN 配置。

iOS、macOS、tvOS 和 Android 都会要求用户明确授权 VPN 配置，这是系统安全机制。

## 常见问题

### 安装包无法安装

可能原因：

- IPA 没有正确签名
- Android APK 没有签名或签名校验失败
- 描述文件和设备不匹配
- 当前设备没有加入开发者描述文件
- IPA 下载损坏
- 系统版本低于最低要求
- 设备存在 MDM、屏幕使用时间或企业策略限制

### App 可以打开，但没有 VPN 授权提示

可能原因：

- IPA 签名时缺少 NetworkExtension 权限
- 安装的不是正确的真机包
- 系统策略禁止添加 VPN 配置
- 之前的 VPN 配置残留导致创建失败

可以尝试：

- 删除旧版本 VPNova 后重新安装
- 在系统设置中删除旧的 VPN 配置
- 重启设备后再打开 VPNova

### VPN 无法连接

可能原因：

- 节点配置错误
- 服务器不可用
- 密码、UUID、密钥或端口错误
- 订阅中存在不支持或格式错误的节点
- 当前网络阻断了对应协议
- NetworkExtension 配置创建失败
- Android VpnService 权限未授权或系统策略禁止 VPN

### 订阅导入失败

可以尝试：

- 确认订阅链接可以在 Safari 中打开
- 确认订阅没有过期
- 确认订阅格式是 Shadowrocket、Clash、sing-box 或普通 URI 列表
- 先尝试导入单条节点 URI
- 反馈日志前删除 token、密码、私钥和服务器凭据

## 安全建议

- 只从官方 Releases 下载安装包。
- 下载后优先校验 SHA-256。
- 不要公开分享订阅 token、代理密码、WireGuard 私钥或节点二维码。
- 只连接你信任并有权使用的代理服务器。
- 不要安装来源不明的重签名 IPA。
