# Analisis Pola Aglomerasi Spasial Tempat Billiard Modern terhadap Tipologi Nilai Lahan (NJOP) dan Kedekatan terhadap Pusat Perbelanjaan di Provinsi DKI Jakarta Menggunakan Metode Getis-Ord Gi*

**Praktikum Aplikasi SIG untuk Sosial, Ekonomi, dan Bisnis**
SVIG223650

**Nama:** Hilman Thoriq
**NIM:** 23/522897/SV/23809

---

## Deskripsi

Notebook ini bertujuan untuk menganalisis pola aglomerasi spasial tempat billiard modern di Provinsi DKI Jakarta menggunakan pendekatan Exploratory Spatial Data Analysis (ESDA), Kernel Density Estimation (KDE), Buffer dan Nearest Distance Analysis, serta Getis-Ord Gi* Hotspot Analysis.

Analisis dilakukan pada tingkat kecamatan dengan mempertimbangkan hubungan antara persebaran tempat billiard modern, nilai lahan (NJOP), kepadatan penduduk, dan kedekatan terhadap pusat perbelanjaan.

---

## Struktur Folder

```text
(folder kerja)
├── FINAL_SEB_1.ipynb
├── README.md
├── requirement.txt
└── DATA/
    ├── clean_billiard_dki-jakarta.geojson
    ├── clean_mall_dki-jakarta.geojson
    └── enriched_njop_kepadatan_dki-jakarta_2024.geojson
```

## Catatan

- Google Colab: file GeoJSON dibaca dari `/content/`.
- Jupyter Notebook lokal: file GeoJSON dibaca dari folder `DATA/`.
- Environment akan dideteksi secara otomatis.


---

## Instalasi

Install seluruh dependency dengan perintah:

```bash
pip install -r requirements.txt
```

---

## Library yang Digunakan

| Library     | Kegunaan                          |
| ----------- | --------------------------------- |
| NumPy       | Operasi numerik dan array         |
| Pandas      | Manipulasi data tabular           |
| SciPy       | Analisis statistik dan KDE        |
| GeoPandas   | Manipulasi data spasial           |
| Shapely     | Operasi geometri                  |
| PyProj      | Transformasi sistem koordinat     |
| MapClassify | Klasifikasi choropleth            |
| Matplotlib  | Visualisasi peta dan grafik       |
| Contextily  | Basemap OpenStreetMap dan CartoDB |
| libpysal    | Spatial Weight Matrix             |
| esda        | Moran's I dan Getis-Ord Gi*       |
| splot       | Visualisasi analisis spasial      |

---

## Data Input

### 1. Tempat Billiard Modern

* Format: GeoJSON (Point)
* Sumber: Google Maps dan OpenStreetMap
* Tahun: 2026

### 2. Pusat Perbelanjaan (Mall/Supermarket)

* Format: GeoJSON (Point)
* Sumber: Google Maps dan OpenStreetMap
* Tahun: 2026

### 3. Batas Kecamatan DKI Jakarta

* Format: GeoJSON (Polygon)
* Sumber: BIG dan BPS DKI Jakarta
* Tahun: 2024

### 4. Nilai Jual Objek Pajak (NJOP)

* Sumber: Bapenda DKI Jakarta
* Referensi: Kepgub DKI Jakarta Nomor 124 Tahun 2024

### 5. Kepadatan Penduduk

* Sumber: BPS DKI Jakarta
* Tahun: 2024

---

## Tahapan Analisis

### 1. Persiapan Lingkungan

* Instalasi library
* Konfigurasi visualisasi
* Definisi fungsi kartografi

### 2. Pemuatan dan Validasi Data

* Validasi struktur GeoJSON
* Validasi CRS
* Eliminasi Kecamatan Kepulauan Seribu

### 3. Exploratory Spatial Data Analysis (ESDA)

* Distribusi spasial titik
* Statistik deskriptif
* Choropleth NJOP
* Choropleth kepadatan penduduk

### 4. Kernel Density Estimation (KDE)

* KDE tempat billiard modern
* KDE pusat perbelanjaan
* Overlay KDE

### 5. Buffer dan Nearest Distance Analysis

* Jarak billiard ke pusat perbelanjaan terdekat
* Klasifikasi kedekatan spasial

### 6. Spatial Autocorrelation

* Moran's I Global
* Moran Scatterplot

### 7. Getis-Ord Gi*

* Spatial Weight Matrix
* Hotspot Analysis
* Coldspot Analysis
* Confidence Level Analysis

### 8. Korelasi Spasial

* Gi* vs NJOP
* Gi* vs jarak ke pusat perbelanjaan
* Gi* vs kepadatan penduduk

### 9. Sintesis dan Interpretasi

* Integrasi hotspot
* Nilai lahan
* Kedekatan pusat perbelanjaan
* Pola aglomerasi spasial

---

## Sistem Koordinat

| Sistem Koordinat | Kegunaan                  |
| ---------------- | ------------------------- |
| EPSG:4326        | Data geografis            |
| EPSG:3857        | Visualisasi basemap       |
| EPSG:32748       | Analisis jarak dan buffer |

---

## Catatan

Notebook mendukung:

* Google Colab
* Jupyter Notebook
* JupyterLab

Pada Google Colab, file GeoJSON akan dicari terlebih dahulu pada folder:

```text
/content/
```

Apabila file tidak ditemukan, notebook akan meminta pengguna mengunggah file secara interaktif.

---

## Output

Notebook menghasilkan beberapa peta dan grafik analisis, antara lain:

* Distribusi Spasial Billiard Modern
* Distribusi Pusat Perbelanjaan
* Choropleth NJOP
* Choropleth Kepadatan Penduduk
* Kernel Density Estimation (KDE)
* Buffer dan Nearest Distance
* Moran Scatterplot
* Hotspot Getis-Ord Gi*
* Peta Sintesis Aglomerasi Billiard Modern

Seluruh output disimpan pada folder:

```text
output/
```

---

## Penulis

Hilman Thoriq
Program Studi Sistem Informasi Geografis
Sekolah Vokasi Universitas Gadjah Mada
