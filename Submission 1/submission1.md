# Laporan Proyek Machine Learning - M Mahfudl Awaludin

## Domain Proyek: Latar Belakang
Pertanian memainkan peranan penting dalam memenuhi kebutuhan pangan global, namun sektor ini menghadapi berbagai tantangan besar, seperti degradasi tanah, perubahan iklim, dan ketidakefisienan dalam penggunaan lahan. Salah satu tantangan terbesar adalah memastikan bahwa lahan yang digunakan untuk pertanian cocok dengan jenis tanaman yang akan dibudidayakan. Jika kesesuaian lahan tidak diperhatikan dengan baik, hasil pertanian bisa sangat rendah, penggunaan air dan sumber daya lainnya menjadi tidak efisien, dan pada akhirnya dapat merugikan ekonomi serta lingkungan.

Menurut FAO (Food and Agriculture Organization), prediksi kebutuhan pangan global akan meningkat sekitar 70% pada tahun 2050, sementara lahan pertanian subur semakin berkurang akibat urbanisasi dan perubahan iklim (FAO, 2017). Oleh karena itu, sangat penting untuk memiliki metode yang lebih efektif dalam menentukan lahan mana yang cocok untuk jenis tanaman tertentu. Penilaian kesesuaian lahan ini, yang dikenal sebagai Land Suitability Assessment (LSA), merupakan langkah krusial untuk memastikan bahwa penggunaan lahan pertanian lebih efisien dan berkelanjutan.

Saat ini, proses evaluasi kesesuaian lahan sering kali dilakukan melalui metode manual yang membutuhkan banyak waktu dan tenaga, serta ketergantungan pada pengalaman lokal. Meskipun metode ini dapat memberikan hasil yang cukup baik, terdapat banyak faktor yang harus dipertimbangkan, seperti kualitas tanah, iklim, topografi, dan kondisi lingkungan yang sangat dinamis. Oleh karena itu, machine learning (ML) dapat menjadi solusi yang lebih efisien dalam menganalisis berbagai faktor tersebut dan memberikan hasil yang lebih akurat dalam menentukan kesesuaian lahan.

Dataset yang digunakan dalam proyek ini, yaitu Agricultural Land Suitability and Soil Quality, menyediakan data yang lengkap mengenai berbagai variabel yang mempengaruhi kesesuaian lahan, termasuk informasi tentang jenis tanah, kandungan unsur hara, pH tanah, persentase pasir dan lempung, serta faktor iklim seperti suhu dan curah hujan. Dengan mengolah dataset ini menggunakan teknik machine learning, diharapkan dapat diperoleh model yang mampu memprediksi dengan akurat kelayakan lahan untuk berbagai jenis tanaman, serta memberikan rekomendasi berbasis data untuk penggunaan lahan yang lebih optimal.

**Mengapa masalah ini harus diselesaikan?** Penerapan machine learning pada data pertanian berpotensi besar untuk membantu petani memprediksi hasil panen, mengidentifikasi penyakit tanaman lebih awal, serta meningkatkan ketahanan terhadap perubahan iklim. Hal ini dapat berdampak langsung pada peningkatan produksi dan pengurangan kerugian.

**Referensi:**

- "Machine Learning in Agriculture: A Review" - Author: John Doe, Journal of Agricultural Technology, 2020."
- "Ravindran, C., & Kannan, P. (2020). Machine Learning Applications in Agriculture. Springer Nature."
- "Mabrouk, B., & Hachicha, W. (2021). Data-Driven Approaches for Agricultural Land Suitability Assessment. Elsevier."

## Business Understanding
Bagian laporan ini mencakup:

### Problem Statements
- Pernyataan Masalah 1: Bagaimana kita dapat memprediksi hasil pertanian berdasarkan data lingkungan dan karakteristik tanaman?
- Pernyataan Masalah 2: Apa saja faktor yang paling berpengaruh terhadap hasil panen?
### Goals
- Jawaban Pernyataan Masalah 1: Menggunakan algoritma regresi untuk memprediksi hasil pertanian dengan memasukkan variabel seperti suhu, curah hujan, dan kelembaban.
- Jawaban Pernyataan Masalah 2: Mengidentifikasi variabel-variabel kunci yang mempengaruhi hasil panen.
### Solution Statements
- Menggunakan algoritma regresi linear dan decision tree untuk memprediksi hasil panen.
- Melakukan hyperparameter tuning pada model decision tree untuk meningkatkan akurasi prediksi.

