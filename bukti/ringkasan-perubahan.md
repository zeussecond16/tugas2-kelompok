# Ringkasan Perubahan Kode Dashboard Adaptif

Dokumen ini mencatat bukti perubahan kode pada `app/src/main/java/com/example/uicompose/MainActivity.kt` sesuai dengan 5 persyaratan Tugas Mandiri.

---

## Tabel Perubahan Persyaratan

| No. Persyaratan | File & Nama Fungsi / Baris | Nilai Sebelum | Nilai Sesudah |
| :--- | :--- | :--- | :--- |
| **1. Tambah minimal 2 kartu mata kuliah** | `MainActivity.kt` / `DashboardContent` (Baris 179 - 184) | 2 Mata Kuliah (*Pemrograman Mobile*, *Basis Data*) | **4 Mata Kuliah** (Ditambahkan *Struktur Data* & *Analisis Data*) |
| **2. Palet warna diubah tanpa mengorbankan kontras** | `MainActivity.kt` / Top-level constants (Baris 48 - 56) | Warna standar bawaan | Custom Palette: `BrandPurple` (#6750A4), `BrandLavender` (#EADDFF), `SoftGreen` (#E0F2E8), `SoftBlue` (#E3EDFF), `SoftOrange` (#FFEAD5), `SoftPink` (#FCE4EC) |
| **3. minSize GridCells.Adaptive diatur** | `MainActivity.kt` / `DashboardContent` (Baris 187) | `minSize = 160.dp` / default | `minSize = 220.dp` |
| **4. Teks panjang tidak terpotong (overflow handled)** | `MainActivity.kt` / `CourseCard` (Baris 314 - 317) | `Column` polos tanpa weight/maxLines | `Column(modifier = Modifier.weight(1f))` dengan `maxLines = 2` dan `overflow = TextOverflow.Ellipsis` |
| **5. Diuji di ponsel dan tablet/layar lebar** | `MainActivity.kt` / `@Preview` (Baris 339 - 349) | Single Preview default | **Dual Preview**: `PhonePreview` (393x850 dp) & `TabletPreview` (1000x800 dp) |

---

## Potongan Kode Sebelum vs Sesudah

### 1. Penambahan Kartu Mata Kuliah & Pengaturan `minSize`
* **File**: `app/src/main/java/com/example/uicompose/MainActivity.kt`
* **Baris**: 179–187

#### Sebelum:
```kotlin
// Baris 179-183 (Sebelum)
val courses = listOf(
    CourseData("Pemrograman Mobile", "Jetpack Compose dan Kotlin", "Pertemuan 5 · Layout Adaptif", 0.72f, Icons.Filled.School, BrandPurple, BrandLavender),
    CourseData("Basis Data", "Normalisasi dan perancangan ERD", "Tugas dikumpulkan Jumat", 0.56f, Icons.Filled.Science, Color(0xFF24734A), SoftGreen)
)

// Baris 187 (Sebelum)
LazyVerticalGrid(
    columns = GridCells.Adaptive(minSize = 160.dp),
```

#### Sesudah:
```kotlin
// Baris 179-184 (Sesudah)
val courses = listOf(
    CourseData("Pemrograman Mobile", "Jetpack Compose dan Kotlin", "Pertemuan 5 · Layout Adaptif", 0.72f, Icons.Filled.School, BrandPurple, BrandLavender),
    CourseData("Basis Data", "Normalisasi dan perancangan ERD", "Tugas dikumpulkan Jumat", 0.56f, Icons.Filled.Science, Color(0xFF24734A), SoftGreen),
    CourseData("Struktur Data", "Array, list, dan pencarian", "Latihan mandiri", 0.84f, Icons.Filled.Code, Color(0xFF9A5700), SoftOrange),
    CourseData("Analisis Data", "Statistik deskriptif", "Materi minggu ini", 0.41f, Icons.Filled.BarChart, Color(0xFF9A405D), SoftPink)
)

// Baris 187 (Sesudah)
LazyVerticalGrid(
    columns = GridCells.Adaptive(minSize = 220.dp),
```

---

### 2. Definisi Palet Warna
* **File**: `app/src/main/java/com/example/uicompose/MainActivity.kt`
* **Baris**: 48–56

#### Sebelum:
```kotlin
// Baris 48-51 (Sebelum)
private val BrandPurple = Color(0xFF6750A4)
private val BrandLavender = Color(0xFFEADDFF)
private val PageBackground = Color(0xFFF7F5FC)
```

#### Sesudah:
```kotlin
// Baris 48-56 (Sesudah)
private val BrandPurple = Color(0xFF6750A4)
private val BrandLavender = Color(0xFFEADDFF)
private val PageBackground = Color(0xFFF7F5FC)
private val Ink = Color(0xFF211A31)
private val MutedInk = Color(0xFF625D70)
private val SoftGreen = Color(0xFFE0F2E8)
private val SoftBlue = Color(0xFFE3EDFF)
private val SoftOrange = Color(0xFFFFEAD5)
private val SoftPink = Color(0xFFFCE4EC)
```

---

### 3. Penanganan Teks Panjang (`TextOverflow.Ellipsis` & `weight`)
* **File**: `app/src/main/java/com/example/uicompose/MainActivity.kt`
* **Baris**: 314–317

#### Sebelum:
```kotlin
// Baris 314-317 (Sebelum)
Column {
    Text(course.title, style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.Bold, color = Ink)
    Spacer(Modifier.height(4.dp))
    Text(course.subtitle, style = MaterialTheme.typography.bodySmall, color = MutedInk)
}
```

#### Sesudah:
```kotlin
// Baris 314-317 (Sesudah)
Column(modifier = Modifier.weight(1f)) {
    Text(course.title, style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.Bold, color = Ink, maxLines = 2, overflow = TextOverflow.Ellipsis)
    Spacer(Modifier.height(4.dp))
    Text(course.subtitle, style = MaterialTheme.typography.bodySmall, color = MutedInk, maxLines = 2, overflow = TextOverflow.Ellipsis)
}
```
