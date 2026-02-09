# Privacy Leak - Public Releases

Public distribution repository for signed APK releases of Privacy Leak.

The source code is maintained in a private repository. This public repository is used to publish release binaries, checksums, and changelog history.

## Features

- ✅ Automatic login (email/password) with Cloudflare Turnstile
- ✅ List followed profiles
- ✅ Download photos (with URL edits stripping)
- ✅ Download videos (direct MP4 and HLS with decryption)
- ✅ Media source selection: Profile Feed, Purchased, Chat, or All
- ✅ Media type selection: Photos, Videos, or Both
- ✅ Real-time progress tracking with speed, ETA, and activity log
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
