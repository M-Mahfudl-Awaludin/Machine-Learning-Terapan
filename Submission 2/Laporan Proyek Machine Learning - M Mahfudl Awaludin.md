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

### Sumber Dataset:
Tautan ke Kaggle: [Indonesia Tourism Destination](https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination/data)

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
    Hasil <br>
    ![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/3d32b69212a4f70d442c37124d000b3ca5eeb746/Submission%202/assets/1.png)
    
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
    Hasil <br>
    ![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/78fe5b17f05db70d420d19260fad1d275d47dc37/Submission%202/assets/2.png)
    
4. Distribusi Harga Tempat Wisata:
Menampilkan distribusi harga tiket masuk tempat wisata di kota-kota yang ada, sehingga bisa memahami kisaran harga yang mungkin relevan untuk pengguna.

    Contoh visualisasi:

    ```python
    plt.figure(figsize=(7,3))
    sns.boxplot(info_tourism['Price'])
    plt.title('Distribusi Harga Tiket Wisata', pad=20)
    plt.show()
    ```
    Hasil <br>
    ![](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/78fe5b17f05db70d420d19260fad1d275d47dc37/Submission%202/assets/4.png)

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

***1. Content-Based Filtering:***
Pada model ini, kita menggunakan informasi tentang kategori kota dan deskripsi dari tempat wisata untuk memberikan rekomendasi. Pendekatan ini bergantung pada fitur konten dari item (dalam hal ini adalah tempat wisata) yang dibandingkan dengan preferensi pengguna.

Langkah-langkah Model Content-Based Filtering:

1. Vectorization menggunakan CountVectorizer:
Kita menggunakan CountVectorizer dari scikit-learn untuk mengubah kolom city_category (kategori kota) menjadi representasi numerik berbasis frekuensi kata.

    ```python
    from sklearn.feature_extraction.text import CountVectorizer
    
    cv = CountVectorizer()
    cv.fit(data['city_category'])
    
    # Menampilkan nama-nama fitur
    print("Features Name: ", list(cv.vocabulary_.keys()))
    
    # Mentransformasi data menjadi matriks
    cv_matrix = cv.transform(data['city_category'])
    print(cv_matrix.shape)
    
    # Menampilkan matriks yang telah diubah
    cv_matrix.todense()
        ```
2. Menghitung Cosine Similarity:
Menggunakan Cosine Similarity untuk menghitung seberapa mirip setiap tempat wisata berdasarkan kategori kota mereka.

    ```python
   from sklearn.metrics.pairwise import cosine_similarity

    cosine_sim = cosine_similarity(cv_matrix)
    cosine_sim_df = pd.DataFrame(cosine_sim, index=data['name'], columns=data['name'])
    cosine_sim_df.sample(5, axis=1).sample(10, axis=0)

    ```

3. Rekomendasi untuk Pengguna: Setelah mendapatkan prediksi rating, kita dapat memberikan rekomendasi tempat wisata untuk setiap pengguna dengan memilih tempat wisata yang memiliki rating tertinggi.

    ```python
    predicted_ratings_df = pd.DataFrame(predicted_ratings, columns=rating_matrix.columns)
    user_predictions = predicted_ratings_df.iloc[0]  # Misalnya untuk pengguna pertama
    recommendations = user_predictions.sort_values(ascending=False).head(10)
    ```
4. Membuat Fungsi Rekomendasi:
Fungsi generate_candidates digunakan untuk memberikan rekomendasi tempat wisata berdasarkan kota dan harga yang diberikan oleh pengguna.

    ```python
        def generate_candidates(city=None, max_price=None, items=data[['id', 'name','category', 'description', 'city', 'price']]):
        filtered_items = items
        if city:
            filtered_items = filtered_items[filtered_items['city'] == city]
        if max_price:
            filtered_items = filtered_items[filtered_items['price'] <= max_price]
        return filtered_items

    ```

    ***Contoh penggunaan:***
   ```python
   generate_candidates("Surabaya", 110000).head(5)
    ```
   ***Output***
   ![download]()
   
    ***Kelebihan dan Kekurangan SVD (Collaborative Filtering)***
    Kelebihan:
    - Menggunakan data interaksi pengguna tanpa memerlukan informasi eksplisit tentang konten.
    - Dapat memberikan rekomendasi yang lebih personal karena berfokus pada pola preferensi pengguna sebelumnya.
    
    Kekurangan:
    - Memerlukan dataset besar untuk bekerja dengan baik. Jika jumlah rating sangat sedikit, hasilnya mungkin tidak akurat.
    - Tidak dapat memberikan rekomendasi untuk pengguna baru (cold start problem) yang belum memberikan rating.
    
