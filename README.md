# SMS Forwarder Personal downloads

Application source remains private. This repository contains signed APK downloads and public update metadata only.

## Current release 1.6

[Download version 1.6](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.6/app-release.apk), or open the installed app's **Settings > App updates > Check for updates**. On older versions, Check for updates is directly in Settings.

Update over your existing release installation without uninstalling to retain destinations, overrides and history. If Android asks for installation permission, allow it, return to the app and tap Install downloaded update again. A debug build cannot accept these release-signed updates.

## Changes in version 1.6

- Improved credit/cash-advance and starter-pack promo filtering. Authentication, actual transaction notices and successful subscription confirmations remain protected.
- Optional seven-day suppression of repeated non-critical branded text on the same incoming SIM and destination. Different codes and important confirmations are exempt. Existing sender overrides retain priority.
- HIFIN added to the visible verification-sender defaults, alongside AUTHMSG, TWVerify, VerifyTWL, VONAGEVFY, PIN and NOTICE. Defaults can be disabled and additional exact IDs added.
- Settings separated into focused pages, with Save report at the top of Diagnostics.
- Optional short numeric verification-code format, off by default. Read warnings and expiry on the source phone when using it.
- Optional missed-call SMS alerts, off by default. Select a saved destination in Settings, enable alerts and grant Android notification access. Caller details depend on the Phone app, and SMS charges apply.
- New content-free diagnostic fields for repeated messages, short-code formatting and missed-call configuration.

Tonik compatibility, native joined long messages, web-link removal and existing destination settings remain available. Accepted messages are not automatically resent. Unknown/new brands still receive content-based protection and conservative forwarding. Sender-list membership is forwarding priority, not proof of identity or a complete OTP-provider directory.

## Delivery and phone testing

The reported Lazada attempts were captured but received a negative carrier report; HIFIN received a successful carrier report while the user reported no visible message. Filtering improvements and optional formatting do not guarantee recipient display.

Check actual receipt on both Android and iPhone. Request fresh authentication messages; do not replay expired codes. For missed calls, test a new missed call after enabling the feature and access, then verify alerts stop when disabled. Hidden caller details, group-summary-only dialers and manufacturer restrictions can limit alerts. Old calls are not scanned, and no call-log permission is used.

Android grants broad notification access, but this feature processes only Phone-app missed-call notifications. Other apps' notifications are ignored. Queued call alerts expire after one hour and are cancelled before dispatch if alerts are disabled or access is revoked.

Unit tests, debug/release lint, Android test APK compilation and signed release packaging passed. No connected phone/emulator was available to execute device tests. Real carrier acceptance and recipient visibility require phone testing.

## Verification and earlier releases

The app checks APK SHA-256, package, announced version and installed signing identity before opening Android's installer. Each release includes checksum metadata.

[Live update metadata](https://raw.githubusercontent.com/nGgit11/SMSForwarderPersonal-Updates/refs/heads/main/update.json)

- [1.5 verification senders and link removal](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.5)
- [1.4.1 OTP compatibility and receipt wording](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4.1)
- [1.4 notifications and configurable filters](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4)
- [1.3.1 OTA validation](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)
- [1.3 baseline](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)

For a problem, save a diagnostic report and note the approximate time, sender ID and actual recipient outcome. Do not share OTP values, private messages or phone numbers.
