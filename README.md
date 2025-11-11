# SQLInjection-XSS-KerentananUpload-BrokenAccessControl
**web-security-labs-RinantaIndraDewi_C2C023062**
# 1. SQL Injection

Penjelasan:
Terjadi saat pengguna memasukkan data (seperti username atau password) yang langsung digunakan di perintah SQL tanpa dicek dulu. Akibatnya, penyerang bisa mengubah isi perintah SQL dan mengakses data penting di database. ' OR '1'='1
bisa membuat login berhasil tanpa password asli.

Cara mencegah:
Gunakan Prepared Statement agar input tidak bisa mengubah query.


Cek dan batasi input pengguna (hanya huruf/angka yang dibutuhkan).

Jangan tampilkan pesan error database ke pengguna.

Gunakan akun database dengan hak akses terbatas.

# 2. Cross-Site Scripting (XSS)
Penjelasan:
Terjadi ketika input pengguna (misalnya dari form atau URL) langsung ditampilkan di halaman tanpa disaring, sehingga script berbahaya bisa dijalankan di browser orang lain.
Contoh: <script>alert('Hacked!');</script>
Cara mencegah:

Gunakan htmlspecialchars() agar simbol seperti < dan > tidak dijalankan.

Jangan tampilkan input pengguna langsung di HTML.

Gunakan Content Security Policy (CSP) untuk membatasi script yang boleh jalan.

Hindari penggunaan eval() di JavaScript.
# 3. Unrestricted File Upload
Penjelasan:
Terjadi saat sistem mengizinkan upload file tanpa memeriksa tipe atau isi filenya. Penyerang bisa mengunggah file berbahaya (misalnya .php) untuk mengontrol server.

Contoh:
Upload file shell.php ke folder yang bisa dijalankan di server.

Cara mencegah:

Batasi jenis file yang boleh di-upload (misalnya hanya .jpg, .png, .pdf).

Periksa MIME type dan ekstensi file.

Simpan file di folder yang tidak bisa dieksekusi.

Ubah nama file secara otomatis (jangan pakai nama asli).

Batasi ukuran file yang bisa diupload.

# 4. Broken Access Control
Penjelasan:
Terjadi ketika pengguna bisa mengakses halaman atau data yang seharusnya tidak boleh, misalnya membuka halaman admin tanpa login.

Contoh:
Langsung membuka URL /admin tanpa autentikasi.

Cara mencegah:

Pastikan setiap halaman memeriksa login dan hak akses pengguna.

Gunakan sistem role-based access (misal admin, user biasa, dsb).

Jangan hanya sembunyikan tombol atau menu, tapi periksa juga di server.

Gunakan session dan token yang aman.
