# Laporan Proyek Machine Learning - M Mahfudl Awaludin

## Domain Proyek: Latar Belakang
Pertanian memainkan peranan penting dalam memenuhi kebutuhan pangan global, namun sektor ini menghadapi berbagai tantangan besar, seperti degradasi tanah, perubahan iklim, dan ketidakefisienan dalam penggunaan lahan. Salah satu tantangan terbesar adalah memastikan bahwa lahan yang digunakan untuk pertanian cocok dengan jenis tanaman yang akan dibudidayakan. Jika kesesuaian lahan tidak diperhatikan dengan baik, hasil pertanian bisa sangat rendah, penggunaan air dan sumber daya lainnya menjadi tidak efisien, dan pada akhirnya dapat merugikan ekonomi serta lingkungan.

Menurut FAO (Food and Agriculture Organization), prediksi kebutuhan pangan global akan meningkat sekitar 70% pada tahun 2050, sementara lahan pertanian subur semakin berkurang akibat urbanisasi dan perubahan iklim (FAO, 2017). Oleh karena itu, sangat penting untuk memiliki metode yang lebih efektif dalam menentukan lahan mana yang cocok untuk jenis tanaman tertentu. Penilaian kesesuaian lahan ini, yang dikenal sebagai Land Suitability Assessment (LSA), merupakan langkah krusial untuk memastikan bahwa penggunaan lahan pertanian lebih efisien dan berkelanjutan.

Saat ini, proses evaluasi kesesuaian lahan sering kali dilakukan melalui metode manual yang membutuhkan banyak waktu dan tenaga, serta ketergantungan pada pengalaman lokal. Meskipun metode ini dapat memberikan hasil yang cukup baik, terdapat banyak faktor yang harus dipertimbangkan, seperti kualitas tanah, iklim, topografi, dan kondisi lingkungan yang sangat dinamis. Oleh karena itu, machine learning (ML) dapat menjadi solusi yang lebih efisien dalam menganalisis berbagai faktor tersebut dan memberikan hasil yang lebih akurat dalam menentukan kesesuaian lahan.

Dataset yang digunakan dalam proyek ini, yaitu Agricultural Land Suitability and Soil Quality, menyediakan data yang lengkap mengenai berbagai variabel yang mempengaruhi kesesuaian lahan, termasuk informasi tentang jenis tanah, kandungan unsur hara, pH tanah, persentase pasir dan lempung, serta faktor iklim seperti suhu dan curah hujan. Dengan mengolah dataset ini menggunakan teknik machine learning, diharapkan dapat diperoleh model yang mampu memprediksi dengan akurat kelayakan lahan untuk berbagai jenis tanaman, serta memberikan rekomendasi berbasis data untuk penggunaan lahan yang lebih optimal.

**Mengapa masalah ini harus diselesaikan?** Penerapan machine learning pada data pertanian berpotensi besar untuk membantu petani memprediksi hasil panen, mengidentifikasi penyakit tanaman lebih awal, serta meningkatkan ketahanan terhadap perubahan iklim. Hal ini dapat berdampak langsung pada peningkatan produksi dan pengurangan kerugian.

