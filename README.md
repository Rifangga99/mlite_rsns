# mLITE - Sistem Informasi Logistik Non-Medis

Aplikasi manajemen logistik non-medis rumah sakit berbasis PHP dengan arsitektur mLITE Framework, dirancang agar ringan, mudah dipahami, dan mudah dikembangkan untuk kebutuhan mobile dan browser.

## Fitur Tambahan logistik_non_medis

- **Manajemen Inventaris**: Pencatatan master barang (habis pakai & aset), kategori, satuan, dan gudang penyimpanan.
- **Modul Aset & Tracking**: Registrasi aset, mutasi aset antar unit, perhitungan penyusutan (depresiasi), pencetakan QR Code aset, serta pelacakan riwayat aset.
- **Rantai Pasok Pengadaan (Procurement)**: Alur pengadaan lengkap mulai dari Perencanaan, Permintaan Unit, Purchase Order (PO), hingga Penerimaan Barang ke Gudang.
- **Audit Gudang & Stock Opname**: Fitur pemeriksaan stok fisik vs sistem dengan pencatatan selisih barang.
- **Mutasi Antar Gudang**: Distribusi barang antar gudang logistik.
- **Early Warning System (EWS)**: Peringatan dini untuk barang yang mendekati tanggal kedaluwarsa.
- **Kuota Unit Bulanan**: Batasan kuota pengeluaran barang habis pakai per unit/departemen per periode bulan.
- **Sensus Aset**: Pemeriksaan kondisi fisik aset secara berkala oleh petugas.

---

## Persyaratan Sistem

- **PHP**: Versi 7.0 s/d 8.1 (Sangat direkomendasikan menggunakan PHP 7.3)
- **Database**: MySQL / MariaDB
- **Web Server**: Apache dengan modul `mod_rewrite` aktif (untuk *pretty URL*) atau Nginx
- **Dependency Manager**: Composer

---

## Cara Instalasi & Konfigurasi

### 1. Kloning / Unduh Proyek
Unduh zip proyek ini dari GitHub atau kloning menggunakan Git:
```bash
git clone https://github.com/Rifangga99/mlite_rsns.git
```
Pindahkan folder proyek ke direktori web root Anda (misalnya `C:/xampp/htdocs/mlite-5.2.0`).

### 2. Instal Dependensi Composer
Karena folder `vendor` diabaikan dalam repositori ini, Anda harus menginstalnya terlebih dahulu dengan menjalankan perintah berikut di direktori proyek:
```bash
composer install
```

### 3. Impor Database
1. Buka **phpMyAdmin** atau GUI Database client favorit Anda.
2. Buat database baru bernama `mlite`.
3. Impor berkas database yang sesuai:
   - Gunakan **`mlite_db.sql`** jika Anda melakukan instalasi baru dari awal (termasuk skema dasar SIMKES Khanza).
   - Gunakan **`mlite_only.sql`** jika Anda hanya ingin menambahkan tabel mLITE ke database SIMKES Khanza yang sudah ada.

### 4. Konfigurasi Koneksi Database
Buka berkas konfigurasi di `config.php` pada root direktori proyek dan sesuaikan dengan setelan server lokal Anda:
```php
define('DBHOST', 'localhost');
define('DBPORT', '3306');
define('DBUSER', 'root');
define('DBPASS', ''); // Isi password mysql Anda jika ada
define('DBNAME', 'mlite');
```

---

## Kredensial Login Default (Default Users)

Setelah mengimpor database, Anda dapat masuk ke dalam sistem menggunakan akun default berikut:

| Peran (Role) | Username | Password | Deskripsi |
| :--- | :--- | :--- | :--- |
| **Administrator** | `admin` | `admin` | Akses penuh ke seluruh menu administrasi, pengaturan, dan manajemen modul. |

> [!WARNING]
> Sangat disarankan untuk segera mengubah kata sandi default setelah berhasil masuk untuk pertama kalinya demi keamanan sistem Anda.
