# 🤲 Amalanku - Contributing Guide

Terima kasih ingin berkontribusi untuk **Amalanku**! Panduan ini akan membantu kamu menambahkan task/amalan baru ke dalam aplikasi.

## 📋 Cara Kontribusi

### 1️⃣ Fork & Clone Repository

```bash
git clone https://github.com/amalanku/amalanku.github.io.git
cd amalanku.github.io
```

### 2️⃣ Buat Branch Baru

```bash
git checkout -b add-task-nama-amalan
```

### 3️⃣ Tambahkan Task Baru

Ada 2 file yang perlu kamu edit:

#### A. File Task Data (`data/APP/task/id/custom/(nomor-id).json`)

Tambahkan object task baru dengan struktur berikut:

```json
{
  "id": 999,
  "created_at": "2025-11-10T00:00:00.000000+00:00",
  "max_poin": 5,
  "type": 1,
  "rule": {
    "type": "all_day",
    "description": "Whole day"
  },
  "status": 2,
  "name": "Nama Amalan",
  "group": "Kategori Amalan",
  "desc": "Deskripsi singkat amalan",
  "source": "Dalil/sumber rujukan amalan (hadist, ayat, dll)",
  "level": 1,
  "unique_id": 3001
}
```

#### B. File Task Name (`data/APP/task/id/custom.json`)

Tambahkan metadata task untuk widget:

```json
{
  "author": "@username_github_kamu",
  "widget_deeds": true,
  "widget_shalat": false,
  "title": "Judul Task",
  "desc": "Deskripsi task untuk widget",
  "category": "Kategori"
}
```

---

## 🔧 Parameter Explained

### Task Object (`tasks.json`)

