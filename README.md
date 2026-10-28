# Praktikum 6: JavaScript DOM dan Event Handling

Dokumentasi ini dibuat untuk memenuhi tugas mata kuliah **Pemrograman Web** (Pertemuan 7). Praktikum ini berfokus pada pemahaman Document Object Model (DOM), pemilihan dan manipulasi elemen, penanganan event pengguna (*event handling*), validasi form, serta pembuatan aplikasi interaktif sederhana.

---

## 📋 Capaian & Tujuan Praktikum

1. Memahami DOM sebagai representasi dokumen HTML yang dapat diakses melalui JavaScript.
2. Menggunakan `id`, `class`, dan selector CSS untuk memilih elemen HTML (`getElementById`, `querySelector`, `querySelectorAll`).
3. Mengubah teks, atribut, kelas CSS, dan gaya elemen melalui JavaScript.
4. Menangani event pengguna menggunakan `addEventListener()`.
5. Membuat validasi form dan menampilkan pesan sesuai kondisi input.
6. Mengembangkan halaman interaktif dengan minimal tiga fungsi yang berjalan dengan benar.

---

## 📁 Struktur File

```text
lab6_dom_event/
├── index.html      # Struktur utama halaman web
├── style.css       # Berisi aturan styling CSS dan class interaktif
├── script.js       # Logika manipulasi DOM dan penanganan event
└── README.md       # Laporan dan dokumentasi praktikum
```

---

## 🚀 Cara Menjalankan Project

1. *Clone* atau unduh repository ini ke komputer Anda.
2. Pastikan struktur file `index.html`, `style.css`, dan `script.js` berada dalam satu folder yang sama (`lab6_dom_event`).
3. Buka file `index.html` menggunakan browser modern (Google Chrome, Mozilla Firefox, Edge, dll).
4. Tekan tombol `F12` atau klik kanan > **Inspeksi (Inspect)** lalu buka tab **Console / Developer Tools** untuk memantau eksekusi script jika diperlukan.

---

## 📝 Langkah Kerja & Penjelasan Fitur

### 1. Latihan 1: Mengubah Teks dengan DOM
- **Deskripsi:** Memilih elemen HTML `<h1>` dan `<p>` berdasarkan `id` (`judul` & `pesan`), kemudian mengubah isi teksnya secara dinamis saat halaman pertama kali dimuat.
- **Fungsi Utama:** `textContent`.

### 2. Latihan 2: Event Click
- **Deskripsi:** Menambahkan *event listener* `click` pada tombol. Saat tombol diklik, paragraf pesan akan diperbarui dengan menampilkan waktu terkini (`new Date().toLocaleTimeString()`).

### 3. Latihan 3: Mengubah Kelas dan Gaya CSS
- **Deskripsi:** Menambahkan dan menghapus class CSS (`highlight` dan `teks-besar`) pada elemen paragraf menggunakan tombol toggle.
- **Fungsi Utama:** `classList.toggle()`.

### 4. Latihan 4: Event Input dan Penghitung Karakter
- **Deskripsi:** Menghitung jumlah karakter secara *real-time* saat pengguna mengetik di dalam kolom input nama.
- **Fungsi Utama:** Event `input` dan properti `value.length`.

### 5. Latihan 5: Validasi Form Pendaftaran
- **Deskripsi:** Menvalidasi data formulir sebelum diproses. Mencegah reload halaman default (`event.preventDefault()`) dan memeriksa:
  - Nama tidak boleh kosong.
  - Email harus berformat valid (menggunakan RegEx).
  - Usia harus berupa angka bulat antara 17 hingga 100.
- **Hasil:** Menampilkan pesan kesalahan atau pesan sukses sesuai dengan kondisi input pengguna.

### 6. Latihan 6: Daftar Tugas Sederhana (To-Do List)
- **Deskripsi:** Aplikasi interaktif untuk menambahkan item tugas ke dalam daftar (`<ul>`).
- **Fitur Interaktif:**
  - Menambah item baru dengan penanganan input kosong.
  - Membubuhi tanda selesai (*strike-through*) menggunakan `classList.toggle("selesai")`.
  - Mengubah teks tombol secara dinamis antara "Tandai selesai" dan "Batalkan selesai".

---

## 🖼️ Screenshot Hasil Praktikum

