# SMS Forwarder Personal - downloads

Application source remains private. This repository contains signed APK downloads and public update metadata only.

## Current release: 1.5 (8)

[Download version 1.5](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.5/app-release.apk) or open the installed app's **Settings > Check for updates**.

Update over the existing release installation without uninstalling to retain settings and history. If Android asks for installation permission, allow it, return to the app and tap **Install downloaded update** again.

### What's new

- **Important verification senders:** visible defaults AUTHMSG, TWVerify, VerifyTWL, VONAGEVFY, PIN and NOTICE; individual switches and a saved list for additional exact IDs. Existing sender overrides remain intact.
- **Remove web links:** enabled by default for newly prepared messages. Removes domain/path/query data and adds one short **[Link on source phone]** note. Original SMS stays on the source phone. Turning the option off restores the previous defanged-link format.
- **Local outgoing preview:** test example text and see the prepared body without sending an SMS.
- **Sender recognition:** normalizes case, invisible formatting and width differences for exact matching. Unknown/new brands are still processed and protected by OTP/important-content detection.
- **Reception diagnostics:** persistent broadcast counter, last-observed time and content-free parse/route events. Xiaomi/Redmi guidance points to Service SMS controls where available.
- Recipient wording covers both Android and iPhone. Tonik compatibility and native joined options remain. Destinations, settings and history are preserved; accepted messages are not automatically resent.

Sender-list membership is forwarding priority, not authentication. There is no complete fixed directory of every sender a verification provider may use. AUTHMSG, TWVerify and VerifyTWL are documented by [Twilio](https://help.twilio.com/articles/19753651809947-Alphanumeric-Sender-ID-for-Verify-and-Authy); the other defaults reflect observed verification tests.

The Xiaomi AuthMSG capture gap still needs phone validation. A sender list cannot capture a message Android never broadcasts to the app. Check [Xiaomi Other permissions / Service SMS guidance](https://www.mi.com/global/support/faq/details/KA-497760/) where supported and verify SMS versus RCS. No new permissions or automatic inbox scanning are introduced.

Link removal is supported by a user comparison where manual forwarding without a URL arrived. It is not a guarantee against all carrier/recipient filtering. Carrier reports still do not prove the receiving phone displayed or saved a message.

Unit tests, debug/release lint and signed packaging passed. Android test APK compiles; no connected phone was available to execute device tests. Real recipient visibility requires phone testing.

## Verification

The app checks APK SHA-256, package, version and installed signing identity before opening the Android installer. Each release includes checksum metadata.

[Live update metadata](https://raw.githubusercontent.com/nGgit11/SMSForwarderPersonal-Updates/refs/heads/main/update.json)

## Earlier releases

- [1.3 baseline](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)
- [1.3.1 OTA validation](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)
- [1.4 notifications, joined SMS and configurable filters](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4)
- [1.4.1 OTP compatibility and carrier receipt wording](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.4.1)

The live feed now offers 1.5. A debug build cannot accept these release-signed updates.

For problems, export diagnostics promptly and note the approximate source receipt time, sender ID and actual recipient outcome. Do not share OTP values, private messages or phone numbers.
