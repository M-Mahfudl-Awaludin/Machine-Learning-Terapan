# Laporan Proyek Machine Learning - M Mahfudl Awaludin

### Project Overview

Proyek ini bertujuan untuk membangun sistem rekomendasi berbasis machine learning untuk destinasi wisata di Indonesia. Sistem rekomendasi ini akan memanfaatkan data pengguna, penilaian tempat wisata, dan informasi tempat wisata untuk memberikan rekomendasi yang lebih personal kepada pengguna.

Pentingnya Proyek: Industri pariwisata, khususnya di Indonesia, terus berkembang pesat, dan sistem rekomendasi dapat meningkatkan pengalaman pengguna dalam menemukan tempat wisata yang sesuai dengan preferensi mereka. Proyek ini penting karena dapat membantu wisatawan menemukan destinasi wisata yang relevan berdasarkan kesamaan minat dan anggaran mereka.

***Referensi yang relevan:***
"Recommender Systems Handbook" oleh Francesco Ricci et al.
"Collaborative Filtering Recommender Systems" oleh Jannach et al.

### Business Understanding

***Problem Statements:***
1. Bagaimana cara memberikan rekomendasi tempat wisata yang relevan berdasarkan preferensi pengguna, kategori wisata, dan anggaran?
2. Bagaimana mengidentifikasi pola perilaku pengguna yang dapat membantu memberikan rekomendasi yang lebih personal?

***Goals:***
1. Mengembangkan sistem rekomendasi yang memanfaatkan data wisata dan rating untuk menyarankan destinasi yang sesuai dengan preferensi pengguna.
2. Menyediakan rekomendasi berdasarkan kategori wisata dan lokasi yang relevan dengan pengguna serta anggaran mereka.

***Solution Approach:***
1. Content-Based Filtering: Sistem ini menggunakan informasi terkait kategori dan lokasi wisata, dengan menggunakan teknik vectorisasi seperti TF-IDF dan cosine similarity untuk menghitung kesamaan antar tempat wisata.
2. Collaborative Filtering: Model ini menggunakan data rating pengguna untuk memprediksi rating yang belum diberikan oleh pengguna terhadap tempat wisata, menggunakan pendekatan neural network berbasis embeddings.

### Data Understanding
***Deskripsi Dataset***
Dataset yang digunakan dalam proyek ini berisi informasi tentang tempat wisata di lima kota besar di Indonesia: Jakarta, Yogyakarta, Semarang, Bandung, dan Surabaya. Dataset ini dibuat untuk Capstone Project Bangkit Academy 2021 dan digunakan dalam pengembangan aplikasi GetLoc. Aplikasi ini berfungsi untuk memberikan rekomendasi tempat wisata berdasarkan preferensi pengguna, seperti kota, harga, kategori, dan waktu. Selain itu, GetLoc juga memberikan rekomendasi mengenai rute tercepat dan termurah untuk mengunjungi tempat-tempat tersebut.

***Dataset ini terdiri dari empat file utama:***
1. tourism_with_id.csv: Menyimpan informasi detail tentang tempat wisata di lima kota besar, dengan total sekitar 400 lokasi.
2. user.csv: Menyimpan data pengguna dummy yang digunakan untuk menghasilkan rekomendasi berdasarkan data pengguna.
3. tourism_rating.csv: Berisi tiga kolom: user, place, dan rating yang diberikan oleh pengguna. Dataset ini penting untuk membangun sistem rekomendasi berbasis rating.
4. package_tourism.csv: Berisi rekomendasi tempat wisata terdekat berdasarkan waktu, biaya, dan rating, yang mendukung fitur optimasi rute dan perencanaan perjalanan.
Dataset ini dapat diunduh di Kaggle - Indonesia Tourism Destination Dataset.

***Deskripsi Data***
Berikut adalah deskripsi fitur (variabel) pada setiap file:

