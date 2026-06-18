# Apakah Keterlambatan Pengiriman Mempengaruhi Kepuasan Pelanggan?

## Business Question

Apakah keterlambatan pengiriman berpengaruh terhadap kepuasan pelanggan?

Analisis ini bertujuan untuk memahami hubungan antara keterlambatan pengiriman dan review score pelanggan, serta mengidentifikasi faktor-faktor yang mungkin berkontribusi terhadap keterlambatan ekstrem.

## Dataset

Dataset yang digunakan adalah:

* `olist_classified_public_dataset.csv`
* Jumlah data: 3.584 baris
* Jumlah kolom: 34

Dataset berisi informasi mengenai order, estimasi pengiriman, tanggal pengiriman aktual, review pelanggan, dan atribut transaksi lainnya.

Setelah filtering (order_status == delivered) dan seleksi kolom relevan: 3.467 baris, 10 kolom.

## Tools

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

## Key Findings

### 1. Estimasi Pengiriman Jauh Lebih Lama dari Realisasi

Rata-rata estimasi pengiriman adalah **24.3 hari**, sedangkan rata-rata realisasi pengiriman hanya **14.04 hari**.

Terdapat buffer sekitar **10 hari**, yang mengindikasikan bahwa estimasi delivery cenderung terlalu longgar dan dapat membuat performa *on-time delivery* terlihat lebih baik daripada kondisi sebenarnya.

### 2. Keterlambatan Berhubungan dengan Review Score

Order yang terlambat cenderung memiliki review score yang lebih rendah dibanding order yang tidak terlambat.

Namun, keterlambatan bukan satu-satunya faktor yang memengaruhi kepuasan pelanggan karena hubungan yang ditemukan relatif lemah.

### 3. Keterlambatan Ekstrem Berdampak Besar pada Kepuasan

Ditemukan **95 order (2.74% dari total data)** yang mengalami keterlambatan lebih dari 14 hari.

Kelompok ini memiliki:

* Median review score = 1
* 75% pelanggan memberikan rating 1

Hal ini menunjukkan bahwa keterlambatan ekstrem memiliki dampak signifikan terhadap pengalaman pelanggan.

### 4. Jumlah Item Tidak Menjelaskan Keterlambatan

Hipotesis bahwa order dengan jumlah item lebih banyak akan lebih sering mengalami keterlambatan tidak terbukti.

Mayoritas order, baik yang terlambat ekstrem maupun normal, sama-sama hanya berisi satu item.

### 5. Estimasi Delivery Tidak Seragam

Order yang dibuat pada hari yang sama dapat memiliki estimasi tanggal pengiriman yang berbeda.

Temuan ini membantah hipotesis bahwa estimasi delivery ditentukan secara seragam berdasarkan tanggal pembelian.

## Business Recommendations

1. Evaluasi ulang estimasi delivery agar lebih realistis dan sesuai dengan performa aktual pengiriman.

2. Lakukan investigasi lebih lanjut terhadap 95 order dengan keterlambatan ekstrem untuk menemukan akar penyebabnya.

3. Kumpulkan data tracking atau checkpoint pengiriman yang lebih rinci agar analisis penyebab keterlambatan dapat dilakukan dengan lebih akurat di masa depan.

## Project Structure
ecommerce-analysis/
├── data/
│   └── olist_classified_public_dataset.csv
├── notebooks/
│   └── 01_data_understanding.ipynb
├── README.md
└── .gitignore

## How to Run

1. Download dataset `olist_classified_public_dataset.csv` dari kaggle.com di : https://www.kaggle.com/code/andresionek/understanding-the-olist-ecommerce-dataset?select=olist_classified_public_dataset.csv
dan simpan ke folder:

```text
data/
```

Sehingga struktur folder menjadi:

```text
ecommerce-analysis/
│
├── data/
│   └── olist_classified_public_dataset.csv
│
├── notebooks/
│   └── 01_data_understanding.ipynb
│
├── README.md
└── .gitignore
```

2. Clone repository

```bash
git clone https://github.com/username/ecommerce-analysis.git
```

3. Masuk ke folder project

```bash
cd ecommerce-analysis
```

4. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

5. Jalankan Jupyter Notebook

```bash
jupyter notebook
```

6. Buka file:

```text
notebooks/01_data_understanding.ipynb
```


## Limitations

* Dataset tidak memiliki informasi mengenai kualitas produk, kualitas kemasan, maupun persepsi harga pelanggan.
* Variabel lokasi pelanggan (`customer_city`) belum dianalisis lebih lanjut.
* Jumlah sampel pada kategori tepat waktu relatif kecil (41 order atau sekitar 1% dari total data).

## Author

Tantri Silaen

Portfolio Project – Data Analytics
