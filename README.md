# Sistem-Fuzzy-Kecerdasan-Buatan
# Sistem Penilaian Menggunakan Fuzzy Logic
---

## Link Youtube Presentasi
https://youtu.be/ei3UQ0V1VTI

---
Sistem ini menggunakan **logika fuzzy** untuk menilai dua studi kasus berbeda:  

1. **Risiko Kredit** – menilai risiko kredit nasabah berdasarkan **Gaji** dan **Cicilan**  
2. **Kelayakan Beasiswa** – menilai kelayakan mahasiswa berdasarkan **IPK**, **TOEFL**, dan **Penghasilan Orang Tua**

Metode yang digunakan:  
- **Mamdani** → inferensi dengan defuzzifikasi centroid  
- **Tsukamoto** → inferensi dengan output linear monoton (hanya untuk risiko kredit)

Sistem dapat menampilkan hasil ke layar dan menyimpan **Top 10 nilai terendah** ke file Excel (khusus risiko kredit).

---

## Studi Kasus 1: Risiko Kredit

### Input
- **Gaji**: nominal bulanan nasabah
- **Cicilan**: jumlah cicilan per bulan

### Proses
1. **Fuzzifikasi**  
   - Gaji: `rendah`, `sedang`, `tinggi`  
   - Cicilan: `kecil`, `sedang`, `besar`  

2. **Aturan Fuzzy** (contoh):  
   - IF Gaji TINGGI AND Cicilan KECIL THEN Risiko RENDAH  
   - IF Gaji RENDAH AND Cicilan BESAR THEN Risiko TINGGI  

3. **Inferensi**:  
   - Mamdani → agregasi fungsi keanggotaan & defuzzifikasi centroid  
   - Tsukamoto → output linear monoton  

4. **Defuzzifikasi** → menghasilkan nilai risiko (0–100)

### Output
- Nilai risiko per nasabah untuk **Mamdani** dan **Tsukamoto**  
- **Top 10 nilai risiko terendah** → disimpan ke file Excel:  
  - `top10_mamdani.xlsx`  
  - `top10_tsukamoto.xlsx`  

---

## Studi Kasus 2: Kelayakan Beasiswa

### Input
- **IPK**: Indeks Prestasi Kumulatif mahasiswa  
- **TOEFL**: skor TOEFL mahasiswa  
- **Penghasilan Orang Tua**: nominal penghasilan bulanan

### Proses
1. **Fuzzifikasi**  
   - IPK: `buruk`, `cukup`, `bagus`  
   - TOEFL: `rendah`, `menengah`, `tinggi`  
   - Penghasilan: `kecil`, `sedang`, `besar`, `sangat_besar`  

2. **Aturan Fuzzy** (contoh):  
   - IF IPK BAGUS AND Penghasilan KECIL/Sedang THEN Kelayakan TINGGI  
   - IF TOEFL MENENGAH AND Penghasilan BESAR/SANGAT BESAR THEN Kelayakan RENDAH  

3. **Inferensi Mamdani** → defuzzifikasi centroid menghasilkan nilai kelayakan (0–100)

### Output
- Nilai kelayakan per mahasiswa  
- **Top 10 nilai kelayakan terendah** → ditampilkan ke layar  

---

## Fungsi Utama

| Fungsi                  | Deskripsi |
|-------------------------|-----------|
| `triangular(x, a, b, c)` | Fungsi keanggotaan segitiga |
| `trapezoidal(x, a, b, c, d)` | Fungsi keanggotaan trapesium |
| `fuzzify_*()`           | Fuzzifikasi input sesuai kategori (gaji, cicilan, IPK, TOEFL, penghasilan) |
| `inferensi_mamdani()`   | Inferensi Mamdani dengan defuzzifikasi centroid |
| `inferensi_tsukamoto()` | Inferensi Tsukamoto dengan output linear monoton (risiko kredit) |
| `top_10_terendah()`     | Menampilkan 10 nilai terendah dan menyimpan ke file Excel |

---

## Cara Menjalankan

1. Pastikan **Python 3** dan **pandas** terinstal  
2. Siapkan file input risiko kredit: `resiko kredit.xlsx` (kolom: ID, Gaji, Cicilan)  
3. Jalankan program:
```bash
Coding Study Case Fuzzy.ipynb
```

---
## Anggota Kelompok
1. Cindy Natasa - 103102400024
2. Ivana Gabby Lauretta 103102400037
3. Evelyna Angie – 103102400040



