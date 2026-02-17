# Changelog

### Version 2.3.7 (Current)
- 🖼️ Fixed image token transform to request full-resolution JPEG (`quality=100`) instead of falling back to resized/watermarked variants
- 🔄 Improved chat/purchased pagination to continue after short pages (`items < limit`) with safe repeated-page signature stop conditions
- 🧪 Added extra pagination diagnostics (`maybeLastPage`, `repeatedSignature`, `hardPageLimit`) to speed up troubleshooting

### Version 2.3.6
- 👥 Fixed followed-profiles loading by adding pagination to `UserFollowing` (removes first-page-only cap)
- 💬 Fixed chat/purchased media matching by normalizing profile identifiers (`@`, casing) and considering creator nickname
- 🧪 Added extra diagnostics for no-match scenarios in chat/purchased collection to speed up support triage

### Version 2.3.5
- 🧪 Added dedicated `Debug Log` area in Download screen (top-bar bug icon) with copy/share actions for support diagnostics
- 📊 Added deep pagination diagnostics for profile/purchased/chat collection (HTTP status, per-page counts, last-page detection, summaries)
- 🧭 Hardened profile media collection against fragile HTML count parsing to reduce partial-download scenarios
- 🧮 Added collection counters before/after dedup and media-type filtering in download pipeline

### Version 2.3.4
- 🔧 Fixed missing `androidx-security-crypto` entry in version catalog causing unresolved build reference
- 🗃️ Added `postDate` field to `MediaItem`, `MosaicItem`, and `PurchasedPost` models for date-based filenames
- 🌐 Added `getTurnstileConfig()` endpoint to `PrivacyApiService` for Cloudflare Turnstile integration
- 🔑 Added credential persistence (`savedEmail`, `savedPassword`, `saveCredentials`, `clearCredentials`) to `AuthRepository`
- 🛡️ Changed OkHttp logging level from BODY to HEADERS to prevent OOM on large binary downloads

### Version 2.3.3
- 🌐 Moved language selector to the top area of About screen for faster access
- 📜 Changelog section in About now uses a compact fixed-height panel with internal scroll

### Version 2.3.2
- 📱 Fixed Profiles header alignment on narrower devices with responsive top actions and a dedicated profile-count row
- 📝 GitHub public releases now publish version changelog notes extracted from `README.md` instead of generic static text

### Version 2.3.1
- 🤖 Added GitHub App based public release pipeline (`release-public.yml`) for zero personal contributor footprint
- 🚀 Added cross-repo APK publishing to `KyoNinja/PrivacyLeakApp` GitHub Releases on semver tags
- 🔐 Added CI release signing support via keystore secrets and environment-based Gradle signing config
- 🧭 Update source now points to `KyoNinja/PrivacyLeakApp` via BuildConfig fields (no hardcoded repo in code)

### CI/CD Internal Updates (No App Version Bump)
- 🏷️ Added `auto-tag-on-version-bump.yml` to create `vX.Y.Z` tags from `main` version bumps
- 🔁 `release-public.yml` now supports `workflow_dispatch` with `tag_name` for deterministic chained releases
- 🧰 Hardened bootstrap/release workflows (input compatibility, empty-repo bootstrap, stricter secret validation)
- 📘 Added setup docs for `GH_APP_PRIVATE_KEY` and `ANDROID_KEYSTORE_BASE64`

### Version 2.3.0
- 🔄 Added GitHub Releases update check with automatic checks on app startup and when opening About
- 🧪 Added manual "Check for updates" action with 6-hour cache TTL to avoid unnecessary requests
- ⬆️ Added one-tap "Update" button that opens the latest release page in the browser

### Version 2.2.3
- 🧰 Migrated app Gradle script to AGP 9/10-safe DSL using `ApplicationExtension`
- ⚙️ Replaced deprecated `kotlinOptions.jvmTarget` with `kotlin { compilerOptions { jvmTarget = JVM_17 } }`
- ✅ Removed the deprecation warnings reported by Android Studio/Gradle for current build setup