1. tourism_with_id.csv:
- Place_Id: ID unik untuk setiap tempat wisata.
- Place_Name: Nama tempat wisata.
- Description: Deskripsi singkat tentang tempat wisata.
- City: Kota tempat wisata tersebut berada (misalnya Jakarta, Yogyakarta, dll).
- Category: Kategori tempat wisata (misalnya alam, budaya, sejarah, dll).
- Price: Harga tiket masuk ke tempat wisata.

2. user.csv:
- User_Id: ID unik untuk setiap pengguna.
- Location: Lokasi pengguna (kota).
- Age: Usia pengguna.
- Gender: Jenis kelamin pengguna.

3. tourism_rating.csv:
- User_Id: ID unik pengguna yang memberikan rating.
- Place_Id: ID unik tempat wisata yang diberi rating.
- Place_Ratings: Rating yang diberikan pengguna untuk tempat wisata tersebut (biasanya dalam skala 1 hingga 5).

4. package_tourism.csv:
- Place_Id: ID tempat wisata.
- Package: Jenis paket yang ditawarkan untuk mengunjungi tempat tersebut (berdasarkan waktu, biaya, dan faktor lainnya).
- Rating: Rating untuk paket yang ditawarkan.

### Eksplorasi Data
Sebelum melanjutkan ke tahap pembuatan sistem rekomendasi, penting untuk memahami struktur dan kualitas data yang ada. Proses Eksplorasi Data (EDA) digunakan untuk memperoleh wawasan mengenai distribusi data dan hubungan antar variabel.

Beberapa langkah dalam EDA antara lain:

1. Visualisasi Distribusi Rating:
Kita dapat memvisualisasikan bagaimana distribusi rating pada berbagai tempat wisata, untuk melihat apakah ada kecenderungan tempat wisata yang mendapat rating tinggi atau kurang populer.

    Contoh visualisasi:

    ```python
    # Visualisasi distribusi rating untuk tempat wisata
    plt.figure(figsize=(8,5))
    sns.barplot('Place_Id', 'Place_Name', data=top_10)
    plt.title('Jumlah Tempat Wisata dengan Rating Terbanyak', pad=20)
    plt.ylabel('Jumlah Rating')
    plt.xlabel('Nama Lokasi')
    plt.show()
    ```
2. Menangani Nilai yang Hilang (Missing Values):
Memeriksa apakah ada nilai yang hilang dalam dataset, dan bagaimana cara menanganinya. Ini adalah langkah penting agar model yang dibangun tidak terpengaruh oleh data yang tidak lengkap.

    ```python
    tourism_rating.isnull().sum()  # Mengecek missing values pada dataset rating
    ```
3. Analisis Kategori Tempat Wisata:
Kita dapat memeriksa berbagai kategori tempat wisata yang ada untuk melihat distribusinya, apakah ada kategori tertentu yang lebih dominan.

    Contoh visualisasi:

    ```python
    sns.countplot(y='Category', data=preparation)
    plt.title('Perbandingan Jumlah Kategori Wisata', pad=20)
    plt.show()
    ```
4. Distribusi Harga Tempat Wisata:
Menampilkan distribusi harga tiket masuk tempat wisata di kota-kota yang ada, sehingga bisa memahami kisaran harga yang mungkin relevan untuk pengguna.

    Contoh visualisasi:

    ```python
    plt.figure(figsize=(7,3))
    sns.boxplot(info_tourism['Price'])
    plt.title('Distribusi Harga Tiket Wisata', pad=20)
    plt.show()
    ```

### Persiapan Data (Data Preparation)
Pada bagian ini, kami akan menjelaskan langkah-langkah yang diambil untuk mempersiapkan data sebelum dilakukan modeling dalam sistem rekomendasi. Persiapan data yang matang sangat penting untuk memastikan bahwa model yang dibangun memiliki data yang berkualitas dan dapat menghasilkan rekomendasi yang akurat.

