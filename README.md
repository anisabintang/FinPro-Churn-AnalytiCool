# FinPro-Churn-AnalytiCool
Final Project Data Science Stage 1

# Summary Insight

### Data Cleansing
- **Missing Values:** Tidak ada missing values yang ditemukan.
- **Duplicated Data:** Tidak ada data yang duplikat.
- **Outliers Handling:** Outliers ditangani dengan menggunakan metode Z-Score dengan threshold 1.5 standard deviasi, khusus untuk kolom 'CreditScore'. Metode ini cocok untuk fitur dengan distribusi yang hampir normal.
- **Feature Transformation:**
  - **Log Transformation:** Diterapkan pada fitur 'Age' karena distribusinya yang right-skewed untuk menormalkan skalanya.
- **Feature Encoding:**
  - **Label Encoding:** Digunakan untuk fitur 'Gender', yang memiliki dua nilai unik.
  - **One Hot Encoding:** Diimplementasikan untuk fitur 'Geography', tepat digunakan untuk fitur yang bukan kategori biner/ordinal.
  - **Note:** Fitur 'Surname' akan dieliminasi karena kurang relevan.

### Feature Engineering
- **Handle Class Imbalance:** Menggunakan SMOTE untuk mengurangi risiko overfitting yang mungkin terjadi pada oversampling tradisional dengan menciptakan sampel sintetis yang lebih realistis.
- **Feature Selection:**
  - **Numerical Data:** Pearson correlation digunakan untuk mengidentifikasi fitur yang memiliki korelasi tinggi (korrelasi > 0.6). Tidak ada fitur yang memenuhi ambang batas untuk eliminasi berdasarkan heatmap korelasi.
  - **Categorical Data:** Metode high cardinality menyebabkan eliminasi 'RowNumber', 'CustomerId', dan 'Surname' karena memiliki jumlah nilai unik yang tinggi.
- **Feature Extraction:**
  - **Age Tenure Ratio:** Menunjukkan rasio usia pelanggan terhadap masa/tenure cicilan, menunjukkan berapa lama mereka melakukan cicilan relatif terhadap usia mereka.
  - **Product Tenure Ratio:** Menunjukkan rasio masa cicilan terhadap jumlah produk yang dimiliki. Nilai yang lebih tinggi menunjukkan penggunaan produk yang lebih lama.
  - **Wealth Index:** Mengestimasi kekayaan relatif dengan menggabungkan saldo akun dan pendapatan.
- **Additional Features:**
  - **Marital Status:** Penting untuk menganalisis kecenderungan churn pelanggan. Individu yang menikah mungkin memiliki tanggung jawab finansial yang mempengaruhi loyalitas mereka.
  - **Transaction Frequency:** Menunjukkan jumlah transaksi atau aktivitas perbankan yang dilakukan oleh pelanggan dalam periode waktu tertentu.
  - **Home Ownership:** Menunjukkan apakah pelanggan memiliki atau menyewa rumah, memberikan wawasan tentang stabilitas tempat tinggal dan keamanan finansial.
  - **Employment Status:** Menjelaskan apakah pelanggan bekerja penuh waktu, paruh waktu, atau tidak bekerja sama sekali.
  - **Education:** Tingkat pendidikan pelanggan bisa mempengaruhi perilaku keuangan dan preferensi produk.

