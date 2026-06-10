# VPNova 版本与功能

这个文件用于单独展示公开 IPA 的版本号、构建号、新增功能、修复内容和已知问题。主页 README 会链接到这里，方便用户快速查看每个版本的变化。

## 当前公开版本

最新版本：`v1.0.0-build2`

下载地址：

- Release：https://github.com/zhongaiyemaozi/vpnova/releases/tag/v1.0.0-build2
- IPA：`VPNova-v1.0.0-build2.ipa`
- SHA-256：`ca62916d4f43277eca9dc0f189c5022d9233b5bf00ad80e6bac78dfd776075ad`

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
