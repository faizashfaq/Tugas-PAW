# Tugas Individu 2 - Pengembangan Aplikasi Web

## 1. Identitas

| Field | Nilai |
|---|---|
| Nama | Muhammad Faiz Ashfaq |
| NIM | 124140144 |
| Kelas | RA |
| Mata Kuliah | Pengembangan Aplikasi Web |
| Topik | Struktur HTML Semantik |

## 2. Deskripsi Website

Website ini merupakan halaman web sederhana yang dibuat untuk memenuhi Tugas
Individu 2 mata kuliah Pengembangan Aplikasi Web dengan topik struktur HTML
semantik. Tujuan tugas adalah menerapkan elemen-elemen HTML sesuai fungsi dan
makna kontennya, bukan hanya menampilkan isi halaman.

Website mengangkat tema **Helpdesk ITERA**, yaitu pusat informasi dan bantuan
layanan teknologi informasi bagi mahasiswa dan civitas akademika Institut
Teknologi Sumatera. Seluruh berita, kontak, dan data pada website merupakan
konten simulasi untuk keperluan tugas, bukan informasi resmi ITERA.

Website terdiri dari dua halaman yang saling terhubung:

1. **Halaman Beranda** (`index.html`)
   Berisi pengenalan Helpdesk ITERA, daftar layanan, tabel informasi layanan
   beserta prioritas penanganannya, dan informasi kontak. Halaman ini juga
   menjadi tujuan tautan dari artikel berita melalui anchor (`#layanan`,
   `#tabel-layanan`, `#kontak`).

2. **Halaman Berita** (`berita.html`)
   Menampilkan tiga artikel berita yang berdiri sendiri, yaitu Pemeliharaan
   Jaringan Internet ITERA, Peningkatan Layanan Sistem Informasi Kampus, dan
   Pengumuman Layanan Helpdesk. Setiap artikel memiliki judul, tanggal, kategori,
   dan tautan menuju bagian terkait pada halaman beranda.

**Fitur utama:**
- Struktur halaman semantik (`header`, `nav`, `main`, `section`, `article`,
  `aside`, `footer`).
- Navigasi antarhalaman menggunakan hyperlink.
- Tabel layanan dengan `caption`, `thead`, `tbody`, `th`, dan `td`.
- Informasi kontak menggunakan `address`, `dl`, `dt`, dan `dd`.
- Tautan langsung ke bagian halaman melalui atribut `id` (anchor link).
- Atribut aksesibilitas seperti `aria-label`, `aria-labelledby`, dan
  `aria-current`.

**Struktur folder:**
```
tugas2/
├── tugas2/
│   ├── index.html          (halaman beranda)
│   ├── berita.html         (halaman berita)
│   └── images/
│       └── logo-itera.png  (logo Helpdesk ITERA)
├── pdf/
│   ├── Dokumentasi Tugas 2 PAW.pdf
│   ├── index.png           (hasil validasi index.html)
│   └── berita.png          (hasil validasi berita.html)
├── LICENSE
└── README.md
```

## 3. Penerapan HTML Semantik

### 3.1 Struktur Dasar Dokumen
Setiap halaman menggunakan struktur standar HTML5: deklarasi `<!DOCTYPE html>`,
elemen root `<html lang="id">`, bagian `<head>` berisi `meta charset`,
`meta viewport`, `meta description`, dan `<title>`, serta `<body>` sebagai
kontainer konten. Atribut `lang="id"` menandai bahwa bahasa halaman adalah
Bahasa Indonesia.

### 3.2 Elemen Semantik
- **`<header>`** menjadi pengenal halaman. Pada beranda berisi logo, judul
  "Helpdesk ITERA", keterangan "Pusat Informasi dan Bantuan Layanan IT", dan
  nama institusi. Pada halaman berita berisi logo, judul "Berita Helpdesk
  ITERA", dan keterangan singkat.
- **`<nav>`** menjadi navigasi utama menuju Beranda dan Berita. Atribut
  `aria-label="Navigasi utama"` memperjelas fungsi navigasi bagi pembaca layar.
- **`<main>`** menampung konten utama setiap halaman. Pada beranda berisi empat
  bagian, sedangkan pada halaman berita berisi kumpulan artikel.
- **`<section>`** membagi konten beranda berdasarkan topik: Tentang Helpdesk
  ITERA, Layanan Helpdesk, Informasi Layanan, dan Informasi Kontak. Setiap
  section dihubungkan dengan judulnya melalui `aria-labelledby`.
- **`<article>`** digunakan pada halaman berita karena setiap berita merupakan
  konten yang berdiri sendiri dan dapat dipahami tanpa bagian lain.
- **`<aside>`** menampung informasi tambahan yang masih berkaitan dengan konten
  utama, yaitu Pengumuman Helpdesk pada beranda dan "Butuh Bantuan?" pada
  halaman berita.
- **`<footer>`** menjadi penutup halaman dan berisi hak cipta serta nama
  institusi.

Penggunaan elemen tersebut membuat bagian navigasi, konten utama, artikel,
informasi tambahan, dan penutup memiliki struktur yang jelas dan bermakna.

### 3.3 Tabel
Tabel layanan pada beranda menggunakan `<table>` dengan `<caption>` sebagai
keterangan tabel, `<thead>` untuk baris judul kolom, `<tbody>` untuk isi, serta
`<tr>`, `<th scope="col">`, dan `<td>`. Tabel merangkum jenis layanan, deskripsi
singkat, dan tingkat prioritas penanganan.

### 3.4 Informasi Kontak
Informasi kontak disusun menggunakan `<address>` yang berisi `<dl>`, dengan
`<dt>` sebagai label (Email, Lokasi, Jam Layanan) dan `<dd>` sebagai nilainya.
Email juga dibuat sebagai tautan menggunakan `mailto:`.

### 3.5 Hyperlink dan Anchor
Navigasi antarhalaman menggunakan tautan relatif `index.html` dan
`berita.html`. Bagian pada beranda diberi `id` (`#layanan`, `#tabel-layanan`,
`#kontak`) sehingga artikel berita dapat mengarahkan pengguna langsung ke
bagian yang relevan. Halaman aktif ditandai dengan `aria-current="page"`.

### 3.6 Elemen Pendukung
- `<time datetime="...">` menandai tanggal terbit artikel secara terstruktur.
- `<em>` digunakan untuk catatan bahwa seluruh berita adalah konten simulasi.
- `<img>` dilengkapi atribut `alt`, `width`, dan `height` agar aksesibel dan
  tidak menyebabkan layout bergeser saat gambar dimuat.
- Entitas `&amp;` dan `&copy;` digunakan untuk karakter khusus.

## 4. Tantangan dan Solusi

Tantangan utama dalam pembuatan website adalah menentukan elemen HTML yang
sesuai dengan fungsi setiap konten. Halaman tidak hanya berisi teks, tetapi juga
navigasi, beberapa bagian informasi, tabel layanan, artikel berita, informasi
tambahan, dan bagian penutup. Selain itu, hubungan antarhalaman serta hubungan
antara artikel dan bagian tertentu pada beranda perlu dibangun melalui
hyperlink.

Solusinya adalah membagi halaman menggunakan elemen semantik sesuai fungsinya:
`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan
`<footer>`. Navigasi antarhalaman menggunakan tautan relatif, sedangkan bagian
beranda diberi `id` agar dapat dituju langsung dari artikel. Tabel layanan
dibangun dengan `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, dan `<td>`,
sementara informasi kontak menggunakan `<address>` dan `<dl>` dengan `<dt>`
serta `<dd>`.

## 5. Validasi

Kedua halaman telah diperiksa menggunakan W3C Markup Validation Service. Bukti
hasil validasi tersedia pada:

- `pdf/index.png` untuk `index.html`
- `pdf/berita.png` untuk `berita.html`

Dokumentasi lengkap tugas tersedia pada `pdf/Dokumentasi Tugas 2 PAW.pdf`.

## 6. Tautan

- **GitHub Pages:** https://faizashfaq.github.io/Tugas-PAW/tugas2

