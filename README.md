Bondowoso - Single Service Backend
18221076 Gevyndo Gunawan
Menggunakan javascript dibantu prisma


Deskripsi
Proyek ini adalah single service backend yang dikembangkan menggunakan Prisma sebagai ORM (Object-Relational Mapping) dan XAMPP sebagai lingkungan pengembangan lokal. Backend menyediakan endpoint untuk mengelola produk dan perusahaan, serta fitur login admin. Layanan ini dirancang untuk bekerja dengan Admin Page yang disediakan oleh Labpro.

Persyaratan
Sebelum menjalankan layanan backend, pastikan Anda telah menginstal persyaratan berikut di sistem Anda:

Node.js dan npm (Node Package Manager): Unduh dan instal Node.js dari situs web resmi (https://nodejs.org/en/download/).

XAMPP: Unduh dan instal XAMPP dari situs web resmi (https://www.apachefriends.org/download.html). XAMPP menyediakan lingkungan yang diperlukan untuk menjalankan database MySQL, yang akan digunakan backend.

Persiapan:
1. Klon repositori:
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

Install dependensi
npm install

1. Siapkan database:
-Jalankan XAMPP dan mulai layanan Apache dan MySQL.
-Buka peramban web Anda dan arahkan ke http://localhost/phpmyadmin.
-Buat database baru dengan nama pilihan Anda (misalnya, single_service_backend).

2. Konfigurasi variabel lingkungan:

Ganti nama file .env.example menjadi .env.

Buka file .env dan ganti DATABASE_URL dengan URL koneksi database MySQL Anda. Contoh:
DATABASE_URL="mysql://your-username:your-password@localhost:3306/single_service_backend?schema=public"

3. Generate Prisma client:
npx prisma generate

Menjalankan Backend
Untuk memulai layanan backend, jalankan perintah berikut:
npm start index

Backend akan tersedia di http://localhost:5000.

Endpoint
Produk
GET /products: Dapatkan daftar semua produk.
POST /products: Tambahkan produk baru (Hanya diakses oleh admin).
PUT /products/:id: Edit produk yang ada (Hanya diakses oleh admin).
DELETE /products/:id: Hapus produk (Hanya diakses oleh admin).
Perusahaan
GET /perusahaan: Dapatkan daftar semua perusahaan.
POST /perusahaan: Tambahkan perusahaan baru (Hanya diakses oleh admin).
PUT /perusahaan/:id: Edit perusahaan yang ada (Hanya diakses oleh admin).
DELETE /perusahaan/:id: Hapus perusahaan (Hanya diakses oleh admin).
Login Admin
POST /login: Lakukan login admin dan terima token JWT.
Autentikasi
Untuk mengakses endpoint yang hanya dapat diakses oleh admin (menambahkan/mengedit/menghapus produk dan perusahaan), sertakan token JWT dalam header Authorization permintaan dengan menggunakan metode autentikasi Bearer token.


