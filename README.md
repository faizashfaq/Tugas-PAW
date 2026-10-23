# Tugas Pengembangan Aplikasi Web

Repositori ini berisi kumpulan tugas mata kuliah Pengembangan Aplikasi Web.
Isinya mencakup perancangan alur proses aplikasi, penerapan struktur HTML
semantik, serta penggunaan tabel, formulir, layout, dan microformats. Seluruh
tugas berupa dokumen dan halaman statis yang dapat dibuka langsung di browser
tanpa proses build.

## Daftar Tugas

| Tugas | Topik | Berkas Utama | Dokumentasi |
|---|---|---|---|
| Tugas 1 | Diagram alur proses pelaporan kerusakan sarana dan prasarana (Lapor SARPRAS ITERA) | `tugas1/124140144_tugas1_paw.pdf` | [README](./tugas1/README.md) |
| Tugas 2 | Struktur HTML semantik pada website Helpdesk ITERA | `tugas2/tugas2/index.html`, `tugas2/tugas2/berita.html` | [README](./tugas2/README.md) |
| Tugas 3 (`task_3`) | Tabel, formulir, layout (Flexbox & Grid), dan microformats | `task_3/registration.html`, `task_3/detail.html` | [README](./task_3/README.md) |

## Tugas 1 - Alur Proses Lapor SARPRAS ITERA

Berisi flowchart proses pelaporan kerusakan sarana dan prasarana pada aplikasi
Lapor SARPRAS ITERA. Diagram dibagi ke dalam tiga swimlane: **User**,
**Aplikasi**, dan **Database**, mulai dari pengguna membuka situs, mengisi
formulir dan mengunggah bukti foto, validasi data oleh aplikasi, penyimpanan
laporan, hingga notifikasi bahwa laporan berhasil dikirim.

- Folder: [`tugas1/`](./tugas1)
- Dokumentasi: [`tugas1/README.md`](./tugas1/README.md)

## Tugas 2 - HTML Semantik Helpdesk ITERA

Website dua halaman bertema Helpdesk ITERA yang menerapkan elemen HTML sesuai
fungsi kontennya, seperti `header`, `nav`, `main`, `section`, `article`,
`aside`, dan `footer`. Dilengkapi tabel layanan, informasi kontak menggunakan
`address` dan `dl`, navigasi antarhalaman, serta tautan langsung ke bagian
halaman melalui anchor.

- Folder: [`tugas2/`](./tugas2) (halaman web berada di `tugas2/tugas2/`)
- Dokumentasi: [`tugas2/README.md`](./tugas2/README.md)

## Tugas 3 - Tabel, Formulir, Layout, dan Microformats

Dua halaman yang saling terhubung: halaman pendaftaran dengan berbagai elemen
form control dan pengiriman data melalui query string (GET), serta halaman
detail yang menampilkan data pendaftar dalam tabel dengan microformats h-card.
Layout menggunakan Flexbox dan CSS Grid dengan tampilan responsif.

- Folder: [`task_3/`](./task_3)
- Dokumentasi: [`task_3/README.md`](./task_3/README.md)

## Struktur Repositori

```
.
├── tugas1/
│   ├── 124140144_tugas1_paw.pdf
│   └── README.md
├── tugas2/
│   ├── tugas2/
│   │   ├── index.html
│   │   ├── berita.html
│   │   └── images/
│   ├── pdf/
│   ├── LICENSE
│   └── README.md
├── task_3/
│   ├── registration.html
│   ├── detail.html
│   ├── style.css
│   └── README.md
├── .gitignore
└── README.md
```

## Menjalankan

Tidak ada dependensi atau proses build. Buka file HTML terkait langsung di
browser, misalnya:

- `tugas2/tugas2/index.html`
- `task_3/registration.html`

Dokumentasi dan lampiran tiap tugas tersedia di folder masing-masing.
