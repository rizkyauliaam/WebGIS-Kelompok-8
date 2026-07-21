# Klasifikasi dan Deteksi Perubahan Vegetasi Kabupaten Jember (2024–2025)

Repositori ini berisi source code, data spasial, hasil analisis, serta aplikasi WebGIS yang dikembangkan untuk memetakan perubahan tutupan vegetasi di Kabupaten Jember, Jawa Timur, pada periode 2024–2025. Analisis dilakukan menggunakan citra Sentinel-2, indeks NDVI, dan algoritma Random Forest yang dijalankan melalui Google Earth Engine. Hasil klasifikasi kemudian divisualisasikan dalam WebGIS interaktif untuk mendukung eksplorasi perubahan vegetasi secara spasial.

**Mata Kuliah:** Kapita Selekta Sistem Informasi & Maha Data

**Dosen Pengampu:** Zakiul Fahmi Jailani, S.Kom., M.Sc.

**Program Studi:** Sistem Informasi — Fakultas Teknik dan Ilmu Komputer, Universitas Bakrie

**Semester:** Genap 2025/2026

---

# Informasi Proyek

| Informasi | Keterangan |
|-----------|------------|
| **Wilayah Studi** | Kabupaten Jember, Jawa Timur, Indonesia |
| **Objek Analisis** | Tutupan Vegetasi |
| **Periode** | 2024–2025 |
| **Data Satelit** | Sentinel-2 Surface Reflectance Harmonized |
| **Fitur Analisis** | 6 Band Spektral + NDVI, NDWI, NDBI, EVI, SAVI |
| **Metode Klasifikasi** | Random Forest |
| **Evaluasi Model** | Confusion Matrix, Accuracy, Precision, Recall, F1-Score, Kappa Coefficient |
| **Output** | WebGIS Interaktif |

Kabupaten Jember dipilih sebagai wilayah studi karena memiliki karakteristik yang sesuai untuk analisis perubahan tutupan vegetasi. Sebagai salah satu daerah dengan sektor pertanian dan perkebunan yang dominan di Jawa Timur, kondisi vegetasi di Kabupaten Jember mengalami perubahan yang dinamis dari waktu ke waktu. Selain itu, wilayah ini memiliki batas administrasi yang jelas serta ketersediaan citra Sentinel-2 yang memadai, sehingga mendukung proses analisis menggunakan Google Earth Engine dan algoritma Random Forest.

---

# Tim Pengembang

| Nama | NIM | Peran |
|------|------|--------------------------------|
| Yudha Pandu Widyanto | 1232002075 | Data Collector & GEE Engineer |
| Willy Jonatan Sibagariang | 1232002020 | GEE Engineer |
| Rizky Aulia Maharani | 1232002072 | WebGIS Developer & Repository Manager |
| Exel Goklas Rivollet Sihombing | 1232002063 | Repository Manager |
| Cassandra Etania | 1232002065 | Technical Writer |
| Atih Yulianti | 1232002001 | Technical Writer |

## Data dan Pra-pemrosesan

| Parameter | Konfigurasi |
|-----------|-------------|
| Dataset | Sentinel-2 Surface Reflectance Harmonized |
| Wilayah | Kabupaten Jember, Jawa Timur |
| Periode | 2024 dan 2025 |
| Filter Awan | CLOUDY_PIXEL_PERCENTAGE < 20% |
| Cloud Masking | QA60 |
| Metode Komposit | Median Composite |
| Resolusi | 10 meter |
| Band | B2, B3, B4, B8, B11, B12 |
| Indeks | NDVI, NDWI, NDBI, EVI, SAVI |

# Metodologi

```text
Sentinel-2
      │
      ▼
Preprocessing
      │
      ▼
Perhitungan NDVI
      │
      ▼
Ground Truth
      │
      ▼
Random Forest
      │
      ▼
Evaluasi APRF
      │
      ▼
Analisis Gain • Loss • Stable
      │
      ▼
WebGIS Interaktif
```
## Konfigurasi Model

| Parameter | Nilai |
|-----------|--------|
| Metode Split | 70:30 |
| Seed | 42 |
| Algoritma | Random Forest |
| Jumlah Trees | 100 |
| Jumlah Fitur | 11 (6 band + 5 indeks) |
| Ground Truth | 300 titik |
| Data Training | 215 titik |
| Data Testing | 85 titik |

Link WebGIS: https://web-gis-kelompok-8-kab-jember.vercel.app/

Cara Membuka WebGIS
Buka link: https://web-gis-kelompok-8-kab-jember.vercel.app/

WebGIS terdiri dari 4 tab:
1. Peta Hasil : peta interaktif berisi basemap, batas Kabupaten Jember,
vegetasi 2024, vegetasi 2025, gain, loss, legenda, layer control, dan
popup informasi.
2. Data & Proses : sumber data, metode preprocessing, band/indeks,
ground truth, dan parameter Random Forest yang digunakan.
3. Evaluasi Model : confusion matrix, Accuracy, Precision, Recall,
F1-score, dan interpretasinya.
4. Insight Hasil : ringkasan luas dan perubahan vegetasi, lokasi
perubahan terbesar, serta rekomendasi lanjutan.