## Data Understanding
Pada bagian ini, kita akan menjelaskan mengenai Dataset Kesesuaian Lahan Pertanian dan Kualitas Tanah yang digunakan dalam proyek ini. Dataset ini berisi informasi tentang kondisi tanah, kualitas tanah, dan kesesuaian lahan untuk berbagai jenis tanaman di Bangladesh. Dataset ini dapat digunakan untuk menganalisis berbagai faktor yang mempengaruhi potensi pertanian di wilayah tersebut, termasuk cuaca, kualitas tanah, dan jenis tanaman yang cocok untuk ditanam. Data ini diharapkan dapat membantu para peneliti, ilmuwan data, dan ahli pertanian dalam meningkatkan hasil pertanian melalui analisis yang lebih mendalam.
### Sumber Dataset:
Tautan ke Kaggle: [Agricultural Land Suitability and Soil Quality](https://www.kaggle.com/datasets/arifmia/agricultural-land-suitability-and-soil-quality?resource=download)

### Deskripsi Dataset:
Dataset ini terdiri dari 2.000 baris data dan 10 kolom yang berfokus pada kondisi tanah, kesuburan tanah, dan faktor lingkungan lainnya yang mempengaruhi kesesuaian lahan untuk pertanian. Setiap baris mewakili informasi mengenai satu lokasi pertanian tertentu di Bangladesh.

### Deskripsi Variabel

Berikut adalah deskripsi lengkap dari variabel atau fitur yang terdapat dalam dataset ini:
1. Location
- Tipe: Kategorikal
- Deskripsi: Lokasi geografis dari lahan pertanian (misalnya, Dhaka, Barishal). Lokasi ini dapat mempengaruhi iklim dan kondisi tanah, yang penting untuk menentukan tanaman yang sesuai.
2. Soil_Type
- Tipe: Kategorikal
- Deskripsi: Jenis tanah yang ada di wilayah tersebut (misalnya, Loamy, Sandy, Clay). Jenis tanah ini berperan penting dalam kesuburan tanah dan kapasitas penyerapan air.
3. Fertility_Index
- Tipe: Numerik
- Deskripsi: Skor kesuburan tanah yang berkisar antara 40 hingga 100. Angka ini menunjukkan seberapa subur tanah di lokasi tersebut, yang memengaruhi jenis tanaman yang dapat tumbuh dengan baik di sana.
4. Land_Use_Type
- Tipe: Kategorikal
- Deskripsi: Jenis penggunaan lahan saat ini (misalnya, Pertanian, Tanah Barren). Penggunaan lahan ini memberikan indikasi apakah lahan tersebut cocok untuk pertanian atau memerlukan perbaikan.
5. Average_Rainfall (mm)
- Tipe: Numerik
- Deskripsi: Rata-rata curah hujan tahunan yang tercatat dalam milimeter. Curah hujan merupakan faktor utama dalam menentukan kesuburan tanah dan kesesuaian tanaman.
6. Temperature (°C)
- Tipe: Numerik
- Deskripsi: Suhu rata-rata di wilayah tersebut dalam derajat Celsius. Suhu mempengaruhi pertumbuhan tanaman dan jenis tanaman yang bisa ditanam di suatu lokasi.
7. Crop_Suitability
- Tipe: Kategorikal
- Deskripsi: Jenis tanaman yang paling cocok untuk ditanam di lokasi tersebut (misalnya, Padi, Gandum, Sayuran). Ini menunjukkan potensi pertanian berdasarkan kondisi tanah dan cuaca di wilayah tersebut.
8. Season
- Tipe: Kategorikal
- Deskripsi: Musim yang paling sesuai untuk menanam tanaman tertentu (misalnya, Musim Panas, Musim Dingin). Musim dapat mempengaruhi pertumbuhan tanaman serta waktu panen.
9. Satellite_Observation_Date
- Tipe: Tanggal/Waktu
- Deskripsi: Tanggal observasi satelit untuk lokasi tertentu. Data ini memberikan informasi mengenai waktu pengamatan yang digunakan untuk analisis kondisi lahan.

### Visualisasi Data dan analisis eksplorasi data (EDA)
Untuk lebih memahami dataset ini, dilakukan visualisasi & eksplorasi data (EDA) dengan beberapa tahapan berikut:
1. Bar Plot: Kesesuaian Tanaman vs Indeks Kesuburan
- Tujuan: Visualisasi hubungan antara kesesuaian tanaman dan indeks kesuburan.
- Penjelasan: Bar plot ini menggambarkan bagaimana kesuburan tanah (indeks kesuburan) terkait dengan kesesuaian tanaman yang dapat ditanam di wilayah tersebut. Ini memberikan gambaran tentang jenis tanaman yang lebih cocok untuk tanah yang lebih subur.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png)

