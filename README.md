[README-3.md](https://github.com/user-attachments/files/28070228/README-3.md)


 # HAZIRLAYAN    BUĞRA ÇETİN - BİLGİSAYAR PROGRAMCILIĞI - AHİ EVRAN ÜNİVERSİTESİ - 245711052 - 
# 📷 Dış Mekan Çekimi
### Lokasyon Bazlı Işık Planlama Platformu

![Version](https://img.shields.io/badge/versiyon-2.0.0-D4A843?style=flat-square)
![Status](https://img.shields.io/badge/durum-yayında-27AE60?style=flat-square)
![License](https://img.shields.io/badge/lisans-MIT-blue?style=flat-square)
![Pages](https://img.shields.io/badge/GitHub%20Pages-aktif-brightgreen?style=flat-square)

> 135mm F2 gibi dar açılı lenslerle yapılan dış mekan çekimlerinde **doğru ışığı, doğru anda** yakalamak için geliştirilmiş lokasyon planlama aracı.

---

## 🌐 Canlı Demo

**→ [Siteyi Görüntüle](https://kullaniciadi.github.io/dis-mekan-cekimi)**

---

## 📸 Proje Hakkında

Dış mekan fotoğrafçılığında **Altın Saat** yalnızca ~47 dakika sürer. Bu kısa pencereyi verimli kullanmak için:

- Hangi lokasyona gideceğini önceden planlamalısın
- O noktanın güneş açısını ve altın saat saatini bilmelisin
- Hava durumunun çekime uygun olup olmadığını kontrol etmelisin

Bu platform tüm bu ihtiyaçları **tek bir arayüzde** toplar.

---

## ✨ Özellikler

### 🗺️ Harita & Lokasyon
- Mapbox GL JS ile interaktif harita
- Haritaya tıklayarak yeni çekim noktası ekleme
- Lokasyona özel altın saat ve SunCalc hesaplama
- Kategori bazlı renkli pin sistemi

### 🌤️ Canlı Hava Durumu
- Open-Meteo API ile Kırşehir anlık hava verisi
- Sıcaklık, nem, rüzgar, bulutluluk bilgileri
- Otomatik **çekim uygunluk skoru** (0–100)
- API key gerektirmez, CORS sorunu yoktur

### 🔍 Gelişmiş Arama & Filtreleme
| Özellik | Açıklama |
|---------|----------|
| Arama kutusu | İsim, açıklama, etiket ve şehir bazlı anlık arama |
| Kategori filtresi | Portre / Otomobil Çekimi |
| Şehir filtresi | Ankara / İstanbul / İzmir / Kırşehir |
| Sıralama | Puana göre ↑↓, İsme göre A→Z / Z→A |
| Favoriler | Lokasyonları favorilere ekleme / çıkarma |

### 👤 Kullanıcı Sistemi
- Kayıt ol / Giriş yap
- Giriş yapan kullanıcı yeni lokasyon ekleyebilir
- Eklenen lokasyonlar kişiye özel listelenir
- Silme işlemi ile veri yönetimi

---

## 🗂️ Proje Yapısı

```
dis-mekan-cekimi/
│
├── index.html          ← Ana sayfa (harita, lokasyonlar, hava durumu)
├── about.html          ← Proje hakkında, motivasyon, lens rehberi
├── contact.html        ← İletişim formu, SSS
├── project.html        ← Teknik detaylar, mimari, DB şeması
│
├── style.css           ← Global stiller (dark/light tema)
├── main.js             ← Yardımcı fonksiyonlar
├── locations.json      ← 15 lokasyon verisi (4 şehir)
│
└── README.md
```

---

## 📍 Lokasyon Veritabanı

Platform **15 hazır lokasyon** içermektedir:

| Şehir | Adet | Lokasyonlar |
|-------|------|-------------|
| 🏛️ Ankara | 6 | Çankaya Bulvarı, AOÇ, Anıtkabir, Kuğulu Park, Gençlik Parkı, Köşk Yolu |
| 🌉 İstanbul | 4 | Boğaziçi Köprüsü, Bebek Sahili, Emirgan Korusu, E-5 TEM |
| 🏖️ İzmir | 2 | Kordon Sahil Yolu, Kadifekale Yokuşu |
| 💧 Kırşehir | 3 | Kale Çevresi, Ankara Yolu, Hirfanlı Baraj Gölü |

Kullanıcılar giriş yaptıktan sonra **kendi lokasyonlarını** ekleyebilir ve silebilir.

---

## 🛠️ Kullanılan Teknolojiler

**Frontend**
- HTML5 / CSS3 / Vanilla JavaScript
- CSS Custom Properties (tema sistemi)
- IntersectionObserver API (scroll animasyonları)
- LocalStorage (kullanıcı verisi, oturum, favoriler)

**Harici API'ler**
- [Mapbox GL JS](https://www.mapbox.com/) — interaktif harita
- [SunCalc](https://github.com/mourner/suncalc) — güneş pozisyonu hesaplama
- [Open-Meteo](https://open-meteo.com/) — ücretsiz hava durumu API

**Tasarım**
- Tipografi: Cormorant Garamond + Space Mono
- Tema: Koyu/Açık mod desteği
- Responsive: Mobil uyumlu, hamburger menü

---

## 🚀 Kurulum

### Yerel Geliştirme

```bash
# Repoyu klonla
git clone https://github.com/kullaniciadi/dis-mekan-cekimi.git

# Klasöre gir
cd dis-mekan-cekimi

# Bir HTTP sunucu başlat (fetch için gerekli)
npx serve .
# veya
python -m http.server 8000
```

Tarayıcıda `http://localhost:8000` adresini aç.

> ⚠️ `file://` protokolüyle açarsan `locations.json` fetch edilemez; inline fallback verisi devreye girer.

### Mapbox Token

`index.html` dosyasındaki `MAPBOX_TOKEN` değişkenine kendi token'ını gir:

```js
const MAPBOX_TOKEN = 'pk.eyJ1IjoiSEVTAP_TOKUNINIZI_BURAYA...';
```

Ücretsiz token için: [mapbox.com](https://www.mapbox.com/)

---

## 📊 Proje Takvimi

```
Sprint 1 ████████░░░░  Planlama & Tasarım         ✅ Tamamlandı
Sprint 2 ████████████  Frontend Geliştirme         ✅ Tamamlandı
Sprint 3 ████████████  API & Dinamik Veri          ✅ Tamamlandı
Sprint 4 ████████████  Veritabanı & Filtreleme     ✅ Tamamlandı
Sprint 5 ████████████  Yayın & Final Raporu        ✅ Tamamlandı
```

---

## 📄 Sayfalar

| Sayfa | Dosya | İçerik |
|-------|-------|--------|
| Ana Sayfa | `index.html` | Hero, özellikler, harita, hava durumu, lokasyonlar |
| Hakkında | `about.html` | Motivasyon, lens rehberi, nasıl çalışır |
| Proje | `project.html` | Teknik mimari, DB şeması, API detayları |
| İletişim | `contact.html` | İletişim formu, SSS |

---

## 🔐 Kullanıcı Sistemi

Veriler tarayıcının `localStorage` alanında saklanır:

| Anahtar | İçerik |
|---------|--------|
| `dmc_users` | Kayıtlı kullanıcılar |
| `dmc_session` | Aktif oturum bilgisi |
| `dmc_user_locations` | Kullanıcının eklediği lokasyonlar |
| `dmc_favorites` | Favorilere eklenen lokasyon ID'leri |
| `dmc_locations` | Haritaya eklenen pinler |

> Gerçek bir backend entegrasyonu için `localStorage` çağrıları `fetch('/api/...')` ile değiştirilebilir.

---

## 👥 Ekip

> Web Projesi Yönetimi Dersi — 2025

---

## 📜 Lisans

Bu proje [MIT Lisansı](LICENSE) altında eğitim amaçlı geliştirilmiştir.

---

<div align="center">
  <sub>Dış Mekan Çekimi — Lokasyon bazlı ışık planlama platformu</sub>
</div>
