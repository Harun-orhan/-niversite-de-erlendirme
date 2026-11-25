# 🎓 Üniversite Değerlendirme Uygulaması

Üniversite öğrencilerinin **hoca ve ders içeriklerini anonim olarak değerlendirebildiği**, e-Devlet barkod doğrulaması ile sahte hesapları tamamen engelleyen bir Android mobil uygulaması.

---

## 🔍 Problem Tanımı

Mevcut platformlarda (Ekşi Sözlük, itiraf sayfaları, RateMyProfessors benzerleri) hoca ve ders değerlendirmeleri güvenilir değildir:
- Sahte/bot hesaplarla puanlar manipüle edilebiliyor
- Hiç o dersi almamış kişiler yorum yapabiliyor
- Kullanıcılar kimliğiyle yorum yazmaktan çekiniyor; anonimken ise yorumlar güvenilirliğini kaybediyor

**Hedef kullanıcı:** Üniversite öğrencileri — ders ve hoca seçiminde güvenilir, doğrulanmış geribildirime ihtiyaç duyanlar.

---

## ✅ Çözüm

> Uygulama; **e-Devlet öğrenci belgesi barkod doğrulaması** sayesinde bot ve sahte hesapları tamamen engelleyip kullanıcı anonimliğini koruyarak, yalnızca doğrulanmış gerçek öğrencilerin manipüle edilmemiş, güvenilir hoca ve ders değerlendirmelerine ulaşmasını sağlar.

---

## 🚀 Özellikler

- 🔐 **e-Devlet Barkod Doğrulama** — Sadece gerçek öğrenciler kayıt olabilir
- 🗺️ **Keşfet & Harita** — İl bazlı üniversite arama
- 🏫 **Üniversite / Bölüm** — Genel puan ve sınıf bazlı müfredat
- 📚 **Sınıf & Dönem** — Güz/Bahar dönemi dersleri ve hocalar
- ⭐ **Değerlendirme** — Dersi geçenlerin hoca ve içerik puanı (anonim)

---

## 🏗️ Teknik Mimari (MVVM + Repository Pattern)

```
UI Layer        →  Jetpack Compose (Kayıt, Keşfet, Üniversite, Ders, Değerlendirme)
ViewModel Layer →  Durum yönetimi & iş mantığı
Repository Layer→  Single Source of Truth (Room ↔ Firebase)
Uzak Kaynak     →  Cloud Firestore + Firebase Authentication
Yerel Önbellek  →  Room Database + DataStore
```

---

## 🔒 Kişisel Kısıt: Offline Çalışma

Bu uygulamada atanan kişisel teknik kısıt **offline (çevrimdışı) çalışma** desteğidir.

**Nasıl uygulandı:**
- Room Database ile üniversite, bölüm ve ders verileri lokale önbelleğe alınır
- İnternet bağlantısı olmadan uygulama açılışında önbellekten veri gösterilir
- Bağlantı geldiğinde Firebase ile senkronizasyon otomatik yapılır
- Repository katmanı, verinin Room'dan mı yoksa Firebase'den mi geleceğine karar verir

---

## 🛠️ Kullanılan Teknolojiler

| Teknoloji | Kullanım Amacı |
|-----------|---------------|
| Kotlin | Ana programlama dili |
| Jetpack Compose | Modern UI |
| Firebase Firestore | Uzak veritabanı |
| Firebase Authentication | Kullanıcı oturumu |
| Room Database | Yerel önbellek |
| DataStore | Kullanıcı durumu |
| MVVM + Repository | Mimari desen |

---

## 📦 Kurulum

1. Repoyu klonla:
   ```bash
   git clone https://github.com/Harun-orhan/-niversite-de-erlendirme.git
   ```
2. Android Studio'da aç (Android Studio Hedgehog veya üzeri)
3. `google-services.json` dosyasını `app/` klasörüne ekle (Firebase projesi gerekli)
4. Çalıştır ▶️

---

## 📂 Proje Yapısı

```
app/src/main/
├── AndroidManifest.xml
├── java/           # Activity ve ViewModel sınıfları
└── res/
    ├── drawable/   # Logo ve görseller
    ├── layout/     # XML ekranlar (SplashActivity vb.)
    └── values/     # Renkler, temalar, metinler
```

---

## 📅 Haftalık İlerleme

| Hafta | Hedef | Durum |
|-------|-------|-------|
| 1 | Problem, persona, fikir, Git kurulumu | ✅ |
| 2 | Splash ekranı, mimari, wireframe | 🔄 Devam ediyor |
| 3 | Çekirdek özellik 1 + kısıt prototipi | ⏳ |
| 4 | Çekirdek özellik 2 | ⏳ |
| 5 | Test, mağaza sayfası | ⏳ |
| 6 | Final teslim | ⏳ |

---

## 👨‍💻 Geliştirici

**Harun Orhan**  
Repo: [github.com/Harun-orhan/-niversite-de-erlendirme](https://github.com/Harun-orhan/-niversite-de-erlendirme)
