# VPNova

> Apple-platform rule-based proxy client - public package release page

[简体中文](README.md) | [Versions](VERSIONS.md) | [Installation](INSTALL.md) | [Privacy](PRIVACY.md) | [FAQ](FAQ.md) | [Issues](https://github.com/zhongaiyemaozi/vpnova/issues) | [Releases](https://github.com/zhongaiyemaozi/vpnova/releases)

VPNova is an Apple-platform rule-based proxy utility client. Current public packages cover iOS/iPadOS, macOS, tvOS, and visionOS. It helps users manage their own proxy nodes and route traffic by domain, IP, geolocation, and fallback rules.

**This repository is used only for public package distribution, release notes, installation guidance, privacy information, and issue feedback. The VPNova app source code is not published in this repository.**

## Current Status

This repository is prepared as the public release entry for VPNova. Public packages are published through [GitHub Releases](https://github.com/zhongaiyemaozi/vpnova/releases).

Version numbers, build numbers, new features, and known issues are tracked separately in [VERSIONS.md](VERSIONS.md).

Current packages are unsigned/resignable builds. They cannot be assumed to install directly; users must re-sign them with their own Apple certificate, provisioning profiles, and entitlements.

Each release should include:

- `VPNova-v1.0.0-buildN-iOS.ipa` - iOS/iPadOS package
- `VPNova-v1.0.0-buildN-macOS.pkg` - macOS installer
- `VPNova-v1.0.0-buildN-macOS.zip` - macOS app archive
- `VPNova-v1.0.0-buildN-tvOS.ipa` - tvOS package
- `VPNova-v1.0.0-buildN-visionOS.ipa` - visionOS package
- `SHA256SUMS.txt` - SHA-256 checksums
- Release notes - changes, compatibility, and known issues

Install packages should be uploaded as GitHub Release assets instead of committed to Git history.

## Product Positioning

VPNova is a local proxy client, not a hosted VPN service.

VPNova does not provide proxy servers, sell proxy nodes, include a VPNova account system, or depend on a VPNova backend. You need to provide your own proxy server, subscription, or configuration URI.

Good use cases:

- Manage personal proxy nodes and subscriptions
- Route domains or IP ranges through proxy, direct, or reject policies
- Test network connectivity on iPhone, iPad, Mac, Apple TV, or Apple Vision devices
- Use local proxy tooling for development, debugging, and network research
- Import existing node URIs, QR codes, or subscription links

Not intended for:

- Acting as a commercial VPN service with built-in servers
- Automatically providing free proxy nodes
- Sharing passwords, private keys, subscription tokens, or QR configurations in public issues
- Illegal, abusive, or unauthorized network activity

## Core Features

VPNova v1.0 focuses on the core proxy experience:

- Node management: manual input, URI paste, QR scan, subscription import
- Protocol support: Shadowsocks, VMess, VLESS, Trojan, Hysteria2, TUIC, WireGuard, SOCKS5, HTTP, and HTTPS proxy
- Proxy modes: Rule, Global Proxy, and Direct
- Rule engine: `DOMAIN`, `DOMAIN-SUFFIX`, `DOMAIN-KEYWORD`, `GEOIP`, `IP-CIDR`, and `FINAL`
- DNS: custom DNS and DNS over HTTPS
- Traffic stats: real-time upload/download speed and usage
- Native SwiftUI experience: iPhone/iPad, Mac, Apple TV, Apple Vision, dark mode, light mode, English, and Simplified Chinese

## Supported Platforms

| Platform | Package | Status |
| --- | --- | --- |
| iOS/iPadOS 15.0+ | `.ipa` | Main app + PacketTunnel |
| macOS 13.0+ | `.pkg` / `.zip` | Main app + PacketTunnel |
| tvOS 17.0+ | `.ipa` | Main app + PacketTunnel |
| visionOS 1.0+ | `.ipa` | Shared UI/Core shell only; no PacketTunnel runtime yet |

## Download And Install

Get the latest packages from:

- [Latest release](https://github.com/zhongaiyemaozi/vpnova/releases/latest)
- [All releases](https://github.com/zhongaiyemaozi/vpnova/releases)

Because VPNova is distributed outside the App Store, installation depends on your own signing or sideloading method.

Common options:

- AltStore
- Sideloadly
- Apple Configurator
- Xcode device install
- Enterprise or personal developer signing, where legally available

See [INSTALL.md](INSTALL.md) for details.

## Compatibility

- Device: iPhone, iPad, Mac, Apple TV, or Apple Vision
- System: iOS/iPadOS 15.0+, macOS 13.0+, tvOS 17.0+, or visionOS 1.0+
- VPN permission: required on iOS/iPadOS, macOS, and tvOS to add the system VPN configuration
- Camera permission: optional, used only for QR code node import

VPN behavior must be validated on physical devices. Simulators cannot fully test Packet Tunnel behavior. The current visionOS public package does not include the PacketTunnel runtime.

## Privacy

VPNova is designed to work without a backend server.

- No analytics SDK
- No advertising SDK
- No tracking SDK
- No VPNova account
- No built-in proxy service
- Proxy configurations are stored locally on the device
- Network traffic is routed only through proxy servers configured by the user

Read [PRIVACY.md](PRIVACY.md) for details.

## Feedback

Use [GitHub Issues](https://github.com/zhongaiyemaozi/vpnova/issues) for installation problems, crashes, import failures, VPN connection problems, UI issues, and compatibility reports.

Do not post proxy passwords, subscription tokens, private keys, server credentials, QR configurations, or Apple signing files in public issues.

## Source And License Notice

Public package distribution is not the same as open-sourcing the application source code. This repository publishes release assets and documentation only.

VPNova uses sing-box/libbox as its proxy engine. sing-box uses a GPL-family license. Before publishing packages that include sing-box/libbox, review the license obligations carefully, including license text, copyright notices, corresponding source requirements, or build instruction requirements.

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for more information.