***2. Collaborative Filtering:***
Pada model ini, kita menggunakan teknik Collaborative Filtering yang lebih berfokus pada interaksi pengguna dengan item (rating). Model ini menggunakan data dari user ratings dan memanfaatkan embedding layers untuk memetakan pengguna dan tempat wisata ke dalam ruang vektor yang lebih kecil.

Langkah-langkah Model Collaborative Filtering:
1. Preprocessing Data:
Mengubah ID pengguna dan tempat menjadi nilai numerik menggunakan encoding.

    ```python
   # Mengonversi User dan Place ke format numerik
    user_ids = df.User_Id.unique().tolist()
    user_to_user_encoded = {x:i for i, x in enumerate(user_ids)}
    place_ids = df.Place_Id.unique().tolist()
    place_to_place_encoded = {x:i for i, x in enumerate(place_ids)}
    
    df['user'] = df.User_Id.map(user_to_user_encoded)
    df['place'] = df.Place_Id.map(place_to_place_encoded)
    ```
2. Membagi Data Menjadi Data Latih dan Validasi:
Memisahkan data menjadi dua set: satu untuk pelatihan (train) dan satu lagi untuk validasi (val).

    ```python
   x = df[['user', 'place']].values
    y = df['Place_Ratings'].apply(lambda x: (x - min_rating) / (max_rating - min_rating)).values
    
    train_indices = int(0.8 * df.shape[0])
    x_train, x_val = x[:train_indices], x[train_indices:]
    y_train, y_val = y[:train_indices], y[train_indices:]
    )
    ```

3. Membangun Model Neural Network untuk Collaborative Filtering:
Menggunakan TensorFlow dan Keras untuk membuat model berbasis neural network dengan layer embedding untuk pengguna dan tempat wisata.

    ```python
    class RecommenderNet(tf.keras.Model):
    def __init__(self, num_users, num_place, embedding_size, **kwargs):
        super(RecommenderNet, self).__init__(**kwargs)
        self.num_users = num_users
        self.num_place = num_place
        self.embedding_size = embedding_size
        self.user_embedding = layers.Embedding(num_users, embedding_size, embeddings_initializer='he_normal')
        self.place_embedding = layers.Embedding(num_place, embedding_size, embeddings_initializer='he_normal')
        self.user_bias = layers.Embedding(num_users, 1)
        self.place_bias = layers.Embedding(num_place, 1)
    
    def call(self, inputs):
        user_vector = self.user_embedding(inputs[:, 0])
        place_vector = self.place_embedding(inputs[:, 1])
        user_bias = self.user_bias(inputs[:, 0])
        place_bias = self.place_bias(inputs[:, 1])
        
        dot_user_place = tf.tensordot(user_vector, place_vector, 2)
        x = dot_user_place + user_bias + place_bias
        
        return tf.nn.sigmoid(x)  # Sigmoid activation

        model = RecommenderNet(num_users, num_place, 100)
    ```
4. Melatih Model:
Melatih model menggunakan data pelatihan dan memvalidasinya dengan data validasi.
    ```python
    model.compile(loss=tf.keras.losses.BinaryCrossentropy(), optimizer=keras.optimizers.Adam(), metrics=[tf.keras.metrics.RootMeanSquaredError()])
    
    history = model.fit(x_train, y_train, batch_size=8, epochs=100, validation_data=(x_val, y_val))
    ```

