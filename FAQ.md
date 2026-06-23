# VPNova 常见问题

## VPNova 是开源项目吗？

不是。这个仓库只用于公开发布安装包、维护版本说明、提供安装文档和收集问题反馈，不包含 VPNova 应用源码。

更准确地说，VPNova 当前是“公开发布安装包”，不是“源码开源”。

## 为什么不放到 App Store？

VPN 和代理类 App 在 App Store / Google Play 上架时会受到 VPN 权限、账号类型、审核规则和应用描述等多方面限制。当前这个仓库用于提供一个公开下载入口，让能够自行签名或侧载安装包的用户进行安装。

## 可以通过 TestFlight 安装 iOS 版本吗？

可以。iOS 版本已经通过 TestFlight 审核。需要 TestFlight 下载入口的用户，请发送邮件到 `zhongaiyemaozi@outlook.com`，我会根据邮箱添加测试员。

## VPNova 是否提供免费节点？

不提供。VPNova 是客户端工具，不是代理服务商。你需要使用自己的代理服务器、订阅链接或配置 URI。

## VPNova 是完整 VPN 服务吗？

VPNova 使用 Apple NetworkExtension 或 Android VpnService 创建本地隧道，并按照用户配置把流量路由到代理节点。它不是托管 VPN 服务，也不销售服务器访问权限。

## 没有电脑可以安装吗？

取决于你的签名和侧载方式。很多 Apple 安装流程需要电脑、Apple ID、开发者账号、企业签名或第三方签名服务。Android 未签名 APK 需要先用你自己的 Android 签名密钥签名。

## 为什么 iOS 要求允许 VPN 配置？

iOS、macOS、tvOS 和 Android 都要求所有使用 VPN 能力的 App 由用户明确授权。VPNova 需要这个权限来创建本地代理隧道。

## 可以导入订阅链接吗？

可以。VPNova 设计上支持常见订阅格式，包括 Shadowrocket/Base64 列表、Clash YAML、sing-box JSON 和普通 URI 列表。

## 可以导入二维码吗？

可以。二维码导入需要相机权限。VPNova 只在扫描节点二维码时使用相机。

## 支持哪些系统版本？

当前公开包支持 iOS/iPadOS 15.0+、macOS 13.0+、tvOS 17.0+、visionOS 1.0+ 和 Android 6.0+。VPN 连接行为需要在真实设备上测试，模拟器不能完整验证。

## 为什么安装后 VPN 连接失败？

常见原因包括节点配置错误、服务器不可用、Apple 签名缺少 NetworkExtension 权限、Android VpnService 未授权、设备策略限制、订阅节点格式异常或当前网络阻断对应协议。

请先确认节点在其他客户端中可用，再反馈 VPNova 的具体问题。

## 如何反馈问题？

请打开 GitHub Issue：

https://github.com/zhongaiyemaozi/vpnova/issues

反馈时建议提供：

- VPNova 版本
- 系统版本
- 设备型号
- 安装方式
- 问题描述
- 复现步骤
- 已脱敏的日志或截图

请不要公开发布密码、私钥、订阅 token、节点二维码、证书、描述文件、Android keystore 或签名密码。
