# Lab8Web

|                |                    |
| ------------------ | ------------------ |
|      _Nama_    | Dwi Okta Ramadhani |
|      _NIM_     |      312410056     |
|     _Kelas_    |      TI.24.A1      |
|  _Mata Kuliah_ | Bahasa Pemrograman Web 1 |

Aplikasi manajemen barang berbasis web yang dibangun dengan PHP dan MySQL. Aplikasi ini memungkinkan pengguna untuk mengelola data barang seperti menambah, melihat, mengubah, dan menghapus data barang.

## Fitur

- **Manajemen Data Barang**
  - Menampilkan daftar barang
  - Menambah data barang baru
  - Mengubah data barang yang ada
  - Menghapus data barang
  - Upload gambar untuk setiap barang

- **Antarmuka Pengguna**
  - Desain responsif yang modern
  - Tampilan tabel yang rapi
  - Form input yang user-friendly
  - Notifikasi untuk setiap aksi

- **Keamanan**
  - Proteksi SQL Injection
  - Validasi input
  - Penanganan error yang baik

## Persyaratan Sistem

- PHP 7.4 atau lebih baru
- MySQL 5.7 atau lebih baru
- Web server (XAMPP, WAMP, LAMP, dll.)
- Browser web modern (Chrome, Firefox, Edge, dll.)

## Instalasi

1. Clone atau download repositori ini ke dalam folder htdocs (XAMPP) atau www (WAMP) Anda.
   ```
   git clone [url-repositori] lab8_php_database
   ```

2. Buat database baru di MySQL:
   ```sql
   CREATE DATABASE lab8_php_database;
   ```

3. Import file SQL yang disediakan (jika ada) atau buat tabel dengan perintah berikut:
   ```sql
   CREATE TABLE data_barang (
       id_barang int(10) NOT NULL AUTO_INCREMENT,
       nama varchar(100) NOT NULL,
       kategori enum('Elektronik','Pakaian','Makanan','Minuman','Lainnya') NOT NULL,
       harga_beli decimal(10,0) NOT NULL,
       harga_jual decimal(10,0) NOT NULL,
       stok int(4) NOT NULL,
       gambar varchar(100) DEFAULT NULL,
       PRIMARY KEY (id_barang)
   ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
   ```

4. Salin file `koneksi.example.php` menjadi `koneksi.php` dan sesuaikan konfigurasi database:
   ```php
   <?php
   $host = "localhost";
   $user = "root";
   $pass = "";
   $dbname = "lab8_php_database";
   $port = 3307; // Sesuaikan dengan port MySQL Anda
   
   $conn = new mysqli($host, $user, $pass, $dbname, $port);
   
   if ($conn->connect_error) {
       die("Koneksi gagal: " . $conn->connect_error);
   }
   ?>
   ```

5. Pastikan folder `gambar` memiliki izin tulis (permission 755 atau 777).

## Struktur File

```
lab8_php_database/
├── gambar/                 # Folder penyimpanan gambar
├── css/
│   └── style.css           # File CSS untuk styling
├── index.php              # Halaman utama menampilkan daftar barang
├── tambah.php             # Halaman untuk menambah data barang
├── ubah.php               # Halaman untuk mengubah data barang
├── hapus.php              # Script untuk menghapus data barang
├── koneksi.php            # File konfigurasi koneksi database
└── README.md              # Dokumentasi ini
```

## Cara Penggunaan

1. **Menampilkan Data Barang**
   - Buka `index.php` di browser
   - Data barang akan ditampilkan dalam bentuk tabel

2. **Menambah Data Barang**
   - Klik tombol "Tambah Barang" di halaman utama
   - Isi form yang disediakan
   - Upload gambar (opsional)
   - Klik "Simpan"

3. **Mengubah Data Barang**
   - Klik tombol "Ubah" pada baris data yang ingin diubah
   - Ubah data yang diperlukan
   - Upload gambar baru jika ingin mengganti (opsional)
   - Klik "Simpan Perubahan"

4. **Menghapus Data Barang**
   - Klik tombol "Hapus" pada baris data yang ingin dihapus
   - Konfirmasi penghapusan

## Validasi Form

- Semua field wajib diisi
- Harga jual harus lebih besar dari harga beli
- Stok tidak boleh negatif
- File yang diupload harus berupa gambar (jpg, jpeg, png, gif)
- Ukuran file maksimal 2MB

## Teknologi yang Digunakan

- **Frontend**
  - HTML5
  - CSS3 (dengan variabel CSS)
  - JavaScript (untuk validasi dan interaksi)
  - Font Awesome (untuk ikon)
  - Google Fonts (Poppins)

- **Backend**
  - PHP 7.4+
  - MySQLi (untuk koneksi database)
  - Prepared Statements (untuk keamanan)

## Kontribusi

1. Fork repositori ini
2. Buat branch baru (`git checkout -b fitur-baru`)
3. Commit perubahan Anda (`git commit -am 'Menambahkan fitur baru'`)
4. Push ke branch (`git push origin fitur-baru`)
5. Buat Pull Request

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).

## Kontak

Dwi Okta Ramadhani  
Email: [email@example.com]  
GitHub: [username]

---
© 2023 Dwi Okta Ramadhani - Lab 8 PHP Database
