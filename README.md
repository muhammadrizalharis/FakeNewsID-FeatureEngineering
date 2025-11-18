# FakeNewsID-FeatureEngineering  
Proyek Applied Machine Learning – Feature Engineering untuk Dataset FakeNewsID  
Oleh **Muhammad Rizal Haris – 105841103223 - Informatika UNISMUH**

---

## Deskripsi Proyek
Repositori ini berisi proses **preprocessing** dan **feature engineering** untuk tugas mata kuliah *Applied Machine Learning*.  
Dataset yang digunakan adalah **FakeNewsID**, yang berisi teks berita berlabel *hoax* dan *valid* dalam Bahasa Indonesia.

Tahapan proyek mengikuti pipeline machine learning standar:

1. **Data ingestion** (membaca data latih & data uji)
2. **Preprocessing teks** (cleaning, stopwords, normalization)
3. **Feature Engineering** (TF–IDF Vectorization)
4. **Model Baseline** (opsional di notebook baseline)
5. **Prediksi output** untuk data uji

Semua proses dilakukan menggunakan Python pada lingkungan Jupyter Notebook.

---

## Struktur Folder di Repositori

FakeNewsID-FeatureEngineering/
│
├── data/
│ ├── Data_latih.csv
│ ├── Data_uji.csv
│ └── prediksi_Data_uji.csv
│
├── notebooks/
│ ├── FakeNewsID_Baseline.ipynb
│ └── FakeNewsID_OneClick_VSCode.ipynb
│
├── references/
│ └── references_FakeNewsID.bib
│
└── README.md


---

## Tahap Preprocessing
Preprocessing dilakukan pada kolom teks menggunakan beberapa tahapan standar NLP Bahasa Indonesia:

- Case folding (lowercase)
- Menghapus URL
- Menghapus mention, hashtag
- Menghapus angka & karakter non-alfabet
- Stopword removal
- Stemming menggunakan **Sastrawi**
- Token normalization

Output dari tahap ini adalah kolom `clean_text` yang digunakan untuk ekstraksi fitur.

Semua proses preprocessing dapat ditemukan di notebook:  
**`notebooks/FakeNewsID_OneClick_VSCode.ipynb`**

---

##  Tahap Feature Engineering
Fitur utama diekstrak menggunakan:

### **TF–IDF Vectorization**
- `ngram_range = (1, 2)` → unigram + bigram  
- `max_features = 20.000` (menyesuaikan notebook)
- Menggunakan `TfidfVectorizer` dari scikit-learn

Pipeline:
1. Fit TF–IDF pada data latih  
2. Transform data uji  
3. Hasil transformasi digunakan untuk model baseline  
4. Prediksi disimpan ke file `prediksi_Data_uji.csv`

---

##  Notebook Utama
### **1. FakeNewsID_OneClick_VSCode.ipynb**
Berisi:
- Import library  
- Load dataset  
- Preprocessing  
- TF–IDF Feature Engineering  
- Training model baseline  
- Menyimpan hasil prediksi  

### **2. FakeNewsID_Baseline.ipynb**
Berisi model baseline sederhana untuk pembanding.

---

## Dataset
Dataset FakeNewsID terdiri dari:

| File | Fungsi |
|------|--------|
| `Data_latih.csv` | Data latih (training set) beserta label |
| `Data_uji.csv`   | Data uji (unlabeled) |
| `prediksi_Data_uji.csv` | Hasil prediksi akhir setelah model dilatih |

---

## Tujuan Proyek
- Menerapkan preprocessing teks menggunakan standar NLP Bahasa Indonesia  
- Membangun pipeline feature engineering menggunakan TF–IDF  
- Melatih model sederhana untuk mendeteksi hoax berbasis teks  
- Membuat repositori GitHub rapi & reproducible sesuai standar akademik  

---

##  Cara Menjalankan Notebook
1. Clone repositori:
   ```bash
   git clone https://github.com/muhammadrizalharis/FakeNewsID-FeatureEngineering.git
2. Masuk ke folder
   ```bash
   cd FakeNewsID-FeatureEngineering
3. Aktifkan environment Python (Anaconda / venv)
4. Install dependensi
   ```bash
   pip install scikit-learn pandas numpy matplotlib Sastrawi
5. Jalankan Jupyter Notebook
   ```bash
   jupyter notebook
6. Buka folder /notebooks/ dan jalankan file .ipynb

##referensi
Daftar referensi tersedia dalam:
references/references_FakeNewsID.bib

##Penutup
Repositori ini dibuat untuk memenuhi tugas Feature Engineering pada mata kuliah Applied Machine Learning.
Seluruh pipeline telah dirapikan agar mudah dipahami, dijalankan ulang, dan digunakan sebagai acuan penelitian lanjutan.

Jika ada update, model tambahan, atau peningkatan performa, repositori akan diperbarui.
