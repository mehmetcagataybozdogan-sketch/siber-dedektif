# 🔍 SİBER DEDEKTİF – Hazine Avı Web Altyapısı
**Siberay – Siber Güvenlik ve Teknoloji Kulübü**

---

## 📁 Dosya Yapısı

```
siber-dedektif/
│
├── index.html                  → Ana giriş & takım seçim sayfası
│
├── mavi-adim1.html             → Mavi Takım – İstasyon 1 (Kütüphane)
├── mavi-adim2.html             → Mavi Takım – İstasyon 2 (Bilg. Lab)
├── mavi-adim3.html             → Mavi Takım – İstasyon 3 (Bahçe)
├── mavi-adim4-final.html       → Mavi Takım – Final (Amfi)
│
├── kirmizi-adim1.html          → Kırmızı Takım – İstasyon 1 (Bilg. Lab) ← ÇAPRAZ BAŞLANGIÇ
├── kirmizi-adim2.html          → Kırmızı Takım – İstasyon 2 (Kütüphane)
├── kirmizi-adim3.html          → Kırmızı Takım – İstasyon 3 (Kulüpler)
├── kirmizi-adim4-final.html    → Kırmızı Takım – Final (Amfi)
│
├── tuzak.html                  → Tuzak / Sahte QR Kodu → Phishing eğitimi
└── tebrikler.html              → Ortak final tebrikler sayfası
```

---

## 🔀 Çapraz Rota Mantığı

| Adım  | 🔵 Mavi Takım          | 🔴 Kırmızı Takım       |
|-------|------------------------|------------------------|
| 1     | Kütüphane Girişi       | Bilgisayar Laboratuvarı|
| 2     | Bilgisayar Laboratuvarı| Kütüphane Girişi       |
| 3     | Kampüs Bahçesi         | Öğrenci Kulüpleri Odası|
| 4     | Merkez Amfi (Final)    | Merkez Amfi (Final)    |

> İki takım birbirini görmeden farklı rotalardan ilerler, finalde buluşur!

---

## 🔑 Şifreler (Değiştirilebilir)

| Sayfa                  | Şifre    | Değiştirilecek Yer            |
|------------------------|----------|-------------------------------|
| mavi-adim1.html        | KITAP    | `const CORRECT_PASSWORD`      |
| mavi-adim2.html        | FARE     | `const CORRECT_PASSWORD`      |
| mavi-adim3.html        | AGAC     | `const CORRECT_PASSWORD`      |
| mavi-adim4-final.html  | ZAFER    | `const CORRECT_PASSWORD`      |
| kirmizi-adim1.html     | KLAVYE   | `const CORRECT_PASSWORD`      |
| kirmizi-adim2.html     | KITAP    | `const CORRECT_PASSWORD`      |
| kirmizi-adim3.html     | KULUP    | `const CORRECT_PASSWORD`      |
| kirmizi-adim4-final.html| ZAFER   | `const CORRECT_PASSWORD`      |

---

## 🔗 QR Koda Çevrilecek URL'ler

### GitHub Pages üzerinde yayınlıyorsan:
`https://KULLANICI_ADIN.github.io/siber-dedektif/DOSYA_ADI.html`

### Vercel üzerinde yayınlıyorsan:
`https://siber-dedektif.vercel.app/DOSYA_ADI.html`

### QR Kod oluşturma (ücretsiz araçlar):
- https://www.qr-code-generator.com
- https://qr.io
- https://goqr.me

---

## 📋 Kampüse Asılacak QR Kodlar

| QR Kod Etiketi              | Yönlendirdiği URL             | Nereye Asılır                  |
|-----------------------------|-------------------------------|-------------------------------|
| 🔵 MAVİ – Başlangıç         | `index.html`                  | Kulüp standı / dağıtım        |
| 🔴 KIRMIZI – Başlangıç      | `index.html`                  | Kulüp standı / dağıtım        |
| 🔵 MAVİ İstasyon 1          | `mavi-adim1.html`             | Kütüphane girişi – sol kapı   |
| 🔵 MAVİ İstasyon 2          | `mavi-adim2.html`             | Lab. – 3. bilgisayar arkası   |
| 🔵 MAVİ İstasyon 3          | `mavi-adim3.html`             | Büyük ağacın dibi – mavi taş  |
| 🔵 MAVİ Final               | `mavi-adim4-final.html`       | Amfi – sahne önü mavi bayrak  |
| 🔴 KIRMIZI İstasyon 1       | `kirmizi-adim1.html`          | Lab. – 5. bilgisayar yanı     |
| 🔴 KIRMIZI İstasyon 2       | `kirmizi-adim2.html`          | Kütüphane girişi – sağ kapı   |
| 🔴 KIRMIZI İstasyon 3       | `kirmizi-adim3.html`          | Kulüpler panosu – kırmızı zarf|
| 🔴 KIRMIZI Final            | `kirmizi-adim4-final.html`    | Amfi – sahne önü kırmızı bayrak|
| ⚠️ TUZAK (birden fazla)     | `tuzak.html`                  | Etrafta rastgele – 3-5 adet   |

---

## ✏️ İçerik Değiştirme Rehberi

### Bilmece metnini değiştirmek:
```html
<!-- Her adım sayfasında bu bölümü bul: -->
<div class="clue-text">
  "Bilmece metni buraya..."
</div>
```

### İstasyon adını değiştirmek:
```html
<div class="station-name">Kütüphane Girişi</div>
```

### Şifreyi değiştirmek (JS bölümü):
```javascript
const CORRECT_PASSWORD = 'YENİ_ŞİFRE';
```

### İpucunu değiştirmek:
```html
<div class="hint-box">
  İpucu metni buraya...
</div>
```

### Yeni istasyon eklemek:
1. Mevcut bir adım sayfasını kopyala
2. `station-num`, `station-name`, `clue-text` bölümlerini güncelle
3. `href` bağlantılarını yeni sıraya göre düzenle
4. `progress-steps` dot'larını güncelle (done / active)

---

## 🚀 Yayınlama (GitHub Pages)

```bash
# 1. GitHub'da yeni repo oluştur: siber-dedektif
# 2. Dosyaları yükle
git init
git add .
git commit -m "Siber Dedektif hazine avı"
git remote add origin https://github.com/KULLANICI/siber-dedektif.git
git push -u origin main

# 3. GitHub → Settings → Pages → Source: main branch → Save
# Site adresi: https://KULLANICI.github.io/siber-dedektif/
```

## 🚀 Yayınlama (Vercel)

```bash
# 1. vercel.com'a giriş yap
# 2. "New Project" → GitHub repo'yu seç
# 3. Framework: "Other" (Static Site) → Deploy
# Otomatik URL verilir
```

---

## 🎨 Renk & Tasarım Özelleştirme

Her sayfanın `<style>` bölümünün başındaki `:root` değişkenlerini değiştir:

```css
:root {
  --bg:         #0A0E1A;   /* Arka plan */
  --neon:       #00FF88;   /* Neon yeşil */
  --team-color: #00BFFF;   /* Takım rengi (mavi/kırmızı sayfalarda farklı) */
}
```

---

*Siberay – Siber Güvenlik ve Teknoloji Kulübü | 2025*
