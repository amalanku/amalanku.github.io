# 📊 Data Directory - Amalanku Project

Selamat datang di folder **Data**! Direktori ini berisi semua data pendukung yang dibutuhkan untuk membangun aplikasi Amalanku. Semua data di sini bersifat **open source** dan dapat digunakan oleh komunitas untuk berkontribusi pada pengembangan aplikasi.

## 📁 Struktur Folder

```
./data/
├── README.md                 # File ini
├── prayers/                  # Data terkait salat
│   ├── prayer-times.json     # Jadwal waktu salat
│   ├── qibla-directions.json # Arah kiblat berbagai kota
│   └── prayer-names.json     # Nama-nama salat dalam berbagai bahasa
├── quran/                    # Data Al-Qur'an
│   ├── surahs.json          # Daftar nama surah
│   ├── ayahs/               # Ayat-ayat per surah
│   ├── translations/        # Terjemahan berbagai bahasa
│   └── audio/               # Link audio tilawah
├── dhikr/                    # Data dzikir dan doa
│   ├── daily-dhikr.json     # Dzikir harian
│   ├── morning-evening.json # Dzikir pagi petang
│   ├── post-prayer.json     # Dzikir setelah salat
│   └── duas.json            # Kumpulan doa pilihan
├── islamic-calendar/         # Kalender Islam
│   ├── hijri-months.json    # Nama bulan hijriyah
│   ├── important-dates.json # Tanggal penting Islam
│   └── moon-phases.json     # Data fase bulan
├── habits/                   # Data amalan dan kebiasaan
│   ├── daily-habits.json    # Amalan harian yang direkomendasikan
│   ├── weekly-habits.json   # Amalan mingguan
│   └── categories.json      # Kategori amalan
├── motivations/              # Konten motivasi
│   ├── verses.json          # Ayat-ayat motivasi
│   ├── hadiths.json         # Hadits pilihan
│   ├── quotes.json          # Quotes Islami
│   └── reminders.json       # Reminder spiritual
├── locations/                # Data lokasi
│   ├── cities.json          # Database kota-kota
│   ├── countries.json       # Database negara
│   └── mosques.json         # Data masjid terdekat
└── localization/             # Data terjemahan
    ├── id.json              # Bahasa Indonesia
    ├── en.json              # English
    ├── ar.json              # العربية
    └── ms.json              # Bahasa Melayu
```

## 🎯 Jenis Data yang Dibutuhkan

### 📿 1. Data Salat (`./prayers/`)
- **prayer-times.json**: Rumus perhitungan waktu salat untuk berbagai metode
- **qibla-directions.json**: Koordinat arah kiblat untuk kota-kota besar
- **prayer-names.json**: Nama salat dalam berbagai bahasa

**Contoh Struktur:**
```json
{
  "fajr": {
    "name": "Subuh",
    "arabic": "الفجر",
    "english": "Fajr"
  }
}
```

