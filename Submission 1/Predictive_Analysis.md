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
 


