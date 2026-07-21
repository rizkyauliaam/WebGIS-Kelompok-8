# 🌿 Klasifikasi dan Deteksi Perubahan Vegetasi Kabupaten Jember (2024–2025)

Repositori ini berisi source code, data spasial, hasil analisis, serta aplikasi WebGIS yang dikembangkan untuk memetakan perubahan tutupan vegetasi di Kabupaten Jember, Jawa Timur, pada periode 2024–2025. Analisis dilakukan menggunakan citra Sentinel-2, indeks NDVI, dan algoritma Random Forest yang dijalankan melalui Google Earth Engine. Hasil klasifikasi kemudian divisualisasikan dalam WebGIS interaktif untuk mendukung eksplorasi perubahan vegetasi secara spasial.

**Mata Kuliah:** Kapita Selekta Sistem Informasi & Maha Data

**Dosen Pengampu:** Zakiul Fahmi Jailani, S.Kom., M.Sc.

**Program Studi:** Sistem Informasi — Fakultas Teknik dan Ilmu Komputer, Universitas Bakrie

**Semester:** Genap 2025/2026

Informasi Proyek

Kota/Wilayah: Kabupaten Jember, Jawa Timur, Indonesia
Objek Target: Vegetasi (dianalisis menggunakan indeks NDVI)
Periode: 2024 vs 2025
Metode: Sentinel-2, Random Forest, evaluasi APRF, WebGIS interaktif

Proyek ini memetakan perubahan tutupan vegetasi di Kabupaten Jember antara
tahun 2024 dan 2025 menggunakan citra Sentinel-2 dan indeks NDVI, kemudian
diklasifikasikan dengan model Random Forest. Hasil klasifikasi dievaluasi
menggunakan confusion matrix dan metrik Accuracy, Precision, Recall, F1-score,
lalu disajikan dalam WebGIS interaktif untuk menampilkan area vegetasi yang
bertambah (gain), berkurang (loss), dan tetap (stable).

Anggota Kelompok 8

1. Yudha Pandu Widyanto - 1232002075
2. Willy Jonatan Sibagariang - 1232002020
3. Rizky Aulia Maharani - 1232002072
4. Cassandra Etania - 1232002065
5. Atih Yulianti - 1232002001
6. Exel Goklas Rivollet Sihombing - 1232002063

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
