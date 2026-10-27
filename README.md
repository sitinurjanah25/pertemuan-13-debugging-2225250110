# Pertemuan 13 - Debugging dan Testing
Nama: Siti Nurjanah
NIM: 2225250110
Kelas: S1 Pendidikan Matematika - Semester 3

## Kasus
Program yang diuji adalah program pemroses data nilai mahasiswa yang memiliki fungsi untuk menghitung rata-rata nilai, menentukan status kelulusan, dan mencari nilai tertinggi.

## Test Case
| ID | Input | Expected | Actual Awal | Status |
|---|---|---|---|---|
| T1 | [80, 60, 90, 70] | 75.0 | 60.0 | FAIL |
| T2 | [100, 80] | 90.0 | 36.0 | FAIL |
| T3 | 60 | Lulus | Tidak lulus | FAIL |
| T4 | 59 | Tidak lulus | Tidak lulus | PASS |
| T5 | [80, 60, 90, 70] | 90 | 0 | FAIL |

## Bug Report
* **B01 (Rata-rata):** Gejala: Hasil rata-rata salah. Lokasi: `hitung_rata_rata`. Akar penyebab: Pembagi statis 5. Perbaikan: Ubah menjadi `len(nilai)`.
* **B02 (Status):** Gejala: 60 "Tidak lulus". Lokasi: `status`. Akar penyebab: Memakai operator `>`. Perbaikan: Mengubah jadi `>= 60`.
* **B03 (Tertinggi):** Gejala: Hasilnya 0. Lokasi: `nilai_tertinggi`. Akar penyebab: Inisialisasi awal 0 dan operator `<`. Perbaikan: Inisialisasi `tertinggi = nilai[0]` dan pakai `>`.

## Retest
Seluruh test case dijalankan ulang dan berstatus PASS.

## Cara Menjalankan
python3 praktik/praktik_4_debugging.py

## Refleksi
Teknik test case batas (boundary testing) sangat membantu membongkar bug logika.