# KampusKu - Dashboard Perkuliahan Adaptif (Jetpack Compose)

**KampusKu** adalah aplikasi Android berbasis **Jetpack Compose** dan **Material 3** yang menerapkan prinsip tata letak adaptif (*Adaptive Layout*). Aplikasi ini menyesuaikan penempatan elemen dan struktur antarmuka secara dinamis berdasarkan lebar ruang layar yang tersedia (*Window Size Classes*), baik pada ponsel, tablet, maupun laptop/layar lebar.

---

## 🚀 Fitur Utama

- **Layout Adaptif Berbasis Window Size Class**:
  - **Compact (`< 600 dp`)**: Tampilan responsif 1 kolom untuk ponsel.
  - **Medium (`600 - 839 dp`)**: Tampilan multi-kolom untuk ponsel lanskap atau layar sedang.
  - **Expanded (`>= 840 dp`)**: Tampilan dashboard lengkap dengan navigasi samping (*DashboardSideRail* selebar `88 dp`) dan grid 3 kolom.
- **Adaptive Grid**: Menggunakan `LazyVerticalGrid` dengan `GridCells.Adaptive(minSize = 220.dp)` sehingga jumlah kolom terhitung otomatis sesuai sisa ruang layar.
- **Aksesibilitas & Kontras Tinggi**: Palet warna kustom (*Brand Purple*, *Brand Lavender*, *Soft Green/Blue/Orange/Pink*) yang lulus standar kontras WCAG 2.1 AA (rasio >= 4.5:1).
- **Proteksi Teks Panjang (Overflow Handling)**: Setiap kartu mata kuliah dilengkapi `maxLines = 2`, `overflow = TextOverflow.Ellipsis`, serta fleksibilitas `Modifier.weight(1f)`.
- **Jetpack Compose Preview**: Dilengkapi `@Preview` eksplisit untuk pengujian `PhonePreview` (393 dp) dan `TabletPreview` (1000 dp).

---

## 📁 Struktur Proyek

```
UICompose/
├── app/
│   └── src/main/java/com/example/uicompose/
│       └── MainActivity.kt       # Kode utama (Theme, AdaptiveDashboard, SideRail, Grid, Cards)
├── bukti/                        # Lampiran bukti pengujian & laporan tugas mandiri
│   ├── diff.patch                # Patch perubahan kode dari versi awal
│   ├── ringkasan-perubahan.md    # Tabel perubahan & potongan kode sebelum vs sesudah
│   ├── perangkat-uji.md          # Spesifikasi dimensi & lingkungan pengujian Compose Preview
│   ├── kontras.md                # Laporan pengujian kontras warna WCAG 2.1 AA
│   ├── penjelasan-grid.md        # Penjelasan adaptivitas GridCells.Adaptive
│   ├── komponen-layout.md        # Daftar 13 komponen layout Compose dan fungsinya
│   └── cek-pemahaman.md          # Jawaban pertanyaan pemahaman layout adaptif
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## 🛠️ Prasyarat & Pustaka Utama

* **Android Studio**: Ladybug / Meerkat / 2026.1+
* **Kotlin**: 2.2+
* **Minimum SDK**: API 24 (Android 7.0)
* **Compile SDK**: API 37
* **Pustaka Utama**:
  * `androidx.compose.material3:material3`
  * `androidx.compose.material:material-icons-extended`
  * `androidx.activity:activity-compose`

---

## 💻 Cara Menjalankan & Membangun Proyek

1. **Clone / Buka Proyek di Android Studio**:
   Buka folder proyek `UICompose` di Android Studio.

2. **Sinkronisasi Gradle**:
   Jalankan Gradle Sync untuk mengunduh seluruh dependensi.

3. **Build & Run via Terminal**:
   ```bash
   ./gradlew :app:assembleDebug
   ```

4. **Melihat Preview Adaptif Tanpa Emulator**:
   - Buka file [`MainActivity.kt`](app/src/main/java/com/example/uicompose/MainActivity.kt).
   - Aktifkan mode **Split** atau **Design** di pojok kanan atas editor.
   - Preview `PhonePreview` (Compact) dan `TabletPreview` (Expanded) akan dirender secara otomatis.

---

## 📄 Lampiran & Dokumen Tugas

Seluruh berkas bukti pengujian dan jawaban pertanyaan tugas mandiri tersedia di dalam folder [`bukti/`](bukti/):
* [`bukti/ringkasan-perubahan.md`](bukti/ringkasan-perubahan.md) - Tabel perubahan persyaratan tugas mandiri.
* [`bukti/penjelasan-grid.md`](bukti/penjelasan-grid.md) - Penjelasan akademik adaptivitas grid.
* [`bukti/kontras.md`](bukti/kontras.md) - Laporan rasio kontras warna WCAG 2.1 AA.
* [`bukti/komponen-layout.md`](bukti/komponen-layout.md) - Rincian komponen layout Compose.
* [`bukti/cek-pemahaman.md`](bukti/cek-pemahaman.md) - Jawaban pertanyaan evaluasi.
