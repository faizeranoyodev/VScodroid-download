# VScodroid-download

Unofficial VSCodroid test builds. Requires Android 13+ and ARM64.

## Codex startup test

[**Download Codex test APK**](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-startup-test/VSCodroid-codex-fix.apk)

[ZIP alternative](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-startup-test/VSCodroid-codex-fix-install.zip) · [Release and checksums](https://github.com/faizeranoyodev/VScodroid-download/releases/tag/codex-startup-test)

1. Force-stop your previous VSCodroid app, then install and open this APK. It installs separately as `com.vscodroid.codextest`, preserving the previous app and its files.
2. In the new app's terminal, run `mkdir -p ~/.codex`.
3. Install Codex extension **26.908.40401**, disable its automatic updates, then open Codex and sign in.

This build packages the matching Codex backend in Android's permitted executable directory and enables its proposed APIs. It also includes the earlier image attachment fix. Build, unit tests, lint, APK signature/integrity, payload digests and ARM64 Linux backend initialization checks passed. Actual Android device testing is still needed. Approval and sandbox settings remain unchanged; Android may impose additional restrictions on Linux tools.

[Source and implementation](https://github.com/faizeranoyodev/VSCodroid/blob/59ba1ec4aa9a3f894c38d05bbbd4f941fddc2305/docs/CODEX_ANDROID.md)

## Earlier image attachment test

[Download image fix APK](https://github.com/faizeranoyodev/VScodroid-download/releases/download/image-fix-test/VSCodroid-image-fix.apk) · [ZIP alternative](https://github.com/faizeranoyodev/VScodroid-download/releases/download/image-fix-test/VSCodroid-image-fix-install.zip)

Installs as `com.vscodroid.debug`. The earlier build addresses gallery image selection and image clipboard support but does not include the Codex startup changes. Isolated extension composers may require further fixes.

[Original VSCodroid project](https://github.com/rmyndharis/VSCodroid)
