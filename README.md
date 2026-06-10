# 🟢 Brat Generator

> **Charli XCX Brat Album Cover Text Generator** — Sebuah web app interaktif yang memungkinkan pengguna membuat gambar bergaya sampul album *Brat* milik Charli XCX dengan teks kustom.

🌐 **Live Site:** [bratgenerator.com](https://www.bratgenerator.com/)

---

## 📖 Deskripsi

Brat Generator adalah website single-page yang dibangun untuk memungkinkan penggemar Charli XCX membuat gambar bergaya sampul album **Brat**. Pengguna dapat mengetikkan teks kustom dan memilih dari **6 tema warna** yang berbeda, masing-masing merepresentasikan era/versi berbeda dari album Brat.

Website ini awalnya di-deploy menggunakan **Drupal 10** sebagai CMS dan di-host melalui infrastruktur **Warner Music Group (WMG) Artist Services**.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|---|---|
| 🎨 **6 Tema Warna** | Green, White, Black, Blue (Sweat), Strike, dan Red (The Moment) |
| ✏️ **Input Teks Kustom** | Pengguna dapat mengetikkan teks mereka sendiri |
| 🔤 **Auto-fit Teks** | Teks otomatis menyesuaikan ukuran container menggunakan library `textFit` |
| 💎 **Diamond Layout** | Tema Black menyusun kata-kata dalam pola diamond/berlian |
| 📱 **Responsive** | Mendukung desktop, tablet, dan mobile (portrait & landscape) |
| 📸 **Screenshot to Save** | Pengguna mengambil screenshot untuk menyimpan hasil |
| 🔗 **Social Media Links** | Link ke semua platform sosial Charli XCX |

---

## 🎨 Tema yang Tersedia

### 1. 🟢 Green (Default Brat)
- Background: `#8ACF00` (brat green)
- Font: Arial Narrow (blur effect)
- Teks default: `"brat"`
- Max karakter: 20

### 2. ⚪ White (Brat Deluxe)
- Background: Putih
- Font: Arial Narrow (blur effect)
- Teks default: `"brat and it's completely different but also still brat"`
- Teks ditampilkan dengan justify alignment dalam kotak 500×300px

### 3. ⚫ Black (Brat Remix)
- Background: Hijau dengan overlay hitam
- Font: Arial Narrow (blur effect, mirrored/flipped)
- Teks default: `"brat and it's completely different but also still brat"`
- Layout: Diamond pattern — kata-kata disusun berbentuk berlian
- Max karakter: 450

### 4. 🔵 Blue (SWEAT)
- Background: `#0A00AD` (deep blue)
- Font: Compacta Black, uppercase, warna merah `#DE0100`
- Input background: `#F9FF3E` (kuning neon)
- Teks default: `"SWEAT"`
- Max karakter: 20

### 5. ~~Strike~~ (Brat Strikethrough)
- Background: `#8ACF00` (brat green)
- Input teks memiliki efek strikethrough
- Overlay gambar scribble/coret-coretan
- Font: Times (blur effect)
- Teks default: `"brat"`
- Max karakter: 70

### 6. 🔴 Red (The Moment)
- Background: Animasi warna berputar (biru → hitam → merah → hijau)
- Font: Druk Condensed Super, uppercase
- Teks animasi warna berputar kontras tinggi
- Teks default: `"the moment"`
- Max karakter: 30
- **Tema default saat halaman pertama kali dimuat**

---

## 📁 Struktur Proyek

```
brat-generator/
├── index.html                          # File utama — semua HTML, CSS, dan JS dalam satu file (1811 baris)
├── robots.txt                          # Konfigurasi crawler/SEO
├── README.md                           # Dokumentasi proyek (file ini)
├── sites/
│   └── g/files/
│       ├── g2000012696/files/
│       │   └── 2021-09/
│       │       └── ajax-loader.svg     # SVG loading spinner
│       └── g2000017981/files/
│           ├── favicon_96.jpg          # Favicon website
│           ├── 2024-01/                # Font: Times Roman
│           │   ├── times-roman-01-webfont.eot.html
│           │   ├── times-roman-01-webfont.woff.html
│           │   ├── times-roman-01-webfont.ttf.html
│           │   └── times-roman-01-webfont.svg
│           ├── 2024-02/
│           │   └── album-art.png       # 🟢 Album art Brat (cover hijau)
│           ├── 2024-03/
│           │   └── arial_narrow-webfont.woff.html  # Font: Arial Narrow
│           ├── 2024-09/                # Font: Compacta Black (untuk tema Blue/SWEAT)
│           │   ├── compacta_black_regular-webfont.woff.html
│           │   ├── compacta_black_regular-webfont.woff2.html
│           │   └── compacta_black_regular-webfont.svg
│           ├── 2025-04/
│           │   ├── Image 4.png         # Overlay scribble untuk tema Strike
│           │   └── Group 3.png         # Ikon tombol tema Strike
│           ├── 2026-01/                # Font: Druk Condensed Super (untuk tema Red)
│           │   ├── drukcond-super-webfont.eot.html
│           │   ├── drukcond-super-webfont.woff.html
│           │   ├── drukcond-super-webfont.woff2.html
│           │   ├── drukcond-super-webfont.ttf.html
│           │   └── drukcond-super-webfont.svg
│           └── 2026-02/
│               └── H_logo.svg         # Logo Howard Stirling
└── themes/
    └── contrib/
        └── bartik/
            └── icons/                 # Ikon tema Drupal Bartik
                ├── 000000/            # Chevron icons (hitam)
                ├── 424242/            # Loupe/search icon
                ├── 505050/            # Loupe/search icon
                ├── 73b355/            # Check icon (hijau)
                ├── e29700/            # Warning icon (kuning)
                ├── e32700/            # Error icon (merah)
                ├── ee0000/            # Required icon (merah)
                ├── ffffff/            # Hamburger, twistie icons (putih)
                ├── feed.svg
                ├── help.png
                ├── required.svg
                ├── tabs-border.png
                ├── menu-collapsed.png
                ├── menu-collapsed-rtl.png
                └── menu-expanded.png
```

---

## 🛠️ Tech Stack

| Teknologi | Penggunaan |
|---|---|
| **HTML5** | Struktur halaman (single-page) |
| **CSS3** | Styling inline (`<style>` tags), animasi `@keyframes`, responsive `@media` queries |
| **JavaScript (Vanilla)** | Logika tema, text fitting, diamond layout |
| **jQuery** | DOM manipulation, event handling |
| **Drupal 10** | CMS backend (Bartik theme) |
| **textFit v2.3.1** | Library auto-sizing teks (embedded langsung) |
| **html2canvas** | Library screenshot (dari CDN WMG) |
| **Owl Carousel** | Library carousel (dari CDN WMG) |
| **Adobe DTM** | Analytics/tracking |
| **OneTrust** | Cookie consent management |
| **Google Fonts** | Archivo Narrow font |
| **Adobe Typekit** | Font hosting tambahan |

---

## 🔧 Analisis Teknis

### `index.html` (58.8 KB, 1811 baris)

File monolitik yang berisi seluruh aplikasi:

#### Bagian-bagian Utama:

1. **Head (baris 1–67)**
   - Meta tags SEO (Open Graph, Twitter Cards)
   - Google Site Verification
   - External CSS & JS libraries (jQuery, Owl Carousel, Adobe DTM)
   - OneTrust cookie consent script

2. **Inline CSS — Font Faces (baris 203–262)**
   - `timesregular` — untuk input teks tema Green/default
   - `arial_narrowregular` — font utama overlay teks
   - `compactablack` — untuk tema Blue/SWEAT
   - `drukCondsuper` — untuk tema Red/The Moment
   - `Helvetica Neue LT Std Hv` — variable heavy weight

3. **Inline CSS — Layout & Themes (baris 263–957)**
   - Container meme (`#memeContainer`) — flexbox center, 80vh
   - Input teks (`#textInput`) — rounded, centered
   - Text overlay (`#textOverlay`) — absolute positioned, 280px default
   - 6 konfigurasi tema berbeda dengan warna, font, dan behavior
   - Animasi `@keyframes` untuk tema Red (color cycling)
   - Responsive breakpoints: 1024px portrait, 1023px landscape, iPad Pro

4. **HTML Content (baris 982–1070)**
   - `#memeContainer` — wrapper gambar & teks overlay
   - `#memeImage` — gambar album art
   - `#memeText` — teks tambahan (visible hanya di tema Blue)
   - `#textOverlay` — teks yang di-render di atas gambar
   - `#textInput` — input teks pengguna
   - `.themeSelector` — 6 tombol pemilih tema (fixed position)
   - `.footerWrapper` — copyright, privacy links, social media

5. **JavaScript — Diamond Layout (baris 1072–1144)**
   - Fungsi `createDiamond()` — menyusun kata dalam pola berlian
   - Menggunakan square root dari jumlah kata untuk menghitung baris
   - Hanya digunakan pada tema Black

6. **JavaScript — textFit Library (baris 1146–1414)**
   - Library textFit v2.3.1 (embedded, modified)
   - Binary search untuk menemukan font size optimal
   - Override `maxFontSize` berdasarkan tema aktif
   - UMD module pattern (AMD/CommonJS/Browser)

7. **JavaScript — Theme Switching (baris 1416–1649)**
   - Fungsi `setupTheme(color)` — mengatur semua parameter per tema
   - Event listener pada `#textInput` untuk real-time text update
   - Initial state: tema Red (`"the moment"`)
   - `window.onload` memanggil `setupTheme('red')`

### `robots.txt` (2.1 KB, 78 baris)

Konfigurasi Drupal standard:
- Allow: CSS, JS, gambar dari `/core/` dan `/profiles/`
- Disallow: Admin paths, search, user forms
- Disallow: Filter/faceted URLs (`?f[`, `&f[`)
- Disallow: On-tour paths
- Support clean URLs dan non-clean URLs (`/index.php/`)

### `sites/` (Assets)

#### Font Files (19 file)
Berisi font custom dalam berbagai format (`.woff`, `.woff2`, `.eot`, `.ttf`, `.svg`):
- **Times Roman** — input placeholder text
- **Arial Narrow** — main overlay text  
- **Compacta Black** — SWEAT/Blue theme
- **Druk Condensed Super** — The Moment/Red theme

> ⚠️ Beberapa font file memiliki ekstensi `.html` (misalnya `.woff.html`) — kemungkinan artifact dari proses deployment Drupal/WMG.

#### Image Files (4 file)
- `album-art.png` — Cover album Brat (background hijau ikonik)
- `Image 4.png` — Overlay scribble/coret-coretan untuk tema Strike
- `Group 3.png` — Ikon tombol pemilih tema Strike
- `H_logo.svg` — Logo Howard Stirling (link external di kanan atas)

#### Other
- `favicon_96.jpg` — Favicon website
- `ajax-loader.svg` — Loading spinner SVG (legacy)

### `themes/contrib/bartik/icons/` (18 file)

Icon set standar dari tema **Bartik** Drupal:
- SVG dan PNG icons untuk UI elements (chevrons, search, hamburger menu, form validation)
- Diorganisir per warna hex (`000000/`, `ffffff/`, `73b355/`, dll.)

---

## 🚀 Cara Menjalankan Secara Lokal

Karena ini adalah website statis (single HTML file), cukup:

```bash
# Menggunakan Python
python3 -m http.server 8000

# Atau menggunakan Node.js
npx serve .

# Atau menggunakan PHP
php -S localhost:8000
```

Lalu buka `http://localhost:8000` di browser.

> **Catatan:** Beberapa font di-load dari CDN external (`bratgenerator.com`, `wmgartistservices.com`), sehingga memerlukan koneksi internet untuk tampilan penuh.

---

## 📊 Statistik Proyek

| Metrik | Nilai |
|---|---|
| Total ukuran | ~1.9 MB |
| File HTML | 1 (58.8 KB, 1811 baris) |
| File font | 19 |
| File gambar | 5 |
| File SVG icons | 13 |
| Tema warna | 6 |
| External dependencies | jQuery, Owl Carousel, html2canvas, Adobe DTM, OneTrust |

---

## 🏗️ Arsitektur

```
┌─────────────────────────────────────────────┐
│                 index.html                  │
│  ┌─────────┐ ┌──────────┐ ┌─────────────┐  │
│  │ Inline  │ │  Inline  │ │   Inline    │  │
│  │  CSS    │ │   HTML   │ │ JavaScript  │  │
│  │(themes, │ │(meme     │ │(textFit,    │  │
│  │ layout, │ │ container│ │ setupTheme, │  │
│  │ @media) │ │ input,   │ │ diamond     │  │
│  │         │ │ footer)  │ │ layout)     │  │
│  └─────────┘ └──────────┘ └─────────────┘  │
├─────────────────────────────────────────────┤
│              External CDN                   │
│  jQuery │ html2canvas │ Owl Carousel │ DTM  │
├─────────────────────────────────────────────┤
│              Local Assets                   │
│  Fonts (.woff/.svg) │ Images (.png/.jpg)    │
└─────────────────────────────────────────────┘
```

---

## 📝 Catatan Penting

1. **Single-file architecture** — Seluruh CSS dan JS di-embed langsung dalam `index.html`, tidak ada file CSS/JS terpisah (selain external CDN).
2. **Drupal artifact** — Proyek ini awalnya bagian dari instalasi Drupal 10, terlihat dari struktur folder `sites/g/files/`, tema Bartik, dan markup Drupal di HTML.
3. **WMG Infrastructure** — Banyak asset di-load dari `libraries.wmgartistservices.com` (CDN Warner Music Group).
4. **Font file `.html` extension** — Beberapa font file memiliki ekstensi ganda (`.woff.html`), kemungkinan hasil dari proses migrasi atau export Drupal.
5. **Tema default berubah** — Tema default saat ini adalah **Red (The Moment)**, bukan Green (Brat original).

---

## 📜 Lisensi & Hak Cipta

© 2026 Charli XCX & Atlantic Records

- [Privacy Policy](https://privacy.wmg.com/atlantic/privacy-policy)
- [Terms of Use](https://www.atlanticrecords.com/terms-of-use)
- [Cookies Policy](https://www.wminewmedia.com/cookies-policy/)

---

## 🔗 Social Media Charli XCX

[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white)](https://www.facebook.com/CharliXCX/)
[![X/Twitter](https://img.shields.io/badge/X-000000?style=flat&logo=x&logoColor=white)](https://twitter.com/charli_xcx)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat&logo=instagram&logoColor=white)](https://www.instagram.com/charli_xcx/)
[![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/@officialcharlixcx)
[![Spotify](https://img.shields.io/badge/Spotify-1DB954?style=flat&logo=spotify&logoColor=white)](https://open.spotify.com/artist/25uiPmTg16RbhZWAqwLBy5)
[![TikTok](https://img.shields.io/badge/TikTok-000000?style=flat&logo=tiktok&logoColor=white)](https://www.tiktok.com/@charlixcx)
[![Apple Music](https://img.shields.io/badge/Apple_Music-FA243C?style=flat&logo=apple-music&logoColor=white)](https://music.apple.com/us/artist/charli-xcx/432942256)
[![SoundCloud](https://img.shields.io/badge/SoundCloud-FF3300?style=flat&logo=soundcloud&logoColor=white)](https://soundcloud.com/charlixcx)
