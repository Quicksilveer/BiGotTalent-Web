# 🎤 BI Got Talent — Web

Aplikasi web pendaftaran lomba bakat siswa **SMK Bina Informatika**. Siswa dapat melihat mata lomba, mendaftar, dan memantau status pendaftarannya. Admin mengelola mata lomba, akun siswa, dan tahapan seleksi peserta.

Dibuat untuk Ulangan Harian mata pelajaran **Pemrograman Web 2** di bawah bimbingan **Ibu Nia Adiyanti**.

> Versi desktop (Java Swing + MySQL): [BiGotTalent-Desktop](https://github.com/Quicksilveer/BiGotTalent-Desktop)

---

## ✨ Fitur

**Admin**
- Kelola mata lomba: tambah, ubah, dan hapus (CRUD)
- Kelola akun siswa: tambah, ubah, dan hapus (CRUD)
- Kelola status pendaftaran peserta: **Dokumen dalam Tinjauan → Jadwal Briefing → Tahap Pelatihan → Final**

**Siswa**
- Registrasi dan login akun
- Mendaftar mata lomba dengan mengisi kelas dan nomor WhatsApp
- Validasi agar siswa tidak mendaftar lomba yang sama dua kali
- Riwayat pendaftaran beserta status seleksi terbaru

**Keamanan & Akses**
- Autentikasi Laravel Breeze (login, registrasi, lupa password, edit profil)
- Role-based access control dengan middleware `role:admin` dan `role:siswa`
- Pengalihan otomatis ke dashboard sesuai role setelah login

---

## 🛠️ Tech Stack

| Kategori | Teknologi |
|---|---|
| Backend | PHP 8.3, Laravel 13, Laravel Breeze |
| Frontend | Blade, Tailwind CSS, Alpine.js, Vite |
| Database | MySQL (XAMPP) |
| Tools | Git, GitHub, Composer, NPM, VS Code |

---

## 🗂️ Struktur Data

| Tabel | Isi |
|---|---|
| `users` | Akun admin dan siswa (kolom `role`) |
| `lombas` | Nama dan deskripsi mata lomba |
| `pendaftarans` | Siswa, lomba, kelas, no. WA, dan status seleksi |

---

## ⚙️ Cara Menjalankan

**Prasyarat:** PHP 8.3+, Composer, Node.js & NPM, XAMPP (MySQL)

```bash
git clone https://github.com/Quicksilveer/BiGotTalent-Web.git
cd BiGotTalent-Web

composer install
npm install

copy .env.example .env      # Windows (Linux/Mac: cp .env.example .env)
php artisan key:generate
```

Buat database `db_bi_got_talent` di phpMyAdmin, lalu atur file `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_bi_got_talent
DB_USERNAME=root
DB_PASSWORD=
```

```bash
php artisan migrate
npm run dev
php artisan serve
```

Buka `http://127.0.0.1:8000`.

**Membuat akun admin:** daftar akun baru lewat halaman Register, lalu ubah kolom `role` akun tersebut menjadi `admin` di tabel `users` melalui phpMyAdmin. Akun baru otomatis ber-role `siswa`.

---

## 👤 Pengembang

**Mikhael** — Murid RPL, SMK Bina Informatika
[GitHub @Quicksilveer](https://github.com/Quicksilveer)