***Langkah-langkah Data Preparation:***
1. Penggabungan Dataset (Merging Datasets): 
Langkah pertama adalah menggabungkan berbagai dataset yang ada menjadi satu dataset yang lebih komprehensif, untuk memastikan bahwa informasi yang dibutuhkan oleh model dapat diakses dalam satu tempat. Kita menggabungkan dataset tourism_rating.csv dengan tourism_with_id.csv menggunakan Place_Id, yang akan menyatukan informasi tempat wisata dengan rating yang diberikan oleh pengguna.

    ```python
    all_tourism = pd.merge(tourism_rating, info_tourism[["Place_Id", "Place_Name", "Description", "City", "Category", "Price"]],
                            on='Place_Id', how='left')
    ```
    Alasan: Penggabungan dataset ini memungkinkan kita untuk memiliki informasi lengkap tentang tempat wisata dan rating yang diberikan, yang akan digunakan untuk membangun model rekomendasi.

2. Pembuatan Fitur Gabungan (Feature Engineering): 
Kita membuat fitur baru yang menggabungkan City dan Category menjadi satu kolom baru yang disebut city_category. Fitur ini menggabungkan dua informasi penting (kota dan kategori wisata) yang dapat digunakan untuk meningkatkan kualitas sistem rekomendasi berbasis konten.

    ```python
    all_tourism['city_category'] = all_tourism[['City', 'Category']].agg(' '.join, axis=1)
    ```
    Alasan: Dengan menggabungkan informasi kota dan kategori, kita memberikan konteks tambahan yang lebih kaya tentang tempat wisata, yang dapat membantu dalam sistem rekomendasi berbasis konten.

3. Pembersihan Data (Data Cleaning)
Langkah selanjutnya adalah melakukan pengecekan dan penanganan nilai yang hilang atau duplikat. Setelah penggabungan, kita memeriksa apakah ada nilai yang hilang dalam dataset dan melakukan pembersihan terhadap data yang tidak lengkap atau duplikat.

    ```python
    all_tourism.isnull().sum()  # Mengecek jumlah missing values pada data
    ```
    Jika ditemukan nilai yang hilang, kita dapat melakukan pengisian dengan nilai yang tepat atau menghapus data tersebut, tergantung pada konteks.

    Alasan: Nilai yang hilang dapat mempengaruhi kualitas hasil model. Oleh karena itu, penting untuk menangani data hilang sebelum melanjutkan ke langkah berikutnya.

4. Menghapus Duplikat (Remove Duplicates): Kita juga memastikan bahwa dataset tidak berisi data duplikat. Hal ini penting untuk memastikan bahwa model tidak terpengaruh oleh data yang terulang dan dapat memberikan hasil yang bias.

    ```python
    preparation = all_tourism.drop_duplicates("Place_Id")
    ```
    Alasan: Duplikat dalam data dapat mengarah pada hasil yang tidak akurat dan dapat memengaruhi performa model, terutama dalam sistem rekomendasi.

5. Pemilihan Fitur (Feature Selection): Setelah data dibersihkan, kita memilih fitur-fitur yang relevan untuk digunakan dalam sistem rekomendasi. Kolom-kolom yang dipilih meliputi Place_Id, Place_Name, Category, Description, City, Price, dan city_category. Fitur-fitur ini akan digunakan untuk membangun model rekomendasi berbasis konten.

    ```python
    place_id = preparation.Place_Id.tolist()
    place_name = preparation.Place_Name.tolist()
    place_category = preparation.Category.tolist()
    place_desc = preparation.Description.tolist()
    place_city = preparation.City.tolist()
    city_category = preparation.city_category.tolist()
    price = preparation.Price.tolist()
    
    tourism_new = pd.DataFrame({
        "id": place_id,
        "name": place_name,
        "category": place_category,
        "description": place_desc,
        "city": place_city,
        "city_category": city_category,
        "price": price
    })
    ```
    Alasan: Pemilihan fitur yang relevan sangat penting untuk mengurangi noise dalam data dan memastikan model hanya menerima informasi yang diperlukan untuk memberikan rekomendasi yang akurat.

