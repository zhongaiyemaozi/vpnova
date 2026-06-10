# VPNova IPA 公开发布页

[English](README.md)

VPNova 是一款面向 iPhone 和 iPad 的规则代理工具客户端。这个仓库只用于公开发布 IPA、展示版本说明、提供安装教程、说明隐私政策，以及收集用户反馈。

**本仓库不公开 VPNova 源代码。**

也就是说，这里不是源码开源仓库，而是一个独立的公开发布仓库。源代码会继续保留在私有项目中，GitHub 上只放用户下载安装所需要的内容。

## 下载

最新版 IPA 将发布在 GitHub Releases：

- 最新版：`https://github.com/<your-github-username>/vpnova-ipa-release/releases/latest`
- 全部版本：`https://github.com/<your-github-username>/vpnova-ipa-release/releases`

创建 GitHub 仓库后，把 `<your-github-username>` 替换为你的真实 GitHub 用户名或组织名。

建议每个 Release 都包含：

- `VPNova-vX.Y.Z.ipa`
- SHA-256 校验值
- 更新日志
- 已知问题
- 支持的最低 iOS 版本

## 产品定位

VPNova 是一个本地运行的 iOS 代理客户端，用于帮助用户管理自己的代理节点，并按照规则选择代理、直连或拒绝连接。

VPNova 不提供代理服务器，不出售代理服务，也不依赖 VPNova 后端账号系统。用户需要自行准备可用的代理节点、订阅链接或配置 URI。

适合的使用场景：

- 管理个人代理节点
- 使用规则控制不同域名或 IP 的出站方式
- 在 iPhone/iPad 上测试网络连通性
- 给开发、调试、网络研究场景提供本地代理工具
- 导入自己已有的订阅链接或节点 URI

不适合的使用场景：

- 把 VPNova 当作内置节点的商业 VPN 服务
- 期待应用自动提供免费服务器
- 发布或分享包含密码、私钥、订阅 token 的配置
- 用于任何违法、滥用或未经授权的网络行为

## 核心功能

计划公开发布的 IPA 将围绕 v1.0 功能：

- 节点管理：手动添加、URI 粘贴、二维码扫描、订阅导入
- 协议支持：Shadowsocks、VMess、VLESS、Trojan、Hysteria2、TUIC、WireGuard、SOCKS5、HTTP、HTTPS Proxy
- 代理模式：规则模式、全局代理、直连模式
- 规则引擎：`DOMAIN`、`DOMAIN-SUFFIX`、`DOMAIN-KEYWORD`、`GEOIP`、`IP-CIDR`、`FINAL`
- DNS：自定义 DNS、DNS over HTTPS
- 流量统计：实时上传/下载速度、流量用量
- 原生 iOS 体验：支持 iPhone/iPad、深色模式、浅色模式、英文和简体中文

## 安装方式

由于 VPNova 暂不通过 App Store 发布，安装 IPA 需要你使用自己的签名或侧载方式。

常见方式：

- AltStore
- Sideloadly
- Apple Configurator
- Xcode 设备安装
- 企业签名或个人开发者签名，前提是当地法律和 Apple 规则允许

详细步骤见 [INSTALL.md](INSTALL.md)。

## 首次使用

1. 安装 VPNova IPA。
2. 打开 VPNova。
3. 添加代理节点或订阅链接。
4. 选择当前使用的节点。
5. 选择规则、全局代理或直连模式。
6. 点击连接。
7. 按 iOS 提示允许添加 VPN 配置。

iOS 会要求用户明确授权 VPN 配置，这是系统安全机制，任何使用 VPN 能力的 App 都需要这个步骤。

## 隐私说明

VPNova 设计上不需要后端服务器。

- 不包含第三方统计 SDK
- 不包含广告 SDK
- 不包含追踪 SDK
- 不需要 VPNova 账号
- 不内置代理服务器
- 节点、规则、DNS 等配置保存在本机
- 网络流量只会根据用户配置路由到用户自己的代理服务器

完整隐私说明见 [PRIVACY.md](PRIVACY.md)。

## 校验 IPA

下载 IPA 后建议校验 SHA-256：

```sh
shasum -a 256 VPNova-vX.Y.Z.ipa
```

把输出结果和 Release 页面提供的 SHA-256 值对比，确认文件没有损坏或被替换。

## 反馈问题

你可以通过 GitHub Issues 反馈：

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

## 重要说明

公开分发 IPA 和源码开源不是同一件事。本仓库只负责公开安装包和文档，不代表 VPNova 的应用源码已经公开。

另外，VPNova 使用 sing-box/libbox 作为代理核心。sing-box 项目使用 GPL 系列许可证。公开分发包含该组件的 IPA 前，需要认真确认许可证合规义务，例如许可证文本、版权说明、对应源码或构建说明等要求。

相关说明见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

## 免责声明

VPNova 是一个工具型客户端。用户应自行确认所在地区的法律法规、网络使用规则、Apple 账号和签名方式的合规性。

请只连接你拥有、管理或被授权使用的代理服务器。不要将 VPNova 用于违法、侵权、攻击、滥用或绕过未授权访问控制的行为。