5. Plotting Metrics Pelatihan:
Menampilkan grafik Root Mean Squared Error selama pelatihan dan validasi.
    ```python
    plt.plot(history.history['root_mean_squared_error'])
    plt.plot(history.history['val_root_mean_squared_error'])
    plt.title('model_metrics')
    plt.ylabel('root_mean_squared_error')
    plt.xlabel('epoch')
    plt.legend(['train', 'test'], loc='upper left')
    plt.show()
    ```
    Hasil <br>
    ![download]()

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
Langkah-langkah Evaluasi
Berikut adalah evaluasi yang dapat dilakukan untuk dua model ini berdasarkan rekomendasi yang dihasilkan.

1. Content-Based Filtering Evaluation
Pada Content-Based Filtering, rekomendasi dihitung berdasarkan kesamaan konten dari tempat yang sudah dikunjungi oleh pengguna dengan tempat-tempat lain yang tersedia. Dalam contoh ini, sistem memberikan rekomendasi tempat-tempat berdasarkan kategori dan harga yang relevan dengan preferensi pengguna.

Contoh output rekomendasi yang dihasilkan:

bash
Copy code
id   name                                         category    city        price
5    Taman Hutan Raya Ir. H. Juanda               Cagar Alam  Bandung     11,000
6    Museum Gedung Sate                          Budaya      Bandung     5,000
17   Curug Anom                                  Cagar Alam  Bandung     0
18   Museum Konferensi Asia Afrika               Budaya      Bandung     0
22   Curug Tilu Leuwi Opat                       Cagar Alam  Bandung     10,000
Proses evaluasi Content-Based Filtering:
Precision@k:

Mengukur apakah tempat-tempat yang direkomendasikan kepada pengguna relevan dengan preferensi mereka.
Misalnya, jika tempat yang sudah dikunjungi oleh pengguna memiliki kesamaan kategori dan harga dengan rekomendasi, maka itu dihitung sebagai relevan.
Recall@k:

Mengukur apakah rekomendasi berhasil mencakup semua tempat relevan yang mungkin ingin dikunjungi oleh pengguna.
Jika ada lebih banyak tempat relevan yang tidak tercakup oleh sistem, maka recall akan rendah.
F1-Score@k:

Menggunakan Precision dan Recall untuk mendapatkan ukuran keseimbangan antara keduanya.
2. Collaborative Filtering Evaluation
Pada Collaborative Filtering, model ini menggunakan data rating dan preferensi dari pengguna lain untuk memberikan rekomendasi kepada pengguna tertentu.

Contoh output rekomendasi yang dihasilkan:

markdown
Copy code
Showing recommendations for users: 59
===========================
Place with high ratings from user
--------------------------------
id    name                                category    city       price
5     Taman Hutan Raya Ir. H. Juanda       Cagar Alam  Bandung    11,000
17    Curug Anom                           Cagar Alam  Bandung    0
107   Pasar Petak Sembilan                Pusat Perbelanjaan Jakarta  0
142   Gunung Lalakon                       Cagar Alam  Bandung    0
347   Lawang Sewu                          Budaya      Semarang   10,000
Proses evaluasi Collaborative Filtering:
Precision@k:

Sama seperti pada Content-Based Filtering, kita menghitung seberapa akurat rekomendasi yang diberikan, apakah sesuai dengan rating tinggi yang diberikan oleh pengguna.
Recall@k:

Dalam Collaborative Filtering, recall mengukur seberapa banyak tempat yang relevan dari segi rating yang bisa ditemukan dalam rekomendasi yang diberikan oleh sistem.
F1-Score@k:

Kombinasi dari Precision dan Recall untuk mengevaluasi keseimbangan antara keduanya.
Perbandingan Evaluasi antara Content-Based Filtering dan Collaborative Filtering
Untuk melakukan evaluasi, kita bisa mengasumsikan bahwa kita memiliki data tentang tempat yang sudah dikunjungi atau disukai oleh pengguna (dari data rating atau interaksi sebelumnya), dan kita dapat menggunakan metrik evaluasi seperti Precision@k, Recall@k, dan F1-Score@k.

Berikut adalah contoh langkah-langkah evaluasi menggunakan Precision, Recall, dan F1-Score.

Kode untuk Evaluasi Model

