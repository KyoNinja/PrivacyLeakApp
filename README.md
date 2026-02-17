# Privacy Leak - Public Releases

Public distribution repository for signed APK releases of Privacy Leak.

The source code is maintained in a private repository. This public repository is used to publish release binaries, checksums, and changelog history.

## Release Download Counter

[![Latest Version](https://img.shields.io/github/v/release/KyoNinja/PrivacyLeakApp?style=for-the-badge&label=Latest%20Version)](../../releases/latest)
[![Total Downloads](https://img.shields.io/github/downloads/KyoNinja/PrivacyLeakApp/total?style=for-the-badge&label=Total%20Downloads)](../../releases)
[![Latest Release Downloads](https://img.shields.io/github/downloads/KyoNinja/PrivacyLeakApp/latest/total?style=for-the-badge&label=Latest%20Release%20Downloads)](../../releases/latest)

Detailed chart/table tracker:
- https://somsubhra.github.io/github-release-stats/?username=KyoNinja&repository=PrivacyLeakApp

## Features

- ✅ Automatic login (email/password) with Cloudflare Turnstile
- ✅ Turnstile preloading/refresh on login screen with retry handling for captcha/HTTP 400 failures
- ✅ List followed profiles
- ✅ Download photos in highest available quality with smart fallback
- ✅ Automatic overwrite when remote photo is larger than local existing file
- ✅ Download videos (direct MP4 and HLS with decryption)
- ✅ Media source selection: Profile Feed, Purchased, Chat, or All
- ✅ Media type selection: Photos, Videos, or Both
- ✅ Real-time progress tracking with speed, ETA, and activity log
- ✅ Dedicated Debug Log (separate from activity log) with copy/share support for troubleshooting
- ✅ Organized storage: Downloads/PrivacyLeak/{profile}/fotos|videos
- ✅ Multi-language support (English and Portuguese)
- ✅ Optional TS-to-MP4 conversion for HLS videos via FFmpegKit (stream copy, no re-encoding)
- ✅ GitHub Releases update check and one-tap update action from the app

## Download

1. Open the [Releases](../../releases) page.
2. Download the latest `PrivacyLeak-vX.Y.Z-release.apk`.
3. (Optional) Download `PrivacyLeak-vX.Y.Z-release.apk.sha256` to verify integrity.

## Verify APK Integrity

Use SHA-256 to confirm the APK matches the published checksum.

Example (PowerShell):

```powershell
Get-FileHash .\PrivacyLeak-vX.Y.Z-release.apk -Algorithm SHA256
```

Compare the resulting hash with the value inside `PrivacyLeak-vX.Y.Z-release.apk.sha256`.

## Changelog

Full release history is available in [`CHANGELOG.md`](CHANGELOG.md).

## Source and Automation

- Source repository: private
- Public release publishing: GitHub App bot automation
- Assets published per version:
  - `PrivacyLeak-vX.Y.Z-release.apk`
  - `PrivacyLeak-vX.Y.Z-release.apk.sha256`
