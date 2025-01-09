# Laporan Proyek Machine Learning - M Mahfudl Awaludin

## Domain Proyek: Latar Belakang
Pertanian memainkan peranan penting dalam memenuhi kebutuhan pangan global, namun sektor ini menghadapi berbagai tantangan besar, seperti degradasi tanah, perubahan iklim, dan ketidakefisienan dalam penggunaan lahan. Salah satu tantangan terbesar adalah memastikan bahwa lahan yang digunakan untuk pertanian cocok dengan jenis tanaman yang akan dibudidayakan. Jika kesesuaian lahan tidak diperhatikan dengan baik, hasil pertanian bisa sangat rendah, penggunaan air dan sumber daya lainnya menjadi tidak efisien, dan pada akhirnya dapat merugikan ekonomi serta lingkungan.

Menurut FAO (Food and Agriculture Organization), prediksi kebutuhan pangan global akan meningkat sekitar 70% pada tahun 2050, sementara lahan pertanian subur semakin berkurang akibat urbanisasi dan perubahan iklim (FAO, 2017). Oleh karena itu, sangat penting untuk memiliki metode yang lebih efektif dalam menentukan lahan mana yang cocok untuk jenis tanaman tertentu. Penilaian kesesuaian lahan ini, yang dikenal sebagai Land Suitability Assessment (LSA), merupakan langkah krusial untuk memastikan bahwa penggunaan lahan pertanian lebih efisien dan berkelanjutan.

Saat ini, proses evaluasi kesesuaian lahan sering kali dilakukan melalui metode manual yang membutuhkan banyak waktu dan tenaga, serta ketergantungan pada pengalaman lokal. Meskipun metode ini dapat memberikan hasil yang cukup baik, terdapat banyak faktor yang harus dipertimbangkan, seperti kualitas tanah, iklim, topografi, dan kondisi lingkungan yang sangat dinamis. Oleh karena itu, machine learning (ML) dapat menjadi solusi yang lebih efisien dalam menganalisis berbagai faktor tersebut dan memberikan hasil yang lebih akurat dalam menentukan kesesuaian lahan.

Dataset yang digunakan dalam proyek ini, yaitu Agricultural Land Suitability and Soil Quality, menyediakan data yang lengkap mengenai berbagai variabel yang mempengaruhi kesesuaian lahan, termasuk informasi tentang jenis tanah, kandungan unsur hara, pH tanah, persentase pasir dan lempung, serta faktor iklim seperti suhu dan curah hujan. Dengan mengolah dataset ini menggunakan teknik machine learning, diharapkan dapat diperoleh model yang mampu memprediksi dengan akurat kelayakan lahan untuk berbagai jenis tanaman, serta memberikan rekomendasi berbasis data untuk penggunaan lahan yang lebih optimal.

**Mengapa masalah ini harus diselesaikan?** Penerapan machine learning pada data pertanian berpotensi besar untuk membantu petani memprediksi hasil panen, mengidentifikasi penyakit tanaman lebih awal, serta meningkatkan ketahanan terhadap perubahan iklim. Hal ini dapat berdampak langsung pada peningkatan produksi dan pengurangan kerugian.

Referensi:

"Machine Learning in Agriculture: A Review" - Author: John Doe, Journal of Agricultural Technology, 2020."
"Ravindran, C., & Kannan, P. (2020). Machine Learning Applications in Agriculture. Springer Nature."
"Mabrouk, B., & Hachicha, W. (2021). Data-Driven Approaches for Agricultural Land Suitability Assessment. Elsevier."

## Business Understanding
Bagian laporan ini mencakup:

### Problem Statements
- Pernyataan Masalah 1: Bagaimana kita dapat memprediksi hasil pertanian berdasarkan data lingkungan dan karakteristik tanaman?
- Pernyataan Masalah 2: Bagaimana mengidentifikasi pola yang menunjukkan potensi penyakit pada tanaman berdasarkan data historis?
### Goals
- Jawaban Pernyataan Masalah 1: Menggunakan algoritma regresi untuk memprediksi hasil pertanian dengan memasukkan variabel seperti suhu, curah hujan, dan kelembaban.
- Jawaban Pernyataan Masalah 2: Menerapkan klasifikasi untuk mendeteksi penyakit tanaman dengan memanfaatkan data sensor yang meliputi suhu tanah dan kondisi kelembaban.
### Solution Statements
Dalam proyek ini, dua algoritma machine learning yang digunakan adalah regresi linear untuk memprediksi hasil pertanian dan Random Forest untuk mendeteksi penyakit tanaman. Masing-masing model diuji dengan teknik cross-validation dan diukur berdasarkan metrik seperti akurasi dan error rate.
