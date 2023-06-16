# QR Code-Based School Attendance System Web Application

[![PHP Composer](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/actions/workflows/php.yml/badge.svg)](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/actions/workflows/php.yml)
![GitHub Repo stars](https://img.shields.io/github/stars/ikhsan3adi/Absensi-Sekolah-QR-Code?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/ikhsan3adi/Absensi-Sekolah-QR-Code?style=social)

![Dashboard preview](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/hero.png)

QR Code-Based School Attendance System Web Application is a project that aims to automate the attendance process in the school environment using QR code technology. This application was developed using the CodeIgniter 4 framework and is designed to make it easier to manage and record student and teacher attendance.

## Fitur Utama
- **QR Code scanner.** Setiap siswa/guru menunjukkan qr code kepada perangkat yang dilengkapi dengan kamera. Aplikasi akan memvalidasi QR code dan mencatat kehadiran siswa ke dalam database.
- **Login petugas.**
- **Dashboard petugas.** Petugas sekolah dapat dengan mudah memantau kehadiran siswa dalam periode waktu tertentu melalui tampilan yang disediakan.
- **QR Code generator.** Petugas yang sudah login akan men-generate qr code setiap siswa/guru secara otomatis. Setiap siswa akan diberikan QR code unik yang terkait dengan identitas siswa. QR code ini akan digunakan saat proses absensi.
- **Ubah data absen siswa/guru.** Petugas dapat mengubah data absensi setiap siswa/guru. Misalnya mengubah data kehadiran dari `tanpa keterangan` menjadi `sakit` atau `izin`.
- **Tambah, Ubah, Hapus(CRUD) data siswa/guru.**
- **Tambah, Ubah, Hapus(CRUD) data kelas.**
- **Lihat, Tambah, Ubah, Hapus(CRUD) data petugas.** (khusus petugas yang login sebagai **`superadmin`**).
- **Generate Laporan.** Generate laporan dalam bentuk pdf.

## Framework dan Library Yang Digunakan
- CodeIgniter 4
- [Material Dashboard Bootstrap 4](https://www.creative-tim.com/product/material-dashboard-bs4)
- [Myth Auth Library](https://github.com/lonnieezell/myth-auth)
- [Endroid QR Code Generator](https://github.com/endroid/qr-code)
- [ZXing JS QR Code Scanner](https://github.com/zxing-js/library)

## Screenshots
### Tampilan Halaman QR Scanner
![QR Scanner view](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_5_2023_204644.jpeg)

### Tampilan Absen Masuk dan Pulang
![QR Scanner absen](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/absen.jpg)

### Tampilan Login Petugas
![Login](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_4_2023_20573.jpeg)

### Tampilan Dashboard Petugas
![Dashboard](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_10_2023_205123.jpeg)

### Tampilan CRUD Data Absen
| Siswa (Dengan Data Kelas)     | Guru          |
| ----------------------------- |:-------------:|
| ![CRUD Absen Siswa](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_11_2023_205146.jpeg) | ![CRUD Absen Guru](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_2_2023_20525.jpeg) |

### Tampilan Ubah Data Kehadiran
![Kehadiran](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_17_2023_205557.jpeg)

### Tampilan CRUD Data Siswa & Guru
| Siswa         | Guru          |
| ------------- |:-------------:|
| ![CRUD Data Siswa](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_12_2023_205221.jpeg) | ![CRUD Data Guru](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_14_2023_205256.jpeg) |

### Tampilan Generate QR Code dan Generate Laporan
| Generate QR   | Generate Laporan |
| ------------- |:----------------:|
| ![Generate QR](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_3_2023_20539.jpeg) | ![Generate Laporan](https://github.com/ikhsan3adi/Absensi-Sekolah-QR-Code/raw/master/screenshots/image_15_2023_205322.jpeg) |

## Cara Penggunaan
### Persyaratan
- [Composer](https://getcomposer.org/).
- PHP dan MySQL atau [XAMPP](https://www.apachefriends.org/download.html) versi 8.0+ dengan mengaktifkan extension `-intl` dan `-gd`.
- Pastikan perangkat memiliki kamera/webcam untuk menjalankan qr scanner. Bisa juga menggunakan kamera HP dengan bantuan software DroidCam.

### Instalasi
- Unduh dan impor kode proyek ini ke dalam direktori proyek anda (htdocs).
- (Opsional) Konfigurasi file `.env` untuk mengatur parameter seperti koneksi database dan pengaturan lainnya sesuai dengan lingkungan pengembangan Anda.
- Konfigurasi file `app/Config/App.php` untuk mengubah base url sesuai dengan nama folder project.
- Penting ⚠️. Install dependencies yang diperlukan dengan cara menjalankan perintah berikut di terminal:
```shell
composer install
```
- Penting ⚠️. Jalankan migrasi database untuk membuat struktur tabel yang diperlukan. Ketikkan perintah berikut di terminal:
```shell
php spark migrate --all
```
- Buka file `vendor/myth/auth/src/Config/Auth.php`. Lalu ubah baris berikut:
```php
public $views = [
        'login'           => 'Myth\Auth\Views\login', // baris ini
        'register'        => 'Myth\Auth\Views\register',
        'forgot'          => 'Myth\Auth\Views\forgot',
        'reset'           => 'Myth\Auth\Views\reset',
        'emailForgot'     => 'Myth\Auth\Views\emails\forgot',
        'emailActivation' => 'Myth\Auth\Views\emails\activation',
    ];
```
menjadi:
```php
public $views = [
        'login'           => '\App\Views\admin\login', // ubah seperti ini agar login bisa diakses
        'register'        => 'Myth\Auth\Views\register',
        'forgot'          => 'Myth\Auth\Views\forgot',
        'reset'           => 'Myth\Auth\Views\reset',
        'emailForgot'     => 'Myth\Auth\Views\emails\forgot',
        'emailActivation' => 'Myth\Auth\Views\emails\activation',
    ];
```
- Jalankan web server.
- Lalu jalankan aplikasi di browser.
- Login menggunakan krendensial superadmin:
```
username : superadmin
password : 1234ikh123
```
- Izinkan akses kamera.

## Kesimpulan
Dengan aplikasi web sistem absensi sekolah berbasis QR code ini, diharapkan proses absensi di sekolah menjadi lebih efisien dan terotomatisasi. Proyek ini dapat diadaptasi dan dikembangkan lebih lanjut sesuai dengan kebutuhan dan persyaratan sekolah Anda.

Jangan lupa beri star ya...⭐

## Contributing
Kami menerima kontribusi dari komunitas terbuka untuk meningkatkan aplikasi ini. Jika Anda menemukan masalah, bug, atau memiliki saran untuk peningkatan, silakan buat issue baru dalam repositori ini atau ajukan pull request.

## Authors
- [@ikhsan3adi](https://www.github.com/ikhsan3adi)
