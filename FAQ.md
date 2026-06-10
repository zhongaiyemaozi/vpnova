# VPNova FAQ

## Is VPNova open source?

No. This repository is for public IPA distribution and release support only. It does not contain the VPNova application source code.

## Why is the IPA not on the App Store?

VPN and proxy apps can be difficult to publish through the App Store when using personal developer accounts and NetworkExtension capabilities. This repository provides an alternative public distribution channel for users who can install signed IPA files themselves.

## Does VPNova include free proxy servers?

No. VPNova is a client. You need to provide your own proxy server, subscription, or configuration URI.

## Is VPNova a full VPN service?

VPNova uses iOS VPN APIs to create a local tunnel and route traffic through user-configured proxy nodes. It is not a hosted VPN service and does not sell server access.

## Can I install it without a computer?

That depends on your signing method and iOS environment. Many sideloading workflows require a computer, developer account, enterprise profile, or third-party signing service.

## Why does iOS ask me to allow VPN configuration?

iOS requires user approval before any app can add or manage a VPN profile. VPNova needs this permission to create the Packet Tunnel used for proxy routing.

## Can I use subscription links?

Yes, the app is designed to support common subscription formats, including Shadowrocket-style base64 lists, Clash YAML, sing-box JSON, and plain URI lists.

## Where should I report bugs?

Open a GitHub Issue in this repository and include app version, iOS version, device model, installation method, and clear reproduction steps.

Do not post secrets, passwords, proxy credentials, private keys, subscription tokens, or QR codes in public issues.
