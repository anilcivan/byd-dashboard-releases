# Release metadata contract

The updater consumes `release.json` from the latest non-draft, non-prerelease GitHub Release.

```json
{
  "schemaVersion": 1,
  "applicationId": "com.byd.dashboard",
  "versionCode": 2,
  "versionName": "0.2.0",
  "apkAsset": "byd-dashboard-0.2.0-arm64-v8a.apk",
  "sha256": "lowercase-hex-sha256",
  "minimumAndroidSdk": 25,
  "mandatory": false,
  "publishedAt": "2026-09-20T00:00:00Z",
  "notes": {
    "tr": "Sürüm notları",
    "en": "Release notes"
  }
}
```

Rules:

1. `applicationId` must remain `com.byd.dashboard`.
2. `versionCode` must increase for every published update.
3. `apkAsset` must exactly match one APK asset in the same GitHub Release.
4. `sha256` is calculated from the final signed APK.
5. A release is published only after every asset is uploaded and verified.
6. Drafts and prereleases are never offered to the vehicle unless a future opt-in beta channel explicitly enables them.

