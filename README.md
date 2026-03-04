<a name="top"></a>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.10-blue?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter" />
  <img src="https://img.shields.io/badge/Dart-3.10-0175C2?style=for-the-badge&logo=dart&logoColor=white" alt="Dart" />
  <img src="https://img.shields.io/badge/Provider-State_Management-00C853?style=for-the-badge" alt="Provider" />
  <img src="https://img.shields.io/badge/Material_3-Letterboxd_Style-0F141A?style=for-the-badge" alt="Material 3 Letterboxd" />
</p>

<h1 align="center">Registrasi Event Demo</h1>
<p align="center">
  <i>Aplikasi demo registrasi event dengan tema gelap ala Letterboxd dan state management Provider.</i>
</p>
<p align="center">
  <b>Mata Kuliah Pemrograman Aplikasi Bergerak (PAB)</b>
</p>
<p align="center">
  <b>Aris Candra Muzaffar</b> · 2409116088
</p>

---

## 📚 Daftar Isi

- [📚 Daftar Isi](#-daftar-isi)
- [📄 Deskripsi](#-deskripsi)
- [✨ Fitur](#-fitur)
- [🛠 Stack & Widget](#-stack--widget)
- [📁 Struktur Proyek](#-struktur-proyek)
- [🚀 Cara Menjalankan](#-cara-menjalankan)
- [📸 Tampilan Aplikasi](#-tampilan-aplikasi)

---

## 📄 Deskripsi

**Registrasi Event Demo** adalah aplikasi Flutter sederhana untuk mengelola data pendaftar sebuah event. Projek ini dibuat sebagai latihan materi **form, validasi, navigasi multi-page, dan state management dengan Provider** di mata kuliah PAB.

Fokus aplikasi:

- Form registrasi dengan validasi yang jelas dan feedback ramah pengguna.
- Penyimpanan data pendaftar di memori menggunakan `ChangeNotifier` + `Provider`.
- Tampilan daftar dan detail pendaftar yang konsisten.
- **Tema visual gelap terinspirasi Letterboxd**: background gelap kebiruan, kartu berlapis, serta aksen hijau neon untuk elemen penting.

---

## ✨ Fitur

<p>
  <img src="https://img.shields.io/badge/Create-Tambah_Peserta-22c55e?style=flat-square" alt="Create" />
  <img src="https://img.shields.io/badge/Read-Lihat_Daftar-3b82f6?style=flat-square" alt="Read" />
  <img src="https://img.shields.io/badge/Read-Detail_Peserta-8b5cf6?style=flat-square" alt="Detail" />
  <img src="https://img.shields.io/badge/Delete-Hapus_Peserta-ef4444?style=flat-square" alt="Delete" />
</p>

| Fitur                | Keterangan                                                                                 |
|----------------------|--------------------------------------------------------------------------------------------|
| Form registrasi      | Input nama lengkap, email, password, jenis kelamin, program studi, dan tanggal lahir      |
| Validasi data        | Validasi wajib isi, format email, panjang password, dan pilihan dropdown/radio            |
| Syarat & ketentuan   | Checkbox persetujuan; form tidak bisa dikirim sebelum disetujui                           |
| Cek email duplikat   | Tidak bisa mendaftar dengan alamat email yang sama dua kali                               |
| Daftar peserta       | List peserta dalam kartu dengan avatar inisial dan informasi ringkas                      |
| Detail peserta       | Halaman detail: email, jenis kelamin, program studi, tanggal lahir, dan umur otomatis     |
| Hapus peserta        | Tombol hapus dengan dialog konfirmasi sebelum menghapus data                              |
| Badge jumlah peserta | Icon di AppBar form yang menampilkan total pendaftar (badge) dan navigasi ke daftar       |

<details>
<summary><b>Detail alur penggunaan</b></summary>

- **Halaman Form (utama)**  
  - Pengguna mengisi form registrasi event.  
  - Jika ada field yang belum valid, akan muncul pesan error di bawah field terkait.  
  - Checkbox persetujuan syarat & ketentuan wajib dicentang sebelum submit.
  - Saat submit berhasil:
    - Data peserta baru disimpan ke `RegistrationProvider`.
    - Muncul dialog sukses dengan dua opsi: "Daftar Lagi" atau "Lihat Daftar".

- **Halaman Daftar Peserta**  
  - Menampilkan semua peserta yang sudah terdaftar.  
  - Setiap item bisa diketuk untuk melihat detail peserta.  
  - Tombol hapus di sisi kanan akan menampilkan dialog konfirmasi sebelum menghapus.

- **Halaman Detail Peserta**  
  - Menampilkan profil ringkas peserta (inisial, nama, waktu terdaftar).  
  - Informasi lengkap seperti email, jenis kelamin, program studi, tanggal lahir, dan umur dalam tahun.  

</details>

---

## 🛠 Stack & Widget

<p>
  <img src="https://img.shields.io/badge/Flutter-UI_Framework-64748b?style=flat-square" alt="Flutter" />
  <img src="https://img.shields.io/badge/Provider-State_Management-64748b?style=flat-square" alt="Provider" />
  <img src="https://img.shields.io/badge/Material_3-Dark_Theme-64748b?style=flat-square" alt="Material 3" />
</p>

### Stack Teknologi

| Teknologi     | Kegunaan                                                                           |
|--------------|------------------------------------------------------------------------------------|
| **Flutter**  | Framework UI utama untuk membangun aplikasi mobile cross-platform                 |
| **Dart**     | Bahasa pemrograman yang digunakan oleh Flutter                                    |
| **Provider** | State management untuk menyimpan dan mengelola daftar pendaftar di memori        |
| **Material 3** + custom theme | Styling global (warna, typography, input, tombol, kartu) dengan gaya ala Letterboxd |

### Widget yang Digunakan

| Kategori      | Widget                                                                                   |
|---------------|------------------------------------------------------------------------------------------|
| **Struktur**  | `MaterialApp`, `Scaffold`, `AppBar`, `Form`                                              |
| **Layout**    | `Column`, `Row`, `SingleChildScrollView`, `ListView.builder`, `Center`, `ConstrainedBox` |
| **Input**     | `TextFormField`, `DropdownButtonFormField`, `RadioListTile`, `CheckboxListTile`          |
| **Kontainer** | `Card`, `CircleAvatar`, `Padding`, `SizedBox`                                            |
| **Navigasi**  | `Navigator.pushNamed`, `Navigator.pop`, named routes                                    |
| **Tombol**    | `ElevatedButton.icon`, `ElevatedButton`, `OutlinedButton`, `IconButton`, `FloatingActionButton` |
| **Feedback**  | `SnackBar`, `AlertDialog`, `Badge`                                                       |

<details>
<summary><b>Widget per file (ringkas)</b></summary>

**`main.dart`**
- `MaterialApp`, `ChangeNotifierProvider`, konfigurasi `ThemeData` dengan `AppTheme.dark`, routing antar halaman.

**`pages/registration_page.dart`**
- `Scaffold`, `AppBar`, `Form`, `SingleChildScrollView`, `TextFormField`, `DropdownButtonFormField`,
  `RadioListTile`, `CheckboxListTile`, `ElevatedButton.icon`, `OutlinedButton`, `SnackBar`, `Badge`.

**`pages/registrant_list_page.dart`**
- `Scaffold`, `AppBar`, `Consumer`, `ListView.builder`, `Card`, `ListTile`, `CircleAvatar`,
  `IconButton`, `AlertDialog`, `FloatingActionButton`.

**`pages/registrant_detail_page.dart`**
- `Scaffold`, `AppBar`, `SingleChildScrollView`, `Card`, `ListTile`, `CircleAvatar`, `Icon`.

</details>

---

## 📁 Struktur Proyek

<details>
<summary><b>Lihat struktur folder</b></summary>

```text
assets/
└──                                      # (Isi jika nanti menambah aset)
documentation/                               # Screenshot untuk dokumentasi README
│   ├── FORM - REGISTRASI.png                # Form registrasi utama
│   ├── FORM - ERROR_VALIDASI.png            # Contoh error validasi form
│   ├── FORM - DIALOG_SUKSES.png             # Dialog sukses setelah registrasi
│   ├── DAFTAR - PESERTA.png                 # Halaman daftar peserta
│   └── DETAIL - PESERTA.png                 # Halaman detail peserta
lib/
├── main.dart                                # Entry point, Provider setup, routing, tema global
├── theme/
│   └── app_theme.dart                       # Tema gelap ala Letterboxd (AppTheme, AppColors)
├── models/
│   └── registrant_model.dart                # Model data pendaftar (+ helper umur & format tanggal)
├── providers/
│   └── registration_provider.dart           # Provider daftar pendaftar (add, remove, getById, cek email)
└── pages/
    ├── registration_page.dart               # Halaman form registrasi event
    ├── registrant_list_page.dart            # Halaman daftar semua pendaftar
    └── registrant_detail_page.dart          # Halaman detail satu pendaftar
pubspec.yaml                                 # Dependensi Flutter & Provider
README.md                                    # Dokumentasi proyek (file ini)
```

</details>

---

## 🚀 Cara Menjalankan

<details>
<summary><b>Prasyarat</b></summary>

- Flutter SDK **3.10** atau lebih baru
- Dart SDK sesuai versi Flutter
- Editor (VS Code / Android Studio) atau terminal

</details>

1. **Clone repository**

   ```bash
   git clone https://github.com/ariscandra/PAB-Tugas2.git
   cd PAB-Tugas2
   ```

2. **Pasang dependensi**

   ```bash
   flutter pub get
   ```

3. **Jalankan aplikasi**

   ```bash
   flutter run
   ```

   Pilih emulator atau perangkat fisik yang sudah terhubung.

---

## 📸 Tampilan Aplikasi

<details>
<summary><b>1. Halaman Form Registrasi</b></summary>

<div align="center">
  <img src="documentation/FORM - REGISTRASI.png" alt="Form registrasi event dengan tema gelap ala Letterboxd" width="700px">
</div>

<p align="justify">
Halaman utama aplikasi. Menampilkan <em>card</em> form registrasi di tengah layar dengan tema gelap ala Letterboxd. 
Pengguna mengisi nama lengkap, alamat email, password akun, jenis kelamin, program studi, dan tanggal lahir. 
Di AppBar terdapat ikon peserta dengan badge jumlah pendaftar yang bisa ditekan untuk menuju halaman daftar.
</p>

</details>

<details>
<summary><b>2. Error Validasi Form</b></summary>

<div align="center">
  <img src="documentation/FORM - ERROR_VALIDASI.png" alt="Contoh error validasi pada form registrasi" width="700px">
</div>

<p align="justify">
Contoh tampilan ketika pengguna menekan tombol kirim namun beberapa field belum valid. 
Setiap field menampilkan pesan error yang spesifik (misalnya format email belum valid, password terlalu pendek, atau tanggal lahir belum diisi). 
Checkbox syarat & ketentuan juga wajib dicentang sebelum form dapat dikirim.
</p>

</details>

<details>
<summary><b>3. Dialog Sukses Setelah Registrasi</b></summary>

<div align="center">
  <img src="documentation/FORM - DIALOG_SUKSES.png" alt="Dialog sukses setelah registrasi peserta" width="700px">
</div>

<p align="justify">
Setelah semua data valid dan tersimpan, muncul dialog sukses dengan ikon hijau. 
Dialog menampilkan nama peserta yang baru terdaftar serta dua tombol aksi: 
<strong>Daftar Lagi</strong> untuk mengosongkan form dan kembali mengisi, atau <strong>Lihat Daftar</strong> untuk pindah ke halaman daftar peserta.
</p>

</details>

<details>
<summary><b>4. Halaman Daftar Peserta</b></summary>

<div align="center">
  <img src="documentation/DAFTAR - PESERTA.png" alt="Halaman daftar peserta event" width="700px">
</div>

<p align="justify">
Menampilkan daftar seluruh peserta yang sudah mendaftar. 
Setiap item berupa kartu dengan avatar inisial nama, nama peserta, program studi, dan email. 
Terdapat ikon hapus di sisi kanan dengan dialog konfirmasi sebelum data dihapus. 
FAB di pojok kanan bawah digunakan untuk kembali ke halaman form registrasi.
</p>

</details>

<details>
<summary><b>5. Halaman Detail Peserta</b></summary>

<div align="center">
  <img src="documentation/DETAIL - PESERTA.png" alt="Halaman detail peserta event" width="700px">
</div>

<p align="justify">
Menampilkan detail lengkap seorang peserta dalam kartu-kartu informasi. 
Bagian atas memperlihatkan avatar besar dengan inisial, nama lengkap, dan waktu terdaftar. 
Bagian bawah terdiri dari beberapa kartu: email, jenis kelamin, program studi, serta tanggal lahir yang sudah diformat rapi beserta umur (dalam tahun).
</p>

</details>

---

<p align="center">
  <sub>Registrasi Event Demo · Tugas PAB (Pemrograman Aplikasi Bergerak)</sub>
</p>

<p align="center">
  <a href="#top">⬆️ Kembali ke Atas</a>
</p>