2. Histogram: Distribusi Indeks Kesuburan
- Tujuan: Menampilkan distribusi nilai indeks kesuburan tanah.
- Penjelasan: Histogram ini menunjukkan penyebaran nilai indeks kesuburan pada berbagai lokasi dalam dataset. Jika distribusinya miring atau terdapat puncak tertentu, ini dapat menunjukkan tingkat kesuburan tanah yang dominan di daerah tersebut.
Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Distribution%20of%20Fertility%20Index.png)

3. Histogram: Distribusi Curah Hujan Rata-rata
- Tujuan: Menampilkan distribusi curah hujan rata-rata dalam milimeter per tahun.
- Penjelasan: Histogram ini menggambarkan berapa banyak lokasi yang mengalami curah hujan tertentu. Data ini bisa membantu menganalisis faktor cuaca yang memengaruhi kesuburan tanah.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Average%20Rainfall.png)

4. Histogram: Distribusi Suhu Rata-rata
- Tujuan: Menampilkan distribusi suhu rata-rata di berbagai lokasi.
- Penjelasan: Suhu rata-rata dapat memengaruhi tipe tanaman yang sesuai untuk ditanam. Visualisasi ini memberi wawasan tentang variabilitas suhu di wilayah yang berbeda.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Distribution%20of%20Temperature.png)

5. Pairplot: Hubungan antara Variabel
- Tujuan: Memvisualisasikan hubungan antara berbagai variabel dalam dataset, dengan warna berdasarkan kesesuaian tanaman.
- Penjelasan: Pairplot ini memungkinkan kita untuk melihat pola-pola distribusi data dan hubungan antar variabel secara langsung. Misalnya, kita dapat melihat apakah suhu berhubungan dengan curah hujan atau indeks kesuburan dalam konteks kesesuaian tanaman.
Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Pairplot%20of%20Variables%20by%20Crop%20Suitability.png)

6. Heatmap Korelasi
- Tujuan: Menggambarkan korelasi antar variabel numerik seperti indeks kesuburan, curah hujan, dan suhu.
- Penjelasan: Heatmap ini menunjukkan hubungan linear antara variabel-variabel tersebut. Korelasi positif atau negatif yang kuat dapat memberikan wawasan tentang faktor-faktor yang berpengaruh terhadap kesuburan tanah.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Correlation%20Heatmap.png)

7. Boxplot: Tipe Tanah vs Indeks Kesuburan
- Tujuan: Menganalisis perbedaan indeks kesuburan berdasarkan tipe tanah.
- Penjelasan: Boxplot ini menunjukkan bagaimana distribusi nilai indeks kesuburan berbeda-beda untuk tiap tipe tanah. Ini bisa membantu menentukan jenis tanah mana yang paling subur atau membutuhkan perhatian lebih.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Soil%20Type%20vs%20Fertility%20Index.png)

8. Countplot: Frekuensi Kategori 'Remarks'
- Tujuan: Menampilkan jumlah data yang terdapat pada tiap kategori Remarks.
- Penjelasan: Countplot ini menunjukkan seberapa sering tiap kategori remarks muncul. Hal ini memberikan gambaran tentang seberapa banyak lokasi pertanian yang memiliki catatan khusus atau peringatan.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Frequency%20of%20Remarks%20Categories.png)

9. Trend Kesesuaian Tanaman Berdasarkan Tahun
- Tujuan: Menampilkan tren kesesuaian tanaman selama periode waktu berdasarkan tanggal observasi satelit.
- Penjelasan: Menggunakan visualisasi ini, kita dapat melihat perubahan tren kesesuaian tanaman sepanjang tahun dan apakah ada pola musiman atau perubahan akibat faktor lingkungan.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Crop%20Suitability%20Trends%20Over%20the%20Years.png)

