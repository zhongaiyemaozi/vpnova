# 更新日志

这里记录 VPNova 公开 IPA 版本的主要变化。

## [Unreleased]

- 准备公开 IPA 发布仓库。
- 添加中文主 README 和英文 README。
- 添加 `VERSIONS.md`，单独展示版本号、构建号、新增功能和已知问题。
- 添加安装指南、隐私说明、常见问题、安全说明、第三方组件说明。
- 添加 GitHub Release 模板和 Issue 模板。

## [1.0.0-build3] - 2026-06-12

Apple 平台未签名二次签名包发布。

版本策略：

- Apple 平台 `MARKETING_VERSION` 固定为 `1.0.0`
- 后续 Apple 发布只递增 build 号

包含：

- iOS/iPadOS 未签名 IPA
- macOS 未签名 PKG
- macOS 未签名 ZIP
- tvOS 未签名 IPA
- visionOS 未签名 IPA
- `SHA256SUMS.txt`
- Release notes

说明：

- iOS、macOS、tvOS 的 VPN 功能需要重签账号具备 NetworkExtension `packet-tunnel-provider` 权限。
- visionOS 当前为共享 UI/Core shell，不包含 PacketTunnel 运行时。

## [1.0.0-build2] - 2026-06-10

第一个公开 IPA 版本。

发布类型：未签名二次签名包。

包含：

- 节点管理
- 规则、全局代理、直连模式
- 常见代理协议导入
- 规则路由
- DNS 配置
- 实时流量统计
- 原生 iOS/iPadOS 界面
