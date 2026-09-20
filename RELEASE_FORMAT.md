# Release metadata contract

The updater consumes `release.json` from the latest non-draft, non-prerelease GitHub Release.

```json
{
  "schemaVersion": 2,
  "applicationId": "com.byd.dashboard",
  "versionCode": 5,
  "versionName": "0.2.3",
  "outputSha256": "target-apk-lowercase-hex-sha256",
  "outputSize": 67123456,
  "minimumAndroidSdk": 25,
  "patches": [{
    "baseVersionCode": 4,
    "baseSha256": "base-apk-lowercase-hex-sha256",
    "patchAsset": "byd-dashboard-0.2.2-to-0.2.3.bsdiff",
    "patchSha256": "patch-lowercase-hex-sha256"
  }],
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
3. Every `patchAsset` must exactly match one `.bsdiff` asset in the same GitHub Release.
4. `baseSha256`, `patchSha256`, and `outputSha256` are mandatory and calculated from the exact binary files.
5. Full APK files must never be uploaded to the public repository or its GitHub Releases.
6. A release is published only after every asset is uploaded and verified.
7. Drafts and prereleases are never offered to the vehicle unless a future opt-in beta channel explicitly enables them.
8. A version installed manually by USB may be published as a baseline with an empty `patches` array. Its exact signed APK must be retained privately so the next OTA delta can use it as its base.
