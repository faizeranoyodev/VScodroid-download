# VScodroid-download

[**Download the latest APK — build 19**](https://github.com/faizeranoyodev/VScodroid-download/releases/latest/download/VSCodroid-codex-paste-fix.apk)

Unofficial VSCodroid build for **Android 13+ / ARM64**. This repository keeps one release with one APK.

Codex startup, the GPT-6.1 Sol model picker, and image/file attachments through **+** work. **Clipboard image paste remains unresolved; use + for screenshots.**

## Install

1. Force-stop other VSCodroid apps, install this APK, and tap **Open**. Its package is `com.vscodroid.codexpaste`, version code **19**; your previously installed apps and data remain available.
2. Install Codex **26.908.40401**, disable automatic extension updates, and sign in.
3. Use **+** in the composer to attach screenshots or files.

If the exact extension version is missing from the marketplace, run this in the app's terminal:

```sh
mkdir -p ~/.codex
python3 -c 'import os,urllib.request; urllib.request.urlretrieve("https://open-vsx.org/api/openai/chatgpt/alpine-arm64/26.908.40401/file/openai.chatgpt-26.908.40401@alpine-arm64.vsix",os.path.expanduser("~/codex.vsix")); print("Saved: ~/codex.vsix")'
```

Open the Command Palette, choose **Extensions: Install from VSIX...**, select `~/codex.vsix`, and reload the window.

The bundled Codex backend is **0.162.1**. Build, unit tests, lint, APK signature/integrity and ARM64 backend checks passed.

APK SHA256: `cc04959d7ce0ee9b83d7511075569796e8d3a0374f8e7fef5328bc9fe233a9db`

[Source and setup details](https://github.com/faizeranoyodev/VSCodroid/blob/8950b3a592dadacacf364fa0e429d990748c66ff/docs/CODEX_ANDROID.md) · [Original project](https://github.com/rmyndharis/VSCodroid)
