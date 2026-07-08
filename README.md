# mLITE (Customized for RSNS)

mLITE adalah alternatif ringan dan aman untuk Sistem Informasi Kesehatan (SIMKES Khanza) agar bisa dijalankan via Mobile / Browser. Repositori ini (`mlite_rsns`) merupakan versi kustomisasi khusus dengan penambahan modul dan penyesuaian fungsionalitas untuk kebutuhan RSNS.

mLITE dibangun menggunakan kerangka kerja mandiri (*Independent Framework*) yang mengutamakan kesederhanaan, kecepatan, serta kemudahan bagi pengembang untuk membuat modul-modul kustom baru.

---

## 🛠️ Persyaratan Sistem

* **Web Server**: Apache 2.2+ (dengan `mod_rewrite` aktif) atau Nginx.
* **PHP**: Versi `7.0` s/d `8.1`.
* **Database**: MySQL Server 5.5+ / MariaDB.
* **Ekstensi PHP wajib**:
  * `dom`, `gd`, `mbstring`, `pdo`, `zip`, `cURL`.

---

## 🗄️ Panduan Penggunaan Database (.sql)

Project ini memiliki dua jenis skema database yang berada di root direktori:

1. **`mlite_db.sql` (Full Schema)**
   * **Isi**: Berisi seluruh tabel dasar SIMKES Khanza sekaligus tabel fitur/modul bawaan mLITE.
   * **Penggunaan**: Gunakan file ini jika Anda melakukan **instalasi baru dari awal** pada database yang masih kosong.

2. **`mlite_only.sql` (mLITE Tables Only)**
   * **Isi**: Hanya berisi tabel-tabel berprefiks `mlite_` (seperti `mlite_settings`, `mlite_users`, dll.) tanpa menyertakan tabel standar SIMKES Khanza.
   * **Penggunaan**: Gunakan file ini jika Anda **sudah memiliki database SIMKES Khanza aktif** yang sudah berjalan, sehingga proses impor tidak menimpa data transaksi dan pasien yang sudah ada.

---

## 👥 Cara Menambah Pengguna Baru

Untuk menambahkan akun pengguna (user) baru, silakan gunakan Panel Administrasi:
1. Akses halaman admin di browser: `http://localhost/mlite-5.2.0/admin` (sesuaikan domain/IP Anda).
2. Login menggunakan akun administrator (Default: Username `admin` / Password `admin`).
3. Buka menu **Pengguna** -> **Tambah Baru**.
4. Lengkapi formulir (Username/NIK, Email, Password minimal 8 karakter, Role, dan Hak Akses Modul).
5. Klik **Simpan**.

---

## 🚀 Mengunggah ke GitHub (Git Commands)

Untuk melakukan push project ini ke repositori GitHub Anda:

```bash
# 1. Hubungkan ke repositori online (jika belum)
git remote add origin https://github.com/Rifangga99/mlite_rsns.git

# 2. Push seluruh perubahan di branch main ke GitHub
git push -u origin main
```

---

## 📝 Catatan Tambahan Modul Kustom
Project ini dilengkapi beberapa skema tabel kustom tambahan seperti:
* Aset Logistik Non-Medis (`rsns_custom_logistik_non_medis_aset`)
* Mutasi dan Pemeliharaan Aset RSNS.

Informasi lisensi dan pengembangan lebih lanjut dapat merujuk pada file [LICENSE](LICENSE) dan dokumentasi internal di folder [docs/](docs/).
