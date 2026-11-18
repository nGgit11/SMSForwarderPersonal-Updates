# SMS Forwarder Personal — downloads

Application source remains private. This repository contains signed APK downloads and public update metadata only.

## Current release: 1.4 (6)

[Download version 1.4](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.4/app-release.apk) or open the installed app's **Settings → Check for updates**.

Update over 1.3.1 without uninstalling to retain settings and history. If Android asks for installation permission, allow it, return to the app and tap **Install downloaded update** again.

### What's new

- Ongoing status notification for the configured active SIM routes; optional in Settings.
- Standard joined multipart SMS by default for new messages. Numbered separate-message compatibility mode remains available.
- Optional SMS-friendly punctuation and improved sizing diagnostics. A joined bubble can still contain multiple billable SMS segments.
- Visible default promotional categories with individual switches, including loan/extra-cash and credit/card ads.
- Personal literal words/phrases, one per line, with branded-only or all-sender scope.
- Sender overrides, important-message protection, private diagnostics and failure notifications remain.
- Database migration preserves existing queue entries. Partial or uncertain joined sends require review rather than blind retries.

Release lint and all 24 JVM unit tests pass. Device tests compile; real-phone notification, joining and carrier behavior still need testing. If a carrier/iPhone has trouble with joined messages, disable **Join long SMS** to restore compatibility sending.

## Verification

The app checks APK SHA-256, package, version and the currently installed signing identity before opening Android's installer. Each release includes its own checksum metadata.

[Live update metadata](https://raw.githubusercontent.com/nGgit11/SMSForwarderPersonal-Updates/refs/heads/main/update.json)

## Earlier update test

The 1.3 → 1.3.1 OTA flow was confirmed on the user's phone. Those downloads remain available:

- [1.3 baseline](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)
- [1.3.1 OTA validation](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)

The live feed now offers 1.4. A debug build cannot accept these release-signed updates.

For problems, use the app's diagnostic export. Do not share OTPs, private messages or phone numbers.
