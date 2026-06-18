# 🟢 Sticker Generator — Ziyad Studio

> **Sticker Generator** — Sebuah aplikasi web satu halaman (single-page app) minimalis dan interaktif yang dikembangkan oleh **Ziyad Studio** untuk membuat gambar stiker kustom dengan pembungkusan kata otomatis (auto-fit) berkinerja tinggi.

---

## 📖 Deskripsi

Sticker Generator adalah website berbasis klien (*client-side only*) yang memungkinkan pengguna mengetik teks secara bebas, lalu secara otomatis menyesuaikan ukuran teks agar pas di dalam kontainer pratinjau stiker menggunakan pencarian biner ukuran font. 

Desain visual stiker mengadopsi gaya teks terjustifikasi penuh (*fully justified alignment*) dengan perataan baris kanan-kiri yang presisi dan dilengkapi efek buram (*blur filter*) kustom untuk menciptakan tampilan yang estetik dan bersih.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|---|---|
| ✏️ **Input Teks Real-time** | Teks pratinjau diperbarui secara langsung saat pengguna mengetik di dalam kotak input. |
| 🔤 **Auto-fit Teks Cerdas** | Pustaka `textFit` mendeteksi ukuran kontainer dan menghitung font terbesar yang pas secara dinamis. |
| 📱 **Responsive Layout** | Tampilan web menggunakan kontainer pratinjau persegi 1:1 (`aspect-ratio: 1/1`) yang responsif untuk seluler, tablet, dan desktop. |
| 💾 **Ekspor 2048x2048 PNG** | Mengunduh hasil stiker resolusi tinggi (2048x2048px) yang 100% identik dengan tampilan di layar (tanpa pergeseran font, line break, blur, atau alignment). |
| 🛡️ **Vector Favicon** | Menggunakan favicon berbasis SVG data URL minimalis "ZS" (Ziyad Studio) tanpa memuat aset eksternal. |

---

## 💾 Alur Proses Ekspor Gambar (100% Identik)

Sistem ekspor gambar pada proyek ini menggunakan **Canvas 2D API terintegrasi dengan deteksi posisi baris DOM** untuk menjamin hasil unduhan 100% identik dengan apa yang tampil di layar secara aman, tanpa dependensi eksternal, dan kompatibel penuh dengan pembatasan browser modern:
1. **Preload Aset Font**: Aset font `arial_narrowregular` di-preload langsung menggunakan `<link rel="preload">` di dalam HTML untuk memastikan font telah siap dan langsung dapat dirender pada canvas tanpa penundaan.
2. **Penyelarasan Rasio 1:1**: Kontainer pratinjau `#memeContainer` pada layar menggunakan rasio aspek 1:1 (`aspect-ratio: 1/1`) dengan lebar responsif.
3. **Deteksi Baris via DOM**: Sebelum merender pada canvas, teks dibungkus secara dinamis dengan elemen `<span>` sementara untuk mendeteksi letak kata, pembungkusan baris, dan koordinat Y (`offsetTop`) yang dirender secara asli oleh mesin tata letak peramban.
4. **Rasterisasi Resolusi Tinggi (2048x2048)**: Canvas berukuran 2048x2048px dibuat. Skala konversi dihitung dengan membandingkan lebar target 2048px dengan lebar pratinjau layar. Seluruh teks dan filter blur diskalakan secara linear menggunakan koordinat Y asli dari DOM untuk menjamin presisi visual yang absolut.
5. **Perataan Justify Kustom**: Sistem merender kata-kata pada canvas dengan mendistribusikan sisa ruang kosong secara matematis demi mempertahankan gaya teks terjustifikasi penuh (*fully justified alignment*).
6. **Unduhan Blob URL Sinkron**: Hasil render canvas diubah secara langsung dan sinkron menjadi Blob URL (`blob:`) alih-alih Base64 Data URL yang berat. Proses unduhan dipicu secara sinkron di dalam event klik tombol, sehingga menghindari pembatasan ukuran data URL oleh browser seluler serta memotong pemblokiran unduhan/popup oleh peramban modern.

---

## 📁 Struktur Proyek

Berikut adalah peta berkas proyek yang aktif:

```
sticker-generator/
├── index.html                          # Berkas utama — HTML, CSS, dan JS terpadu
├── robots.txt                          # Konfigurasi perayap mesin pencari
└── README.md                           # Berkas dokumentasi proyek (berkas ini)
```

> **Catatan:** Direktori `sites/` dan `themes/` berisi aset lama yang tidak lagi aktif dirujuk oleh kode utama, selain sisa berkas Drupal yang dapat diabaikan atau dihapus.

---

## 🛠️ Analisis Dependensi & Pustaka

* **jQuery v3.7.1** — Digunakan untuk manipulasi DOM dasar dan penanganan event.
* **textFit v2.3.1 (Cleaned)** — Pustaka utama berukuran sangat kecil yang mengontrol penyesuaian font dinamis di dalam kontainer menggunakan binary search.

---

## 🚀 Cara Menjalankan secara Lokal

Karena aplikasi ini sepenuhnya berjalan di sisi klien (static HTML), Anda dapat membukanya secara langsung dengan mengklik ganda file [index.html](index.html) di komputer Anda, atau menggunakan server lokal statis:

### Menggunakan Python
```bash
python3 -m http.server 8000
```
Buka alamat `http://localhost:8000` di browser Anda.

### Menggunakan Node.js
```bash
npx serve .
```

### Menggunakan PHP
```bash
php -S localhost:8000
```

---

## 📜 Lisensi & Hak Cipta

© 2026 Ziyad Studio. Semua hak cipta dilindungi.
