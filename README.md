# VPNova

> iOS/iPadOS 规则代理客户端 - 公开 IPA 发布页

[English](README.en.md) | [安装指南](INSTALL.md) | [隐私说明](PRIVACY.md) | [常见问题](FAQ.md) | [问题反馈](https://github.com/zhongaiyemaozi/vpnova/issues) | [Releases](https://github.com/zhongaiyemaozi/vpnova/releases)

VPNova 是一款面向 iPhone 和 iPad 的规则代理工具客户端。它用于管理用户自己的代理节点，并根据域名、IP、地理位置和兜底规则选择代理、直连或拒绝连接。

**这个仓库只用于公开发布 IPA、展示版本说明、提供安装教程、说明隐私政策，以及收集用户反馈。VPNova 源代码不在本仓库公开。**

## 当前状态

仓库已经准备好作为 VPNova 的公开发布入口。首次 IPA 构建完成后，会通过 [GitHub Releases](https://github.com/zhongaiyemaozi/vpnova/releases) 发布。

发布时建议下载以下文件：

- `VPNova-vX.Y.Z.ipa` - iOS/iPadOS 安装包
- `VPNova-vX.Y.Z.sha256` - SHA-256 校验值
- Release notes - 更新内容、兼容性和已知问题

IPA 文件不会直接提交到 Git 历史中，避免仓库过大，也方便用户始终从 Releases 下载正式版本。

## 产品定位

VPNova 是一个本地运行的代理客户端，不是托管 VPN 服务。

VPNova 不提供代理服务器，不出售代理节点，不内置账号系统，也不依赖 VPNova 后端。用户需要自行准备可用的代理节点、订阅链接或配置 URI。

适合的使用场景：

- 管理个人代理节点和订阅
- 根据规则控制不同域名或 IP 的出站方式
- 在 iPhone/iPad 上测试网络连通性
- 给开发、调试、网络研究场景提供本地代理工具
- 导入自己已有的节点 URI、二维码或订阅链接

不适合的使用场景：

- 把 VPNova 当作内置服务器的商业 VPN 服务
- 期待应用自动提供免费代理节点
- 在公开 Issue 中分享密码、私钥、订阅 token 或二维码配置
- 用于任何违法、滥用或未经授权的网络行为

## 核心功能

VPNova v1.0 计划围绕核心代理体验：

- 节点管理：手动添加、URI 粘贴、二维码扫描、订阅导入
- 协议支持：Shadowsocks、VMess、VLESS、Trojan、Hysteria2、TUIC、WireGuard、SOCKS5、HTTP、HTTPS Proxy
- 代理模式：规则模式、全局代理、直连模式
- 规则引擎：`DOMAIN`、`DOMAIN-SUFFIX`、`DOMAIN-KEYWORD`、`GEOIP`、`IP-CIDR`、`FINAL`
- DNS：自定义 DNS、DNS over HTTPS
- 流量统计：实时上传/下载速度、流量用量
- 原生体验：SwiftUI 风格界面，支持 iPhone/iPad、深色模式、浅色模式、英文和简体中文

## 协议与导入

| 类型 | 支持情况 |
| --- | --- |
| Shadowsocks | `ss://`，手动、二维码、URI、订阅 |
| VMess | `vmess://`，手动、二维码、URI、订阅 |
| VLESS | `vless://`，手动、二维码、URI、订阅 |
| Trojan | `trojan://`，手动、二维码、URI、订阅 |
| Hysteria2 | `hy2://` / `hysteria2://`，手动、二维码、URI、订阅 |
| TUIC | `tuic://`，手动、二维码、URI、订阅 |
| WireGuard | `wireguard://`，手动、URI |
| SOCKS5 | `socks5://`，手动、URI |
| HTTP/HTTPS Proxy | `http://` / `https://`，手动、URI |

订阅格式计划支持：

- Shadowrocket/Base64 URI 列表
- Clash YAML
- sing-box JSON
- 普通 URI 列表

## 下载与安装

最新版 IPA 将发布在：

- [最新版本](https://github.com/zhongaiyemaozi/vpnova/releases/latest)
- [全部版本](https://github.com/zhongaiyemaozi/vpnova/releases)

由于 VPNova 暂不通过 App Store 发布，安装 IPA 需要你使用自己的签名或侧载方式。

常见方式：

- AltStore
- Sideloadly
- Apple Configurator
- Xcode 设备安装
- 企业签名或个人开发者签名，前提是当地法律和 Apple 规则允许

详细步骤见 [INSTALL.md](INSTALL.md)。

## 系统要求

- 设备：iPhone 或 iPad
- 系统：iOS/iPadOS 15.0 或更高版本
- VPN 权限：必须允许 iOS 添加 VPN 配置
- 相机权限：可选，只用于扫描节点二维码

VPN 功能必须在真实 iPhone 或 iPad 上验证。iOS Simulator 不能完整测试 Packet Tunnel 行为。

## 首次使用

1. 下载并安装 VPNova IPA。
2. 打开 VPNova。
3. 添加代理节点或订阅链接。
4. 选择当前使用的节点。
5. 选择规则、全局代理或直连模式。
6. 点击连接。
7. 按 iOS 提示允许添加 VPN 配置。

iOS 会要求用户明确授权 VPN 配置，这是系统安全机制，任何使用 VPN 能力的 App 都需要这个步骤。

## 校验 IPA

下载 IPA 后建议校验 SHA-256：

```sh
shasum -a 256 VPNova-vX.Y.Z.ipa
```

把输出结果和 Release 页面提供的 SHA-256 值对比，确认文件没有损坏或被替换。

## 隐私

VPNova 设计上不需要后端服务器。

- 不包含第三方统计 SDK
- 不包含广告 SDK
- 不包含追踪 SDK
- 不需要 VPNova 账号
- 不内置代理服务器
- 节点、规则、DNS 等配置保存在本机
- 网络流量只会根据用户配置路由到用户自己的代理服务器

完整说明见 [PRIVACY.md](PRIVACY.md)。

## 问题反馈

你可以通过 [GitHub Issues](https://github.com/zhongaiyemaozi/vpnova/issues) 反馈：

- 安装失败
- App 启动失败
- VPN 连接失败
- 节点导入失败
- 订阅解析失败
- 规则匹配问题
- DNS 问题
- UI 显示问题
- 特定 iOS 版本兼容问题

反馈时建议提供：

- VPNova 版本
- iOS/iPadOS 版本
- 设备型号
- 安装方式
- 复现步骤
- 截图或日志，前提是已经移除敏感信息

请不要在公开 Issue 中发布：

- 代理密码
- 订阅 token
- WireGuard 私钥
- 服务器凭据
- 二维码配置
- Apple 开发者证书或描述文件

## 源码与许可证说明

公开分发 IPA 和源码开源不是同一件事。本仓库只负责公开安装包和文档，不代表 VPNova 的应用源码已经公开。

VPNova 使用 sing-box/libbox 作为代理核心。sing-box 项目使用 GPL 系列许可证。公开分发包含该组件的 IPA 前，需要认真确认许可证合规义务，例如许可证文本、版权说明、对应源码或构建说明等要求。

相关说明见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

## 免责声明

VPNova 是一个工具型客户端。用户应自行确认所在地区的法律法规、网络使用规则、Apple 账号和签名方式的合规性。

请只连接你拥有、管理或被授权使用的代理服务器。不要将 VPNova 用于违法、侵权、攻击、滥用或绕过未授权访问控制的行为。
