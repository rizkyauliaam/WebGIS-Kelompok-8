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

Alur: Sentinel-2 → Cloud Masking (QA60) → Median Composite → Feature Extraction (Band Spektral + NDVI, NDWI, NDBI, EVI, SAVI) → Ground Truth → Split Data 70:30 → Random Forest → Evaluasi Model (Accuracy, Precision, Recall, F1-Score, Kappa) → Klasifikasi Vegetasi 2024 & 2025 → Analisis Perubahan (Gain, Loss, Stable) → WebGIS Interaktif

---

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

Konfigurasi model dirancang untuk menghasilkan klasifikasi vegetasi yang optimal dengan memanfaatkan 11 fitur (6 band spektral dan 5 indeks vegetasi). Data ground truth dibagi menggunakan rasio 70:30, kemudian model Random Forest dilatih menggunakan 100 decision trees sebelum dilakukan evaluasi performa.

---

## 📊 Hasil

### Evaluasi Model

| Metrik | Nilai |
|--------|-------:|
| Accuracy | 96.47% |
| Precision | 95.74% |
| Recall | 97.83% |
| F1-Score | 96.77% |
| Kappa Coefficient | 0.9288 |

## Hasil Analisis Perubahan Vegetasi

| Komponen | Luas (ha) | Persentase |
|----------|----------:|-----------:|
| Luas Kabupaten Jember | 332,036.98 | 100.00% |
| Vegetasi 2024 | 207,235.79 | 62.41% |
| Vegetasi 2025 | 241,333.38 | 72.68% |
| Gain (Bertambah) | 47,830.92 | 14.41% |
| Loss (Berkurang) | 13,733.33 | 4.14% |
| Stable (Tetap Vegetasi) | 193,502.46 | 58.28% |
| Net Change | +34,097.59 | +16.45% |

Hasil klasifikasi menggunakan algoritma **Random Forest** menunjukkan performa yang sangat baik dengan **Accuracy 96.47%**, **Precision 95.74%**, **Recall 97.83%**, dan **F1-Score 96.77%**. Analisis menunjukkan bahwa tutupan vegetasi di Kabupaten Jember meningkat dari **62.41%** pada tahun 2024 menjadi **72.68%** pada tahun 2025, dengan **penambahan bersih vegetasi sebesar 34,097.59 ha (+16.45%)**.

---

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
