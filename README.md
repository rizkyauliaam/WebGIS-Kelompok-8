# 🌿 Klasifikasi dan Deteksi Perubahan Vegetasi Kabupaten Jember (2024–2025)

Repositori ini berisi source code, data spasial, hasil analisis, serta aplikasi WebGIS yang dikembangkan untuk memetakan perubahan tutupan vegetasi di Kabupaten Jember, Jawa Timur, pada periode 2024–2025. Analisis dilakukan menggunakan citra Sentinel-2, indeks NDVI, dan algoritma Random Forest yang dijalankan melalui Google Earth Engine. Hasil klasifikasi kemudian divisualisasikan dalam WebGIS interaktif untuk mendukung eksplorasi perubahan vegetasi secara spasial.

**Mata Kuliah:** Kapita Selekta Sistem Informasi & Maha Data

**Dosen Pengampu:** Zakiul Fahmi Jailani, S.Kom., M.Sc.

**Program Studi:** Sistem Informasi — Fakultas Teknik dan Ilmu Komputer, Universitas Bakrie

**Semester:** Genap 2025/2026

---

# 📌 Informasi Proyek

| Informasi | Keterangan |
|-----------|------------|
| **Wilayah Studi** | Kabupaten Jember, Jawa Timur, Indonesia |
| **Objek Analisis** | Vegetasi |
| **Periode** | 2024–2025 |
| **Data Satelit** | Sentinel-2 |
| **Indeks Vegetasi** | NDVI |
| **Metode Klasifikasi** | Random Forest |
| **Evaluasi Model** | Accuracy, Precision, Recall, F1-Score (APRF) |
| **Output** | WebGIS Interaktif |

---

# 👥 Tim Pengembang

| Nama | NIM | Peran |
|------|------|--------------------------------|
| Yudha Pandu Widyanto | 1232002075 | Data Collector & GEE Engineer |
| Willy Jonatan Sibagariang | 1232002020 | GEE Engineer |
| Rizky Aulia Maharani | 1232002072 | WebGIS Developer & Repository Manager |
| Exel Goklas Rivollet Sihombing | 1232002063 | Repository Manager |
| Cassandra Etania | 1232002065 | Technical Writer |
| Atih Yulianti | 1232002001 | Technical Writer |

# ⚙️ Metodologi

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
