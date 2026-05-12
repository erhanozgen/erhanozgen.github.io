# Kişisel CV Sitesi — Kurulum Rehberi

Bu klasörde tek dosyalık bir CV sitesi var (`index.html`). Aşağıdaki adımları sırayla takip et, ~15-20 dakikada canlıya çıkar.

---

## 1. İçeriği düzenle

`index.html`'i bir editörde aç (Notepad, VS Code, PyCharm — fark etmez). İçinde `<!-- TODO: ... -->` yorumlarını ara, hepsini kendi bilgilerinle değiştir:

- [ ] Sayfa başlığı (`<title>`) ve `<meta description>`
- [ ] Nav'daki "Erhan Özgen" yazısı (`.nav-logo`)
- [ ] Hero bölümü: isim, ünvan, şehir, kısa tanıtım
- [ ] About bölümünün metni
- [ ] Stack kartlarındaki yetenekler (kategori ekleyebilir/çıkarabilirsin)
- [ ] Experience: her bir iş tecrübeni `<div class="experience-item">` bloğu olarak ekle
- [ ] Education bilgileri
- [ ] Certifications (yoksa o bütün `<section>`'ı silebilirsin)
- [ ] Contact linkleri: email, LinkedIn URL'in, GitHub URL'in
- [ ] Footer'daki isim ve yıl

## 2. Profil fotoğrafı

Kare format bir profil fotoğrafı (~400x400px ideal, ama herhangi bir boyut da olur) bu klasöre **`profile.jpg`** adıyla koy. Farklı bir isim/format kullanırsan `<img src="profile.jpg" ...>` satırındaki yolu güncelle.

> Fotoğraf yoksa da site açılır, sadece o kısımda boş bir daire görürsün.

## 3. Lokal olarak test et

`index.html` dosyasının üstüne çift tıkla — tarayıcıda açılır. Her şey iyi mi kontrol et:
- Bölümler doğru görünüyor mu?
- Dark mode toggle çalışıyor mu? (sağ üstteki 🌙 / ☀)
- Telefonda nasıl görünüyor? (Tarayıcıda F12 → cihaz görünümü)

## 4. GitHub'a yükle

### 4a. Repo oluştur

GitHub'da yeni bir public repo oluştur. Repo adı **çok önemli**: tam olarak şu formatta olmalı:

```
KULLANICIADIN.github.io
```

Örnek: GitHub username'in `erhanozgen` ise repo adı `erhanozgen.github.io` olacak. Bu özel bir isim — GitHub bu repodaki içeriği otomatik olarak siteye dönüştürür.

### 4b. Lokal repo'yu push'la

Bu klasörde terminali aç (PyCharm'da → Terminal). Sırayla şu komutları çalıştır:

```bash
git init
git add .
git commit -m "Initial CV site"
git branch -M main
git remote add origin https://github.com/KULLANICIADIN/KULLANICIADIN.github.io.git
git push -u origin main
```

> `KULLANICIADIN` kısmını **iki yerde de** kendi GitHub username'inle değiştir.

## 5. GitHub Pages'i aktive et

1. Repo'nun GitHub sayfasına git
2. **Settings** sekmesi → sol menüden **Pages**
3. **Build and deployment** altında:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`, folder: `/ (root)`
4. **Save**'e bas

1-3 dakika sonra sitenin yayında olacak. URL'in:

```
https://KULLANICIADIN.github.io
```

## 6. LinkedIn'e ekle

İki yöntem:

**A — Profil header'ına link**:
LinkedIn → profil → Edit Intro → "Website" → URL'i yapıştır → "Other" veya "Personal" seç

**B — Featured bölümüne**:
LinkedIn → profil → "Add featured section" → "Add a link" → URL'i yapıştır → site önizlemesi olarak görünür (genelde daha şık)

---

## Sonradan içerik güncellemesi

`index.html`'i değiştirip aynı klasörde:

```bash
git add .
git commit -m "Update content"
git push
```

Bir-iki dakika sonra siten güncellenir.

## İleride istersen — Custom domain

`erhanozgen.com` gibi kendi domain'in olsun istersen (~₺200-400/yıl):
1. Namecheap / GoDaddy / Turhost / Cloudflare'den domain al
2. Repo Settings → Pages → "Custom domain" kısmına yaz
3. Domain sağlayıcının panelinden DNS'i GitHub'a yönlendir (GitHub sana adımları gösterir)

Domain almak **zorunlu değil**, `username.github.io` zaten temiz ve profesyonel görünür.
