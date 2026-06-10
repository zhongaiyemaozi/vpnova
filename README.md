# VPNova IPA Public Release

[简体中文介绍](README.zh-CN.md)

VPNova is an iOS/iPadOS rule-based proxy utility client. This repository is used only for public IPA distribution, release notes, installation guidance, privacy information, and issue feedback.

The app source code is not included in this repository.

## Download

Get the latest IPA from the GitHub Releases page:

- Latest release: `https://github.com/<your-github-username>/vpnova-ipa-release/releases/latest`
- All releases: `https://github.com/<your-github-username>/vpnova-ipa-release/releases`

After the GitHub repository is created, replace `<your-github-username>` with the real GitHub username or organization name.

## What VPNova Does

VPNova helps users configure their own proxy nodes and route network traffic through those nodes using clear, local rules.

Core features planned for the public IPA:

- Add proxy nodes manually, from URI text, from QR codes, or from subscription links
- Support common proxy protocols including Shadowsocks, VMess, VLESS, Trojan, Hysteria2, TUIC, WireGuard, SOCKS5, HTTP, and HTTPS proxy
- Switch between Rule, Global Proxy, and Direct modes
- Configure routing rules such as `DOMAIN`, `DOMAIN-SUFFIX`, `DOMAIN-KEYWORD`, `GEOIP`, `IP-CIDR`, and `FINAL`
- Configure custom DNS and DNS over HTTPS
- View real-time upload/download speed and traffic usage
- Use a native iOS interface with English and Simplified Chinese localization

VPNova does not provide proxy servers. You need to use your own servers, subscriptions, or configuration links.

## Installation

Because this IPA is distributed outside the App Store, installation depends on your own signing and sideloading method.

Common options:

- AltStore
- Sideloadly
- Apple Configurator
- Xcode device install
- Enterprise or personal developer signing, where legally available

See [INSTALL.md](INSTALL.md) for details.

## Compatibility

- Platform: iPhone and iPad
- Minimum system: iOS/iPadOS 15.0
- Network permission: VPN configuration permission is required
- Camera permission: optional, used only for QR code node import

VPN functionality must be tested on a physical iPhone or iPad. The iOS Simulator cannot fully validate Packet Tunnel behavior.

## Privacy

VPNova is designed to work without a backend server.

- No analytics SDK
- No advertising SDK
- No account system
- No built-in proxy service
- Proxy configurations are stored locally on the device
- Network traffic is routed only through proxy servers configured by the user

Read the full privacy statement in [PRIVACY.md](PRIVACY.md).

## Release Verification

For each public release, this repository should publish:

- `VPNova-vX.Y.Z.ipa`
- SHA-256 checksum
- Release notes
- Known issues
- Minimum supported iOS version

Checksums are listed in [checksums/](checksums/) when available.

To verify an IPA locally:

```sh
shasum -a 256 VPNova-vX.Y.Z.ipa
```

Compare the output with the checksum published in the matching release notes.

## Important Notes

- This repository is not an open-source source-code repository.
- Public distribution of an IPA may still require proper signing.
- Some sideloading tools may require refreshing the app periodically.
- VPN and NetworkExtension behavior may vary depending on certificate, provisioning profile, iOS version, and device policy.
- Do not use VPNova for illegal activity or for connecting to servers you do not own or have permission to use.

## Feedback

Use GitHub Issues for:

- Installation problems
- Import failures
- Protocol parsing bugs
- UI issues
- Crash reports
- Compatibility reports for specific iOS versions

When reporting a problem, include:

- VPNova version
- iOS/iPadOS version
- Device model
- Installation method
- A clear description of what happened
- Screenshots or logs if available, with secrets removed

Do not post proxy passwords, subscription tokens, private keys, server credentials, or personal data in public issues.

## License And Source Notice

The documentation in this repository is provided for public release support. The VPNova app binary may include third-party open-source components. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for notices and compliance notes.

The VPNova application source code is not published in this repository unless explicitly stated in a future release.
