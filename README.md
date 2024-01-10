# Dataset

Dataset yang digunakan adalah wiki_126.csv yang berisi dokumen teks dari Wikipedia. Dataset ini diambil dari dataset good.csv dan dislice karena terlalu berat.

## Permasalahan dan Tujuan Eksperimen

Permasalahan yang ingin diselesaikan adalah bagaimana mencari dokumen yang relevan dengan teks input. Tujuan eksperimen adalah untuk mengetahui seberapa bagus algoritma yang digunakan untuk mencari dokumen yang relevan.

## Model dan Alur Tahapan

Model yang digunakan adalah Euclidean Distance. Alur tahapan eksperimen adalah sebagai berikut:

#### Pelatihan Vectorizer:
Membuat objek vectorizer dari TfidfVectorizer(), yang digunakan untuk menghitung TF-IDF (Term Frequency-Inverse Document Frequency).
Melatih vectorizer dengan seluruh teks yang ada dalam dataframe df['text'].

#### Transformasi Teks:
Mengubah teks input ke dalam bentuk vektor menggunakan vectorizer.transform([input_text]).
Mengubah teks dalam filtered_df['text'] menjadi vektor.

#### Perhitungan Jarak Euclidean:
Jarak Euclidean dihitung antara vektor teks input dan vektor dokumen yang telah difilter menggunakan sklearn.metrics.pairwise.euclidean_distances.

#### Pengurutan Berdasarkan Jarak:
Nilai jarak ditambahkan ke dalam filtered_df dan diurutkan dari nilai jarak terendah ke tertinggi.

## Performa Model / Uji Performa Model

Untuk mengukur performa model, digunakan metric Relevance. Relevance didefinisikan sebagai rasio antara jumlah dokumen yang relevan dengan jumlah total dokumen yang direkomendasikan.

Pada eksperimen ini, didapatkan bahwa Relevance sebesar 0,7. Artinya, 70% dari dokumen yang direkomendasikan adalah dokumen yang relevan dengan teks input.
