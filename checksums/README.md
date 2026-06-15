# 校验值

公开安装包的 SHA-256 校验值可以放在这里，也可以直接写在对应 GitHub Release 中。

生成校验值：

```sh
shasum -a 256 VPNova-vX.Y.Z-平台.ipa
shasum -a 256 VPNova-vX.Y.Z-android-buildN-unsigned.apk
```

推荐格式：

```text
<sha256>  VPNova-vX.Y.Z-平台.ipa
<sha256>  VPNova-vX.Y.Z-android-buildN-unsigned.apk
```
