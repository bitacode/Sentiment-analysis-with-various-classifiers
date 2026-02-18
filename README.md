Repository ini merupakan implementasi demo dari riset penelitian yang berjudul "Enhancing Minority Sentiment Classification in Gastronomy Tourism: A Hybrid Sentiment Analysis Framework With Data Augmentation, Feature Engineering and Business Intelligence" yang dipublikasikan di IEEE Xplore.

🔗 Link Paper: https://ieeexplore.ieee.org/document/10422746

<h1>📋 I. Pendahuluan</h1>
Penelitian ini bertujuan untuk mengoptimasi analisis sentimen pada kondisi data yang timpang (imbalanced class) , di mana kelas positif jauh lebih banyak dibandingkan kelas negatif.
<br>
<h3>Ringkasan Penelitian:</h3>

- Membandingkan performa **beberapa model deep learning**
- Menggunakan **3 classifier berbeda**: VADER, TextBlob, dan AFINN
- Membandingkan kondisi:
    - Data yang telah diaugmentasi vs belum diaugmentasi
    - Data yang ditokenisasi dengan beberapa metode:
      - Bag of Words (BoW)
      - TF-IDF
      - Word2Vec

<h1>📁 II. Pembahasan</h1>
Repository ini menyimpan beberapa file utama: 3 model yg telah dilatih, 2 dataset CSV dan 1 file Python notebook.
<br>
<h3>A. Model</h3>
Terdapat 3 model yang telah dilatih menggunakan 3 classifier berbeda:

-  `cnn_vader_bow_50.keras` – Model dengan labeling VADER
-  `cnn_afinn_bow_50.keras` – Model dengan labeling AFINN
-  `cnn_tb_bow_50.keras` – Model dengan labeling TextBlob

📌 Detail arsitektur model dapat dilihat dalam file Python notebook.

<h3>B. 📓 Python Notebook</h3>

File: `synonym-augmentation.ipynb`
<br>
Notebook ini berisi:

- Proses dan fungsi-fungsi yang digunakan
- Arsitektur model
- Proses training model
- Hasil evaluasi model

💻 Cara menjalankan: <br>
Buka menggunakan **Jupyter Notebook**, **Google Colab** atau **Kaggle Notebook**

<h3>C. 📊 Dataset</h3>

| No | Nama File | Sumber | Keterangan |
|-----|----------|----------|------------|
| 1 | `sentiment_results.csv` | Kaggle: [Malaysia Restaurant Review Datasets](https://www.kaggle.com/datasets/choonkhonng/malaysia-restaurant-review-datasets) | Dataset ini telah dilabel dan disimpan dengan nama `sentiment_results.csv` (digunakan untuk training model pada demo ini) |
| 2 | `TRIPADVISOR_FOOD_SENTIMENTS_SARAWAK.csv` | Kaggle: [SARAWAK FOOD SENTIMENT ANALYSIS](https://www.kaggle.com/datasets/mohdnorhishamrazali/sarawak-food-sentiment-analysis) | Dataset original yang digunakan pada penelitian asli (digunakan untuk testing model pada demo ini) |

<h1>📈 III. Hasil Evaluasi Model</h1>
Setelah melalui proses evaluasi, diperoleh hasil sebagai berikut:
<br>
<h3>🏆 Performa Model</h3>
- Model CNN dengan labeling VADER unggul 0.25-0.5% dibandingkan kedua model lainnya (TextBlob dan AFINN).

<h3>⚠️ Overfitting Parah</h3>
Namun, bila dilihat dari proses training:

```
loss: 0.6575
val_loss: 0.9462
accuracy: 0.6248
val_accuracy: 0.0528
```

**📌 Interpretasi:**
<br>
- Model ini mengalami overfitting yang sangat parah
- Artinya model bekerja sangat baik dengan data yang dikenal (data training), namun apabila diperkenalkan dengan data baru/asing, model akan sangat tidak akurat
- Hal ini terlihat dari gap yang sangat besar antara accuracy (0.62) dan val_accuracy (0.05)

<h1>🏁 IV. Kesimpulan</h1>
Demo ini hanya mencakup perbandingan model CNN yang dilatih dengan 3 classifier berbeda (VADER, TextBlob, AFINN) dan ditokenisasi menggunakan Bag of Words (BoW).

<h3>🔬 Keterbatasan Demo</h3>

- ✅ Hanya menggunakan 1 metode tokenisasi yaitu Bag of Words
- ✅ Hanya menggunakan 1 arsitektur model yaitu CNN
- ❌ Belum mencakup tokenisasi dengan TF-IDF dan Word2Vec
- ❌ Belum mencakup arsitektur model lain yg disebutkan dalam penelitian yaitu CNN, LSTM, CNN-LSTM, Support Vector Machine, Random Forest dan lain-lain

<h1>💡 Ide Penelitian Lanjutan</h1>

- Menggunakan model BERT family dan menggunakan BERT tokenizer
- Mencoba hyperparameter tuning
- Mengatasi overfitting dengan regularization yang lebih baik

<h1>📚 Referensi</h1>

- Paper asli: [IEEE Xplore - 10422746](https://ieeexplore.ieee.org/document/10422746)
- Dataset 1: [Malaysia Restaurant Review Datasets](https://www.kaggle.com/datasets/choonkhonng/malaysia-restaurant-review-datasets)
- Dataset 2: [Sarawak Food Sentiment Analysis](https://www.kaggle.com/datasets/mohdnorhishamrazali/sarawak-food-sentiment-analysis)

<h1>📜 Lisensi</h1>
Repository ini dibuat untuk keperluan demo dan edukasi. Silakan gunakan dengan menyertakan atribusi yang sesuai.
