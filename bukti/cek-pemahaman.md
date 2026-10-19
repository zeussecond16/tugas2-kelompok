# Jawaban Cek Pemahaman Layout Adaptif

### 1. Perbedaan `Column` dan `Row`
`Column` menyusun komponen anak secara vertikal dari atas ke bawah, sedangkan `Row` menyusun komponen anak secara horizontal dari kiri ke kanan. Keduanya merupakan layout kontainer dasar di Jetpack Compose yang mengatur posisi elemen berdasarkan sumbu aksis utamanya masing-masing.

### 2. Kapan `LazyColumn` lebih tepat daripada `Column`
`LazyColumn` lebih tepat digunakan ketika jumlah item data berukuran besar, bersifat dinamis, atau berasal dari API/database sehingga memerlukan scroll. Berbeda dengan `Column` yang merender seluruh item sekaligus di memori, `LazyColumn` hanya merender item yang saat ini terlihat di layar (*lazy loading*).

### 3. Peran `minSize` pada `GridCells.Adaptive`
Parameter `minSize` menentukan batas lebar terkecil yang harus dimiliki oleh setiap kolom pada grid. Jetpack Compose akan menghitung berapa banyak kolom yang muat pada lebar layar yang ada tanpa membuat lebar per kolom kurang dari nilai `minSize` tersebut.

### 4. Mengapa lebar jendela lebih tepat daripada label "tablet"
Menggunakan lebar jendela (*window size width*) lebih akurat karena satu perangkat tablet dapat diputar (orientasi potret/lanskap), dijalankan dalam mode *split-screen*, atau berupa perangkat *foldable*. Desain adaptif berbasis lebar jendela memastikan tata letak tetap responsif sesuai ruang fisik yang benar-benar tersedia bagi aplikasi, bukan tergantung merk atau tipe perangkat.

### 5. Satu perubahan visual saat dashboard berpindah ke `Expanded`
Saat berpindah ke mode `Expanded` (`lebar >= 840 dp`), perubahan visual utama yang muncul adalah hadirnya bilah navigasi samping (`DashboardSideRail`) selebar 88 dp di sisi paling kiri layar. Selain itu, grid ringkasan akademik dan kartu mata kuliah bertambah jumlah kolomnya secara otomatis menjadi 3 kolom horizontal.