Referensi:

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
- Sumber Dataset:
Tautan ke Kaggle: [Agricultural Land Suitability and Soil Quality](https://www.kaggle.com/datasets/arifmia/agricultural-land-suitability-and-soil-quality?resource=download)
- Deskripsi Dataset:
Dataset ini terdiri dari 2.000 baris data dan 10 kolom yang berfokus pada kondisi tanah, kesuburan tanah, dan faktor lingkungan lainnya yang mempengaruhi kesesuaian lahan untuk pertanian. Setiap baris mewakili informasi mengenai satu lokasi pertanian tertentu di Bangladesh.

###Deskripsi Variabel
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

Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

2. Histogram: Distribusi Indeks Kesuburan
- Tujuan: Menampilkan distribusi nilai indeks kesuburan tanah.
- Penjelasan: Histogram ini menunjukkan penyebaran nilai indeks kesuburan pada berbagai lokasi dalam dataset. Jika distribusinya miring atau terdapat puncak tertentu, ini dapat menunjukkan tingkat kesuburan tanah yang dominan di daerah tersebut.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

3. Histogram: Distribusi Curah Hujan Rata-rata
- Tujuan: Menampilkan distribusi curah hujan rata-rata dalam milimeter per tahun.
- Penjelasan: Histogram ini menggambarkan berapa banyak lokasi yang mengalami curah hujan tertentu. Data ini bisa membantu menganalisis faktor cuaca yang memengaruhi kesuburan tanah.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

4. Histogram: Distribusi Suhu Rata-rata
- Tujuan: Menampilkan distribusi suhu rata-rata di berbagai lokasi.
- Penjelasan: Suhu rata-rata dapat memengaruhi tipe tanaman yang sesuai untuk ditanam. Visualisasi ini memberi wawasan tentang variabilitas suhu di wilayah yang berbeda.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

5. Pairplot: Hubungan antara Variabel
- Tujuan: Memvisualisasikan hubungan antara berbagai variabel dalam dataset, dengan warna berdasarkan kesesuaian tanaman.
- Penjelasan: Pairplot ini memungkinkan kita untuk melihat pola-pola distribusi data dan hubungan antar variabel secara langsung. Misalnya, kita dapat melihat apakah suhu berhubungan dengan curah hujan atau indeks kesuburan dalam konteks kesesuaian tanaman.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

6. Heatmap Korelasi
- Tujuan: Menggambarkan korelasi antar variabel numerik seperti indeks kesuburan, curah hujan, dan suhu.
- Penjelasan: Heatmap ini menunjukkan hubungan linear antara variabel-variabel tersebut. Korelasi positif atau negatif yang kuat dapat memberikan wawasan tentang faktor-faktor yang berpengaruh terhadap kesuburan tanah.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

7. Boxplot: Tipe Tanah vs Indeks Kesuburan
- Tujuan: Menganalisis perbedaan indeks kesuburan berdasarkan tipe tanah.
- Penjelasan: Boxplot ini menunjukkan bagaimana distribusi nilai indeks kesuburan berbeda-beda untuk tiap tipe tanah. Ini bisa membantu menentukan jenis tanah mana yang paling subur atau membutuhkan perhatian lebih.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

8. Countplot: Frekuensi Kategori 'Remarks'
- Tujuan: Menampilkan jumlah data yang terdapat pada tiap kategori Remarks.
- Penjelasan: Countplot ini menunjukkan seberapa sering tiap kategori remarks muncul. Hal ini memberikan gambaran tentang seberapa banyak lokasi pertanian yang memiliki catatan khusus atau peringatan.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

9. Trend Kesesuaian Tanaman Berdasarkan Tahun
- Tujuan: Menampilkan tren kesesuaian tanaman selama periode waktu berdasarkan tanggal observasi satelit.
- Penjelasan: Menggunakan visualisasi ini, kita dapat melihat perubahan tren kesesuaian tanaman sepanjang tahun dan apakah ada pola musiman atau perubahan akibat faktor lingkungan.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

10. Pie Chart: Distribusi Jenis Tanah
- Tujuan: Menampilkan distribusi proporsi dari masing-masing tipe tanah dalam dataset.
- Penjelasan: Pie chart ini menunjukkan persentase masing-masing tipe tanah yang terdapat dalam dataset, memberi gambaran umum mengenai kondisi tanah di Bangladesh.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

11. Violin Plot: Indeks Kesuburan Berdasarkan Kesesuaian Tanaman
- Tujuan: Menampilkan distribusi indeks kesuburan berdasarkan kesesuaian tanaman.
- Penjelasan: Violin plot ini memberikan gambaran mengenai distribusi kesuburan tanah untuk berbagai jenis tanaman, yang dapat menunjukkan perbedaan dalam kualitas tanah yang cocok untuk tanaman tertentu.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

12. Scatter Plot: Hubungan Curah Hujan vs Suhu
- Tujuan: Menampilkan hubungan antara curah hujan dan suhu untuk lokasi yang berbeda.
- Penjelasan: Scatter plot ini membantu mengidentifikasi apakah ada pola atau korelasi antara curah hujan dan suhu yang dapat mempengaruhi kesesuaian tanaman.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))

13. Heatmap Korelasi Matriks
- Tujuan: Menampilkan hubungan korelasi yang lebih mendalam antar variabel numerik.
- Penjelasan: Heatmap ini membantu kita memahami seberapa kuat hubungan antara faktor-faktor seperti indeks kesuburan, curah hujan, dan suhu, yang dapat memengaruhi hasil pertanian di Bangladesh.
Hasil :
![gambar]([Submission 1/assets/Crop_Suitability.png](https://github.com/M-Mahfudl-Awaludin/Machine-Learning-Terapan/blob/bbdb774b50ef3ecc9a600f18ea79f65f8066dfb1/Submission%201/assets/Crop_Suitability.png))
