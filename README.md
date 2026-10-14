# appcern.com

Appcern mobil uygulama stüdyosunun statik web sitesi. Build adımı yok — saf HTML/CSS, GitHub Pages'te doğrudan yayınlanır.

```
index.html          Ana sayfa
404.html            Bulunamayan sayfalar
CNAME               Özel alan adı (appcern.com)
assets/styles.css   Tüm stiller (renkler en üstte :root içinde)
assets/favicon.svg  Appcern logosu / favicon
assets/pare-icon.svg  Pare ikonu (Pare logosundaki kepçe-P, beyaz zemin)
```

## Yayına alma (GitHub Pages)

1. GitHub'da yeni repo aç (ör. `appcern/appcern.com`), bu klasördeki dosyaları köke koy ve push et.
2. Repo → **Settings → Pages** → Source: **Deploy from a branch**, Branch: `main` / `(root)` → Save.
3. Aynı sayfada **Custom domain** alanına `appcern.com` yaz (CNAME dosyası zaten var), DNS doğrulandıktan sonra **Enforce HTTPS**'i aç.
4. Alan adı sağlayıcında DNS:
   - `appcern.com` için 4 adet **A** kaydı: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www` için **CNAME** → `<github-kullanıcı-adın>.github.io`
   - Mevcut **MX** (Google Workspace) ve `legal` CNAME kayıtlarına dokunma.

Özel alan adı kullanmayacaksan `CNAME` dosyasını sil; site `https://<kullanıcı>.github.io/<repo>/` adresinde açılır.

## Sık güncellenecek yerler

- **Mağaza linkleri:** `index.html` en altındaki `STORE_LINKS`. Google Play linki dolu. App Store yayına çıkınca `ios` alanına URL'yi yapıştır; "iPhone version coming soon" etiketi kendiliğinden kalkar ve App Store butonu çıkar.
- **E-posta:** `hello@appcern.com` — farklı bir adres kullanıyorsan `index.html` içinde ara-değiştir.
- **Yeni uygulama:** `.app-card` bloğunu kopyala, `data-app` değerini değiştir, `STORE_LINKS`'e yeni anahtar ekle. Telefondaki bir `tile-soon` kutusunu `tile-live` yap.
