# Haven Steam Library

Haven Steam Library — Steam kütüphanesi yöneticisi (OpenSteamTool tabanlı).

## Depo yapısı

```
opensteamtool/
  pattern/steamclient/<steamclient64.dll sha256>.toml
  pattern/steamui/<steamui.dll sha256>.toml
  ipc/steamclient/<steamclient64.dll sha256>.toml
```

Her TOML dosyası, adında yazan SHA-256'ya sahip Steam DLL'i için gereken
fonksiyon adreslerini (RVA) ve imzaları içerir.

## Otomatik güncelleme

Haven Steam Library uygulaması her açılışta:

1. `steamclient64.dll` ve `steamui.dll` dosyalarının SHA-256'sını hesaplar,
2. uygulamayla gelen yerel `opensteamtool/` klasörüne bakar,
3. yoksa bu depodan (`main` dalı) ve upstream kaynaklardan ilgili TOML'u indirir,
4. dosyayı `Steam/opensteamtool/...` altına kurar.

Böylece Steam güncellendiğinde TOML dosya adlarını elle değiştirmek gerekmez.

## Lisans

Apache-2.0 — bkz. [LICENSE](LICENSE).
