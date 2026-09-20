# BYD Dashboard Releases

Public binary release channel for BYD Dashboard.

Bu depo yalnız BYD Dashboard delta güncellemelerini dağıtmak için kullanılır. Tam APK ve kaynak kod burada tutulmaz.

## Trust model / Güven modeli

- Full APK files are never uploaded. Releases contain only BSDIFF patches and metadata.
- OTA releases include a direct `.bsdiff` from every supported base, plus `release.json`, `release.sig`, and `SHA256SUMS`. The USB bootstrap APK remains private and is not a public release asset.
- The Android client verifies the signed manifest, exact base APK, patch, reconstructed target APK and signing certificate before opening the system installer.
- Signing keys, Mapbox tokens, vehicle logs and databases never belong in this repository.

- Tam APK dosyaları yüklenmez. Yayınlar yalnız BSDIFF patch ve metadata içerir.
- OTA yayınları desteklenen her temelden doğrudan `.bsdiff` ile birlikte `release.json`, `release.sig` ve `SHA256SUMS` içerir. USB temel APK'sı özel kalır ve public yayın varlığı olmaz.
- Android istemcisi kurulum ekranından önce imzalı manifesti, kesin temel APK'yı, patch'i, yeniden oluşturulan hedef APK'yı ve imza sertifikasını doğrular.
- İmza anahtarları, Mapbox token'ları, araç logları ve veritabanları bu depoya konmaz.

## Release assets / Yayın dosyaları

```text
byd-dashboard-<base>-to-<version>.bsdiff
release.json
release.sig
SHA256SUMS
```

See [RELEASE_FORMAT.md](RELEASE_FORMAT.md) for the metadata contract.
