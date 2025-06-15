# Kelompok 8 Pembelajaran Mesin (H)

| No  | Nama                     | NRP        |
| --- | ------------------------ | ---------- |
| 1   | Iftala Zahri Sukmana     | 5025221002 |
| 2   | Ainun Nadhifah Syamsiyah | 5025221053 |
| 3   | Fairuuz Azmi Firas       | 5025221057 |
| 4   | Adnan Abdullah Juan      | 5025221155 |
| 5   | Reynaldi Neo Ramadhani   | 5025221265 |

# Implementasi dan Komparasi Model Pembelajaran Mesin pada Data Niat Pembelian Konsumen Online

Proyek ini menyajikan sebuah model klasifikasi machine learning yang dibangun dalam Jupyter Notebook untuk memprediksi niat beli pelanggan di platform e-commerce. Dengan menganalisis data perilaku pelanggan dan menerapkan berbagai algoritma, model ini secara spesifik menggunakan teknik SMOTE untuk mengatasi ketidakseimbangan kelas data. Tujuannya adalah menghasilkan wawasan prediktif untuk mengidentifikasi pelanggan yang paling mungkin melakukan pembelian.

## 🎯 Tujuan Project

- Menganalisis pengaruh seleksi fitur.
- Mengevaluasi dampak teknik SMOTE untuk data tidak seimbang.
- Mengukur peningkatan dari hyperparameter tuning.
- Membandingkan berbagai algoritma untuk menemukan kombinasi strategi yang paling optimal.

## 📊 Dataset Overview

Dataset "Online Shoppers Purchasing Intention" merupakan kumpulan data yang bersumber dari platform Kaggle. Dataset ini memuat 12.330 sesi pengguna unik yang dikumpulkan selama periode satu tahun, dengan tujuan utama untuk memprediksi apakah seorang pengguna akan menyelesaikan pembelian (konversi) dalam sesi kunjungannya ke situs e-commerce. Dataset ini dapat diakses melalui tautan berikut: [Online Shoppers Purchasing Intention Dataset](https://www.kaggle.com/datasets/imakash3011/online-shoppers-purchasing-intention-dataset/)

Setiap sesi direpresentasikan oleh 18 fitur, yang terdiri dari 10 fitur numerik dan 8 fitur kategorikal. Fitur-fitur ini merekam perilaku pengguna selama sesi kunjungan, seperti interaksi dengan halaman produk, durasi kunjungan, serta karakteristik perangkat dan waktu kunjungan. Berikut daftar fitur beserta penjelasannya:

1. Administrative: Jumlah halaman administratif yang dikunjungi (misalnya: login, register).
2. Administrative_Duration: Total waktu (dalam detik) yang dihabiskan pada halaman administratif.
3. Informational: Jumlah halaman informasi yang diakses (misalnya FAQ, About).
4. Informational_Duration: Durasi waktu yang dihabiskan di halaman informasi.
5. ProductRelated: Jumlah halaman produk yang dikunjungi (terkait pembelian).
6. ProductRelated_Duration: Total waktu yang dihabiskan di halaman produk.
7. BounceRates: Rasio halaman yang ditinggalkan tanpa interaksi lebih lanjut.
8. ExitRates: Rasio keluar pengguna dari masing-masing halaman.
9. PageValues: Estimasi nilai halaman sebelum terjadi transaksi (berdasarkan Google Analytics).
10. SpecialDay: Nilai antara 0 dan 1 yang menunjukkan kedekatan dengan hari spesial (misalnya Hari Valentine, Black Friday, dsb.).
11. Month: Bulan kunjungan pengguna (Jan–Dec).
12. OperatingSystems: Sistem operasi yang digunakan pengunjung.
13. Browser: Jenis browser yang digunakan saat mengakses situs.
14. Region: Wilayah geografis pengunjung.
15. TrafficType: Sumber lalu lintas atau rujukan pengguna menuju situs.
16. VisitorType: Tipe pengunjung, seperti New Visitor, Returning Visitor, atau Other.
17. Weekend: Bernilai TRUE jika sesi dilakukan pada akhir pekan.
18. Revenue (target): Bernilai TRUE jika terjadi pembelian pada sesi tersebut.

## 📋 Model dan Skenario

**Model-model klasifikasi** berikut telah diimplementasikan dan dievaluasi dalam notebook:

- **Logistic Regression:** Model linear untuk klasifikasi biner.
- **Random Forest Classifier:** Ensemble learning method yang membangun banyak pohon keputusan dan menggabungkan prediksi mereka.
- **Gradient Boosting Classifier:** Ensemble learning method lain yang membangun model secara sekuensial, di mana setiap model baru mengoreksi kesalahan dari model sebelumnya.
- **XGBoost Classifier:** Implementasi yang dioptimalkan dari gradient boosting, dikenal karena performa dan kecepatannya.
- **Decision Tree Classifier:** Model pohon yang membagi data berdasarkan fitur untuk membuat keputusan klasifikasi.
- **Gaussian Naive Bayes:** Model probabilistik berdasarkan teorema Bayes dengan asumsi independensi fitur.
- **ANN (MLPClassifier):** Jaringan saraf tiruan (Artificial Neural Network) dengan arsitektur Multi-Layer Perceptron.

**Skenario yang Digunakan:**
Notebook ini mengeksplorasi tiga skenario utama untuk melatih dan mengevaluasi model:

1.  **Perbandingan Data Tanpa Seleksi Fitur dengan Data Seleksi Fitur:**

    - Skenario ini membandingkan performa model ketika dilatih pada dataset lengkap (tanpa seleksi fitur) versus dataset yang telah melalui proses seleksi fitur. Tujuannya adalah untuk menganalisis dampak seleksi fitur terhadap kinerja model, potensi pengurangan dimensi, dan peningkatan interpretasi model.

2.  **Perbandingan Data Tanpa SMOTE dengan Data SMOTE:**

    - Pada skenario ini, model-model dilatih dan dievaluasi pada dataset asli yang tidak seimbang, kemudian dibandingkan dengan performa model yang dilatih pada data yang telah diatasi ketidakseimbangan kelasnya menggunakan teknik **SMOTE (Synthetic Minority Over-sampling Technique)**. Tujuannya adalah untuk melihat apakah penanganan ketidakseimbangan kelas dapat meningkatkan performa model, terutama pada metrik yang sensitif terhadap kelas minoritas seperti recall dan F1-score.

3.  **Perbandingan setelah menggunakan Hyperparameter Tuning:**
    - Skenario ini membandingkan performa model sebelum dan sesudah dilakukan **Hyperparameter Tuning** menggunakan `GridSearchCV`. Tujuannya adalah untuk menemukan kombinasi hyperparameter optimal yang dapat meningkatkan performa model lebih lanjut dan mengukur peningkatan yang dihasilkan.