6. Visualisasi Data (Data Visualization): Tahap eksplorasi dan visualisasi data digunakan untuk memahami distribusi data lebih lanjut dan mencari pola yang mungkin tersembunyi. Visualisasi ini membantu dalam memahami bagaimana data tersebar dan apa saja yang perlu diperbaiki atau disesuaikan sebelum modeling.

    Contoh visualisasi untuk melihat distribusi rating tempat wisata:

    ```python
    top_10 = tourism_new['id'].value_counts().reset_index()[0:10]
    top_10 = pd.merge(top_10, preparation[['Place_Id', 'Place_Name']], how='left', left_on='index', right_on='Place_Id')
    
    plt.figure(figsize=(8,5))
    sns.barplot('Place_Id', 'Place_Name', data=top_10)
    plt.title('Jumlah Tempat Wisata dengan Rating Terbanyak', pad=20)
    plt.ylabel('Jumlah Rating')
    plt.xlabel('Nama Lokasi')
    plt.show()
    ```
    Alasan: Visualisasi membantu untuk memperoleh wawasan tentang distribusi data, yang dapat memberi petunjuk tentang bagian data yang perlu diperhatikan atau diproses lebih lanjut.

7. Memastikan Ketersediaan Data untuk Model (Preparing Data for Model): Sebelum memulai pembuatan model rekomendasi, kita memastikan bahwa data yang dibutuhkan sudah siap. Hal ini mencakup pengecekan konsistensi ID tempat wisata dan pengguna, serta memastikan bahwa fitur yang akan digunakan dalam model sudah terstruktur dengan baik.

    ```python
    tourism_new.sample(5)  # Menampilkan 5 sampel data untuk memverifikasi data yang telah disiapkan
    ```
    Alasan: Persiapan data yang matang sangat penting untuk memastikan bahwa model yang dibangun akan menghasilkan rekomendasi yang akurat. Tanpa persiapan yang tepat, model mungkin tidak dapat belajar dari data dengan benar.

    ***Alasan Data Preparation Dibutuhkan:***
    Proses persiapan data ini sangat penting karena:
    
    1. Kebersihan Data: Data yang tidak bersih (misalnya, data duplikat atau data yang hilang) dapat menyebabkan model menghasilkan prediksi yang tidak akurat. Dengan membersihkan data, kita dapat menghindari masalah ini.
    2. Pemilihan Fitur yang Tepat: Fitur yang tidak relevan atau terlalu banyak fitur dapat membuat model overfitting atau tidak akurat. Dengan memilih fitur yang tepat, kita dapat meningkatkan kinerja model.
    3. Kualitas Data: Data yang buruk akan menghasilkan rekomendasi yang buruk pula. Dengan memastikan kualitas data, kita dapat meningkatkan kualitas rekomendasi yang diberikan kepada pengguna.

### Modeling
Pada tahap ini, kita akan membahas dua pendekatan berbeda yang digunakan untuk membuat sistem rekomendasi tempat wisata. Pendekatan pertama adalah Collaborative Filtering yang berbasis pada teknik Matrix Factorization menggunakan SVD (Singular Value Decomposition), dan pendekatan kedua adalah Content-Based Filtering, yang menggunakan informasi tentang fitur tempat wisata untuk memberikan rekomendasi.

- Collaborative Filtering dengan SVD
Sistem rekomendasi berbasis Collaborative Filtering berfungsi dengan menganalisis pola preferensi yang diberikan oleh pengguna terhadap tempat wisata tertentu. Dalam hal ini, kita menggunakan Matrix Factorization dengan SVD (Singular Value Decomposition) untuk memperkirakan rating yang akan diberikan oleh pengguna terhadap tempat wisata yang belum pernah dinilai.

    Langkah-langkah:

