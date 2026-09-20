# Release metadata contract

The updater consumes `release.json` from the latest non-draft, non-prerelease GitHub Release.

```json
{
  "schemaVersion": 3,
  "applicationId": "com.byd.dashboard",
  "versionCode": 2,
  "versionName": "0.1.1",
  "outputSha256": "target-apk-lowercase-hex-sha256",
  "outputSize": 67123456,
  "targetCertificateSha256": "release-signing-certificate-lowercase-hex-sha256",
  "minimumAndroidSdk": 25,
  "patches": [{
    "baseVersionCode": 1,
    "baseVersionName": "0.1.0",
    "baseSha256": "base-apk-lowercase-hex-sha256",
    "patchAsset": "byd-dashboard-0.1.0-to-0.1.1.bsdiff",
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
2. The clean OTA epoch starts with private USB bootstrap `0.1.0`, Android `versionCode 1`; every later target increments the code exactly once.
3. Every supported archived base APK must have a direct patch to the newest target in the same GitHub Release.
4. Every `patchAsset` must exactly match one `.bsdiff` asset in the same GitHub Release.
5. `baseSha256`, `patchSha256`, `outputSha256`, and `targetCertificateSha256` are mandatory and calculated from exact archived artifacts.
6. The exact bytes of `release.json` must verify against `release.sig` using the ECDSA P-256 public key pinned in the bootstrap app.
7. Full APK files must never be uploaded to the public repository or its GitHub Releases.
8. A release is published only after every patch reconstructs the target APK byte-for-byte and every uploaded asset is downloaded and verified.
9. Drafts and prereleases are never offered to the vehicle unless a future opt-in beta channel explicitly enables them.