### Version 2.2.2
- 🖼️ Launcher icon now uses the exact provided `icone.png` asset as adaptive foreground
- 🎯 Removed custom vector interpretation to preserve the original image composition
- 🫥 Adaptive icon background set to transparent to avoid altering the provided artwork

### Version 2.2.1
- 🎯 Reworked launcher icon to match the requested camera-shutter + lock style
- 🌈 Updated adaptive icon foreground with neon circular ring, shutter blades, and gradient lock
- 🖼️ Adaptive icon background switched to dark radial gradient for stronger contrast

### Version 2.2.0
- 📋 Reworked Profiles screen with cleaner top bar (Refresh + About visible, Sign Out in overflow menu)
- 🔎 Added local profile search and pull-to-refresh for faster navigation in long lists
- 🧭 Updated profile cards with explicit textual CTA ("Download"), support hint, and less aggressive glow
- 🧱 Added richer states: skeleton loading cards, improved error card, empty state, and no-results state

### Version 2.1.1
- 🎨 Expanded Login redesign with a more visible hero header and stronger section hierarchy
- 🧱 Quick actions moved into a dedicated card and form grouped with its own heading/caption
- 📐 Reduced visual dead zones with denser spacing and better first-screen composition

### Version 2.1.0
- 🧩 Full Login screen UX rework with compact hierarchy: brand block, quick actions row, and unified form card
- ✅ Added inline field validation (required + email format) with contextual error messages before network call
- ⌨️ Improved input flow with keyboard actions (`Next`/`Done`) and safer loading state (actions/inputs disabled while signing in)

### Version 2.0.9
- 🌐 Added a visible language selector directly on Login screen (quick dropdown)
- ℹ️ Replaced hidden info-only affordance with a labeled, more prominent `About` quick action
- 🎛️ Added a compact top quick-actions row on Login for discoverability without opening changelog

### Version 2.0.8
- ℹ️ Moved the “Media will be saved...” info strip to directly below the primary top action button
- 📍 Kept info visible without consuming scroll-space in the options/log section

### Version 2.0.7
- 🧭 Moved profile context into the Download header (under title) with truncation for long names
- 🧹 Removed duplicated profile context block from the content area to free vertical space
- 📌 Kept primary action fixed at top so Start/Cancel/Download Again remains visible with activity logs

### Version 2.0.6
- 👤 Added a compact profile context row at the top of Download screen (without clutter/repetition)
- ⬆️ Moved primary action button (Start/Cancel/Download Again) to fixed top action area for constant visibility
- 📜 Kept activity log in scrollable content so actions never get pushed off-screen

### Version 2.0.5
- 🛠️ Fixed Download screen build error caused by invalid `Modifier.padding(...)` argument combination

### Version 2.0.4
- ✅ Stronger selection feedback on option chips (check icon + highlighted selected style)
- 🧹 Removed redundant profile name repetition from Download screen header/content
- 📌 Raised bottom footer/CTA block and fixed compact info row icon rendering

### Version 2.0.3
- 🧩 Reworked Download options layout into compact chip groups (Media Type + Source in one card)
- ↕️ Reduced vertical bloat by removing long radio lists and shrinking static info block
- 🎛️ Switched conversion toggle to a compact switch inside the unified options card

### Version 2.0.2
- 📱 Improved Download screen UX with tighter vertical layout and less wasted space
- 📌 Added sticky bottom primary CTA so "Start Download" is immediately visible on open
- 🧾 Moved version/credit footer to persistent bottom bar for consistent visibility

### Version 2.0.1
- 🎬 Simplified HLS video pipeline to: decrypt `.ts` -> remux `.mp4` -> save
- 🧹 Removed legacy local HLS proxy remux code to reduce failure surface and latency
- 📦 Migrated FFmpeg dependency to maintained Maven Central fork (`com.mrljdx:ffmpeg-kit-full:6.1.4`)

