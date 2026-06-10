# 第三方组件说明

这个仓库用于发布 VPNova IPA 和相关文档。IPA 可能包含第三方开源组件。

## sing-box / libbox

VPNova 使用 sing-box/libbox 作为 iOS NetworkExtension 中的代理核心。

- 项目地址：https://github.com/SagerNet/sing-box
- 文档地址：https://sing-box.sagernet.org/
- 许可证提示：sing-box 的项目元数据标识其许可证为 `GPL-3.0-or-later`。

公开分发包含 sing-box/libbox 的 IPA 前，需要认真确认许可证义务。根据实际链接、修改和分发方式，可能需要提供对应源码、许可证文本、版权说明、构建说明或其他合规分发方式。

这个文件不是法律意见。正式公开发布前，请确认最终分发方式满足相关许可证要求。

## 后续维护

每次公开发布时，建议补充：

- 第三方组件名称
- 版本号或 commit
- 许可证
- 源码地址
- 必须保留的 notice 文本
- 许可证要求的源码提供方式或构建说明
