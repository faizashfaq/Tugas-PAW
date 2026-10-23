# Tugas Individu 1 - Pengembangan Aplikasi Web

## 1. Identitas

| Field | Nilai |
|---|---|
| Nama | Muhammad Faiz Ashfaq |
| NIM | 124140144 |
| Kelas | Pengembangan Aplikasi Web (RA) |
| Mata Kuliah | Pengembangan Aplikasi Web |
| Aplikasi | Lapor SARPRAS ITERA |
| Proses | Pelaporan Kerusakan Sarana dan Prasarana di ITERA |

## 2. Deskripsi Tugas

Tugas ini berisi perancangan diagram alur (flowchart) proses pelaporan
kerusakan sarana dan prasarana pada aplikasi **Lapor SARPRAS ITERA**. Diagram
menggambarkan bagaimana pengguna, aplikasi, dan database saling berinteraksi
sejak pengguna membuka situs hingga menerima notifikasi bahwa laporan berhasil
dikirim.

Diagram dibagi menjadi tiga bagian (swimlane) berdasarkan pihak yang
melakukan proses:

1. **USER** - mahasiswa atau pengguna yang melaporkan kerusakan.
2. **APLIKASI** - sistem yang menerima, memvalidasi, dan menyimpan laporan.
3. **DATABASE** - tempat penyimpanan data laporan dan statusnya.

## 3. Alur Proses

### 3.1 User
1. Membuka `laporan.itera.ac.id`.
2. Memilih menu **Lapor SARPRAS**.
3. Mengisi formulir kerusakan sarana dan prasarana.
4. Mengunggah bukti foto kerusakan.
5. Menekan tombol **Kirim Laporan**.
6. Menerima notifikasi **"Laporan Berhasil"**.

### 3.2 Aplikasi
1. Menerima request dari pengguna dan memvalidasi data yang dikirim.
2. Memeriksa keputusan **Data valid?**
   - **Ya** - laporan dan foto disimpan.
   - **Tidak** - aplikasi mengirim pesan perbaikan data kepada pengguna.
3. Menyimpan laporan dan foto ke database.

### 3.3 Database
1. Menyimpan data laporan yang dikirim aplikasi.
2. Memberikan status laporan yang kemudian diteruskan kembali ke pengguna.

## 4. Hubungan Antarproses

- User mengirim data formulir dan foto ke aplikasi saat menekan **Kirim Laporan**.
- Aplikasi memvalidasi data sebelum menyimpannya. Jika data tidak valid,
  pengguna diminta memperbaiki data; jika valid, laporan diteruskan ke database.
- Database menyimpan laporan dan mengembalikan status laporan ke aplikasi.
- Status tersebut digunakan aplikasi untuk menampilkan notifikasi
  **"Laporan Berhasil"** kepada pengguna.

## 5. Struktur Folder

```
tugas1/
├── 124140144_tugas1_paw.pdf   (dokumen tugas: flowchart proses)
└── README.md                  (dokumentasi)
```

## 6. Dokumen

Dokumen sumber tugas tersedia pada `124140144_tugas1_paw.pdf`. Dokumen tersebut
memuat identitas penyusun serta diagram alur proses pelaporan kerusakan sarana
dan prasarana.
