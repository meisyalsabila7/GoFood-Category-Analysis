# Analisis Tren Kategori Produk GoFood Indonesia

> Analisis mendalam terhadap 39.648 produk dari 687 merchant GoFood di 3 kota besar Indonesia — Jakarta, Medan, dan Surabaya — menggunakan Python dan Tableau.

---

## Latar Belakang & Pernyataan Masalah

GoFood sebagai platform food delivery terbesar di Indonesia menyediakan ribuan pilihan makanan dan minuman dari berbagai kategori. Proyek ini bertujuan menjawab pertanyaan bisnis berikut:

1. Kategori produk apa yang paling banyak tersedia di GoFood?
2. Bagaimana distribusi harga per kategori produk?
3. Kota mana yang punya variasi menu terbanyak per kategori?
4. Seberapa besar proporsi produk yang sedang diskon dan kategori mana yang paling banyak memberikan diskon?

---

## Dashboard Preview

🔗 **[Lihat Dashboard di Tableau Public](https://public.tableau.com/views/GoFoodIndonesia-AnalisisTrenKategoriProduk/AnalisisTrenKategoriProdukGoFoodIndonesia?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

Dashboard terdiri dari 3 visualisasi utama:
- **Jumlah Produk per Kategori** — Top 21 kategori berdasarkan jumlah produk
- **Rata-rata Harga per Kategori** — Perbandingan harga antar kategori
- **Heatmap Kota vs Kategori** — Distribusi produk per kategori di setiap kota

---

## Dataset

| Keterangan | Detail |
|---|---|
| Sumber | [Kaggle — Indonesia Food Delivery GoFood Product List](https://www.kaggle.com/datasets/ariqsyahalam/indonesia-food-delivery-gofood-product-list) |
| Total data mentah | 45.195 baris |
| Total setelah cleaning | 39.648 baris |
| Total merchant | 687 merchant |
| Total kategori | 21 kategori |
| Kota | Jakarta, Medan, Surabaya |

**Kolom yang tersedia:**

| Kolom | Keterangan |
|---|---|
| `merchant_name` | Nama restoran/merchant |
| `merchant_area` | Kota merchant |
| `category` | Kategori produk lengkap |
| `display` | Sub-kategori menu |
| `product` | Nama produk |
| `price` | Harga normal (Rp) |
| `discount_price` | Harga setelah diskon (Rp) |
| `isDiscount` | Status diskon (0/1) |
| `description` | Deskripsi produk |

---

## Tools & Teknologi

| Tool | Kegunaan |
|---|---|
| Python (pandas) | Pembersihan data & eksplorasi |
| Python (matplotlib & seaborn) | Visualisasi awal |
| Tableau Desktop | Dashboard interaktif final |
| Tableau Public | Publikasi dashboard online |

---

## Metodologi

### 1. Pembersihan Data (Python — pandas)
- Menghapus 5.547 baris duplikat
- Ekstraksi kategori utama dari format `Kopi/Minuman/Roti` → `Kopi`
- Standarisasi nama kota dengan `.str.title()`
- Menambahkan kolom `discount_label` untuk label yang lebih jelas

### 2. Eksplorasi Data (EDA)
- Analisis distribusi kategori produk
- Analisis harga per kategori (rata-rata, min, max, distribusi)
- Analisis proporsi dan sebaran produk diskon
- Perbandingan variasi menu antar kota

### 3. Visualisasi Python (matplotlib & seaborn)
- Bar chart horizontal Top 10 kategori
- Bar chart perbandingan kategori per kota
- Boxplot distribusi harga per kategori
- Pie chart proporsi diskon
- Bar chart kategori dengan diskon terbanyak
- Bar chart rata-rata potongan harga per kategori

### 4. Dashboard Tableau
- Export data agregasi ke CSV untuk Tableau
- Dashboard interaktif dengan filter klik antar chart

---

## Temuan Utama

| # | Temuan | Dampak |
|---|---|---|
| 1 | **Minuman** jadi kategori terbanyak (6.408 produk) — mengalahkan Jajanan dan Aneka Nasi | Tinggi |
| 2 | **Sweets** punya rata-rata harga tertinggi (Rp 100.723) — hampir 4x lipat kategori Bakmie | Tinggi |
| 3 | **Surabaya** unggul di kategori Minuman (2.582 produk) dan Roti (1.738 produk) | Sedang |
| 4 | **Medan** dominasi Aneka Nasi (2.278 produk) dan Jajanan (2.037 produk) | Sedang |
| 5 | Hanya **6.5%** produk yang sedang diskon — mayoritas produk dijual di harga normal | Tinggi |
| 6 | **Pizza & pasta** punya rata-rata potongan diskon terbesar (Rp 30.883 per produk) | Sedang |
| 7 | **Jakarta** unggul di kategori Cepat Saji (1.499) dan Sweets (1.204) | Sedang |

---

## Rekomendasi Bisnis

1. **Perkuat kategori Minuman** — volume tertinggi menunjukkan demand yang besar, cocok untuk campaign promosi rutin
2. **Optimalkan strategi diskon** — hanya 6.5% produk diskon, ada peluang besar untuk menarik pelanggan baru dengan promo kategori tertentu
3. **Ekspansi Sweets di Medan & Surabaya** — kategori ini dominan di Jakarta tapi masih rendah di kota lain, potensi pertumbuhan tinggi
4. **Program loyalitas per kota** — preferensi tiap kota berbeda, strategi marketing perlu disesuaikan per wilayah

---

## Struktur Proyek

```
gofood-category-analysis/
│
├── gofood_analysis.ipynb          
├── gofood_dataset.csv             
├── gofood_cleaned.csv             
├── gofood_summary_tableau.csv    
│
├── viz_01_kategori_produk.png    
├── viz_02_harga_kategori.png    
└── viz_03_diskon.png     
```

---

## Cara Menjalankan

1. Clone repository ini
   ```bash
   git clone https://github.com/meisyalsabila7/gofood-category-analysis.git
   ```

2. Buat virtual environment & install library
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install pandas matplotlib seaborn openpyxl
   ```

3. Buka notebook
   ```bash
   jupyter notebook gofood_analysis.ipynb
   ```

4. Jalankan semua cell secara berurutan

5. Buka `gofood_summary_tableau.csv` di Tableau untuk dashboard interaktif

---

## Tentang Saya

**Meisya Salsabila I.P.** 

- 📧 meisyasalsa7@gmail.com
- 💼 [LinkedIn](https://www.linkedin.com/in/meisyasalsabila/)

---

*Dataset bersumber dari Kaggle dan digunakan untuk tujuan pembelajaran dan pengembangan portofolio.*
