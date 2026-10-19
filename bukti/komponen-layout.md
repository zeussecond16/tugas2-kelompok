# Daftar Komponen Layout dan Fungsinya

Berikut adalah daftar komponen layout yang digunakan dalam kode `MainActivity.kt` beserta fungsinya masing-masing dalam proyek ini:

1. **`Scaffold`**: Berfungsi sebagai struktur tata letak tingkat atas yang menyediakan slot dasar seperti `topBar` dan tempat menampung area konten utama aplikasi.
2. **`TopAppBar`**: Berfungsi sebagai bilah navigasi bagian atas untuk menampilkan judul aplikasi "KampusKu", subjudul "Dashboard Perkuliahan", dan ikon logo kampus.
3. **`BoxWithConstraints`**: Berfungsi membaca ukuran lebar (`maxWidth`) yang tersedia secara dinamis guna menentukan *Window Size Class* (`COMPACT`, `MEDIUM`, `EXPANDED`) serta mengontrol visibilitas side rail.
4. **`Row`**: Berfungsi menyusun elemen secara horizontal, seperti menempatkan `DashboardSideRail` di sebelah kiri dan `DashboardContent` di sebelah kanan pada mode layar lebar.
5. **`Column`**: Berfungsi menyusun elemen secara vertikal dari atas ke bawah, seperti susunan item navigasi pada side rail dan informasi teks pada kartu.
6. **`LazyVerticalGrid`**: Berfungsi menampilkan daftar item dalam bentuk grid yang dapat di-scroll secara efisien dengan alokasi memori dinamis.
7. **`GridCells.Adaptive`**: Berfungsi menentukan jumlah kolom grid secara fleksibel berdasarkan ukuran minimum sel (`minSize = 220.dp`).
8. **`GridItemSpan`**: Berfungsi mengatur sel pada grid agar dapat membentang seluas seluruh lebar kolom (`maxLineSpan`), digunakan untuk komponen banner, welcome card, dan header seksi.
9. **`Card`**: Berfungsi memberikan wadah visual berbentuk kartu dengan sudut melengkung dan elevasi untuk mengelompokkan informasi seperti `WelcomeCard`, `MetricCard`, dan `CourseCard`.
10. **`Surface`**: Berfungsi menyediakan latar belakang dengan warna, bentuk (*shape*), dan elevasi tertentu seperti pada item side rail, indikator ikon, dan banner mode layout.
11. **`Spacer`**: Berfungsi memberikan jarak horizontal atau vertikal antar komponen UI dengan ukuran spesifik (`dp`).
12. **`Box`**: Berfungsi menumpuk elemen secara z-axis atau meratakan elemen tepat di tengah (*center alignment*) di dalam wadah berukuran tetap.
13. **`LinearProgressIndicator`**: Berfungsi menampilkan batang kemajuan visual dari nilai progres pembelajaran pada kartu mata kuliah.
