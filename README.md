# iOS Sideload Host

Personal GitHub repository for hosting your own iOS `.ipa` files so you can sideload updates easily.

This setup supports:
- Direct downloads from **GitHub Releases** (works with Sideloadly, AltStore, SideStore, Feather, etc.)
- An **AltStore / SideStore source** (`source.json`) so apps appear in the store UI and get one-tap updates

## Quick Start

### 1. Upload an IPA
1. Go to the [Releases](https://github.com/144volts-stack/ios-sideload-host/releases) page.
2. Click **Draft a new release**.
3. Create a tag (e.g. `v1.0.0`).
4. Upload your `.ipa` file as an asset.
5. Publish the release.

The direct download URL will look like:
```
https://github.com/144volts-stack/ios-sideload-host/releases/download/v1.0.0/YourApp.ipa
```

### 2. Sideload it
- **Sideloadly / iLoader / AltServer**: Just download the IPA and sideload normally.
- **AltStore / SideStore**: Add the source below for automatic updates.

## AltStore / SideStore Source

The source file lives at:
```
https://raw.githubusercontent.com/144volts-stack/ios-sideload-host/main/source.json
```

Add that URL in AltStore or SideStore under **Sources → +**.

### How to update the source
1. Edit `source.json` (or replace the placeholder app).
2. When you publish a new IPA release, update the `downloadURL`, `version`, `date`, and `size` fields for that app.
3. Commit the change (or I can help you update it).

**Tip**: Newer versions should be listed **first** in the `versions` array.

## File Structure
```
ios-sideload-host/
├── README.md
└── source.json          ← AltStore/SideStore source
```

## Notes
- Free Apple ID sideloading: apps expire every 7 days and are limited to 3 active apps (SideStore/AltStore can refresh them).
- Keep this repo public if you want the source URL to work without authentication, or private if you only use direct downloads.
- You can host multiple apps by adding more objects to the `apps` array in `source.json`.

Built for easy personal sideloading updates.
