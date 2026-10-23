# Tugas Individu 3 - Pengembangan Aplikasi Web

## 1. Identitas

| Field | Nilai |
|---|---|
| Nama | Muhammad Faiz Ashfaq |
| NIM | 124140144 |
| Kelas | RA |
| Mata Kuliah | Pengembangan Aplikasi Web |
| Pertemuan | 4 - Tabel, Formulir, Layout dan Web Media |

## 2. Deskripsi Website

Website ini merupakan halaman web sederhana yang dibuat untuk memenuhi Tugas
Individu 3 mata kuliah Pengembangan Aplikasi Web, dengan topik Pertemuan 4:
Tabel, Formulir, Layout dan Web Media. Tujuan tugas adalah menerapkan materi
tabel, formulir, layout (Flexbox & Grid), dan microformats dalam satu halaman
web yang fungsional dan estetis.

Website terdiri dari dua halaman yang saling terhubung:

1. **Halaman Pendaftaran** (`registration.html`)
   Menampilkan form pendaftaran mahasiswa yang dirancang menggunakan berbagai
   elemen form control HTML (input teks, email, telepon, url, date, file, radio,
   checkbox, select, datalist, textarea). Form menggunakan `method="get"` sehingga
   saat disubmit, browser otomatis membentuk query string dari data yang diisi
   pengguna dan mengarahkannya ke halaman detail. Dilengkapi validasi bawaan
   HTML (required, pattern) dan tampilan yang rapi menggunakan CSS.

2. **Halaman Detail Informasi Pendaftar** (`detail.html`)
   Halaman dummy yang menampilkan data pendaftar secara statis dalam bentuk tabel,
   dilengkapi microformats (h-card) untuk menandai data terstruktur. Halaman ini
   juga menunjukkan contoh query string yang akan diterima dari halaman
   pendaftaran. Tidak ada proses penangkapan/pengolahan data (server-side) karena
   tugas hanya mendesain query string.

**Fitur utama:**
- Form pendaftaran lengkap dengan berbagai tipe input.
- Pengiriman data via query string (GET method).
- Tampilan tabel informasi pendaftar (zebra stripes & hover).
- Layout responsif menggunakan Flexbox dan CSS Grid.
- Microformats untuk data terstruktur.
- Desain modern dengan variabel CSS, gradient, dan efek hover.

**Struktur folder:**
```
task 3/
├── registration.html   (halaman pendaftaran)
├── detail.html         (halaman detail informasi pendaftar)
├── style.css           (stylesheet bersama)
└── README.md           (dokumentasi)
```

## 3. Penerapan HTML

### 3.1 Struktur Dasar Dokumen
Setiap halaman menggunakan struktur standar HTML5: deklarasi `<!DOCTYPE html>`,
elemen root `<html lang="id">`, bagian `<head>` (meta charset, viewport,
title, link stylesheet), dan `<body>` sebagai kontainer konten utama. Struktur ini
menjamin halaman dirender dengan benar dan responsif di berbagai perangkat.

### 3.2 Elemen Semantik
Digunakan elemen semantik seperti `<header>`, `<main>`, `<section>`, dan `<footer>`
untuk membagi halaman menjadi bagian-bagian bermakna. Elemen semantik membantu
aksesibilitas (screen reader) dan SEO, serta membuat struktur kode lebih mudah
dipahami. Link "Kembali ke Pendaftaran" pada halaman detail berperan sebagai navigasi.

### 3.3 Formulir (Halaman Pendaftaran)
Formulir dibuat dengan `<form action="detail.html" method="get">`. Atribut
`method="get"` membuat browser mengirim data melalui query string pada URL ketika
form disubmit, sesuai ketentuan tugas (hanya mendesain query string, tidak
menangkap data). Elemen form control yang digunakan:

- **Input teks**: `text`, `email`, `tel`, `url` untuk nama, email, telepon, website.
- **Input tanggal**: `date` untuk tanggal lahir.
- **Input file**: `file` untuk upload dokumen (KTP/KTM).
- **Pilihan (select)**: `<select>` dengan `<optgroup>` untuk mengelompokkan kelas
  reguler dan khusus, memudahkan pengguna memilih.
- **Datalist**: `<input list="...">` + `<datalist>` untuk saran program studi yang
  bisa diketik maupun dipilih.