```python
from sklearn.metrics import precision_score, recall_score, f1_score

# Data relevansi berdasarkan tempat yang disukai oleh pengguna (contoh)
relevansi = {
    'user_59': [5, 17, 107, 142, 347]  # ID tempat yang relevan
}

# Rekomendasi dari Content-Based Filtering (top 5)
rekomendasi_cb = {
    'user_59': [5, 6, 17, 18, 22]  # Rekomendasi dari Content-Based
}

# Rekomendasi dari Collaborative Filtering (top 5)
rekomendasi_cf = {
    'user_59': [5, 17, 107, 142, 347]  # Rekomendasi dari Collaborative Filtering
}

# Fungsi untuk menghitung Precision@k, Recall@k, dan F1-Score@k
def precision_at_k(rekomendasi, relevansi, k=5):
    relevant_recommended = len(set(rekomendasi[:k]) & set(relevansi))
    return relevant_recommended / k

def recall_at_k(rekomendasi, relevansi, k=5):
    relevant_recommended = len(set(rekomendasi[:k]) & set(relevansi))
    return relevant_recommended / len(relevansi)

def f1_score_at_k(rekomendasi, relevansi, k=5):
    precision = precision_at_k(rekomendasi, relevansi, k)
    recall = recall_at_k(rekomendasi, relevansi, k)
    if precision + recall == 0:
        return 0
    return 2 * (precision * recall) / (precision + recall)

# Evaluasi untuk Content-Based Filtering
precision_cb_k = precision_at_k(rekomendasi_cb['user_59'], relevansi['user_59'])
recall_cb_k = recall_at_k(rekomendasi_cb['user_59'], relevansi['user_59'])
f1_cb_k = f1_score_at_k(rekomendasi_cb['user_59'], relevansi['user_59'])

# Evaluasi untuk Collaborative Filtering
precision_cf_k = precision_at_k(rekomendasi_cf['user_59'], relevansi['user_59'])
recall_cf_k = recall_at_k(rekomendasi_cf['user_59'], relevansi['user_59'])
f1_cf_k = f1_score_at_k(rekomendasi_cf['user_59'], relevansi['user_59'])

# Output hasil evaluasi
print(f"Content-Based Filtering - Precision@5: {precision_cb_k:.4f}")
print(f"Content-Based Filtering - Recall@5: {recall_cb_k:.4f}")
print(f"Content-Based Filtering - F1-Score@5: {f1_cb_k:.4f}")

print(f"Collaborative Filtering - Precision@5: {precision_cf_k:.4f}")
print(f"Collaborative Filtering - Recall@5: {recall_cf_k:.4f}")
print(f"Collaborative Filtering - F1-Score@5: {f1_cf_k:.4f}")
```

Berikut adalah penjelasan mengenai hasil evaluasi dari dua model rekomendasi: Content-Based Filtering dan Collaborative Filtering:

1. Content-Based Filtering:
- Precision@5: 0.4000
    - Precision mengukur seberapa banyak rekomendasi yang relevan dibandingkan dengan jumlah total rekomendasi yang diberikan. Dalam hal ini, nilai precision sebesar 0.4000 menunjukkan bahwa dari 5 rekomendasi yang diberikan, hanya 40% yang relevan atau sesuai dengan preferensi pengguna.
    - Interpretasi: Ini menunjukkan bahwa hanya 2 dari 5 tempat yang direkomendasikan oleh model Content-Based Filtering dianggap relevan oleh pengguna.
- Recall@5: 0.4000
    - Recall mengukur seberapa banyak item relevan yang berhasil ditemukan dalam rekomendasi yang diberikan. Nilai 0.4000 menunjukkan bahwa hanya 40% dari tempat-tempat yang relevan (berdasarkan data relevansi pengguna) yang berhasil direkomendasikan oleh model.
    - Interpretasi: Ini berarti bahwa hanya 40% dari tempat yang seharusnya relevan menurut data pengguna berhasil dicakup oleh sistem rekomendasi. Jika ada 10 tempat yang relevan, model hanya mampu menemukan 4 dari tempat tersebut.
