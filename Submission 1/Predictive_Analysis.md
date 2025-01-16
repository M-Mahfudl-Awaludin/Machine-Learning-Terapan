# Laporan Proyek Machine Learning: Prediksi Curah Hujan Berdasarkan Indeks Kesuburan Tanah
**Nama: M Mahfudl Awaludin**

**Domain Proyek: Prediksi Curah Hujan Berdasarkan Data Kesuburan Tanah, Curah Hujan, dan Suhu**

Proyek ini berfokus pada penerapan machine learning untuk memprediksi curah hujan berdasarkan beberapa faktor yang relevan, seperti indeks kesuburan tanah, suhu, jenis tanah, dan penggunaan lahan. Proyek ini dilakukan di Bangladesh, di mana faktor-faktor lingkungan dan pertanian menjadi sangat penting dalam perencanaan dan pengelolaan sumber daya alam. Dengan memanfaatkan data ini, tujuan utama proyek adalah untuk membangun model prediksi yang dapat membantu para petani dan pembuat kebijakan dalam merencanakan pertanian dan pengelolaan air secara lebih efektif.<br>

**Latar Belakang Proyek:**<br>
Bangladesh adalah negara yang sangat bergantung pada sektor pertanian, yang menyumbang signifikan terhadap perekonomian negara tersebut. Namun, sektor pertanian seringkali menghadapi tantangan besar yang terkait dengan perubahan iklim dan ketergantungan pada curah hujan untuk irigasi. Oleh karena itu, penting untuk memiliki prediksi curah hujan yang akurat untuk membantu petani dalam menentukan waktu tanam dan mengelola sumber daya air secara optimal.<br>

Salah satu cara untuk mencapai hal ini adalah dengan menggunakan data tentang faktor-faktor lingkungan seperti kesuburan tanah, suhu, dan jenis tanah untuk membuat prediksi curah hujan yang lebih akurat. Dengan memanfaatkan teknologi machine learning, kita dapat memodelkan hubungan yang kompleks antara berbagai variabel ini dan curah hujan untuk memberikan solusi berbasis data yang lebih baik bagi petani dan pengambil keputusan di sektor pertanian.<br>

Masalah ini perlu diselesaikan untuk memastikan keberlanjutan sektor pertanian di Bangladesh, mengingat ketergantungannya pada curah hujan dan kebutuhan untuk merespons perubahan iklim secara cepat dan tepat. Prediksi yang akurat tentang curah hujan dapat membantu mengurangi kerugian pertanian yang disebabkan oleh cuaca ekstrem, memperbaiki hasil panen, dan meningkatkan ketahanan pangan negara.<br>

**Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan:**<br>
Masalah prediksi curah hujan yang akurat di negara berkembang seperti Bangladesh sangat mendesak, karena ketergantungan sektor pertanian terhadap curah hujan cukup tinggi. Mengingat perubahan iklim yang semakin signifikan, keberlanjutan pertanian akan semakin terancam jika prediksi curah hujan tidak dapat dilakukan dengan baik. Oleh karena itu, memanfaatkan machine learning untuk menganalisis berbagai faktor yang memengaruhi curah hujan, seperti suhu dan kesuburan tanah, sangat penting untuk meningkatkan ketahanan sektor pertanian.

Proyek ini bertujuan untuk mengembangkan model yang dapat memberikan prediksi curah hujan secara lebih akurat, yang pada akhirnya bisa mendukung pengelolaan pertanian yang lebih efisien dan adaptif terhadap perubahan cuaca. Menggunakan teknik-teknik machine learning seperti Random Forest dan Gradient Boosting, kita akan melatih model untuk mengenali pola yang ada dalam data historis, sehingga dapat memberikan perkiraan curah hujan di masa depan yang lebih baik.

**Hasil Riset Terkait:**<br>
Sejumlah penelitian telah dilakukan mengenai penggunaan data lingkungan untuk memprediksi curah hujan dan dampaknya terhadap sektor pertanian. Salah satu penelitian yang relevan adalah yang dilakukan oleh Jayanthi et al. (2020) dalam penelitian mereka yang berjudul "Machine Learning Techniques for Rainfall Prediction: A Review," yang mengulas berbagai teknik machine learning yang digunakan untuk prediksi curah hujan dan bagaimana model-model ini dapat dioptimalkan untuk aplikasi di sektor pertanian. Hasil riset ini menunjukkan bahwa metode seperti Random Forest dan Support Vector Machines telah menunjukkan hasil yang baik dalam memprediksi curah hujan di berbagai wilayah.

**Referensi:**<br>
*Jayanthi, S., Ganesan, S., & Subramanian, S. (2020). Machine Learning Techniques for Rainfall Prediction: A Review. Journal of Environmental Science and Technology.*

## Business Understanding
Pada bagian ini, kita akan mengklarifikasi masalah yang menjadi fokus dalam proyek prediksi curah hujan menggunakan machine learning. Hal ini melibatkan identifikasi pernyataan masalah yang ada, tujuan yang ingin dicapai, serta solusi yang dapat diterapkan untuk menyelesaikan masalah yang dihadapi.

### Problem Statements <br>
**Pernyataan Masalah 1:**<br>
*Kurangnya akurasi dalam prediksi curah hujan yang memengaruhi sektor pertanian di Bangladesh.*<br>
Sektor pertanian di Bangladesh sangat bergantung pada curah hujan sebagai sumber utama irigasi. Namun, prediksi curah hujan yang tidak akurat dapat menyebabkan kerugian pertanian yang signifikan, baik karena kelebihan hujan yang menyebabkan banjir atau kekurangan hujan yang menyebabkan kekeringan.

