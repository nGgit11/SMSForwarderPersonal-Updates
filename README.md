# SMS Forwarder Personal downloads

Application source remains private. This repository contains signed APK downloads and public update metadata only.

## Current release 1.9

[Download version 1.9](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.9/app-release.apk), or open the installed app's **Settings > App updates > Check for updates**. On older versions, Check for updates is directly in Settings.

Update over your existing release installation without uninstalling to retain destinations, overrides and history. If Android asks for installation permission, allow it, return to the app and tap Install downloaded update again. A debug build cannot accept these release-signed updates.

## Changes in version 1.9

- Per-SIM ringing-state tracking supplements notification metadata to route missed-call alerts to the matching saved SMS destination. The global Sending SIM preference still controls sending.
- Unknown or conflicting incoming-SIM evidence is labeled SIM unknown and uses the selected fallback. Diagnostics show state evidence and fallback use.
- Duplicate summary, child, enriched and reminder notifications are suppressed using retained call history. Distinct observed ringing sessions remain separate.
- Dotted contact names are preserved in generated call alerts. Ordinary SMS web-link filtering remains enabled.
- No new Android permissions or database migration. Update in place to keep settings and history.

After updating, open Settings > Missed-call alerts and choose Reconnect listener. Clear old Phone notifications, miss one call to each source SIM and verify one alert at each matching destination. Actual SIM/OEM behavior still needs phone validation. If routing falls back, export a new report promptly.

## Changes in version 1.8

- Missed-call status shows listener connection, Phone notifications seen, missed notifications recognized, unique alerts saved and the latest reason. Reconnect listener and a separate missed-call log help diagnose failures without exporting caller text.
- Capture supports Phone notifications with missing categories/timestamps and fresh single-call summaries. Old, aggregate and ongoing notifications produce skip reasons. The prior report proved connection but did not identify the rejection condition, so actual phone testing remains necessary.
- Received voucher/reward notices are protected before promo words; invitations to earn a future voucher remain filterable.
- New Network and SIM offers rules cover order-today, WiFi sales, load/top-up and GB/UNLI marketing. Product names alone do not block confirmed transactions. The category can be disabled, and sender overrides retain priority.
- One Save report & diagnostics entry replaces duplicate Settings links. Diagnostics has one Save diagnostic report button beside Clear all logs, expandable sections and newest-first events. Current section headers remain reachable while scrolling.
- Log clearing preserves core message/delivery records, pending queue work, settings and duplicate protection.
- Messages & delivery separates Captured, Queued, Delivery and Filtered. Opening Queued or returning to it automatically rechecks eligible work, respecting global stop and uncertain-send protections.
- Recheck & queue on a filtered message applies current rules without allowlisting its sender. Use it for the earlier Maya voucher if still within expiry; old messages are not automatically resent.

After updating, clear old Phone missed-call notifications, open Missed-call alerts, request Reconnect listener and miss a fresh single call. Compare Seen, Recognized and Saved counts, then actual receipt and Messages & delivery. If it still fails, export a new report promptly; version 1.7 lacked the necessary rejection events.

No new permissions are added. The database upgrade preserves records. Existing forwarding destinations, sender overrides, remote STOP/START and compatibility options remain intact.

## Changes introduced in version 1.7

Missed-call alerts now offer **Follow incoming SIM**. Identified SIM 1 calls use the saved SIM 1 SMS destination; identified SIM 2 calls use the SIM 2 destination. Missing/conflicting metadata uses your selected fallback. All alerts use the global Sending SIM preference; one active SIM follows the existing first-destination behavior. Some Phone apps omit SIM metadata, so test both routes on your device.

**Remote stop & start** is optional and off until configured in Settings. Save two different ten-character printable secrets, or generate random ones. Commands are ordinary SMS to either SIM number in the source phone:

```text
SFSTOP <STOP secret>
SFSTART <START secret>
```

Use one space after the command label and replace the placeholder with your exact secret. Letters, numbers, symbols and printable Unicode are supported; secrets are case-sensitive. The short command label is additional to the ten-character secret. RCS/chat does not trigger this receiver.

STOP turns global forwarding off and discards earlier unsent SMS/call alerts. START resumes future forwarding with existing routes and sending SIM. The command receiver remains active while forwarding is off. A shared sending lock and persistent stop cutoff prevent old queue work or late failure callbacks from reviving discarded sends. An already-submitted SMS cannot be recalled.

START must have a fresh SMS timestamp after the most recent applied command and arrive within ten minutes. Wait a few seconds after STOP before sending a newly composed START. Duplicate receipts and older START timestamps are rejected. Static secrets can be reused by anyone who knows them.

Only salted verification hashes are stored. Once configured, command messages are withheld from app forwarding/history even when incorrect, malformed or disabled. No acknowledgement SMS is sent. Reports omit secrets and verifiers.

The source phone must receive SMS and be allowed to run. Network delay, force-stop, uninstalling or revoked SMS permission can prevent remote control. Android Messages and the sending phone may retain command copies. Keep the START secret away from a destination phone that may be lost, and replace a lost destination before resuming. This controls forwarding; it is not a remote wipe.

No new Android permissions are added. Existing forwarding destinations, sender overrides, Tonik and long-message settings remain intact. Test STOP, a wrong START, a fresh valid START and both call routes before relying on the feature.

## Changes introduced in version 1.6

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

- [1.8 capture diagnostics and message review](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.8)
- [1.7 remote control and incoming-SIM call routing](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.7)
- [1.6 filtering, repeated offers and missed calls](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.6)
- [1.5 verification senders and link removal](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.5)
- [1.4.1 OTP compatibility and receipt wording](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4.1)
- [1.4 notifications and configurable filters](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4)
- [1.3.1 OTA validation](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)
- [1.3 baseline](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)

For a problem, save a diagnostic report and note the approximate time, sender ID and actual recipient outcome. Do not share OTP values, private messages or phone numbers.