- **Radio button**: untuk jenis kelamin (pilihan tunggal, `name` sama).
- **Checkbox**: untuk hobi (pilihan ganda, `name` sama dengan value berbeda).
- **Textarea**: untuk alamat (teks panjang).
- **Validasi**: atribut `required`, `pattern="[0-9]{8,}"`, `placeholder`, dan
  `title` untuk membantu validasi dan UX.

Setiap input memiliki `<label for="...">` yang terhubung dengan atribut `id`,
sehingga aksesibel dan mudah diklik.

### 3.4 Tabel (Halaman Detail)
Halaman detail menggunakan `<table class="info-table">` dengan struktur
`<thead>` (header kolom "Field" dan "Nilai") dan `<tbody>` (baris data pendaftar).
Tabel digunakan untuk menampilkan data terstruktur agar mudah dibaca, sesuai materi
pengenalan tabel.

### 3.5 Microformats
Pada halaman detail digunakan kelas microformats (h-card) seperti `h-card`,
`p-name`, `p-org`, `u-email`, `p-tel`, dan `p-note` untuk menandai data terstruktur
( nama, organisasi, email, telepon, kelas). Hal ini membantu mesin pencari
memahami informasi yang ditampilkan, sesuai materi microformats.

### 3.6 Query String
Nama atribut `name` pada setiap input dirancang agar query string yang dihasilkan
bermakna, contoh:
`detail.html?nama=...&nim=...&kelas=...&email=...&gender=...&hobi=...`
Tidak ada JavaScript/server yang menangkap data; halaman detail bersifat dummy.

## 4. Penerapan CSS

### 4.1 Variabel dan Reset
Digunakan `:root` untuk mendefinisikan custom properties (variabel) seperti
`--primary`, `--accent`, `--bg`, dll. Variabel ini dipakai ulang di seluruh
stylesheet sehingga tema warna konsisten dan mudah diubah. Reset dasar (`*`)
mengatur `box-sizing: border-box` dan menghapus margin/padding default.

### 4.2 Selector (Minimal 3)
- **Element selector**: `body`, `header`, `footer`, `table`, `input`, dll.
- **Class selector**: `.card`, `.btn`, `.form-group`, `.box`, `.h-card`.
- **Id selector**: `#registration-form`.
- **Pseudo-class**: `:hover`, `:focus`, `:nth-child(even)` untuk interaksi dan
  styling baris tabel bergantian (zebra stripes).

### 4.3 Layout dengan Grid dan Flexbox
- **Grid**: `.form-grid` menggunakan `display: grid` dengan
  `grid-template-columns: repeat(auto-fit, minmax(260px, 1fr))` dan `gap`,
  sehingga form responsif (kolom menyesuaikan lebar layar). Item `.full`
  menggunakan `grid-column: 1 / -1` untuk menempati seluruh baris.
- **Flexbox**: `.radio-group`, `.checkbox-group`, `.actions`, `.flex-row`
  menggunakan `display: flex` dengan `flex-wrap: wrap` dan `gap` untuk menyusun
  elemen secara horizontal dan membungkus otomatis di layar kecil.

### 4.4 Box dan Card
`.card` dan `.box` menggunakan `border-radius`, `box-shadow`, `padding`, dan
`border` untuk menciptakan tampilan kotak (box) yang rapi dan modern. Header
menggunakan gradient background dan shadow untuk kesan header yang kuat.

### 4.5 Tabel
Tabel didesain dengan `border-collapse: collapse`, padding pada sel, header
berwarna (`background: var(--primary)` dengan teks putih), zebra stripes
(`tr:nth-child(even)`), dan hover effect (`tr:hover`) agar lebih mudah dibaca
dan interaktif.

### 4.6 Form
Input, select, dan textarea memiliki border, radius, padding, dan transisi. State
`:focus` menambahkan outline berupa `box-shadow` berwarna primer untuk indikasi
fokus yang jelas. Tombol (`.btn`) menggunakan gradient, radius, dan efek hover
(transform + shadow).

### 4.7 Responsive Design
Media query `@media (max-width: 600px)` menyesuaikan ukuran font header dan
padding card agar tampilan tetap nyaman di perangkat mobile, sesuai materi
desain responsif.

### 4.8 Microformats Styling
Kelas `.h-card` dan turunannya (`.p-name`, `.p-org`, `.u-email`, `.p-tel`)
diberi styling khusus (warna, ketebalan) agar data terstruktur tampil menarik
dan mudah dibedakan.