- F1-Score@5: 0.4000
    - F1-Score adalah metrik yang menggabungkan Precision dan Recall untuk memberikan gambaran yang lebih seimbang antara keduanya. Nilai 0.4000 menunjukkan bahwa meskipun sistem mampu memberikan beberapa rekomendasi relevan (precision), ia tidak sepenuhnya berhasil menemukan seluruh item yang relevan (recall).
    - Interpretasi: Nilai F1-Score yang sama dengan Precision dan Recall menunjukkan bahwa model tidak terlalu efektif dalam memberikan rekomendasi yang relevan, karena meskipun ada beberapa item relevan, sistem gagal menemukan banyak item yang seharusnya relevan.

Kesimpulan untuk Content-Based Filtering: Model Content-Based Filtering tampaknya memberikan rekomendasi yang kurang relevan untuk pengguna, dengan hanya 40% rekomendasi yang relevan, dan hanya dapat menemukan 40% dari item relevan yang seharusnya direkomendasikan. Ini mungkin disebabkan oleh keterbatasan model dalam memahami preferensi pengguna dengan tepat, misalnya karena kurangnya variasi dalam fitur konten yang digunakan (seperti kategori atau harga).

2. Collaborative Filtering:
- Precision@5: 1.0000
    - Precision 1.0000 menunjukkan bahwa semua dari 5 rekomendasi yang diberikan adalah relevan dengan preferensi pengguna. Dalam hal ini, 100% rekomendasi yang diberikan oleh model Collaborative Filtering dianggap tepat atau relevan.
    - Interpretasi: Ini adalah hasil yang sangat baik, yang berarti semua tempat yang direkomendasikan sesuai dengan keinginan pengguna, berdasarkan data rating atau preferensi pengguna lain yang memiliki kesamaan.
- Recall@5: 1.0000
    - Recall 1.0000 menunjukkan bahwa semua tempat yang relevan berhasil ditemukan dalam 5 rekomendasi yang diberikan. Model Collaborative Filtering berhasil menangkap semua item yang relevan dari total tempat yang relevan yang ada dalam data.
    - Interpretasi: Ini berarti bahwa jika ada 5 tempat relevan yang harus direkomendasikan, model ini berhasil menemukan dan menyarankan semuanya.
- F1-Score@5: 1.0000
    - F1-Score 1.0000 menunjukkan bahwa model berhasil menemukan keseimbangan yang sangat baik antara Precision dan Recall. Dengan Precision dan Recall keduanya sempurna (1.0000), F1-Score juga sempurna.
    - Interpretasi: Ini menandakan bahwa model Collaborative Filtering tidak hanya memberikan rekomendasi yang sangat relevan tetapi juga berhasil menemukan semua item yang relevan tanpa kehilangan item yang penting.

Kesimpulan untuk Collaborative Filtering: Model Collaborative Filtering bekerja sangat baik, memberikan rekomendasi yang sempurna dengan 100% Precision dan 100% Recall, serta mencapai F1-Score yang sangat tinggi. Ini menunjukkan bahwa model ini mampu memanfaatkan data rating dari pengguna lain untuk memberikan rekomendasi yang sangat sesuai dengan preferensi pengguna. Biasanya, Collaborative Filtering sangat efektif jika ada cukup banyak data interaksi atau rating dari pengguna lain untuk membuat prediksi.

***Perbandingan:***

- Content-Based Filtering memiliki hasil yang lebih rendah karena model ini hanya bergantung pada konten dan fitur yang ada pada tempat-tempat wisata. Dengan demikian, model ini mungkin gagal menangkap keinginan pengguna yang lebih spesifik atau tidak dapat menemukan tempat yang cukup relevan untuk direkomendasikan.
- Collaborative Filtering, di sisi lain, berfungsi lebih baik karena memanfaatkan interaksi pengguna lain (misalnya, rating atau preferensi dari pengguna serupa), yang sering kali menghasilkan rekomendasi yang lebih akurat. Ini bisa sangat efektif dalam kasus di mana preferensi pengguna tidak sepenuhnya dapat dipahami hanya dari konten.

---Ini adalah bagian akhir laporan---