### Version 2.0.0
- 🔑 Remember credentials option — email and password saved locally for easy re-login
- 📝 Credentials auto-fill when session expires (no need to retype)

### Version 1.9.3
- 🐛 Fixed race condition in TS-to-MP4 remux that could produce corrupted (48-byte) MP4 files
- 🔒 Polling now validates output size stability and minimum size (25% of input) before accepting

### Version 1.9.2
- 🔄 Replaced custom TS demuxer with FFmpegKit for reliable TS-to-MP4 conversion
- 🎯 Handles all TS variants (multiple PAT/PMT tables, any codec combination)
- 📦 Stream copy only — no re-encoding, fast and lightweight

### Version 1.9.1
- 🔧 Fixed TS-to-MP4 remux failing on devices where MediaExtractor cannot parse MPEG-TS
- 🔬 Custom TS demuxer: parses PAT/PMT tables, extracts H.264/AAC elementary streams
- 📦 Uses MediaMuxer for MP4 output (zero external dependencies, no re-encoding)

### Version 1.9.0
- 🎬 Optional TS-to-MP4 remuxing for HLS videos (enabled by default)
- 🛡️ Fallback to .ts if remux fails (downloads are never lost)
- ☑️ New checkbox on Download screen to toggle conversion

### Version 1.8.0
- 📁 Descriptive file naming pattern: `postDate-profileName-mediaId.ext`
- 📋 Activity log now persists after cancelling a download

### Version 1.7.0
- 🎨 Compact profile cards with gradient initials avatar and download indicator
- ✨ Neon glow effects on cards (cyan/green shadows)
- 🌈 Animated gradient progress bar (cyan to purple shimmer)
- 📊 Compact inline stat chips replacing bulky stat cards
- 📋 Activity log integrated directly into progress card
- 🏷️ Labeled action buttons (Refresh, About, Sign Out) in toolbar
- ⏭️ Skip existing files automatically with "exists" visual feedback
- 👁️ Improved login text field visibility on dark backgrounds
- 🎨 Neon color palette (green, cyan, purple) for dark theme accents

### Version 1.6.0
- 🔐 Secure session persistence with AES-256 encrypted token storage (EncryptedSharedPreferences)
- 🔄 Automatic session restore on app restart (re-authorization with saved tokens)
- 🚪 Automatic logout on expired session (401 HTTP interceptor)
- 📦 Seamless migration from DataStore (v1.5.0) to encrypted storage

### Version 1.5.0
- 🎨 New brand identity with cyan-to-purple gradient
- 🌈 Gradient TopAppBar on all screens
- 🔒 Updated launcher icon with lock+download design
- 🌙 Branded dark theme with custom color scheme
- ✨ Gradient text logo on Login and About screens

### Version 1.4.0
- 📊 Enhanced download screen with speed, ETA, remaining items, and activity log
- 🗑️ Removed manual login option (simplified login flow)
- ℹ️ About button now available on login screen
- 🦶 Footer with version and credits on all screens

### Version 1.3.0
- 🔐 Added Cloudflare Turnstile support for automatic login
- 🛠️ Fixed OutOfMemoryError on large HLS video downloads (segments now written to disk)
- ❌ Added cancel download button
- ℹ️ Added About screen with developer info, changelog, and language selector
- 🧹 Fixed null byte sanitization in login credentials

### Version 1.2.0
- 🌍 Added manual language selector (English/Portuguese/System)
- 🔧 Fixed HLS key download - keys on keyaes.privacy.com.br don't need special video headers
- 🔄 Activity recreates when language changes for instant effect

### Version 1.1.0
- 🔧 Fixed HLS video download with AES-128 decryption support
- 🌐 Added English language support
- 🔢 Added version display in login screen
- 📝 Improved login screen with privacy.com.br branding
- 🛠️ Added BuildConfig for version tracking
- 📁 Videos are now saved as .ts files (decrypted MPEG-TS format)

### Version 1.0.0
- Initial release
- Basic login functionality
- Profile listing
- Photo and video download support

