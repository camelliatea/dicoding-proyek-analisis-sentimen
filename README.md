
# Analisis Sentimen Ulasan Penggguna Aplikasi Canva Indonesia di Google Play Store
Proyek ini bertujuan untuk melakukan **analisis sentimen** terhadap ulasan pengguna aplikasi **Canva** yang diambil dari **Google Play Store**. Dengan menggunakan algoritma **Machine Learning** dan **Deep Learning**, proyek ini mengevaluasi kecenderungan sentimen pengguna (positif, negatif, atau netral) serta membandingkan performa model dalam melakukan klasifikasi sentimen berdasarkan teks ulasan.

---

## Dataset
Dataset berupa kumpulan **ulasan pengguna aplikasi Canva** yang diperoleh melalui proses scraping menggunakan library `google-play-scraper`. Ulasan-ulasan ini kemudian diberi label sentimen secara manual atau otomatis:  
- **Positif**  
- **Negatif**  
- **Netral**

---

## Tahapan Analisis
1. **Scraping Data** dari Google Play Store
2. **Preprocessing Teks** (cleansing, stopword removal, dll)
3. **Ekstraksi Fitur** menggunakan TF-IDF dan BoW
4. **Pelatihan Model** klasifikasi menggunakan:
   - Logistic Regression  
   - Random Forest  
   - LSTM (Long-Short Term Memory)
5. **Evaluasi dan Perbandingan Akurasi**

---


## Insight Utama
Model Long-Short Term Memory (LSTM) dengan pembagian data **80/20** menunjukkan performa terbaik dengan akurasi testing sebesar **96.23%**.

---

## Struktur Folder
dicoding_proyek_analisis_sentimen/
├── README.md
├── requirements.txt
├── Notebook_Pelatihan_Model.ipynb
├── Scraping.ipynb
└── ulasan_canva.csv

## Cara Menjalankan
1. Instal seluruh library yang dibutuhkan
    `pip install -r requirements.txt`
2. Jalankan file Scraping.ipynb
    `python Scraping.ipynb`
3. Jalankan file Notebook_Pelatihan_Model.ipynb
    `python Notebook_Pelatihan_Model.ipynb`