- Contoh Lengkap [Data Task Pro](https://github.com/amalanku/amalanku.github.io/blob/main/data/APP/task/id/pro.json)

| Field        | Type   | Required | Deskripsi                                                            |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `id`         | number | ✅       | ID unik task (gunakan nomor selanjutnya yang belum terpakai)         |
| `created_at` | string | ✅       | Timestamp ISO 8601                                                   |
| `max_poin`   | number | ✅       | Poin maksimal yang didapat (biasanya 5)                              |
| `type`       | number | ✅       | Tipe frekuensi: `1` = Harian, `2` = Mingguan, `3` = Bulanan          |
| `rule`       | object | ✅       | Aturan waktu task (lihat [Rule Types](#rule-types))                  |
| `status`     | number | ✅       | Status hukum: `1` = Wajib, `2` = Sunnah, `3` = Baik untuk dikerjakan |
| `name`       | string | ✅       | Nama task/amalan                                                     |
| `group`      | string | ✅       | Grup/kategori amalan (contoh: "Rukun Islam", "Ibadah Harian")        |
| `desc`       | string | ✅       | Deskripsi lengkap amalan                                             |
| `source`     | string | ✅       | Dalil dari Al-Qur'an/Hadist atau rujukan lainnya                     |
| `level`      | number | ✅       | Level task (gunakan `1` untuk task baru)                             |
| `unique_id`  | number | ✅       | ID unik global (gunakan range 3000+)                                 |

### Task Name Object (`custom.json`)

| Field           | Type    | Required | Deskripsi                       |
| --------------- | ------- | -------- | ------------------------------- |
| `author`        | string  | ✅       | Username GitHub kamu (dengan @) |
| `widget_deeds`  | boolean | ✅       | Tampil di widget amalan umum?   |
| `widget_shalat` | boolean | ✅       | Tampil di widget sholat?        |
| `title`         | string  | ✅       | Judul untuk widget              |
| `desc`          | string  | ✅       | Deskripsi singkat untuk widget  |
| `category`      | string  | ✅       | Kategori task                   |

---

## ⏰ Rule Types

### 1. All Day (Seharian)

Task yang bisa dikerjakan kapan saja dalam sehari.

```json
{
  "type": "all_day",
  "description": "Whole day"
}
```

**Contoh:** Tilawah Al-Qur'an, Sedekah, Doa Pagi

---

### 2. Time Range (Rentang Waktu)

Task yang harus dikerjakan dalam rentang waktu tertentu.

```json
{
  "type": "time_range",
  "start_time": "05:00",
  "end_time": "12:00"
}
```

**Contoh:** Sholat Dhuha (08:00-11:00), Sholat Subuh (04:00-06:00)

---

### 3. Weekly (Mingguan)

Task yang dilakukan pada hari tertentu setiap minggu.

```json
{
  "type": "weekly",
  "day": "monday",
  "description": "Every Monday"
}
```

**Nilai `day`:** `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`, `sunday`

**Contoh:** Puasa Senin, Puasa Kamis

---

### 4. Hijri Date (Tanggal Hijriyah)

Task yang dilakukan pada tanggal tertentu dalam kalender Hijriyah.

```json
{
  "type": "hijri_date",
  "day": 13,
  "duration": "all_day"
}
```

**Contoh:** Puasa Ayyamul Bidh (tanggal 13, 14, 15), Puasa Asyura (10 Muharram)

---

## 📝 Contoh Lengkap

### Contoh 1: Sholat Dhuha

**File: `data/tasks.json`**

```json
{
  "id": 100,
  "created_at": "2025-11-10T00:00:00.000000+00:00",
  "max_poin": 5,
  "type": 1,
  "rule": {
    "type": "time_range",
    "start_time": "06:00",
    "end_time": "11:00"
  },
  "status": 2,
  "name": "Sholat Dhuha",
  "group": "Sholat Sunnah",
  "desc": "Mengerjakan sholat Dhuha minimal 2 rakaat di pagi hari",
  "source": "\"Barangsiapa yang shalat Dhuha dua rakaat, dia tidak termasuk orang-orang yang lalai.\" [HR. Abu Dawud no. 1289]",
  "level": 1,
  "unique_id": 3100
}
```

**File: `data/task_names.json`**

```json
{
  "author": "@johndoe",
  "widget_deeds": false,
  "widget_shalat": true,
  "title": "Sholat Dhuha",
  "desc": "Sholat sunnah di pagi hari pembuka pintu rezeki",
  "category": "Shalat"
}
```

---

### Contoh 2: Puasa Senin-Kamis

**File: `data/tasks.json`**

```json
{
  "id": 101,
  "created_at": "2025-11-10T00:00:00.000000+00:00",
  "max_poin": 10,
  "type": 2,
  "rule": {
    "type": "weekly",
    "day": "monday",
    "description": "Every Monday"
  },
  "status": 2,
  "name": "Puasa Senin",
  "group": "Puasa Sunnah",
  "desc": "Berpuasa pada hari Senin mengikuti sunnah Rasulullah SAW",
  "source": "\"Amal-amal dihadapkan pada hari Senin dan Kamis, maka aku suka amalku dihadapkan dalam keadaan aku berpuasa.\" [HR. Tirmidzi no. 747]",
  "level": 1,
  "unique_id": 3101
}
```

**File: `data/task_names.json`**

```json
{
  "author": "@johndoe",
  "widget_deeds": true,
  "widget_shalat": false,
  "title": "Puasa Senin-Kamis",
  "desc": "Puasa sunnah dua kali seminggu",
  "category": "Puasa"
}
```

---

### Contoh 3: Sedekah Harian

**File: `data/tasks.json`**

```json
{
  "id": 102,
  "created_at": "2025-11-10T00:00:00.000000+00:00",
  "max_poin": 5,
  "type": 1,
  "rule": {
    "type": "all_day",
    "description": "Whole day"
  },
  "status": 3,
  "name": "Sedekah Harian",
  "group": "Ibadah Harian",
  "desc": "Menyisihkan sebagian rezeki untuk bersedekah setiap hari",
  "source": "\"Sedekah itu tidak akan mengurangi harta.\" [HR. Muslim no. 2588]",
  "level": 1,
  "unique_id": 3102
}
```

**File: `data/task_names.json`**

```json
{
  "author": "@johndoe",
  "widget_deeds": true,
  "widget_shalat": false,
  "title": "Sedekah",
  "desc": "Berbagi rezeki untuk keberkahan",
  "category": "Kebaikan"
}
```

---

## ✅ Checklist Sebelum Submit PR

- [ ] ID task unik dan belum terpakai
- [ ] `unique_id` menggunakan range 3000+ dan belum terpakai
- [ ] Semua field required sudah diisi
- [ ] `type`, `status`, dan `rule.type` sesuai dengan nilai yang valid
- [ ] Source/dalil sudah dicantumkan dengan jelas
- [ ] Sudah test di local (jika memungkinkan)
- [ ] Commit message jelas: `feat: add [nama amalan] task`
- [ ] Task name sudah ditambahkan di `task_names.json`

---

## 🚀 Submit Pull Request

1. Commit perubahan kamu:

```bash
git add .
git commit -m "feat: add Sholat Dhuha task"
git push origin add-task-sholat-dhuha
```

2. Buka Pull Request di GitHub dengan deskripsi:

```markdown
## 📝 Task Baru: [Nama Amalan]

### Deskripsi

[Jelaskan amalan yang ditambahkan]

### Kategori

- Type: [Harian/Mingguan/Bulanan]
- Status: [Wajib/Sunnah/Baik untuk dikerjakan]

### Checklist

- [x] Task data sudah ditambahkan
- [x] Task name sudah ditambahkan
- [x] Dalil sudah dicantumkan
- [x] Sudah test di local
```

---

## 💡 Tips

- Pastikan dalil yang dicantumkan **akurat** dan dari sumber yang **terpercaya**
- Gunakan bahasa yang **mudah dipahami** untuk deskripsi
- Jika ragu dengan hukum/status amalan, konsultasikan dengan ustadz/referensi terpercaya
- Untuk amalan yang kontroversial, lebih baik diskusikan di issue terlebih dahulu

---

## 🤝 Need Help?

- Buka [Issue](https://github.com/amalanku/amalanku.github.io/issues) untuk diskusi
- Email: flagodna.com@gmail

---

## 📜 Kategori Task yang Tersedia

- **Rukun Islam** - Sholat wajib 5 waktu
- **Sholat Sunnah** - Sholat rawatib, dhuha, tahajud, dll
- **Ibadah Harian** - Tilawah, dzikir, doa, dll
- **Puasa Sunnah** - Puasa Senin-Kamis, Ayyamul Bidh, dll
- **Kebaikan** - Sedekah, berbuat baik, silaturahmi, dll
- **Adab & Akhlak** - Senyum, salam, tolong-menolong, dll

Jika kategori yang kamu butuhkan belum ada, silakan usulkan di issue!

---

**JazakAllahu Khairan** untuk kontribusinya! Semoga menjadi amal jariyah yang terus mengalir pahalanya 🤲✨
