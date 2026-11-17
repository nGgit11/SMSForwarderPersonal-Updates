# SMS Forwarder Personal — downloads

This public repository contains signed APK downloads and update metadata only. Application source and signing credentials remain private.

## Test the in-app update

1. Stop forwarding and uninstall the previous unstable app if you want a fresh start. This clears app settings and app history.
2. **Install [version 1.3 (4)](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/download/v1.3/app-release.apk) first.**
3. Open the app, grant SMS/phone permissions and go to Settings.
4. Confirm version **1.3 (4)**, then tap **Check for updates**.
5. Download the offered **1.3.1 (5)**. Tap **Install downloaded update**; if Android requests permission, allow it, return and tap Install again.
6. Confirm Android's update without uninstalling 1.3.
7. Settings should now show **1.3.1 (5)**. Another update check should say it is current.

Both releases have the same verified signing identity. Version 1.3.1 intentionally keeps the forwarding behavior unchanged so the test isolates updating and preference retention.

## Downloads

- [1.3 — install first for the test](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3)
- [1.3.1 — current release](https://github.com/nGgit11/SMSForwarderPersonal-Updates/releases/tag/v1.3.1)
- [Live update metadata](https://raw.githubusercontent.com/nGgit11/SMSForwarderPersonal-Updates/refs/heads/main/update.json)

Each release includes its APK and a metadata file containing its SHA-256. The app checks the checksum, package, version and installed signing identity before opening Android's installer.

## Troubleshooting

If the first check says current, check that you installed 1.3 rather than 1.3.1. If checking fails, open the metadata link on the phone to confirm connectivity. A debug build cannot accept these release-signed updates.

After the update test, configure a trusted destination and enable forwarding to test actual SMS delivery. Carrier delivery is not guaranteed. Use the app's private diagnostic export when reporting a problem; do not share OTPs or private messages.