*(Silakan tambahkan screenshot tampilan halaman untuk setiap latihan di bawah ini)*

| Latihan | Kondisi / Fitur | Screenshot |
|---|---|---|
| **Latihan 1 & 2** | Tampilan Awal & Setelah Tombol Diklik | `![Latihan 1 & 2](path/to/screenshot-latihan1-2.png)` |
| **Latihan 3** | Toggle Class CSS (Highlight & Teks Besar) | `![Latihan 3](path/to/screenshot-latihan3.png)` |
| **Latihan 4** | Real-time Character Counter | `![Latihan 4](path/to/screenshot-latihan4.png)` |
| **Latihan 5** | Form Validasi Gagal (Input Kosong / Email Invalid) | `![Latihan 5 Error](path/to/screenshot-latihan5-error.png)` |
| **Latihan 5** | Form Validasi Berhasil | `![Latihan 5 Sukses](path/to/screenshot-latihan5-success.png)` |
| **Latihan 6** | To-Do List (Tambah & Tandai Selesai) | `![Latihan 6](path/to/screenshot-latihan6.png)` |

---

## ❓ Jawaban Pertanyaan Evaluasi

1. **Apa yang dimaksud dengan DOM dan apa manfaatnya?**
   - **Jawab:** DOM (*Document Object Model*) adalah antarmuka pemrograman (API) yang merepresentasikan struktur dokumen HTML/XML sebagai pohon objek (*tree structure*). Manfaatnya adalah memungkinkan bahasa pemrograman seperti JavaScript untuk mengakses, mengubah, menambah, atau menghapus elemen, atribut, dan gaya CSS secara dinamis.

2. **Apa perbedaan `getElementById()`, `querySelector()`, dan `querySelectorAll()`?**
   - **`getElementById()`:** Memilih satu elemen berdasarkan atribut `id` uniknya.
   - **`querySelector()`:** Memilih elemen *pertama* yang cocok dengan selector CSS tertentu (misal: `.class`, `#id`, `tag`).
   - **`querySelectorAll()`:** Memilih *semua* elemen yang cocok dengan selector CSS dan mengembalikannya dalam bentuk `NodeList`.

3. **Apa fungsi `addEventListener()` dan sebutkan tiga contoh event?**
   - **Jawab:** Fungsi `addEventListener()` digunakan untuk mendaftarkan event handler/listener pada suatu elemen HTML sehingga kode fungsi tertentu akan dijalankan saat event tersebut terjadi. 
   - Contoh event: `click`, `input`, `submit` (contoh lain: `keydown`, `change`, `mouseover`).

4. **Mengapa `event.preventDefault()` digunakan pada event submit form?**
   - **Jawab:** `event.preventDefault()` digunakan untuk menghentikan aksi bawaan (*default action*) dari browser, yaitu memuat ulang (*reload*) halaman atau melakukan navigasi saat form dikirimkan. Hal ini penting agar proses validasi JavaScript dapat dilakukan terlebih dahulu sebelum data diproses.

5. **Apa perbedaan `textContent` dan `innerHTML` dari sisi penggunaan dan keamanan?**
   - **`textContent`:** Hanya membaca atau memasukkan teks biasa. Sangat aman dari serangan XSS (*Cross-Site Scripting*) karena karakter HTML akan di-escape sebagai teks biasa.
   - **`innerHTML`:** Membaca atau memasukkan tag/markup HTML. Berisiko keamanan XSS jika memasukkan teks dari input pengguna yang tidak terenkripsi atau terfilter.

6. **Bagaimana `classList.toggle()` membantu mengubah tampilan elemen?**
   - **Jawab:** `classList.toggle()` bekerja secara otomatis memeriksa apakah suatu nama class ada pada elemen: jika class sudah ada maka akan dihapus, dan jika belum ada maka akan ditambahkan. Ini mempermudah pembuatan efek sakelar/interaktif (seperti gaya aktif/non-aktif).

7. **Sebutkan minimal tiga skenario pengujian validasi form.**
   - Skenario 1: Mengirim form dalam keadaan semua input kosong.
   - Skenario 2: Mengisi email dengan format tidak valid (misal: `user@com` atau `user.domain`).
   - Skenario 3: Mengisi usia di luar rentang yang ditentukan (misal: usia 15 atau usia 105).