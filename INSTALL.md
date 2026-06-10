# VPNova IPA 安装指南

这份文档说明如何在 iPhone 或 iPad 上安装 VPNova 公开发布的 IPA。

由于 VPNova 暂不通过 App Store 发布，安装过程取决于你自己的签名、侧载或设备管理方式。

## 下载地址

请从官方 GitHub Releases 下载：

- 最新版本：https://github.com/zhongaiyemaozi/vpnova/releases/latest
- 全部版本：https://github.com/zhongaiyemaozi/vpnova/releases

建议只从以上地址下载 IPA，不要安装来源不明的二次分发包。

## 安装前准备

你需要：

- iPhone 或 iPad
- iOS/iPadOS 15.0 或更高版本
- 最新 `VPNova-vX.Y.Z.ipa`
- 可用的签名或侧载工具
- 自己的代理节点、订阅链接或配置 URI

VPNova 不内置代理服务器，也不提供免费节点。

## 方式一：AltStore

1. 在电脑和 iOS 设备上安装 AltStore。
2. 从 GitHub Releases 下载最新 VPNova IPA。
3. 在 iOS 设备上打开 AltStore。
4. 进入 `My Apps`。
5. 点击 `+`。
6. 选择下载好的 VPNova IPA。
7. 等待安装完成。
8. 打开 VPNova，并按系统提示允许添加 VPN 配置。

如果使用免费 Apple ID，AltStore 安装的 App 通常需要定期刷新签名。

## 方式二：Sideloadly

1. 在电脑上安装 Sideloadly。
2. 使用 USB 连接 iPhone 或 iPad。
3. 从 GitHub Releases 下载最新 VPNova IPA。
4. 将 IPA 拖入 Sideloadly。
5. 使用 Apple ID 或开发者账号签名。
6. 开始安装。
7. 如果 iOS 提示信任开发者，请到系统设置中完成信任。
8. 打开 VPNova，并按系统提示允许添加 VPN 配置。

## 方式三：Apple Configurator

1. 在 Mac 上安装 Apple Configurator。
2. 使用 USB 连接 iPhone 或 iPad。
3. 下载已签名的 VPNova IPA。
4. 在 Apple Configurator 中选择设备。
5. 添加并安装 IPA。
6. 打开 VPNova，并允许 VPN 配置。

## 方式四：Xcode

这个方式主要适合开发者或测试人员。

1. 使用 USB 连接 iPhone 或 iPad 到 Mac。
2. 打开 Xcode。
3. 进入 `Window` -> `Devices and Simulators`。
4. 选择目标设备。
5. 安装已签名的 VPNova IPA。
6. 在设备上打开 VPNova，并允许 VPN 配置。

## 首次启动

安装完成后：

1. 打开 VPNova。
2. 添加代理节点或订阅链接。
3. 选择当前使用的节点。
4. 选择规则、全局代理或直连模式。
5. 点击连接。
6. 按 iOS 系统提示允许添加 VPN 配置。

iOS 会要求用户明确授权 VPN 配置，这是系统安全机制。

## 常见问题

### IPA 无法安装

可能原因：

- IPA 没有正确签名
- 描述文件和设备不匹配
- 当前设备没有加入开发者描述文件
- IPA 下载损坏
- iOS 版本低于 15.0
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

### 订阅导入失败

可以尝试：

- 确认订阅链接可以在 Safari 中打开
- 确认订阅没有过期
- 确认订阅格式是 Shadowrocket、Clash、sing-box 或普通 URI 列表
- 先尝试导入单条节点 URI
- 反馈日志前删除 token、密码、私钥和服务器凭据

## 安全建议

- 只从官方 Releases 下载 IPA。
- 下载后优先校验 SHA-256。
- 不要公开分享订阅 token、代理密码、WireGuard 私钥或节点二维码。
- 只连接你信任并有权使用的代理服务器。
- 不要安装来源不明的重签名 IPA。
