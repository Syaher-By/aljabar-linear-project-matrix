# MatrixLab — Interactive Matrix Calculator & Sharing

**MatrixLab** adalah aplikasi web kalkulator aljabar linear interaktif berbasis satu file (*single-file web app*) yang memungkinkan Anda membuat, memanipulasi, menghitung, mengekspor, dan membagikan matriks langsung melalui tautan URL tanpa memerlukan backend maupun dependensi eksternal.

---

## Fitur Utama

### 1. Editor Matriks Interaktif (`Matrix A` & `Matrix B`)
- **Ukuran Dinamis (`1×1` hingga `8×8`)**: Tambah atau kurangi jumlah baris dan kolom secara instan melalui tombol `−` dan `+`.
- **Input Fleksibel**: Mendukung bilangan bulat (`2`, `-5`), desimal (`0.5`), maupun pecahan (`3/4`) dengan validasi input otomatis.
- **Navigasi & Paste Multi-Sel**:
  - Pindah antar sel menggunakan tombol panah (`↑`, `↓`, `←`, `→`) atau `Enter`.
  - Tempel (*paste*) tabel langsung dari **Excel**, **Google Sheets**, **CSV**, atau **TSV** ke sel mana pun—ukuran matriks akan otomatis menyesuaikan hingga maksimal `8×8`.
- **Preset Cepat**: Isi matriks secara instan dengan `Random`, `Identity`, `Zeros`, `Upper Tri` (segitiga atas), atau `Clear`.
- **Kontrol Matriks**: Tukar isi kedua matriks dengan **Swap A ↔ B** atau sembunyikan Matriks B dengan **Hide Matrix B**.

### 2. Mesin Aritmetika Rasional Eksak (`BigInt`)
- Semua perhitungan dijalankan menggunakan kelas pecahan eksak berbasis `BigInt` (`Frac`), sehingga hasil operasi seperti invers dan RREF bebas dari galat pembulatan *floating-point*.
- Gunakan tombol **Display: Fraction / Decimal** di bagian header untuk beralih tampilan hasil antara pecahan eksak dan desimal.

### 3. Operasi Aljabar Linear
- **Operasi Matriks A**:
  - **Transpose** ($A^T$)
  - **Inverse** ($A^{-1}$) — dilengkapi deteksi otomatis jika matriks singular ($\det(A) = 0$)
  - **Determinant** ($\det(A)$)
  - **RREF** (*Reduced Row Echelon Form*)
  - **Trace** ($\text{tr}(A)$)
  - **Rank**
- **Operasi Berparameter**:
  - **Perkalian Skalar** ($k \times A$)
  - **Perpangkatan Matriks** ($A^n$, mendukung eksponen negatif untuk matriks yang memiliki invers)
- **Operasi Dua Matriks (`A` & `B`)**:
  - **Penjumlahan** ($A + B$)
  - **Pengurangan** ($A - B$)
  - **Perkalian** ($A \times B$ dan $B \times A$)

### 4. Result Chaining, Ekspor & Share Link
- **Send to A / Send to B**: Masukkan matriks hasil perhitungan langsung kembali ke Matriks A atau Matriks B untuk perhitungan berantai.
- **Ekspor Multi-Format**: Salin hasil perhitungan (atau Matriks A) ke clipboard dalam format:
  - **LaTeX** (`\begin{bmatrix} ... \end{bmatrix}`)
  - **CSV**
  - **JSON**
  - **Plain Text**
- **Share Matrix Link**: Klik **Share Matrix Link** untuk menyalin URL dengan parameter `#data=...`. Saat tautan tersebut dibuka oleh orang lain, dimensi matriks, nilai sel, mode tampilan, dan operasi terakhir akan otomatis dimuat kembali.

---

## Cara Menjalankan

Aplikasi ini tidak membutuhkan proses *build* atau instalasi paket apa pun:

1. Simpan file `index.html` dan `README.md` dalam satu folder.
2. Klik dua kali file `index.html` untuk membukanya langsung di browser (Chrome, Firefox, Edge, Safari).
3. *(Opsional)* Jalankan melalui server lokal:
   ```bash
   # Menggunakan Python
   python -m http.server 8080

   # Atau menggunakan Node.js
   npx serve .