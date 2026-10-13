# VScodroid-download

Unofficial VSCodroid test builds. Requires Android 13+ and ARM64.

## Codex stable backend/model catalog test (latest)

[**Download Codex models APK**](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-models-test/VSCodroid-codex-models.apk)

[ZIP alternative](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-models-test/VSCodroid-codex-models-install.zip) · [Release and checksums](https://github.com/faizeranoyodev/VScodroid-download/releases/tag/codex-models-test)

1. Force-stop your old VSCodroid apps, install this APK, and tap the installer's **Open** button. This separate app is `com.vscodroid.codexmodels`, version code 18; previous apps and data remain available.
2. Install Codex **26.908.40401**, disable automatic extension updates, and sign in. Use the terminal download and **Install from VSIX** instructions below if needed.
3. Run **Developer: Reload Window**, open a new Codex chat, and check the model picker for **GPT-6.1 Sol**.

The bundled backend is upgraded to stable **0.162.1** and its model catalog includes `gpt-6.1-sol`. It checks cache client version and authentication identity. The APK also retains all previous Android image picker, keyboard image paste and Codex startup fixes.

Build, unit tests, lint, Android signature/integrity and exact payload digests passed. The exact ARM64 binary from the APK passed the pinned extension's startup/config/model/auth/remote-control/filesystem requests and listed gpt-6.1-sol without sign-in. This checks client support; your actual account's available models still need confirmation on the phone.

If the model is still missing after sign-in and reload, run:

```sh
"$VSCODROID_NATIVE_LIB_DIR/libcodex.so" --version
"$VSCODROID_NATIVE_LIB_DIR/libcodex.so" debug models | python3 -c 'import json,sys; d=json.load(sys.stdin); print("\n".join(m["slug"] for m in d.get("models",[])))'
```

Send the version and short model list. Account/workspace availability may filter the returned catalog.

[Source and implementation](https://github.com/faizeranoyodev/VSCodroid/blob/529c39d7fdb411fa8e1f3ee8f652fc6f106f9333/docs/CODEX_ANDROID.md)

## Earlier Codex image input test

[**Download Codex images APK**](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-images-test/VSCodroid-codex-images.apk)

[ZIP alternative](https://github.com/faizeranoyodev/VScodroid-download/releases/download/codex-images-test/VSCodroid-codex-images-install.zip) · [Release and checksums](https://github.com/faizeranoyodev/VScodroid-download/releases/tag/codex-images-test)

1. Force-stop the previous VSCodroid app, install this APK, and use the installer's **Open** button. The new package is `com.vscodroid.codeximages`, version code 17; your previous app and data remain available.
2. Install Codex **26.908.40401** and disable automatic extension updates. Sign in again in the new app.
3. Open a Codex chat. Use **+** to choose an image/file from Android storage. For a keyboard image, tap the composer first, then tap an image in Gboard's clipboard.

If you need the exact extension version, run these in the new app's terminal:

```sh
mkdir -p ~/.codex
python3 -c 'import os,urllib.request; print("Downloading...",flush=True); urllib.request.urlretrieve("https://open-vsx.org/api/openai/chatgpt/alpine-arm64/26.908.40401/file/openai.chatgpt-26.908.40401@alpine-arm64.vsix",os.path.expanduser("~/codex.vsix")); print("Saved: ~/codex.vsix")'
```

Then open the Command Palette, choose **Extensions: Install from VSIX...**, and select `codex.vsix` in your home directory. Reload the window if requested.

This build routes Codex file-only attachment dialogs to Android's document picker and accepts keyboard-supplied PNG, JPEG, GIF and WebP images in focused extension composers. Each file is limited to 20 MB. It retains the working Codex startup and proposed API fixes.

Build, unit tests, lint, exact runtime/backend/patch hashes, APK integrity/signature and ARM64 Linux backend initialization checks passed. Actual gallery selection and keyboard insertion still need testing on your Android device. It does not add models absent from the backend catalog returned to your account/client.

[Source and implementation](https://github.com/faizeranoyodev/VSCodroid/blob/1a48c4dba066d2ea6a24e111cdc1d0dfeae600cf/docs/CODEX_ANDROID.md)

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
