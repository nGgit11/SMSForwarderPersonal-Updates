# SMS Forwarder Personal - downloads

Application source remains private. This repository contains signed APK downloads and public update metadata only.

## Current release: 1.4.1 (7)

[Download version 1.4.1](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.4.1/app-release.apk) or open the installed app's **Settings > Check for updates**.

Update over your existing release installation without uninstalling to retain settings and history. If Android asks for installation permission, allow it, return to the app and tap **Install downloaded update** again.

### What's new

- Long OTP-like messages default to independent numbered compatibility SMS. Other long messages retain joined mode.
- Settings can disable OTP compatibility or select exact sender IDs to send separately. Short messages use the same single-SMS method in either mode.
- The outbox now says **Carrier reports delivery**. A network receipt does not prove that the receiving phone displayed or saved the text. Report interpretation explicitly distinguishes GSM/CDMA received codes, pending statuses and uncertain outcomes.
- Private diagnostics now correlate incoming/outgoing IDs and show the actual send API, source message class/part count, chosen policy and carrier report format/status.
- Existing settings, queue history, sender overrides, promo controls and monitoring notification are preserved. Accepted messages are not automatically resent.

Recipient-side disappearing messages remain under investigation. Compatibility mode is a transport alternative, not a confirmed fix. A reported single-part verification message already used the normal single-SMS method, so changing multipart settings does not alter that path.

Unit tests, debug/release lint and signed release packaging passed. Device tests compile; no connected phone was available for execution. Real-phone recipient visibility still needs validation.

## Verification

The app checks APK SHA-256, package, version and the currently installed signing identity before opening Android's installer. Each release includes its own checksum metadata.

[Live update metadata](https://raw.githubusercontent.com/nGgit11/SMSForwarderPersonal-Updates/refs/heads/main/update.json)

## Earlier releases

The 1.3 to 1.3.1 OTA flow was confirmed on the user's phone. Earlier downloads remain available:

- [1.3 baseline](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)
- [1.3.1 OTA validation](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)
- [1.4 notifications, joined SMS and configurable filters](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4)

The live feed now offers 1.4.1. A debug build cannot accept these release-signed updates.

For problems, export diagnostics promptly and note the approximate source receipt time and actual recipient outcome. Do not share OTP values, private messages or phone numbers.