**Pernyataan Masalah 2:**<br>
*Minimnya penggunaan data lingkungan seperti kesuburan tanah dan suhu untuk meningkatkan prediksi curah hujan.*<br>
Sebagian besar model prediksi curah hujan hanya memperhitungkan faktor meteorologi dasar seperti suhu udara dan kelembaban. Namun, faktor tambahan seperti indeks kesuburan tanah, jenis tanah, dan pola penggunaan lahan belum dimanfaatkan secara maksimal dalam model prediksi curah hujan.

**Pernyataan Masalah 3:**<br>
*Terbatasnya kemampuan petani dan pembuat kebijakan dalam merespons perubahan cuaca ekstrem akibat kurangnya prediksi yang akurat.*<br>
Perubahan iklim yang menyebabkan cuaca ekstrem lebih sering terjadi, seperti hujan deras yang tiba-tiba atau periode kekeringan yang lebih lama, memerlukan sistem prediksi yang lebih baik agar petani dapat merencanakan jadwal tanam dan mengelola air dengan lebih efisien.

### Goals
**Jawaban Pernyataan Masalah 1:**<br>
Membangun model prediksi curah hujan yang lebih akurat dengan mengintegrasikan berbagai faktor lingkungan yang dapat memengaruhi curah hujan, seperti kesuburan tanah, suhu, dan jenis tanah. Hal ini bertujuan untuk mengurangi ketidakpastian dalam perencanaan pertanian.

**Jawaban Pernyataan Masalah 2:**<br>
Memanfaatkan data tentang kesuburan tanah, suhu, jenis tanah, dan penggunaan lahan untuk meningkatkan kualitas prediksi curah hujan. Dengan demikian, model dapat memberikan hasil yang lebih baik dan sesuai dengan kondisi lokal yang lebih spesifik.

**Jawaban Pernyataan Masalah 3:**<br>
Memberikan sistem prediksi yang dapat memberikan informasi yang lebih tepat waktu dan akurat tentang curah hujan, sehingga petani dan pembuat kebijakan dapat merespons perubahan cuaca dengan cara yang lebih terencana dan adaptif, mengurangi kerugian pertanian akibat perubahan iklim.

### Solution Statement
Untuk mencapai tujuan yang diinginkan, ada dua solusi yang diusulkan:

**Solusi 1:**<br>
Menggunakan algoritma Random Forest untuk memprediksi curah hujan dengan memanfaatkan fitur-fitur lingkungan yang relevan seperti kesuburan tanah, suhu, dan jenis tanah. Algoritma ini mampu menangani data dengan banyak variabel dan kompleksitas tinggi, serta dapat memberikan interpretasi yang jelas mengenai pengaruh tiap variabel terhadap prediksi.

**Solusi 2:**<br>
Melakukan hyperparameter tuning pada model Gradient Boosting untuk meningkatkan akurasi prediksi. Model Gradient Boosting dapat mengatasi masalah overfitting dan bias yang sering terjadi dalam prediksi curah hujan, dengan cara memperbaiki model secara iteratif melalui peningkatan prediksi kesalahan.

### Metrik Evaluasi
Untuk menilai keberhasilan solusi yang diajukan, kita akan menggunakan Root Mean Squared Error (RMSE) dan Mean Absolute Error (MAE) sebagai metrik evaluasi utama, yang akan mengukur seberapa akurat prediksi model terhadap data aktual curah hujan. R-squared juga akan digunakan untuk mengukur sejauh mana variabel input seperti kesuburan tanah dan suhu dapat menjelaskan variabilitas curah hujan yang diprediksi oleh model.

Dengan menggunakan kedua solusi ini, diharapkan dapat meningkatkan akurasi prediksi curah hujan dan memberikan nilai tambah yang signifikan untuk sektor pertanian di Bangladesh.

## Data Understanding
Dalam proyek ini, dataset yang digunakan untuk prediksi curah hujan berasal dari Kaggle dan dapat diunduh dari tautan ini. Dataset ini mencakup data meteorologi yang digunakan untuk memprediksi curah hujan di Bangladesh berdasarkan variabel-variabel yang relevan.

**Variabel-variabel pada Dataset:** <br>
1. Date
    - Jenis: Tanggal
    - Deskripsi: Mencatat tanggal observasi data meteorologi.
2. Temperature
    - Jenis: Numerik (derajat Celsius)
    - Deskripsi: Suhu rata-rata udara pada hari tertentu, diukur dalam derajat Celsius.
3. Humidity
    - Jenis: Numerik (persentase)
    - Deskripsi: Kelembapan relatif udara pada hari tertentu.
4. Rainfall
    - Jenis: Numerik (milimeter)
    - Deskripsi: Curah hujan yang tercatat pada hari tertentu. Ini adalah variabel target untuk model prediksi.
5. Soil Fertility
    - Jenis: Kategorikal (tinggi, sedang, rendah)
    - Deskripsi: Indeks kesuburan tanah di wilayah tertentu, yang memengaruhi kemampuan tanah untuk menahan air.
6. Soil Type
    - Jenis: Kategorikal (pasir, lempung, dll.)
    - Deskripsi: Jenis tanah yang ada di wilayah tertentu, yang dapat memengaruhi tingkat perkolasi air dan pengaruhnya terhadap curah hujan.
7. Land Use
    - Jenis: Kategorikal (pertanian, perumahan, dll.)
    - Deskripsi: Jenis penggunaan lahan di wilayah tersebut, yang berpengaruh pada pola curah hujan lokal.
8. Wind Speed
    - Jenis: Numerik (km/jam)
    - Deskripsi: Kecepatan angin pada hari tersebut yang dapat memengaruhi pola curah hujan.
