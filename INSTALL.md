# VPNova IPA Installation Guide

This guide explains common ways to install a public VPNova IPA on iPhone or iPad.

## Before You Start

You need:

- An iPhone or iPad running iOS/iPadOS 15.0 or later
- The latest `VPNova-vX.Y.Z.ipa` from GitHub Releases
- A trusted sideloading or signing method
- Your own proxy node or subscription link

VPNova does not include any built-in proxy servers.

## Option 1: AltStore

1. Install AltStore on your computer and iOS device.
2. Download the latest VPNova IPA from GitHub Releases.
3. Open AltStore on the iOS device.
4. Tap `My Apps`.
5. Tap `+`.
6. Select the downloaded VPNova IPA.
7. Wait for installation to finish.
8. Open VPNova and allow VPN configuration when prompted.

If using a free Apple ID, AltStore apps usually need to be refreshed periodically.

## Option 2: Sideloadly

1. Install Sideloadly on your computer.
2. Connect your iPhone or iPad with USB.
3. Download the latest VPNova IPA from GitHub Releases.
4. Drag the IPA into Sideloadly.
5. Sign with your Apple ID or developer account.
6. Start the install.
7. Trust the developer profile on the device if iOS asks.
8. Open VPNova and allow VPN configuration when prompted.

## Option 3: Xcode

This option is mostly useful for developers.

1. Connect your iPhone or iPad to your Mac.
2. Open Xcode.
3. Use `Devices and Simulators`.
4. Select the device.
5. Install the signed IPA.
6. Open VPNova on the device and grant VPN permission.

## First Launch

After installation:

1. Open VPNova.
2. Add a proxy node or subscription.
3. Select the active node.
4. Choose Rule, Global, or Direct mode.
5. Tap Connect.
6. Accept the iOS VPN permission prompt.

## Common Problems

### The App Cannot Be Installed

Possible causes:

- IPA is not signed correctly
- Provisioning profile does not match the device
- Device is not included in the developer profile
- The IPA was corrupted during download
- The iOS version is too old

### VPN Permission Does Not Appear

Possible causes:

- The app was not signed with the required NetworkExtension entitlement
- The installed build is not a proper device build
- The device has restrictions from MDM, Screen Time, or enterprise policy

### The App Opens But VPN Cannot Connect

Possible causes:

- Proxy node configuration is invalid
- Server is offline
- Credentials are wrong
- Subscription contains unsupported or malformed entries
- NetworkExtension profile was not created successfully

### Subscription Import Fails

Try:

- Confirm the subscription URL works in Safari
- Remove expired tokens before sharing logs
- Check whether the subscription is Clash, sing-box, Shadowrocket, or plain URI list format
- Try importing a single proxy URI first

## Security Tips

- Download IPA files only from the official release page.
- Always compare SHA-256 checksums when provided.
- Do not share subscription tokens, private keys, passwords, or QR codes publicly.
- Use only proxy servers you trust.
