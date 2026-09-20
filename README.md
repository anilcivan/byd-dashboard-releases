# BYD Dashboard Releases

Public binary release channel for BYD Dashboard.

Bu depo yalnız BYD Dashboard'un imzalı yayın paketlerini dağıtmak için kullanılır. Uygulamanın kaynak kodu ayrı ve private bir depoda tutulur.

## Trust model / Güven modeli

- APK files are attached to GitHub Releases; they are never committed to Git history.
- Every APK is signed with the same offline production key.
- Every release includes `release.json` and `SHA256SUMS` assets.
- The Android client verifies version, SHA-256 and signing certificate before opening the system installer.
- Signing keys, Mapbox tokens, vehicle logs and databases never belong in this repository.

- APK dosyaları GitHub Release asset olarak eklenir; Git geçmişine commit edilmez.
- Bütün APK'lar aynı çevrimdışı üretim anahtarıyla imzalanır.
- Her yayın `release.json` ve `SHA256SUMS` asset'lerini içerir.
- Android istemcisi sistem kurulum ekranını açmadan önce sürümü, SHA-256 değerini ve imza sertifikasını doğrular.
- İmza anahtarları, Mapbox token'ları, araç logları ve veritabanları bu depoya konmaz.

## Release assets / Yayın dosyaları

```text
byd-dashboard-<version>-arm64-v8a.apk
release.json
SHA256SUMS
```

See [RELEASE_FORMAT.md](RELEASE_FORMAT.md) for the metadata contract.

