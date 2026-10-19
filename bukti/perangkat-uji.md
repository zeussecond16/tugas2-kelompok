# Bukti Spesifikasi Perangkat & Lingkungan Pengujian

Dokumen ini mencatat spesifikasi ukuran layar dan lingkungan pengujian layout adaptif pada aplikasi **KampusKu**.

---

## 1. Spesifikasi Layar Pengujian

Pengujian dilakukan menggunakan **Window Size Classes** sesuai standar Jetpack Compose:

| Jenis Layar / Preview | Dimensi (Lebar x Tinggi) | Window Size Class | Label Layout pada App | Visibilitas Side Rail | Jumlah Kolom Grid Kartu |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Ponsel (Compact)** | 393 dp x 850 dp | `COMPACT` (`< 600 dp`) | `COMPACT · PONSEL` | Tidak Tampil | 1 Kolom |
| **Layar Sedang (Medium)** | 700 dp x 800 dp | `MEDIUM` (`600 dp - 839 dp`) | `MEDIUM · LAYAR SEDANG` | Tidak Tampil | 2-3 Kolom |
| **Tablet / Laptop (Expanded)** | 1000 dp x 800 dp | `EXPANDED` (`>= 840 dp`) | `EXPANDED · TABLET/LAPTOP` | **Tampil** (Lebar 88 dp) | 3 Kolom |

---

## 2. Catatan Lingkungan Pengujian

* **Metode Rendering & Screenshot**: Pengujian dilakukan langsung menggunakan **Jetpack Compose Preview Engine** (`@Preview` annotation pada fungsi `PhonePreview` dan `TabletPreview` di `MainActivity.kt`). Engine ini merender langsung hirarki UI dan piksel asli dari komponen Compose tanpa mengubah logika aplikasi.
* **Perangkat ADB**: Emulator ADB fisik/virtual tidak berjalan aktif pada sesi sistem ini, sehingga penggambilan sampel screenshot disandarkan pada visualisasi resmi Jetpack Compose Preview.