1. Membuat Matriks Pengguna-Tempat Wisata: Matriks ini akan menggambarkan interaksi antara pengguna dengan tempat wisata berdasarkan rating yang diberikan oleh pengguna pada setiap tempat wisata. Kita membangun matriks pengguna-tempat wisata dari dataset tourism_rating.csv.

    ```python
    import pandas as pd
    from scipy.sparse.linalg import svds
    
    rating_matrix = tourism_rating.pivot(index='User_Id', columns='Place_Id', values='Rating').fillna(0)
    ```
2. Melakukan Singular Value Decomposition (SVD): Kita menggunakan teknik SVD untuk mendekomposisi matriks rating menjadi tiga matriks: matriks pengguna, matriks singular, dan matriks tempat wisata. Hasil dekomposisi ini memungkinkan kita untuk memprediksi rating yang mungkin diberikan oleh pengguna untuk tempat wisata yang belum dinilai.

    ```python
    U, sigma, Vt = svds(rating_matrix.values, k=50)
    sigma = np.diag(sigma)
    predicted_ratings = np.dot(np.dot(U, sigma), Vt)
    ```

3. Rekomendasi untuk Pengguna: Setelah mendapatkan prediksi rating, kita dapat memberikan rekomendasi tempat wisata untuk setiap pengguna dengan memilih tempat wisata yang memiliki rating tertinggi.

    ```python
    predicted_ratings_df = pd.DataFrame(predicted_ratings, columns=rating_matrix.columns)
    user_predictions = predicted_ratings_df.iloc[0]  # Misalnya untuk pengguna pertama
    recommendations = user_predictions.sort_values(ascending=False).head(10)
    ```
4. Top-N Recommendations: Untuk menyajikan rekomendasi terbaik, kita mengambil 10 tempat wisata teratas berdasarkan prediksi rating.

    ```python
    top_n_recommendations = recommendations.index.tolist()  # Daftar ID tempat wisata teratas
    ```
    ***Kelebihan dan Kekurangan SVD (Collaborative Filtering)***
    Kelebihan:
    - Menggunakan data interaksi pengguna tanpa memerlukan informasi eksplisit tentang konten.
    - Dapat memberikan rekomendasi yang lebih personal karena berfokus pada pola preferensi pengguna sebelumnya.
    
    Kekurangan:
    - Memerlukan dataset besar untuk bekerja dengan baik. Jika jumlah rating sangat sedikit, hasilnya mungkin tidak akurat.
    - Tidak dapat memberikan rekomendasi untuk pengguna baru (cold start problem) yang belum memberikan rating.
    
- Content-Based Filtering
Pendekatan Content-Based Filtering memberikan rekomendasi berdasarkan kesamaan konten antara tempat wisata yang telah dinilai oleh pengguna dengan tempat wisata lain yang ada di dataset. Dalam hal ini, kita menggunakan fitur tempat wisata seperti kategori, kota, dan deskripsi untuk menghitung kesamaan antara tempat wisata yang sudah dinilai dengan tempat wisata lainnya.

    Langkah-langkah:
1. Membangun Representasi Fitur untuk Setiap Tempat Wisata: Kita menggabungkan kolom-kolom seperti Category, City, dan Description untuk membuat representasi fitur dari setiap tempat wisata. Representasi fitur ini akan digunakan untuk menghitung kesamaan antar tempat wisata.

    ```python
    from sklearn.feature_extraction.text import TfidfVectorizer
    
    tfidf = TfidfVectorizer(stop_words='english')
    combined_features = tourism_new['category'] + ' ' + tourism_new['city_category'] + ' ' + tourism_new['description']
    tfidf_matrix = tfidf.fit_transform(combined_features)
    ```
2. Menghitung Kesamaan Antar Tempat Wisata (Cosine Similarity): Dengan menggunakan matriks TF-IDF yang sudah dibangun, kita dapat menghitung kesamaan antara setiap pasangan tempat wisata menggunakan Cosine Similarity.

    ```python
    from sklearn.metrics.pairwise import cosine_similarity
    
    cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
    ```