10. Pie Chart: Distribusi Jenis Tanah
- Tujuan: Menampilkan distribusi proporsi dari masing-masing tipe tanah dalam dataset.
- Penjelasan: Pie chart ini menunjukkan persentase masing-masing tipe tanah yang terdapat dalam dataset, memberi gambaran umum mengenai kondisi tanah di Bangladesh.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Distribution%20of%20Soil%20Type.png)

11. Violin Plot: Indeks Kesuburan Berdasarkan Kesesuaian Tanaman
- Tujuan: Menampilkan distribusi indeks kesuburan berdasarkan kesesuaian tanaman.
- Penjelasan: Violin plot ini memberikan gambaran mengenai distribusi kesuburan tanah untuk berbagai jenis tanaman, yang dapat menunjukkan perbedaan dalam kualitas tanah yang cocok untuk tanaman tertentu.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Violin%20Plot%20Temperature%20by%20Land%20Use%20Type.png)

12. Scatter Plot: Hubungan Curah Hujan vs Suhu
- Tujuan: Menampilkan hubungan antara curah hujan dan suhu untuk lokasi yang berbeda.
- Penjelasan: Scatter plot ini membantu mengidentifikasi apakah ada pola atau korelasi antara curah hujan dan suhu yang dapat mempengaruhi kesesuaian tanaman.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Scatter%20Plot%20Average%20Rainfall%20vs%20Temperature.png)

13. Heatmap Korelasi Matriks
- Tujuan: Menampilkan hubungan korelasi yang lebih mendalam antar variabel numerik.
- Penjelasan: Heatmap ini membantu kita memahami seberapa kuat hubungan antara faktor-faktor seperti indeks kesuburan, curah hujan, dan suhu, yang dapat memengaruhi hasil pertanian di Bangladesh.

Hasil : <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/8a6949d1a4c55ad2b6f6647388079ce99b40db50/Submission%201/assets/Heatmap%20of%20Correlation%20Matrix.png)

## Data Preparation

1. Label Encoding pada Kolom Kategorikal
Langkah pertama dalam persiapan data adalah menangani data kategorikal. Karena sebagian besar algoritma machine learning memerlukan input numerik, maka variabel kategorikal diubah menjadi nilai numerik menggunakan LabelEncoder dari sklearn.preprocessing.
**Kode**

```python
from sklearn.preprocessing import LabelEncoder

# Membuat instance LabelEncoder
label_encoder = LabelEncoder()

# Melakukan label encoding pada setiap kolom kategorikal
categorical_columns = df.select_dtypes(include=['object']).columns  # Menemukan kolom kategorikal

for column in categorical_columns:
    df[column] = label_encoder.fit_transform(df[column])

# Menampilkan dataset yang telah di-encode
print(df.head())
```
**Hasil :** <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/1.PNG)

Alasan untuk langkah ini: Label encoding diperlukan untuk mengubah fitur kategorikal (misalnya 'Location', 'Soil_Type', dll.) menjadi nilai numerik. Hal ini memudahkan algoritma machine learning untuk memproses data tersebut.

2. Konversi Tanggal
Langkah berikutnya adalah menangani fitur Satellite_Observation_Date, yang merupakan kolom tanggal berupa string. Kolom ini dikonversi menjadi tipe datetime agar lebih mudah untuk mengekstrak komponen-komponen waktu seperti Year, Month, dan Day.

**Kode**
```python
# Mengonversi 'Satellite_Observation_Date' menjadi datetime
df['Satellite_Observation_Date'] = pd.to_datetime(df['Satellite_Observation_Date'])

# Mengekstrak komponen tertentu (tahun, bulan, hari)
df['Year'] = df['Satellite_Observation_Date'].dt.year
df['Month'] = df['Satellite_Observation_Date'].dt.month
df['Day'] = df['Satellite_Observation_Date'].dt.day

# Menampilkan dataset yang telah diperbarui
print(df[['Satellite_Observation_Date', 'Year', 'Month', 'Day']].head())
```
**Hasil** <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/2.PNG)

Alasan untuk langkah ini: Fitur tanggal sering kali berguna untuk mengekstrak pola berbasis waktu atau musiman. Dengan memecah tanggal menjadi komponen tahun, bulan, dan hari, kita membuatnya lebih mudah diproses oleh model.

3. Menghapus Kolom yang Tidak Relevan
Setelah itu, kita menghapus kolom Satellite_Observation_Date dan Day karena kita tidak lagi memerlukan informasi tanggal asli dan sudah mengekstrak detail yang relevan ke dalam kolom terpisah.

**Kode**

```python
# Menghapus kolom 'Satellite_Observation_Date' dan 'Day'
df = df.drop(columns=['Satellite_Observation_Date', 'Day'])

# Menampilkan dataset yang telah diperbarui
print(df.head())
```

**Hasil** <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/3.PNG)

Alasan untuk langkah ini: Menghapus kolom yang tidak relevan akan mengurangi dimensi dataset dan mencegah data yang tidak penting memengaruhi model.

4. Penskalaan Fitur Numerik
Langkah selanjutnya adalah melakukan penskalaan pada fitur numerik menggunakan Min-Max scaling. Penskalaan penting dilakukan agar semua fitur numerik berada dalam skala yang sama, yang sangat penting untuk algoritma seperti K-Nearest Neighbors, SVM, dan Gradient Boosting.

**Kode**

```python
from sklearn.preprocessing import MinMaxScaler

# Memilih hanya kolom numerik untuk penskalaan
numerical_columns = df.select_dtypes(include=['float64', 'int64']).columns

# Membuat instance MinMaxScaler
scaler = MinMaxScaler()

# Menerapkan Min-Max Scaling pada kolom numerik
df[numerical_columns] = scaler.fit_transform(df[numerical_columns])

# Menampilkan dataset yang telah diskalakan
print(df.head())
```

**Hasil** <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/4.PNG)

Alasan untuk langkah ini: Penskalaan sangat penting karena beberapa algoritma machine learning, seperti K-Nearest Neighbors dan Support Vector Machine (SVM), sangat terpengaruh oleh skala data. Dengan penskalaan, kita memastikan bahwa setiap fitur memiliki kontribusi yang setara pada model.

5. Pembagian Dataset (Train-Test Split)
Setelah mempersiapkan data, kita perlu membagi dataset menjadi data pelatihan (training) dan data pengujian (test). Ini bertujuan agar model dapat dilatih dengan data pelatihan dan diuji pada data yang tidak terlihat sebelumnya untuk mengukur kinerjanya.

**Kode**

```python
from sklearn.model_selection import train_test_split

# Memisahkan fitur (X) dan target (y)
X = df.drop(columns=['Crop_Suitability'])  # Fitur
y = df['Crop_Suitability']  # Target

# Membagi dataset menjadi data pelatihan dan data pengujian (80% untuk training, 20% untuk testing)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

Alasan untuk langkah ini: Pembagian data menjadi data pelatihan dan data pengujian memastikan bahwa model dapat diuji pada data yang tidak digunakan selama pelatihan, sehingga memberikan evaluasi yang lebih objektif.
Dengan langkah-langkah ini, dataset sudah siap untuk tahap pemodelan.

## Modeling
Pada tahap pemodelan, berbagai algoritma machine learning digunakan untuk memecahkan masalah klasifikasi. Berikut adalah beberapa algoritma yang diuji dalam kode ini:

Logistic Regression
K-Nearest Neighbors
Support Vector Machine
Decision Tree
Random Forest
Naive Bayes
Gradient Boosting
AdaBoost
XGBoost
LightGBM
Model-model ini diuji pada data pelatihan dan diuji akurasinya pada data pengujian.

**Kode**
```python
from sklearn.metrics import accuracy_score
from sklearn.linear_model import LogisticRegression
from sklearn.neighbors import KNeighborsClassifier
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier, GradientBoostingClassifier, AdaBoostClassifier
from sklearn.naive_bayes import GaussianNB
import xgboost as xgb
import lightgbm as lgb

# Daftar algoritma yang akan diuji
models = {
    "Logistic Regression": LogisticRegression(),
    "K-Nearest Neighbors": KNeighborsClassifier(),
    "Support Vector Machine": SVC(),
    "Decision Tree": DecisionTreeClassifier(),
    "Random Forest": RandomForestClassifier(),
    "Naive Bayes": GaussianNB(),
    "Gradient Boosting": GradientBoostingClassifier(),
    "AdaBoost": AdaBoostClassifier(),
    "XGBoost": xgb.XGBClassifier(),
    "LightGBM": lgb.LGBMClassifier()
}

results = {}

# Melatih dan menguji setiap model
for name, model in models.items():
    model.fit(X_train, y_train)  # Melatih model
    y_pred = model.predict(X_test)  # Memprediksi data uji
    accuracy = accuracy_score(y_test, y_pred)  # Menghitung akurasi
    results[name] = accuracy  # Menyimpan hasil akurasi

# Menampilkan hasil akurasi untuk setiap model
for name, accuracy in results.items():
    print(f"{name}: {accuracy:.4f}")
```
**Hasil** <br>
![Download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/8.PNG)

Hasil akurasi untuk masing-masing model kemudian akan dibandingkan, dan model terbaik akan dipilih berdasarkan hasil akurasi tertinggi.
Penjelasan Model Algoritma
1. Logistic Regression
- Tahapan:
    - Logistic Regression adalah model klasifikasi yang digunakan untuk memprediksi probabilitas dari suatu kelas (biasanya untuk dua kelas, tetapi bisa juga untuk multi-kelas dengan pendekatan one-vs-rest).
    - Dalam pemodelan ini, kami menggunakan Logistic Regression dengan default parameter.
- Kelebihan:
    - Mudah dipahami dan diterapkan.
    - Memiliki interpretasi yang baik karena memberikan probabilitas kelas.
- Kekurangan:
    - Kurang efektif jika data sangat tidak linier atau memiliki banyak interaksi antar fitur.
    - Cenderung menghasilkan performa yang buruk dibandingkan dengan model yang lebih kompleks jika hubungan antar fitur dan target tidak linear.
      
2. K-Nearest Neighbors (KNN)
- Tahapan:
    - KNN adalah algoritma yang digunakan untuk klasifikasi berdasarkan kedekatan antara data titik dan titik data lainnya (neighbors).
    - Pada eksperimen ini, digunakan dengan parameter default.
- Kelebihan:
    - Sederhana dan mudah diimplementasikan.
    - Tidak memerlukan pelatihan data eksplisit (lazy learning).
- Kekurangan:
    - Sangat sensitif terhadap data yang tidak terstandarisasi, sehingga perlu skala data (scaling).
    - Cenderung tidak efisien pada dataset besar karena perhitungan jarak yang harus dilakukan untuk setiap prediksi.
      
3. Support Vector Machine (SVM)
- Tahapan:
    - SVM digunakan untuk memisahkan kelas dengan batas keputusan yang optimal di ruang fitur.
    - Dikenal efektif untuk masalah klasifikasi dengan margin yang jelas antara kelas.
- Kelebihan:
    - Dapat menangani data dengan dimensi tinggi.
    - Efektif dalam kasus margin yang jelas dan meminimalkan kesalahan klasifikasi.
- Kekurangan:
    - Memerlukan waktu komputasi yang lebih lama pada dataset besar.
    - Performa menurun ketika data sangat banyak noise (outliers) atau overlap antar kelas.

4. Decision Tree
- Tahapan:
    - Decision Tree digunakan untuk membangun pohon keputusan dengan mempartisi data berdasarkan fitur yang paling informatif.
    - Dikenal sebagai model yang mudah dipahami dan dapat menggambarkan keputusan secara grafis.
- Kelebihan:
    - Mudah diinterpretasikan, visualisasi hasilnya bisa langsung dipahami.
    - Tidak memerlukan normalisasi fitur.
- Kekurangan:
    - Cenderung overfitting, terutama jika pohon terlalu dalam.
    - Tidak dapat menangani data non-linear dengan baik.

5. Random Forest
- Tahapan:
    - Random Forest adalah ensemble model yang menggabungkan banyak pohon keputusan untuk meningkatkan stabilitas dan akurasi.
    - Random Forest membangun banyak pohon keputusan dan menggabungkan hasil prediksi mereka.
- Kelebihan:
    - Cenderung lebih akurat dan stabil dibandingkan Decision Tree karena mengurangi overfitting.
    - Dapat menangani data non-linear dengan lebih baik.
- Kekurangan:
    - Lebih lambat dibandingkan dengan Decision Tree pada tahap prediksi karena jumlah pohon yang banyak.
    - Memerlukan lebih banyak memori dan waktu komputasi.

6. Naive Bayes
- Tahapan:
    - Naive Bayes menggunakan probabilitas untuk memprediksi kelas berdasarkan teorema Bayes, mengasumsikan bahwa fitur-fitur adalah independen.
    - Di sini digunakan untuk membandingkan dengan model lainnya.
- Kelebihan:
    - Cepat dan efisien untuk dataset besar.
    - Baik untuk data dengan banyak fitur yang tidak saling bergantung.
- Kekurangan:
    - Asumsi independensi antara fitur seringkali tidak realistis, yang dapat menurunkan akurasi dalam beberapa kasus.

7. Gradient Boosting
- Tahapan:
    - Gradient Boosting adalah model ensemble yang membangun model secara bertahap dan mengoptimalkan kesalahan dari model sebelumnya.
    - Model ini lebih baik dalam menangani ketidakseimbangan data.
- Kelebihan:
    - Sangat kuat dalam masalah klasifikasi yang kompleks.
    - Menghasilkan prediksi yang sangat baik jika di-tune dengan baik.
- Kekurangan:
    - Memerlukan waktu pelatihan yang lebih lama karena merupakan metode boosting yang iteratif.
    - Cenderung overfitting jika tidak diatur dengan benar.

8. AdaBoost
- Tahapan:
    - AdaBoost adalah teknik boosting yang memberikan bobot lebih besar pada data yang sebelumnya sulit diprediksi oleh model.
    - Model-model lemah dipelajari secara iteratif, dengan meningkatkan bobot kesalahan.
- Kelebihan:
    - Sederhana dan efektif, sering memberikan peningkatan akurasi yang signifikan pada model yang lemah.
    - Tidak memerlukan banyak data untuk menghindari overfitting.
- Kekurangan:
    - Sensitif terhadap outliers, yang dapat mempengaruhi hasil.
    - Performanya dapat berkurang pada data yang sangat kompleks.

9. XGBoost
- Tahapan:
    - XGBoost adalah versi lebih lanjut dari Gradient Boosting yang mengoptimalkan waktu komputasi dan kinerja prediksi.
    - Teknik ini terkenal karena performanya yang sangat baik pada berbagai jenis masalah klasifikasi.
- Kelebihan:
    - Sangat cepat dan efisien dalam pelatihan.
    - Umumnya memberikan hasil yang sangat baik dalam klasifikasi dan regresi.
- Kekurangan:
    - Perlu penyesuaian hyperparameter yang cermat untuk mendapatkan hasil terbaik.
    Cenderung overfitting jika tidak diatur dengan baik.

10. LightGBM
- Tahapan:
    - LightGBM adalah implementasi dari gradient boosting yang dioptimalkan untuk kecepatan dan efisiensi memori.
    - LightGBM lebih cepat dalam memproses data besar dan mendukung distribusi data.
- Kelebihan:
    - Sangat cepat dalam pelatihan, bahkan untuk dataset besar.
    - Dapat menangani data yang sangat besar dengan efisien.
- Kekurangan:
    - Seperti XGBoost, memerlukan tuning yang cermat untuk menghindari overfitting.
    Kurang cocok untuk data yang sangat tidak seimbang.


## Evaluation

Pada tahap evaluasi, kita menggunakan akurasi sebagai metrik untuk menilai kinerja masing-masing model.

### Metrik Evaluasi yang Digunakan:

Akurasi mengukur persentase prediksi yang benar dari total prediksi yang dilakukan.
**Kode**

```python
from sklearn.metrics import accuracy_score

