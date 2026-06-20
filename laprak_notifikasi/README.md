# laprak_notifikasi - Aplikasi Kamera & Notifikasi 

Aplikasi FLutter sederhana untuk mengambil foto (dari kamera/galeri) serta menampilkan notifikasi lokal setelah kamera berhasil digunakan untuk menangkap foto. 

## Package Yang digunakan 
- **iamage_picker** : Untuk emngambil gambar dari kamera atau galeri 
- **flutter_local_notifications** : Menampilkan notifikasi lokal pada perangkat

## Penjelasan Setiap Widget 

### 1. `MaterialApp`
Widget paling luar yang membungkus seluruh aplikasi. Menyediakan tema (warna, font), judul, dan sistem navigasi berbasis Material Desain 

### 2. `Scaffold`
Kerangka dasar suatu halaman. Menyediakan struktur standar aplikasi seperti `appBar` (atas), `body` (isi utama), dan area lainnya. 

### 3. `Appbar`
Batang judul di bagian atas aplikasi. Di sini menampilkan teks yang berjudul **Kamera & Notifikasi**.

### 4. `Center`
Widget yang memposisiskan widget child tepat di **tengah** layar, baik secara horizontal maupun vertikal. 

### 5. `Column` 
Menyusun beberapa widget secara **vertikal (atas ke bawah)**. Dipakai untuk menumpuk: area foto, jarak. lalu tombol-tombol. 

### 6. `Image.file`
Menampilkan gambar yang berasal dari **file di perangkat** (hasil foto/galeri). Berbeda dari `Image.asset` (gambar bawaan app) atau `Image.networ` (gambar dari internet). 

### 7. `Text`
Menampilkan tulisan ke layar. Dipakai untuk teks petunjuk (contoh : "Belum ada gambar yang dipilih") dan label lainnya. 

### 8. `SizedBox`
Membuat **kotak/jarak kosong** berukuran tertentu. Di sini dipakai sebagai pemberi **jarak (spasi)** antar widget, misalnya antara foto dan tombol. 

### 9. `ElevatedButton` (atau `ElevatedButton.icon`)
Tombol timbul yang bisa ditekan. APlikasi ini memiliki 2 tombol: 
- **Ambil dari Kamera** : memanggil kamera lewat `image_picker`
- **Pilih dari Galeri** : membuka galeri lewat `image_picker`

Versi `.icon` menambahkan ikon di samping teks tombol.

### 10. `Icon`
Menampilkan ikon (mis. ikon kamera/galeri) untuk memperjelas fungsi tombol.

### 11. `Padding` 
Memberi **ruang/jarak di dalam** suatu widget, agar isinya tidak menempel ke tepi layar.

## Penjelasan Komponen Logika 

### `IamgePicker`
Objek dari package `image_picker` untuk mengambil gambar. Method `pickImage(source: ...)` dipakai dengan `ImageSource.camera` (kamera) atau `ImageSource.gallery` (galeri). 

### `FlutterLocalNotificationsPlugin`
Objek untuk mengatur & menampilkan notifikasi lokal. Diinisalisasi terlebih dahulu, lalu method `show()` dipanggin untuk memumculkan notifikasi setelah foto diambil. 

### `StatefulWidget` & `setState()`
Halaman utama memakai **StatefulWidget** karena tampilannya **berubah** (gambar diperbarui setelah menangkap gambar). `setState()` dipanggil untuk memberi tahu FLutter agar **membuat ulang** dengan gamabr baru. 

## Cara menjalankan 
1. `flutter pub get`
2. Jalankan emulator 
3. `flutter run`