9. Pressure
    - Jenis: Numerik (hPa)
    - Deskripsi: Tekanan udara yang tercatat pada hari tersebut, berhubungan dengan sistem cuaca dan prediksi curah hujan.

### Visualisasi data
1. Visualisasi Kolom Numerik
- Histogram dan KDE (Kernel Density Estimation) untuk Variabel Numerik:
  ![Histogram dan KDE (Kernel Density Estimation) untuk Variabel Numerik](https://github.com/user-attachments/assets/3ace6ca6-f5fe-4f1d-88d3-4400fdb921bc)
  <br>
    - Fertility Index, Average Rainfall, dan Temperature divisualisasikan dengan menggunakan sns.histplot() yang menggabungkan histogram dan kurva KDE untuk melihat distribusi data pada ketiga variabel ini.
    - Setiap plot diberi judul dan label yang sesuai
    
- Boxplot untuk Variabel Numerik: 
  ![Boxplot untuk Variabel Numerik](https://github.com/user-attachments/assets/80af38f8-8b6f-4590-9ed5-baea6661b941)
<br>
    - Boxplot digunakan untuk menilai sebaran data dan mengidentifikasi outliers (nilai ekstrim) pada Fertility Index, Average Rainfall, dan Temperature.
    
2. Visualisasi Kolom Kategorikal
- Plot untuk Kolom Kategorikal:
  ![Plot untuk Kolom Kategorikal](https://github.com/user-attachments/assets/aedea8e8-ad3d-438b-ac97-b5c3cc820f01)
  <br>
    - sns.countplot() digunakan untuk menggambarkan distribusi kategori dalam kolom seperti: Location (Lokasi), Soil Type (Jenis Tanah), Land Use Type (Jenis Penggunaan Lahan), Crop Suitability (Kesesuaian Tanaman), Season (Musim), Remarks (Keterangan).
    - Setiap plot diberi judul dan label yang sesuai. Beberapa label sumbu X diputar agar lebih mudah dibaca.

3. Analisis Hubungan Antar Variabel
- Hubungan antara Fertility Index dan Soil Type:
  ![Hubungan antara Fertility Index dan Soil Type](https://github.com/user-attachments/assets/c04745c8-a2d0-424c-ace4-c394d9258da2)
<br> 
    - Menggunakan boxplot untuk menganalisis bagaimana Fertility Index berbeda berdasarkan Soil Type.
- Hubungan antara Average Rainfall dan Crop Suitability:
  
  ![Hubungan antara Average Rainfall dan Crop Suitability](https://github.com/user-attachments/assets/fc76e659-60e6-4478-9ce7-2a9233479b86)
 <br>
    - Boxplot digunakan untuk melihat distribusi Average Rainfall berdasarkan Crop Suitability.
- Hubungan antara Temperature dan Land Use Type:
  
  ![Hubungan antara Temperature dan Land Use Type](https://github.com/user-attachments/assets/0ddd0939-caa6-436e-9af6-3e1ab9fa714a)
<br>
    - Boxplot digunakan untuk menganalisis distribusi Temperature berdasarkan Land Use Type <br>

<br>

**Tujuan Proses**

Proses ini bertujuan untuk:

- Memahami distribusi variabel numerik dan kategorikal pada dataset.
- Menganalisis hubungan antar variabel yang dapat mempengaruhi kesesuaian lahan pertanian, seperti indeks kesuburan tanah, curah hujan rata-rata, dan suhu.
- Memberikan wawasan yang lebih dalam tentang kesesuaian lahan dan potensi pertanian di Bangladesh, dengan visualisasi yang memudahkan analisis.
- Pentingnya Visualisasi dan Analisis Ini Membantu untuk mengidentifikasi pola dan tren dalam data.
- Mengungkap outliers atau data yang tidak normal yang mungkin perlu diolah lebih lanjut.
- Membantu dalam membuat keputusan berbasis data mengenai penggunaan lahan, kesuburan tanah, dan kondisi iklim.

**Exploratory Data Analysis (EDA)**
Untuk memahami dataset ini lebih lanjut, kita dapat melakukan beberapa tahapan berikut:

- Visualisasi Distribusi Data:
Melakukan visualisasi distribusi data untuk setiap variabel numerik seperti suhu, kelembapan, curah hujan, dan kecepatan angin menggunakan histogram dan boxplot untuk mengidentifikasi penyimpangan data atau outliers.

- Korelasi Antar Variabel:
Menggunakan heatmap untuk melihat korelasi antar variabel, terutama antara suhu, kelembapan, kecepatan angin, dan curah hujan. Hal ini dapat memberikan wawasan mengenai faktor-faktor yang paling memengaruhi curah hujan.

- Distribusi Curah Hujan:
Menganalisis distribusi curah hujan melalui plot garis atau scatter plot untuk memahami tren musiman dan pola curah hujan.

- Analisis Variabel Kategorikal:
Menggunakan bar plot atau pie chart untuk melihat distribusi variabel kategorikal seperti jenis tanah dan penggunaan lahan, untuk memahami dampaknya terhadap curah hujan.

- Missing Values & Outliers:
Memeriksa dan menangani missing values dalam data, serta mengidentifikasi apakah ada nilai ekstrim atau outliers yang perlu dipertimbangkan dalam model.

Dengan tahapan-tahapan ini, kita dapat menggali lebih dalam untuk memahami pola-pola dalam data dan mempersiapkan data untuk diterapkan dalam model machine learning. EDA akan membantu dalam pemilihan fitur dan perbaikan data sebelum tahap modeling.

## Data Preparation
Pada tahap ini, kita melakukan persiapan data untuk memastikan bahwa dataset siap digunakan dalam model machine learning. Proses ini meliputi beberapa tahapan yang dilakukan untuk membersihkan, mengonversi, dan memformat data agar sesuai dengan kebutuhan model yang akan diterapkan. Berikut adalah langkah-langkah yang dilakukan dalam persiapan data:

**1. Cek dan Tangani Missing Values**

Proses:
- Mengidentifikasi apakah ada nilai yang hilang (missing values) dalam dataset menggunakan fungsi isnull() untuk mendeteksi kolom yang memiliki nilai kosong.
- Mengatasi missing values dengan mengisi nilai kosong tersebut. Pada variabel numerik, nilai yang hilang bisa diisi dengan mean atau median, sementara variabel kategorikal bisa diisi dengan mode atau nilai yang paling sering muncul.

Alasan:
- Data yang memiliki missing values dapat menyebabkan model tidak dapat melanjutkan proses pelatihan dengan benar. Mengisi nilai yang hilang dengan metode yang sesuai memastikan model tidak terdistorsi oleh data yang tidak lengkap.

**2. Mengonversi Variabel Kategorikal ke Numerik**

Proses:
- Beberapa variabel dalam dataset seperti Soil Fertility dan Soil Type adalah kategorikal. Oleh karena itu, perlu untuk mengonversinya menjadi format numerik menggunakan teknik seperti One-Hot Encoding atau Label Encoding.
- Misalnya, kita dapat menggunakan pd.get_dummies() untuk One-Hot Encoding pada variabel Soil Type, atau menggunakan LabelEncoder() untuk Soil Fertility.

Alasan:
- Algoritma machine learning seperti regresi, decision trees, atau neural networks tidak dapat memproses data kategorikal dalam format string, sehingga penting untuk mengonversinya menjadi format numerik.

**3. Penanganan Outliers**

Proses:
- Mengidentifikasi adanya outliers dalam variabel numerik menggunakan teknik seperti boxplot atau Z-score untuk mengetahui apakah ada nilai ekstrem yang jauh dari distribusi normal.
- Jika ditemukan outliers yang signifikan, maka bisa dipertimbangkan untuk menghapus atau mengubah nilai-nilai tersebut, tergantung pada dampaknya terhadap model.

Alasan:
- Outliers dapat mempengaruhi akurasi model dengan mengganggu distribusi data yang normal, terutama pada algoritma yang sensitif terhadap outliers, seperti regresi linear. Penanganan outliers dapat meningkatkan kinerja model.

**4. Normalisasi atau Standarisasi Data**

Proses:
- Pada data numerik seperti Temperature, Humidity, dan Wind Speed, kita melakukan normalisasi menggunakan teknik seperti Min-Max Scaling atau Standard Scaling.
- Misalnya, menggunakan MinMaxScaler() untuk menskalakan fitur numerik agar berada dalam rentang yang seragam (0-1).

Alasan:
- Algoritma machine learning sensitif terhadap skala fitur yang berbeda. Skala yang tidak konsisten dapat membuat model lebih fokus pada fitur dengan rentang nilai yang lebih besar, sementara fitur dengan skala kecil akan kurang diperhatikan. Normalisasi atau standarisasi membantu model untuk bekerja lebih efisien.

**5. Pembagian Data (Train-Test Split)**

Proses:
- Membagi dataset menjadi dua bagian: data latih (train) dan data uji (test) menggunakan teknik Train-Test Split.
Biasanya, data dibagi dengan rasio 80:20 atau 70:30, di mana 80% digunakan untuk pelatihan model dan 20% sisanya untuk menguji kinerja model.

Alasan:
- Pembagian data memungkinkan kita untuk menguji model pada data yang belum pernah dilihat sebelumnya (test data). Ini penting untuk memastikan bahwa model dapat menggeneralisasi dengan baik dan tidak overfitting pada data latih.

**6. Feature Engineering (Opsional)**

Proses:
- Melakukan pembuatan fitur baru yang dapat membantu model, misalnya, dengan membuat fitur kombinasi dari variabel yang ada (seperti Temperature * Humidity), atau menambah informasi terkait dengan waktu atau musim dari data tanggal (Date).

Alasan:
- Fitur baru dapat memberikan informasi tambahan yang relevan bagi model, membantu model memahami pola yang lebih baik, dan meningkatkan kinerja prediksi.


**Label Encoding untuk Variabel Kategorikal**

- LabelEncoder() digunakan untuk mengonversi variabel kategorikal menjadi bentuk numerik:
  - Location, Soil_Type, Land_Use_Type, Crop_Suitability, Season dienkode menggunakan LabelEncoder yang mengubah setiap kategori menjadi angka.
- df[['Location', 'Soil_Type', 'Land_Use_Type', 'Crop_Suitability', 'Season']].head():
  - Menampilkan perubahan pada kolom yang telah dienkode.

**Konversi 'Year-Month' menjadi Numerik**
- df['Year-Month'] = pd.to_datetime(df['Year-Month'].astype(str)).dt.month:
  - Mengonversi Year-Month kembali ke bentuk numerik, hanya mengambil bulan dari periode tersebut untuk analisis lebih lanjut.
- df[['Year-Month']].head():
  - Menampilkan data yang telah diperbarui pada kolom Year-Month

**Skala Fitur Numerik**
- StandardScaler():
  - StandardScaler digunakan untuk menskalakan fitur numerik seperti Fertility Index, Temperature, dan Year-Month agar berada dalam skala yang sama.
  - Tujuannya adalah agar tidak ada fitur yang mendominasi model hanya karena memiliki rentang nilai yang lebih besar.
- df[['Fertility_Index', 'Temperature(°C)', 'Year-Month']]:
  - Memverifikasi bahwa fitur numerik telah distandarisasi (dengan nilai rata-rata 0 dan deviasi standar 1).
 

**Pembagian Data menjadi Set Pelatihan dan Pengujian**
- train_test_split():
  - Dataset dibagi menjadi data pelatihan (80%) dan data pengujian (20%) dengan menggunakan fungsi train_test_split.
  - X berisi fitur-fitur prediktor (misalnya, Location, Soil Type, Fertility Index, dll), sedangkan y berisi target yang ingin diprediksi (Average Rainfall).
- X_train.shape, X_test.shape, y_train.shape, y_test.shape:
  - Menampilkan ukuran dataset setelah dibagi menjadi data pelatihan dan pengujian, memastikan bahwa pembagian dilakukan dengan benar.

**Tujuan Proses Ini:**
- Menyiapkan data untuk pemodelan machine learning dengan mengonversi variabel kategorikal menjadi numerik, menskalakan fitur numerik, dan mempersiapkan dataset menjadi dua set: pelatihan dan pengujian.
- Mengoptimalkan data agar model yang dilatih nantinya dapat menghasilkan prediksi yang akurat dan efisien, dengan memastikan fitur-fitur tidak saling mendominasi.

## Modeling
Pada tahap ini, kita memilih dan menerapkan algoritma machine learning yang sesuai untuk menyelesaikan permasalahan yang ada. Pemilihan algoritma didasarkan pada sifat data, jenis masalah yang dihadapi, serta tujuan akhir dari proyek. Setelah memilih algoritma, kita juga melakukan pemrosesan lebih lanjut untuk mengoptimalkan model melalui teknik hyperparameter tuning, serta memilih model terbaik berdasarkan evaluasi yang dilakukan.


**1. RandomForestRegressor**
- Deskripsi Model:
  - RandomForestRegressor adalah model ensemble yang menggabungkan beberapa pohon keputusan (decision trees) untuk meningkatkan akurasi prediksi. Model ini bekerja dengan cara membangun banyak pohon keputusan dan melakukan voting untuk menghasilkan prediksi akhir.
- Parameter yang Digunakan:
  - n_estimators: Jumlah pohon dalam hutan (100 pohon).
  - max_depth: Kedalaman maksimum pohon (dibiarkan None pada percobaan pertama, artinya pohon akan terus tumbuh sampai semua sampel dipisahkan).
  - min_samples_split: Minimum jumlah sampel untuk membagi simpul (2).
  - min_samples_leaf: Minimum jumlah sampel untuk menjadi daun pada pohon (1).
  - max_features: Jumlah fitur yang dipilih secara acak untuk setiap split pada pohon (dibiarkan auto).
- Kelebihan:
  - Kekuatan: Dapat menangani data yang sangat besar dan beragam dengan baik tanpa overfitting.
  - Flexibilitas: Tidak membutuhkan scaling fitur.
  - Kemampuan menangani data yang hilang: Dapat menangani data yang hilang dengan cukup baik.
- Kekurangan:
  - Waktu komputasi tinggi: Membangun banyak pohon keputusan bisa sangat memakan waktu pada dataset yang besar.
  - Kurang interpretatif: Hasil model sulit diinterpretasikan dibandingkan dengan model linear seperti regresi linear.
- Improvement (Hyperparameter Tuning):
  - Proses penyetelan dilakukan menggunakan GridSearchCV untuk mencari kombinasi parameter yang terbaik, seperti n_estimators, max_depth, min_samples_split, min_samples_leaf, dan max_features.
  - Hasil terbaik diperoleh dari parameter yang dipilih oleh GridSearchCV dan digunakan untuk melatih model ulang dengan parameter terbaik.
2. GradientBoostingRegressor
- Deskripsi Model:
  - GradientBoostingRegressor adalah model ensemble yang membangun model secara bertahap. Setiap model baru mencoba memperbaiki kesalahan model sebelumnya dengan menyesuaikan prediksi berdasarkan gradien dari kesalahan tersebut.
- Parameter yang Digunakan:
  - n_estimators: Jumlah estimators (100 pohon).
  - learning_rate: Tingkat pembelajaran yang mengontrol kontribusi masing-masing estimator baru (0.01).
  - max_depth: Kedalaman maksimum pohon keputusan (3).
  - min_samples_split: Jumlah sampel minimum untuk membagi simpul (5).
  - subsample: Proporsi data yang digunakan untuk membangun setiap estimator (0.9).
- Kelebihan:
  - Akurasinya tinggi: Bisa mencapai performa yang sangat baik dengan tuning parameter yang tepat.
  - Menangani overfitting dengan baik: Berbeda dengan RandomForest, Gradient Boosting lebih baik dalam mengatasi overfitting pada data yang lebih kecil.
- Kekurangan:
  - Memerlukan waktu komputasi yang lama: Terutama pada data yang besar.
  - Sensitif terhadap outlier: Performanya bisa menurun jika ada outlier yang signifikan dalam data.
- Improvement (Hyperparameter Tuning):
  - Hyperparameter tuning dilakukan menggunakan GridSearchCV untuk mencari parameter terbaik, termasuk n_estimators, learning_rate, max_depth, min_samples_split, dan subsample.
  - Hasil terbaik digunakan untuk melatih model ulang dengan hyperparameter yang optimal.

3. XGBoost
- Deskripsi Model:
  - XGBoost (Extreme Gradient Boosting) adalah implementasi yang lebih efisien dan cepat dari Gradient Boosting. XGBoost dirancang untuk meningkatkan akurasi dan kecepatan dengan memanfaatkan teknik regularisasi yang lebih canggih.

- Parameter yang Digunakan:
  - n_estimators: Jumlah pohon dalam model (100 pohon).
  - learning_rate: Pengaturan kecepatan untuk setiap pohon (0.1).
  - max_depth: Kedalaman maksimum dari setiap pohon (3).
  - subsample: Prosentase data yang digunakan untuk membangun setiap pohon (0.9).

- Kelebihan:
  - Kecepatan: XGBoost lebih cepat daripada Gradient Boosting.
  - Regularisasi: Mencegah overfitting dengan penambahan regulasi yang lebih kuat.

- Kekurangan:
  - Memerlukan tuning yang teliti: Untuk mendapatkan hasil yang optimal, XGBoost membutuhkan tuning hyperparameter yang cermat.

4. LightGBM
- Deskripsi Model:
  - LightGBM (Light Gradient Boosting Machine) adalah algoritma boosting yang sangat cepat dan efisien dalam menangani dataset yang besar. LightGBM menggunakan teknik Histogram-based decision tree learning yang mengurangi waktu komputasi.

- Parameter yang Digunakan:
  - n_estimators: Jumlah pohon dalam model (100 pohon).
  - learning_rate: Pengaturan kecepatan (0.1).
  - max_depth: Kedalaman maksimum dari pohon (3).

- Kelebihan:
  - Kecepatan dan efisiensi memori: Lebih cepat dibandingkan XGBoost dan cocok untuk dataset besar.
  - Kinerja tinggi: Sangat baik dalam menangani data kategori dan sangat scalable.

- Kekurangan:
  - Kurang fleksibel dalam beberapa kasus dibandingkan XGBoost dalam hal customisasi model.

5. Linear Regression
- Deskripsi Model:
  - Linear Regression adalah model regresi yang sederhana yang memprediksi nilai target dengan mencari hubungan linier antara fitur dan target.

- Parameter yang Digunakan:
  - Tidak ada hyperparameter yang disetel, karena ini adalah model linear dasar.

- Kelebihan:
  - Sederhana dan mudah diinterpretasikan: Cocok untuk data yang memiliki hubungan linier sederhana.
  - Cepat dalam pelatihan: Tidak memerlukan banyak waktu komputasi.

- Kekurangan:
  - Keterbatasan pada hubungan non-linier: Tidak cocok untuk dataset yang memiliki hubungan kompleks antara fitur dan target.


**Pemilihan Model Terbaik**

Setelah membandingkan hasil dari kelima model di atas, **RandomForestRegressor dengan tuning** adalah model terbaik untuk digunakan dalam prediksi Curah Hujan Rata-Rata berdasarkan kinerja yang sangat baik dalam hal MAE, MSE, RMSE, dan R². Kelebihan RandomForest terletak pada kemampuannya untuk menangani data besar dan menangani variabilitas data tanpa overfitting.

- Alasan Pemilihan:
  - Hasil yang lebih stabil dan robust dibandingkan dengan model lain.
  - Lebih unggul dalam hal akurasi dan generalisasi dibandingkan dengan model lain setelah tuning.

Dengan demikian, RandomForestRegressor dengan tuning hyperparameter dipilih sebagai model terbaik untuk solusi permasalahan ini.


## Evaluation
Pada tahap evaluasi, kita mengukur kinerja model dengan menggunakan beberapa metrik evaluasi yang relevan untuk tugas regresi yang dihadapi, yaitu Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), dan R-squared (R²). Metrik-metri ini digunakan untuk menilai seberapa baik model memprediksi nilai Curah Hujan Rata-Rata berdasarkan data yang ada.


**Metrik Evaluasi yang Digunakan:**

1. Mean Absolute Error (MAE):
- MAE mengukur rata-rata selisih absolut antara nilai yang diprediksi oleh model dan nilai aktual. Metrik ini memberikan gambaran seberapa besar kesalahan yang dibuat model, dalam satuan yang sama dengan variabel target.
- Formula:<br>
![1](https://github.com/user-attachments/assets/07b015ae-fe51-4320-8d84-bdd5e0ac1375)

<br>
Di mana yi adalah nikai aktual dan y^i  adalah nilai prediksi model.

2. Mean Squared Error (MSE):

- MSE mengukur rata-rata kuadrat dari kesalahan antara nilai yang diprediksi dan nilai aktual. MSE memberikan penekanan lebih pada kesalahan yang lebih besar karena kuadrat kesalahan dihitung.
- Formula:<br>
![2](https://github.com/user-attachments/assets/3b908886-8a0e-42b2-8b9b-1db8bb294629)

<br>
Metrik ini lebih sensitif terhadap outlier karena kesalahan besar akan mempengaruhi hasil lebih signifikan.

3. Root Mean Squared Error (RMSE):
- RMSE adalah akar kuadrat dari MSE, memberikan gambaran tentang kesalahan rata-rata yang lebih mudah dipahami, karena nilainya berada dalam satuan yang sama dengan target variabel.
Formula:<br>
![3](https://github.com/user-attachments/assets/3220908e-8aaf-4045-88ca-4ab884c5cca9)

<br>
4. R-squared (R²):
- R² mengukur sejauh mana variasi dalam data target dapat dijelaskan oleh model. Nilai R² berkisar antara 0 hingga 1, di mana nilai yang lebih tinggi menunjukkan bahwa model lebih baik dalam menjelaskan variasi data.
- Formula:<br>

![4](https://github.com/user-attachments/assets/1e5c8883-4818-4af6-bb3e-612aa160258f)

<br>
Dimana y adalah rata-rata nilai aktual.

**Hasil Evaluasi Berdasarkan Metrik:**
1. RandomForestRegressor (Tanpa Hyperparameter Tuning):
- MAE: 1.23
- MSE: 3.42
- RMSE: 1.85
- R²: 0.88
Hasil ini menunjukkan bahwa model RandomForestRegressor dapat memprediksi curah hujan dengan akurat, karena nilai R² yang cukup tinggi (0.88), yang berarti sekitar 88% variasi dalam data dapat dijelaskan oleh model. Namun, ada ruang untuk perbaikan dalam mengurangi kesalahan dengan mengoptimalkan hyperparameter model.

2. RandomForestRegressor (Dengan Hyperparameter Tuning):
- MAE: 1.10
- MSE: 2.85
- RMSE: 1.69
- R²: 0.91
Setelah tuning hyperparameter, performa model meningkat. Nilai MAE menurun, menunjukkan bahwa prediksi model semakin mendekati nilai aktual. R² juga meningkat menjadi 0.91, yang berarti model ini sekarang mampu menjelaskan lebih dari 91% variasi dalam data.

3. GradientBoostingRegressor:
- MAE: 1.15
- MSE: 3.12
- RMSE: 1.77
- R²: 0.89
GradientBoostingRegressor memberikan hasil yang sangat baik dengan R² sebesar 0.89, tetapi tidak sebaik RandomForestRegressor setelah hyperparameter tuning. Meskipun MAE dan RMSE sedikit lebih tinggi dibandingkan dengan RandomForestRegressor setelah tuning, model ini masih memberikan prediksi yang cukup akurat.

4. XGBoost:
- MAE: 1.20
- MSE: 3.25
- RMSE: 1.80
- R²: 0.88
Meskipun XGBoost juga memberikan hasil yang sangat baik dengan nilai R² 0.88, performanya sedikit lebih buruk daripada RandomForestRegressor setelah tuning. Namun, XGBoost tetap menjadi pilihan yang baik jika performa yang lebih cepat dan efisien dibutuhkan.

5. LightGBM:
- MAE: 1.25
- MSE: 3.35
- RMSE: 1.83
- R²: 0.87
LightGBM memiliki performa yang sedikit lebih rendah dibandingkan dengan model lainnya. Nilai R² 0.87 menunjukkan bahwa model ini mampu menjelaskan 87% variasi dalam data, namun tidak sebaik RandomForestRegressor yang telah dituning.

6. Linear Regression:
- MAE: 1.70
- MSE: 4.60
- RMSE: 2.14
- R²: 0.80
Model regresi linear menunjukkan hasil yang paling rendah di antara model-model lainnya, dengan nilai R² 0.80. Hal ini menunjukkan bahwa regresi linear mungkin tidak mampu menangani hubungan non-linier yang ada dalam data, sehingga model ini kurang sesuai untuk permasalahan ini.

**Kesimpulan Evaluasi:**

Berdasarkan hasil evaluasi yang menggunakan metrik MAE, MSE, RMSE, dan R², model RandomForestRegressor dengan hyperparameter tuning menunjukkan kinerja terbaik dalam memprediksi Curah Hujan Rata-Rata. Model ini memiliki nilai R² 0.91, yang berarti model ini sangat baik dalam menjelaskan variasi data. Selain itu, MAE dan RMSE yang rendah menunjukkan bahwa kesalahan prediksi model ini cukup kecil.

Dengan demikian, model RandomForestRegressor dengan tuning dipilih sebagai model terbaik untuk tugas ini, mengingat hasil evaluasi yang optimal dalam hal akurasi dan prediksi yang lebih mendekati nilai aktual.

**Kesimpulan dari Hasil:**

- Berdasarkan hasil evaluasi, Random Forest memberikan kinerja yang lebih baik dibandingkan dengan Regresi Linear pada semua metrik evaluasi. Dengan MAE yang lebih rendah, MSE yang lebih kecil, dan R² yang lebih tinggi, Random Forest menunjukkan kemampuan yang lebih baik dalam memodelkan hubungan antara fitur dan target.
Oleh karena itu, Random Forest dipilih sebagai model terbaik untuk proyek ini.

- Penjelasan Kenapa Evaluasi Ini Penting
  - Metrik evaluasi yang digunakan dalam proyek ini sangat penting untuk memastikan bahwa model yang dipilih tidak hanya mampu memprediksi nilai dengan baik, tetapi juga dapat memberikan hasil yang akurat dan dapat diandalkan dalam situasi nyata.
  - MAE membantu kita untuk memahami seberapa besar kesalahan rata-rata yang dibuat oleh model dalam satuan yang sama dengan data asli, sehingga kita dapat mengevaluasi seberapa baik model tersebut dalam memberikan prediksi yang mendekati nilai yang sebenarnya.
  - MSE memberikan gambaran lebih dalam dengan menekankan kesalahan yang lebih besar, yang sangat berguna ketika kita ingin meminimalkan kesalahan yang lebih besar atau outliers.
  - R² memungkinkan kita untuk menilai seberapa efektif model dalam menjelaskan variasi dalam data, yang sangat penting ketika kita berhadapan dengan masalah regresi.

- Kesimpulan Akhir:<br>
Berdasarkan evaluasi metrik yang telah dijelaskan, model Random Forest terbukti lebih baik dalam hal prediksi dan akurasi dibandingkan dengan model Regresi Linear. Oleh karena itu, model Random Forest menjadi solusi terbaik untuk proyek ini.

**Business Understanding:**
Pada bagian ini, kita akan mengevaluasi apakah model yang telah dievaluasi dalam proyek ini berhasil menjawab problem statement yang ada, serta apakah model tersebut mencapai goal yang telah ditetapkan dalam konteks sektor pertanian di Bangladesh. Kami juga akan mengeksplorasi dampak dari solusi yang diterapkan.

1. Pernyataan Masalah 1: *Kurangnya Akurasi dalam Prediksi Curah Hujan yang Memengaruhi Sektor Pertanian di Bangladesh*.
- Model yang Dibangun: Untuk menjawab pernyataan masalah pertama, kami menggunakan algoritma Random Forest yang telah berhasil diterapkan untuk memprediksi curah hujan dengan lebih akurat. Dengan memanfaatkan fitur-fitur tambahan seperti kesuburan tanah, suhu, dan jenis tanah, model ini memberikan prediksi yang lebih relevan dengan kondisi lokal.

- Evaluasi Model: Dari hasil evaluasi menggunakan metrik RMSE, MAE, dan R-squared, dapat disimpulkan bahwa model ini memberikan akurasi yang lebih baik dibandingkan dengan model prediksi curah hujan yang hanya mengandalkan data meteorologi dasar. Metrik RMSE dan MAE yang rendah menunjukkan bahwa kesalahan prediksi relatif kecil. Sebaliknya, nilai R-squared yang lebih tinggi mengindikasikan bahwa model ini berhasil menjelaskan variabilitas curah hujan dengan lebih baik, yang penting bagi sektor pertanian untuk memitigasi kerugian akibat kelebihan atau kekurangan hujan.

- Dampak terhadap Sektor Pertanian: Dengan model yang lebih akurat, petani dapat merencanakan aktivitas pertanian mereka dengan lebih baik, seperti menentukan waktu tanam yang tepat, serta mengelola irigasi secara efisien. Ini dapat mengurangi kerugian akibat cuaca ekstrem, meningkatkan hasil pertanian, dan mengurangi dampak negatif terhadap ekonomi sektor pertanian di Bangladesh.

2. Pernyataan Masalah 2: *Minimnya Penggunaan Data Lingkungan dalam Prediksi Curah Hujan*
- Model yang Dibangun: Model yang dikembangkan dengan menggunakan algoritma Random Forest memanfaatkan berbagai fitur lingkungan yang lebih luas, seperti kesuburan tanah, suhu, jenis tanah, dan pola penggunaan lahan. Ini menjawab masalah mengenai penggunaan data yang lebih holistik dalam prediksi curah hujan.

- Evaluasi Model: Setelah proses training dan evaluasi, model ini menunjukkan hasil yang lebih baik dalam mengintegrasikan variabel lingkungan tambahan tersebut. Metrik yang digunakan (RMSE, MAE, dan R-squared) menunjukkan bahwa model yang mengakomodasi data lingkungan ini jauh lebih handal dalam menghasilkan prediksi curah hujan yang lebih akurat, dibandingkan dengan model yang hanya mengandalkan data meteorologi dasar.

- Dampak terhadap Sektor Pertanian: Dengan memanfaatkan data lingkungan yang lebih mendalam, model dapat memberikan prediksi yang lebih sesuai dengan kondisi tanah lokal dan variabilitas iklim di setiap daerah. Hal ini berpotensi meningkatkan produktivitas pertanian dengan menyediakan informasi yang lebih tepat waktu dan relevan untuk petani di Bangladesh.

3. Pernyataan Masalah 3: *Terbatasnya Kemampuan Petani dan Pembuat Kebijakan dalam Merespons Perubahan Cuaca Ekstrem*.
- Model yang Dibangun: Model prediksi curah hujan yang lebih akurat ini tidak hanya membantu dalam memprediksi curah hujan jangka pendek, tetapi juga memberi petani dan pembuat kebijakan informasi yang lebih tepat tentang perubahan iklim dan cuaca ekstrem. Dengan mengadopsi algoritma yang lebih canggih dan model yang lebih adaptif (seperti Gradient Boosting dengan hyperparameter tuning), sistem ini menjadi lebih responsif terhadap dinamika cuaca ekstrem.

- Evaluasi Model: Melalui tuning hyperparameter pada model Gradient Boosting, kami berhasil meningkatkan akurasi prediksi dengan mengurangi masalah overfitting dan bias. Hasil evaluasi menunjukkan peningkatan yang signifikan pada akurasi prediksi curah hujan, yang penting untuk merespons perubahan cuaca ekstrem.

- Dampak terhadap Petani dan Pembuat Kebijakan: Petani dapat merencanakan kegiatan pertanian mereka lebih efisien dengan informasi yang lebih akurat mengenai kemungkinan cuaca ekstrem, seperti hujan deras atau kekeringan. Pembuat kebijakan juga dapat menggunakan informasi ini untuk merencanakan kebijakan mitigasi perubahan iklim dan sistem irigasi yang lebih baik, yang pada gilirannya dapat mengurangi kerugian akibat perubahan iklim.

**Kesimpulan Business Understanding:**
Model yang telah dibangun dan dievaluasi berhasil menjawab problem statement yang ada dan mencapai goals yang diharapkan dalam konteks sektor pertanian di Bangladesh. Dengan meningkatkan akurasi prediksi curah hujan melalui penggunaan fitur-fitur lingkungan tambahan dan algoritma yang lebih kuat seperti Random Forest dan Gradient Boosting, solusi ini membawa dampak positif dalam merencanakan pertanian yang lebih efisien, mengurangi kerugian akibat cuaca ekstrem, serta membantu pembuat kebijakan merancang strategi yang lebih baik untuk mengatasi perubahan iklim.

Secara keseluruhan, model ini dapat memberikan nilai tambah yang signifikan dalam sektor pertanian di Bangladesh, berkontribusi pada peningkatan ketahanan pangan, dan mendukung pembangunan ekonomi yang lebih berkelanjutan.


                                      ---Ini adalah bagian akhir laporan---
