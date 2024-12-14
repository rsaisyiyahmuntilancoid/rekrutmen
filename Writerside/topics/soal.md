# Soal

## **Studi Kasus**
Rumah sakit tipe D di Indonesia memerlukan sistem untuk mengelola data pasien secara aman dan terintegrasi. Sistem ini harus mampu menangani pengelolaan data pasien dengan fitur tambahan untuk memastikan keamanan data dan akses API.

---

## **Deskripsi**

### **Latar Belakang**
Seiring berkembangnya kebutuhan digitalisasi di rumah sakit tipe D, data pasien perlu dikelola secara aman sesuai dengan standar yang berlaku. Sistem ini juga harus menyediakan API untuk memungkinkan integrasi dengan layanan pihak ketiga, dengan kontrol akses menggunakan API key.
Anda diminta untuk mengembangkan aplikasi menggunakan bahasa pemrograman pilihan yang sudah disebutkan pada Pendahuluan.

### **Fitur yang Harus Diimplementasikan**
1. **CRUD dan tampilan Data Pasien**, 
   buat tampilan dan fungsi CRUD untuk sebuah web, untuk mengelola data berikut,
    - **Form**
        - Login
        - Data Pasien
        - Register
        - Data API Key
        - Log
    - **Data pasien yang dikelola**:
        - Nomor Rekam Medis - String - unik 
        - Email - String - unik
        - Nama Lengkap - String
        - Umur - int
        - Keterangan Umur - Enum (Bulan, Tahun)
        - Alamat - String
        - Nomor HP - int
        - Jenis Kelamin - Enum (L, P) 
        - NIK - int
    - **Validasi**:
        - Data NIK pasien harus dienkripsi (bukan hashing) sebelum disimpan ke dalam database.
        - Semua data tidak boleh kosong.
        - Format Nomor Rekam Medis adalah 0 sebanyak 10 angka, kemudian increment (0000000000)
        - NIK wajib 16 digit.

2. **API Key Management**
    - User dapat membuat API key unik.
    - User harus login untuk mendapatkan token akses.
    - Setiap token akses harus memiliki masa berlaku (misalnya 30 hari).
    - Untuk mengakses API, diperlukan API key dan token Akses.
    - Hanya permintaan dengan API key yang valid yang dapat mengakses API.

3. **Log API Request**
    - Catat semua permintaan ke API, meliputi:
        - Endpoint yang diakses.
        - Status respon (berhasil/gagal).
        - Respon dari endpoint.
    - Log ini harus disimpan di database dan dapat ditampilkan sebagai laporan.

4. **Keamanan Data**
    - Data pasien harus dienkripsi di sisi server sebelum disimpan di database.
    - Gunakan teknik hashing untuk menyimpan API key di database.

---

## **Kriteria Pengerjaan**
1. **Basis Data**:
    - Gunakan **MySQL** atau **MariaDB** sebagai basis data.
    - Berikan script SQL untuk pembuatan tabel.

2. **Endpoint API yang Wajib Ada**:
    - **POST /path-login**: Login dan mendapatkan token akses.
    - **POST /path**: Menambahkan data pasien baru.
    - **GET /path**: Mendapatkan daftar pasien.
    - **GET /path/:id** atau **/path?id=:id**: Mendapatkan detail pasien berdasarkan ID.
    - **PUT/PATCH /path/:id**  atau **/path?id=:id**: Mengupdate data pasien berdasarkan ID.
    - **DELETE /path/:id** atau **/path?id=:id**: Menghapus data pasien berdasarkan ID.
    - **GET /path-log**: Mendapatkan log permintaan API.

3. **Validasi**:
    - Pastikan semua input divalidasi dengan baik.
    - Permintaan API tanpa API key dan token akses yang valid harus ditolak dengan respon **401 Unauthorized**.

4. **Opsional**:
    - Tambahkan fitur pencarian pasien berdasarkan nama atau alamat atau email atau nomor rekam medis.
    - Implementasikan middleware untuk membatasi jumlah request berdasarkan API key (rate limiting).

---

## **Catatan**
1. **Kode Program**:
    - Berikan file lengkap aplikasi yang dapat dijalankan, termasuk script SQL untuk pembuatan tabel.
2. **Dokumentasi API**:
    - Tuliskan dokumentasi API, meliputi endpoint, metode HTTP, parameter, dan contoh respon dalam file `README.md`.
3. **Demo Aplikasi**:
    - Berikan langkah-langkah untuk menjalankan aplikasi dan pengujian API.

---

## **Penilaian**
Pengerjaan Anda akan dinilai berdasarkan:
- **Fungsionalitas**: Semua fitur utama dapat berjalan dengan baik.
- **Keamanan**: Implementasi enkripsi data dan hashing API key.
- **Kode Bersih**: Kode mudah dibaca dan mengikuti praktik terbaik.
- **Dokumentasi**: API dan langkah penggunaan jelas dan terstruktur.
- **Opsional**: Fitur tambahan yang meningkatkan nilai aplikasi.

---

Selamat mengerjakan! 



