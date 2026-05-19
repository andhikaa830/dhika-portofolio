# Panduan & Tutorial Website Portofolio Futuristik

Dokumen ini berisi penjelasan cara kerja fitur website portofolio Anda, panduan singkat untuk mengeditnya secara manual, serta kumpulan **contoh prompt** yang bisa Anda berikan kepada AI (seperti Gemini) jika ingin memodifikasi website ini di kemudian hari.

---

## 📂 Struktur File Proyek

Proyek ini dibangun menggunakan teknologi web dasar agar mudah dipahami dan dimodifikasi:
1. **`index.html`** - Menyusun konten dan struktur halaman (Navbar, Hero, About, Experience, Projects, Contact).
2. **`style.css`** - Mengatur tampilan visual (warna, layout, efek neon, kaca transparan, dan animasi).

---

## 💡 Fitur Utama & Cara Kerjanya

### 1. Latar Belakang Orbs Bergerak (`.bg-orbs`)
Di bagian paling atas body, terdapat tiga div dengan kelas `.orb`. Di CSS, bola-bola ini diberikan efek blur besar (`filter: blur(80px)`) dan warna semi-transparan, kemudian digerakkan secara acak menggunakan animasi `@keyframes moveOrb`. Ini menciptakan latar belakang dinamis yang modern.

### 2. Navigasi Tetap (*Fixed Navbar*)
Elemen `<header>` dikunci di bagian atas layar menggunakan `position: fixed`. Agar teks di bawahnya tidak bertabrakan secara visual saat digulir (*scroll*), ditambahkan efek kaca (*glassmorphism*) berupa `background: rgba(5, 8, 22, 0.8)` dan efek blur latar belakang `backdrop-filter: blur(15px)`.

### 3. Animasi Melayang (*Floating Cards*)
Elemen `.about-box`, `.project-card`, dan `.contact-form` menggunakan `@keyframes floatCard` untuk bergerak naik-turun setinggi `15px` secara konstan. Animasi ini akan **jeda otomatis** (`animation-play-state: paused`) ketika kursor mouse diarahkan ke elemen tersebut agar pengunjung dapat membaca teks dengan nyaman.

### 4. Tombol & Teks Berdenyut (*Neon Pulse*)
Tulisan username `.username` serta tombol-tombol sosial media menggunakan animasi `@keyframes pulseShadow` dan `@keyframes neonPulse` untuk mengubah intensitas bayangan cahaya secara berkala, menciptakan efek lampu neon yang menyala redup secara bergantian.

### 5. Animasi Muncul Saat Scroll (*Scroll Fade-in*)
Di bagian bawah `index.html`, terdapat script JavaScript sederhana menggunakan `IntersectionObserver`. Script ini memantau semua elemen berkelas `.fade-in`. Ketika halaman digulir dan elemen tersebut mulai terlihat di layar, script akan menambahkan kelas `.visible` yang memicu transisi CSS untuk memunculkan elemen tersebut secara halus dari bawah ke atas.

---

## 📝 Panduan Prompt AI untuk Modifikasi Masa Depan

Gunakan contoh-contoh instruksi (prompt) di bawah ini untuk Anda berikan kepada AI saat ingin melakukan pembaruan di masa mendatang:

### 🎨 Mengubah Tema Warna Website
> **Prompt:**
> *"Tolong ubah warna tema website portofolio saya. Saat ini temanya menggunakan warna cyan (#00f7ff). Saya ingin menggantinya menjadi tema warna **Ungu Neon (Purple/Magenta)** bergaya Cyberpunk. Tolong sesuaikan semua kode warna, efek box-shadow, text-shadow, dan gradasi tombol di dalam file style.css."*

### ➕ Menambahkan Kotak Proyek Baru
> **Prompt:**
> *"Saya ingin menambahkan satu proyek baru di bagian Projects di index.html. Tolong buatkan kodenya agar sejajar dengan proyek yang sudah ada. Detail proyeknya adalah: judul '[Nama Proyek]', deskripsi '[Deskripsi Singkat]', menggunakan gambar '[nama-file.jpg]', serta tombol Live Demo dan Github."*

### ⏱️ Menyesuaikan Kecepatan Animasi
> **Prompt:**
> *"Animasi melayang pada kartu-kartu proyek terasa terlalu [cepat/lambat]. Tolong cari animasi @keyframes floatCard di style.css dan ubah durasi animasinya menjadi [misal: 10s] agar gerakannya terlihat lebih [halus/lambat]."*

### 📱 Mengatur Tampilan Mobile (Responsif)
> **Prompt:**
> *"Saat dibuka di layar HP, ukuran teks judul nama saya terlalu besar dan tata letak tombol-tombolnya berantakan. Tolong sesuaikan media query `@media (max-width: 480px)` di style.css agar ukurannya pas dan tombol tersusun dengan rapi."*

### 📑 Menambahkan Halaman / Section Baru
> **Prompt:**
> *"Tolong tambahkan bagian baru bernama 'Certifications' (Sertifikasi) di bawah section Experience dan di atas Contact. Buatkan struktur HTML-nya menggunakan desain kartu kaca yang sama seperti Experience, lalu tambahkan tautan 'Certifications' di menu navigasi atas (header) agar bisa di-klik untuk scroll otomatis."*

---

## 🖼️ Cara Memasukkan Gambar Proyek Anda

Saat ini, gambar proyek menggunakan screenshot lokal. Untuk memperbarui gambar proyek di masa mendatang, Anda cukup meletakkan file gambar Anda ke dalam folder proyek ini (misal: bernama `proyek1.png`), lalu ubah kode di `index.html` dari:
```html
<div class="project-img-placeholder">
    <img src="Screenshot (47).png" alt="project">
</div>
```
Menjadi:
```html
<div class="project-img-placeholder">
    <img src="proyek1.png" alt="Detail Proyek 1">
</div>
```
Secara otomatis, gambar akan dipotong menyesuaikan ukuran kotak berkat properti `object-fit: cover` yang telah kita siapkan di CSS.
