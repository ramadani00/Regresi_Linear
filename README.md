
https://github.com/ramadani00/Probabilitas_Dan_Statistika


# Regresi Linear Produksi Padi

Repository ini berisi analisis regresi linear untuk memodelkan produksi padi berdasarkan berbagai faktor seperti luas panen, curah hujan, kelembapan, dan suhu rata-rata. Analisis dilakukan menggunakan Python dan berbagai pustaka statistik serta visualisasi.

## Deskripsi Dataset

Dataset yang digunakan berasal dari file Excel `Data_Tanaman_Padi_Sumatera_version_1.xlsx`. Dataset ini mencakup data produksi padi di berbagai provinsi di Sumatera dari tahun 1993 hingga 2020.

- **Kolom Data:**
  - `Produksi`: Produksi padi (dalam ton).
  - `Luas Panen`: Luas panen (dalam hektar).
  - `Curah hujan`: Curah hujan (dalam mm).
  - `Kelembapan`: Tingkat kelembapan (dalam persen).
  - `Suhu rata-rata`: Suhu rata-rata (dalam derajat Celsius).

Dataset awal mencakup kolom `Provinsi` dan `Tahun`, yang dihapus untuk analisis ini.

---

## Langkah-Langkah Analisis

### 1. Eksplorasi Data (EDA - Exploratory Data Analysis)
- Memeriksa struktur dataset (`info()` dan `describe()`).
- Deteksi nilai yang hilang.
- Visualisasi:
  - Boxplot.
  - Histogram.
  - Heatmap korelasi antar variabel.
  - Pairplot antar variabel numerik.

### 2. Membuat Model Regresi Linear
- Variabel Dependen: `Produksi`.
- Variabel Independen: `Luas Panen`, `Curah hujan`, `Kelembapan`, `Suhu rata-rata`.
- Menambahkan konstanta (`const`) untuk intercept.
- Membuat model menggunakan `statsmodels.OLS`.

### 3. Evaluasi Model
- **R-squared**: 0.826 (82.6% variabilitas data dapat dijelaskan oleh model).
- Melihat koefisien variabel independen dan signifikansinya.

### 4. Uji Asumsi
- **Multikolinearitas**:
  - Menghitung Variance Inflation Factor (VIF) untuk mendeteksi multikolinearitas.
- **Normalitas Residual**:
  - Histogram residual.
  - QQ-plot.
  - Uji Shapiro-Wilk dan Kolmogorov-Smirnov.
- **Homoskedastisitas**:
  - Uji Breusch-Pagan.
- **Autokorelasi Residual**:
  - Uji Durbin-Watson.

---

## Hasil Penting

1. **Korelasi Variabel**:
   - `Produksi` memiliki korelasi positif yang kuat dengan `Luas Panen` (0.9056).
   - Korelasi dengan variabel lain relatif lemah.

2. **Koefisien Model**:
   - `Luas Panen` memiliki pengaruh signifikan terhadap produksi padi.
   - Variabel `Curah hujan`, `Kelembapan`, dan `Suhu rata-rata` tidak signifikan dalam model ini.

3. **Uji Asumsi Model**:
   - Multikolinearitas rendah (VIF < 5).
   - Residual tidak berdistribusi normal (p-value < 0.05 pada uji Shapiro-Wilk dan Kolmogorov-Smirnov).
   - Tidak ada masalah homoskedastisitas (p-value > 0.05 pada uji Breusch-Pagan).

---

## Visualisasi

Berbagai visualisasi telah dibuat untuk mendukung analisis, termasuk:
- **Boxplot** untuk mendeteksi outlier.
- **Histogram** untuk distribusi data.
- **Heatmap korelasi** untuk hubungan antar variabel.
- **Scatter plot residual** untuk linieritas.
- **QQ-plot** untuk memeriksa normalitas residual.

---

## File yang Digunakan

- **Notebook**: [Regresi Linear Produksi Padi.ipynb](https://github.com/ramadani00/Regresi_Linear/blob/main/Regresi%20Linear%20Produksi%20Padi.ipynb)
- **Data**: `Data_Tanaman_Padi_Sumatera_version_1.xlsx` (tidak disertakan dalam repository ini).

---

## Dependencies

Analisis ini dilakukan dengan menggunakan pustaka berikut:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `statsmodels`
- `scipy`
- `sklearn`

Untuk menginstal semua dependencies, gunakan perintah berikut:
```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn
