# BYD Dashboard Releases

Public binary release channel for BYD Dashboard.

Bu depo yalnız BYD Dashboard delta güncellemelerini dağıtmak için kullanılır. Tam APK ve kaynak kod burada tutulmaz.

## Trust model / Güven modeli

- Full APK files are never uploaded. Releases contain only BSDIFF patches and metadata.
- OTA releases include `release.json`, one or more `.bsdiff` assets and `SHA256SUMS`. A USB baseline release contains metadata and checksums only; its signed APK remains private.
- The Android client verifies the base APK, patch, reconstructed target APK and signing certificate before opening the system installer.
- Signing keys, Mapbox tokens, vehicle logs and databases never belong in this repository.

- Tam APK dosyaları yüklenmez. Yayınlar yalnız BSDIFF patch ve metadata içerir.
- OTA yayınları `release.json`, bir veya daha fazla `.bsdiff` ve `SHA256SUMS` içerir. USB temel sürümü yalnız metadata ve checksum içerir; imzalı APK'sı özel olarak saklanır.
- Android istemcisi kurulum ekranından önce temel APK'yı, patch'i, yeniden oluşturulan hedef APK'yı ve imza sertifikasını doğrular.
- İmza anahtarları, Mapbox token'ları, araç logları ve veritabanları bu depoya konmaz.

## Release assets / Yayın dosyaları

```text
byd-dashboard-<base>-to-<version>.bsdiff
release.json
SHA256SUMS
```

See [RELEASE_FORMAT.md](RELEASE_FORMAT.md) for the metadata contract.
