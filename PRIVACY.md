# VPNova Privacy Statement

Effective date: 2026-06-10

VPNova is designed as a local iOS/iPadOS proxy utility. It does not require a VPNova account or a VPNova backend server.

## Data Collection

VPNova does not collect personal data.

VPNova does not include:

- Third-party analytics SDKs
- Advertising SDKs
- Tracking SDKs
- A user account system
- A backend telemetry service

## Local Data

The app may store the following data locally on your device:

- Proxy node configurations
- Routing rules
- DNS settings
- App preferences
- Traffic counters
- Subscription URLs added by you

Sensitive proxy credentials should be stored using secure local storage where supported by the app build.

## Network Traffic

VPNova routes network traffic according to the proxy servers and rules configured by you.

VPNova does not provide proxy servers and does not operate a proxy backend. The owner of the proxy server you configure may be able to observe traffic routed through that server. Use only servers you trust and have permission to use.

## Permissions

VPNova may request:

- VPN permission: required to create and manage the local VPN tunnel
- Camera permission: optional, used only to scan QR codes for proxy node import

If camera access is denied, QR code scanning will not work, but manual import can still be used.

## Third-Party Services

The app may connect to URLs that you explicitly provide, such as proxy subscription URLs or DNS-over-HTTPS endpoints. VPNova does not control those services.

## Contact

Use GitHub Issues in this release repository for privacy questions related to the public IPA distribution. Do not include secrets, credentials, subscription tokens, private keys, or personal data in public issues.