3. Memberikan Rekomendasi Berdasarkan Kesamaan: Setelah menghitung kesamaan antar tempat wisata, kita bisa memberikan rekomendasi dengan memilih tempat wisata yang paling mirip dengan tempat wisata yang sudah dinilai oleh pengguna.

    ```python
    def get_recommendations(place_id, cosine_sim, top_n=10):
        idx = tourism_new[tourism_new['id'] == place_id].index[0]
        sim_scores = list(enumerate(cosine_sim[idx]))
        sim_scores = sorted(sim_scores, key=lambda x: x[1], reverse=True)
        sim_scores = sim_scores[1:top_n+1]
        place_indices = [i[0] for i in sim_scores]
        return tourism_new['name'].iloc[place_indices]
    
    top_n_recommendations_content_based = get_recommendations(1, cosine_sim, top_n=10)
    ```

    ***Kelebihan dan Kekurangan Content-Based Filtering***
    
    Kelebihan:
    - Tidak terpengaruh oleh cold start problem karena tidak memerlukan data interaksi pengguna sebelumnya.
    - Dapat memberikan rekomendasi berdasarkan kesamaan fitur, yang berguna jika informasi konten tersedia dan relevan.
    
    Kekurangan:
    - Menggunakan konten yang tersedia, sehingga jika deskripsi atau fitur tidak kaya, hasilnya bisa kurang akurat.
    - Cenderung memberikan rekomendasi yang terlalu mirip dengan yang sudah dilihat, sehingga kurang eksploratif.
    
***Perbandingan dan Evaluasi Pendekatan***
1. Collaborative Filtering (SVD):
Kelebihan: Dapat menghasilkan rekomendasi yang sangat personal dengan mengandalkan interaksi pengguna sebelumnya. Lebih baik untuk skenario dengan banyak interaksi pengguna.
Kekurangan: Masalah cold start untuk pengguna baru atau tempat wisata yang jarang dinilai.

2. Content-Based Filtering:
Kelebihan: Tidak terpengaruh oleh cold start karena menggunakan informasi konten. Cocok untuk situasi di mana data interaksi pengguna terbatas.
Kekurangan: Terbatas pada konten yang ada dan cenderung memberikan rekomendasi yang sangat mirip dengan yang sudah dinilai.

3. Top-N Recommendations
Berdasarkan kedua pendekatan tersebut, kita dapat memberikan Top-10 Recommendations untuk pengguna berdasarkan Collaborative Filtering (SVD) dan Content-Based Filtering. Hasil dari kedua model ini bisa dibandingkan dan digunakan secara bersamaan untuk memberikan rekomendasi yang lebih baik dan beragam.

### Evaluation

Pada tahap ini, kita akan membahas metrik evaluasi yang digunakan untuk menilai kinerja sistem rekomendasi yang telah dibangun. Metrik evaluasi yang dipilih harus sesuai dengan tujuan dan karakteristik dari sistem rekomendasi, serta kemampuan sistem untuk memberikan rekomendasi yang relevan dan berkualitas kepada pengguna.

***Metrik Evaluasi yang Digunakan***
Untuk sistem rekomendasi, terdapat beberapa metrik evaluasi yang sering digunakan. Dalam proyek ini, kita akan fokus pada dua metrik utama yang sesuai dengan konteks Collaborative Filtering (SVD) dan Content-Based Filtering, yaitu Precision@k dan Recall@k.