### 📖 2. Data Al-Qur'an (`./quran/`)
- **surahs.json**: 114 surah dengan nama, nomor, dan informasi dasar
- **ayahs/**: File JSON per surah berisi ayat-ayat
- **translations/**: Terjemahan dalam bahasa Indonesia, Inggris, dll
- **audio/**: Link atau referensi file audio tilawah

**Prioritas**: Terjemahan Bahasa Indonesia (Kemenag) dan Arab

### 🤲 3. Data Dzikir & Doa (`./dhikr/`)
- **daily-dhikr.json**: Dzikir yang dianjurkan setiap hari
- **morning-evening.json**: Dzikir pagi dan petang lengkap
- **post-prayer.json**: Dzikir setelah salat fardhu
- **duas.json**: Doa sehari-hari (makan, tidur, perjalanan, dll)

**Format yang Diinginkan:**
```json
{
  "id": "dhikr_001",
  "arabic": "سُبْحَانَ اللهِ",
  "transliteration": "Subhanallah",
  "translation": "Maha Suci Allah",
  "count": 33,
  "time": "after_prayer"
}
```

### 🌙 4. Kalender Islam (`./islamic-calendar/`)
- **hijri-months.json**: 12 bulan hijriyah dengan nama dan karakteristik
- **important-dates.json**: Tanggal penting seperti Ramadhan, Idul Fitri, dll
- **moon-phases.json**: Data fase bulan untuk perhitungan tanggal Islam

### ✅ 5. Data Kebiasaan (`./habits/`)
- **daily-habits.json**: Amalan harian yang direkomendasikan
- **weekly-habits.json**: Amalan mingguan (puasa Senin-Kamis, dll)
- **categories.json**: Kategori amalan (Wajib, Sunnah, Mustahab)

### 💖 6. Konten Motivasi (`./motivations/`)
- **verses.json**: Ayat Al-Qur'an yang memotivasi
- **hadiths.json**: Hadits shahih yang inspiratif
- **quotes.json**: Quotes dari ulama dan tokoh Islam
- **reminders.json**: Reminder spiritual untuk notifikasi

### 📍 7. Data Lokasi (`./locations/`)
- **cities.json**: Database kota-kota dengan koordinat
- **countries.json**: Daftar negara dengan timezone
- **mosques.json**: Data masjid untuk fitur "Masjid Terdekat"

### 🌍 8. Lokalisasi (`./localization/`)
- **id.json**: Semua text dalam Bahasa Indonesia
- **en.json**: Terjemahan Bahasa Inggris
- **ar.json**: Terjemahan Bahasa Arab
- **ms.json**: Bahasa Melayu untuk Malaysia/Brunei

## 🚀 Cara Berkontribusi Data

### 📝 Untuk Content Creator
1. **Pilih folder** yang ingin Anda kontribusikan
2. **Ikuti format JSON** yang sudah ada atau buat format baru
3. **Pastikan sumber valid** - rujuk Al-Qur'an, Hadits Shahih, atau sumber terpercaya
4. **Submit Pull Request** dengan deskripsi sumber data

### 🔍 Untuk Data Researcher
1. **Research data** dari sumber-sumber Islami yang terpercaya
2. **Validasi keakuratan** data sebelum submit
3. **Dokumentasikan sumber** data di file terpisah
4. **Format sesuai struktur** yang diinginkan

### 💻 Untuk Developer
1. **Optimize struktur JSON** untuk performa aplikasi
2. **Buat script automation** untuk generate data
3. **Validasi format** dengan JSON schema
4. **Compress dan optimize** ukuran file

## ✅ Guidelines Kontribusi Data

### 🎯 Kriteria Data yang Diterima
- ✅ **Sumber Terpercaya**: Al-Qur'an, Hadits Shahih, fatwa ulama terpercaya
- ✅ **Format Konsisten**: Mengikuti struktur JSON yang sudah ditetapkan
- ✅ **Bahasa Indonesia**: Prioritas utama, bahasa lain sebagai bonus
- ✅ **Lengkap**: Menyertakan transliterasi untuk teks Arab
- ✅ **Terverifikasi**: Data sudah dicek kebenarannya

### ❌ Data yang Tidak Diterima
- ❌ Hadits dhaif atau tidak jelas sumbernya
- ❌ Pendapat pribadi tanpa dasar syar'i
- ❌ Data yang mengandung bid'ah atau menyimpang dari ajaran Islam
- ❌ Format data yang tidak konsisten
- ❌ Data duplikasi tanpa value tambah

## 📋 Priority List - Data yang Paling Dibutuhkan

### 🔥 High Priority
1. **Jadwal Salat** - Algoritma perhitungan untuk berbagai wilayah Indonesia
2. **Dzikir Harian** - Dzikir pagi, petang, dan setelah salat
3. **Data Surah** - 114 surah dengan terjemahan Indonesia
4. **Doa Sehari-hari** - Doa yang sering digunakan muslim
5. **Nama Kota Indonesia** - Untuk fitur jadwal salat otomatis

### ⭐ Medium Priority
6. **Hadits Motivasi** - Hadits pendek yang inspiratif
7. **Kalender Hijriyah** - Tanggal penting Islam 2025-2030
8. **Audio Tilawah** - Link atau referensi audio Qur'an
9. **Arah Kiblat** - Data koordinat untuk kota-kota besar
10. **Terjemahan Multi-bahasa** - English, Arabic, Melayu

### 💫 Nice to Have
11. **Data Masjid** - Database masjid Indonesia
12. **Quotes Ulama** - Kata-kata hikmah dari ulama
13. **Puasa Sunnah** - Jadwal dan keutamaan puasa sunnah
14. **Wirid Harian** - Wirid untuk berbagai waktu
15. **Fase Bulan** - Data astronomis untuk kalender Islam

## 🤝 Cara Memulai Kontribusi

### 1. Fork Repository
```bash
git clone https://github.com/yourusername/amalanku.git
cd amalanku/data
```

### 2. Pilih Data untuk Dikerjakan
- Lihat folder yang masih kosong atau perlu dilengkapi
- Check [Issues](https://github.com/amalanku/amalanku.github.io/issues) dengan label `data-needed`
- Koordinasi di [Discussions](https://github.com/amalanku/amalanku.github.io/discussions)

### 3. Format dan Validasi
- Ikuti struktur JSON yang konsisten
- Gunakan tools seperti [JSONLint](https://jsonlint.com/) untuk validasi
- Test dengan sample aplikasi jika sudah ada

### 4. Submit Kontribusi
```bash
git add .
git commit -m "Add: data dzikr pagi petang dengan sumber yang valid"
git push origin feature/data-dzikr
# Buat Pull Request
```

## 📞 Butuh Bantuan?

### 💬 Diskusi Data
- **GitHub Discussions**: [Data Discussions](https://github.com/amalanku/amalanku.github.io/discussions/categories/data)
- **Issues**: [Data Issues](https://github.com/amalanku/amalanku.github.io/labels/data)

### 📧 Kontak Langsung
- **Email**: amalanku@hotmail.com
- **Telegram**: @AmalankuData

### 🤲 Koordinasi Komunitas
Kami membuat channel khusus untuk koordinasi contributor data: 
- **WhatsApp Group**: [https://chat.whatsapp.com/J0IbBIJwDL80qBrHycW72t](https://chat.whatsapp.com/J0IbBIJwDL80qBrHycW72t)

## 🎖️ Contributor Recognition

Setiap kontribusi data akan diakui dengan:
- ✨ **Credits** di file AUTHORS.md
- 🏆 **Badge** di profile GitHub (jika tersedia)
- 📜 **Certificate** digital untuk kontributor aktif
- 🤲 **Doa baik** dari seluruh tim dan komunitas pengguna

## 🤲 Doa untuk Para Kontributor

*"Barakallahu fiikum wa jazakumullahu khairan kathiran ala ma qaddamtum li khidmati hadza al-mashru'i al-mubarak"*

*(Semoga Allah memberkahi kalian dan membalas kebaikan kalian dengan balasan yang banyak atas apa yang telah kalian sumbangkan untuk melayani proyek yang diberkahi ini)*

---

**⚡ Mari bersama-sama membangun database Islamic terlengkap untuk aplikasi Amalanku!**

*Setiap data yang Anda kontribusikan adalah amal jariyah yang pahalanya akan terus mengalir selama aplikasi digunakan oleh umat Islam di seluruh dunia* 🤲
