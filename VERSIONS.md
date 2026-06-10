# VPNova 版本与功能

这个文件用于单独展示公开 IPA 的版本号、构建号、新增功能、修复内容和已知问题。主页 README 会链接到这里，方便用户快速查看每个版本的变化。

## 当前公开版本

暂未发布 IPA。

首次 IPA 完成后，会在这里更新版本信息，并同步上传到 GitHub Releases：

https://github.com/zhongaiyemaozi/vpnova/releases

## v1.0.0 build TBD

状态：计划发布

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

- IPA 暂未发布
- 侧载安装效果取决于签名方式、描述文件、设备和账号权限
- NetworkExtension 能力需要正确签名和授权

### 下载

发布后会提供：

- IPA 下载链接
- SHA-256 校验值
- Release notes

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