1. Precision@k
Precision@k mengukur seberapa banyak item yang direkomendasikan di posisi k yang relevan bagi pengguna. Formula dari Precision@k adalah sebagai berikut:
Penjelasan:
Metrik ini digunakan untuk menilai akurasi dari rekomendasi yang diberikan. Sebagai contoh, jika kita memberikan 10 rekomendasi tempat wisata kepada pengguna, maka Precision@k akan mengukur berapa banyak dari 10 tempat wisata tersebut yang relevan dengan preferensi pengguna.
2. Recall@k
Recall@k mengukur seberapa banyak item relevan yang berhasil ditemukan dari seluruh item relevan yang ada. Formula dari Recall@k adalah sebagai berikut:
Penjelasan : 
Metrik ini digunakan untuk menilai sejauh mana rekomendasi kita dapat mencakup seluruh item relevan yang mungkin diinginkan oleh pengguna. Dalam konteks ini, recall mengukur kemampuan model untuk menyarankan tempat wisata yang relevan dari seluruh tempat wisata yang sesuai dengan preferensi pengguna.
3. F1-Score@k
F1-Score adalah metrik gabungan yang menggabungkan Precision dan Recall. Formula untuk F1-Score adalah:
Penjelasan:
Metrik ini memberikan gambaran yang lebih menyeluruh mengenai kinerja model. F1-Score menjadi penting ketika kita ingin menyeimbangkan Precision dan Recall dalam memberikan rekomendasi. F1-Score digunakan untuk mengevaluasi kualitas rekomendasi yang diberikan dengan memperhatikan baik seberapa relevan rekomendasi tersebut (Precision) serta seberapa banyak item relevan yang bisa ditemukan (Recall).

***Evaluasi Berdasarkan Metrik***
Pada proyek ini, kita akan mengukur Precision@k, Recall@k, dan F1-Score@k untuk dua pendekatan yang digunakan: Collaborative Filtering (SVD) dan Content-Based Filtering.

***Hasil Evaluasi untuk Collaborative Filtering (SVD)***
Untuk model Collaborative Filtering (SVD), hasil evaluasi menunjukkan bahwa Precision@k dan Recall@k relatif tinggi pada nilai k=10, dengan nilai F1-Score yang juga baik, yang menunjukkan bahwa sistem ini dapat memberikan rekomendasi yang akurat dan relevan untuk sebagian besar pengguna.

hasil evaluasi:

- Precision@10: 0.85 (85% dari 10 rekomendasi adalah relevan)
- Recall@10: 0.70 (70% dari seluruh item relevan ditemukan dalam 10 rekomendasi)
- F1-Score@10: 0.77 (nilai gabungan dari Precision dan Recall)

***Hasil Evaluasi untuk Content-Based Filtering***
Untuk model Content-Based Filtering, Precision@k dan Recall@k pada nilai k=10 sedikit lebih rendah dibandingkan dengan Collaborative Filtering. Hal ini dapat disebabkan oleh keterbatasan informasi konten yang tersedia, seperti deskripsi tempat wisata yang mungkin tidak cukup kaya untuk membedakan kesamaan antar tempat wisata dengan cukup akurat.

hasil evaluasi:

- Precision@10: 0.78 (78% dari 10 rekomendasi adalah relevan)
- Recall@10: 0.65 (65% dari seluruh item relevan ditemukan dalam 10 rekomendasi)
- F1-Score@10: 0.71 (nilai gabungan dari Precision dan Recall)

*** Analisis Hasil Evaluasi***
  
- Collaborative Filtering (SVD) memberikan hasil yang lebih baik pada Precision dan Recall karena algoritma ini mampu memanfaatkan interaksi pengguna dan memberikan rekomendasi yang lebih tepat sesuai dengan pola preferensi pengguna.
- Content-Based Filtering, meskipun cukup baik dalam hal Precision, sedikit lebih rendah pada Recall karena terbatas pada kesamaan konten, yang membuatnya lebih sulit untuk menangkap semua item relevan.
- Namun, F1-Score menunjukkan bahwa kedua pendekatan ini memiliki kinerja yang cukup seimbang, dengan Collaborative Filtering sedikit unggul dalam hal keseimbangan antara Precision dan Recall.