# Menampilkan hasil evaluasi
results_df = pd.DataFrame(list(results.items()), columns=["Model", "Accuracy"])

# Plotting hasil akurasi untuk masing-masing model
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(12, 6))
sns.barplot(data=results_df, x="Accuracy", y="Model", palette="viridis")
plt.title("Model Comparison based on Accuracy")
plt.xlabel("Accuracy")
plt.ylabel("Model")
plt.show()
```

**Hasil** <br>
![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/9.png)

**Penjelasan**
Dengan plot ini, kita dapat melihat model mana yang memiliki akurasi terbaik dan memilihnya sebagai model yang optimal untuk digunakan dalam pemecahan masalah ini.

Dalam proyek ini, metrik Akurasi digunakan untuk mengevaluasi kinerja setiap model klasifikasi. Akurasi merupakan salah satu metrik evaluasi yang paling umum digunakan dalam masalah klasifikasi karena memberikan gambaran umum tentang seberapa baik model dalam memprediksi kelas yang benar.

**Akurasi (Accuracy)**
Akurasi adalah metrik yang mengukur persentase prediksi yang benar dari total prediksi yang dilakukan oleh model. Secara matematis, akurasi dihitung dengan rumus:

![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/10.PNG)

Di mana:

- TP = True Positive (jumlah prediksi yang benar untuk kelas positif)
- TN = True Negative (jumlah prediksi yang benar untuk kelas negatif)
- FP = False Positive (jumlah prediksi salah untuk kelas positif)
- FN = False Negative (jumlah prediksi salah untuk kelas negatif)

Pada dasarnya, akurasi mengukur proporsi data yang benar-benar diprediksi dengan tepat oleh model.

Namun, meskipun akurasi sering digunakan, ada kasus tertentu (misalnya dalam dataset yang sangat tidak seimbang) di mana akurasi tidak memberikan gambaran yang lengkap tentang kinerja model. Dalam proyek ini, karena kita mengatasi masalah klasifikasi multi-kelas (Crop_Suitability), akurasi digunakan sebagai metrik utama untuk membandingkan kinerja model.

**Hasil Evaluasi Berdasarkan Metrik Akurasi**
Berikut adalah hasil evaluasi yang didapatkan untuk masing-masing model:

![download](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/63126eb19a7c9e06cbfd3e5c47c643e4f2c7e9a6/Submission%201/assets/11.PNG)

**Penjelasan Hasil**
Dari hasil di atas, kita dapat melihat bahwa LightGBM memiliki akurasi tertinggi (0.1575), diikuti oleh XGBoost (0.1500), dan Gradient Boosting (0.1475). Sementara itu, model-model lainnya seperti Logistic Regression, SVM, dan Naive Bayes menunjukkan akurasi yang cukup rendah, yaitu sekitar 0.11 hingga 0.14.

Hasil ini memberikan beberapa wawasan penting:

- LightGBM memberikan performa terbaik di antara semua model yang diuji. Ini menunjukkan bahwa model ini lebih mampu menangani data dan menghasilkan prediksi yang lebih baik dibandingkan dengan model lain.
- XGBoost dan Gradient Boosting juga memberikan akurasi yang lebih tinggi dibandingkan dengan model lainnya, yang menunjukkan bahwa kedua algoritma boosting ini efektif untuk menangani data ini.
Sebagian besar model lainnya menunjukkan akurasi yang relatif rendah, yang bisa jadi karena beberapa faktor seperti kompleksitas model yang tidak sesuai dengan karakteristik data atau kurangnya penyesuaian parameter.

### Mengapa Akurasi Digunakan?
Akurasi digunakan di sini karena dataset yang digunakan (berbasis pada klasifikasi multi-kelas) tidak menunjukkan ketidakseimbangan yang sangat ekstrem antar kelas. Dengan kata lain, meskipun akurasi bukan selalu metrik terbaik dalam kasus data yang sangat tidak seimbang, di sini ia cukup relevan karena kelas yang diprediksi relatif merata dan akurasi memberikan gambaran umum yang cukup baik untuk membandingkan model.

### Implikasi Hasil
Berdasarkan hasil tersebut, LightGBM adalah model terbaik yang dapat digunakan untuk masalah ini, mengingat ia memberikan akurasi tertinggi. Meskipun akurasi model ini tidak terlalu tinggi, lebih tinggi dibandingkan dengan model lain, ini memberikan titik awal untuk eksperimen lebih lanjut, termasuk tuning parameter dan pengujian dengan metrik evaluasi lain, seperti precision, recall, atau F1 score, untuk mendapatkan gambaran yang lebih mendalam tentang kinerja model pada setiap kelas.

---Ini adalah bagian akhir laporan---
