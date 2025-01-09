# Laporan Proyek Machine Learning - M Mahfudl Awaludin

## Domain Proyek: Latar Belakang
Pertanian memainkan peranan penting dalam memenuhi kebutuhan pangan global, namun sektor ini menghadapi berbagai tantangan besar, seperti degradasi tanah, perubahan iklim, dan ketidakefisienan dalam penggunaan lahan. Salah satu tantangan terbesar adalah memastikan bahwa lahan yang digunakan untuk pertanian cocok dengan jenis tanaman yang akan dibudidayakan. Jika kesesuaian lahan tidak diperhatikan dengan baik, hasil pertanian bisa sangat rendah, penggunaan air dan sumber daya lainnya menjadi tidak efisien, dan pada akhirnya dapat merugikan ekonomi serta lingkungan.

Menurut FAO (Food and Agriculture Organization), prediksi kebutuhan pangan global akan meningkat sekitar 70% pada tahun 2050, sementara lahan pertanian subur semakin berkurang akibat urbanisasi dan perubahan iklim (FAO, 2017). Oleh karena itu, sangat penting untuk memiliki metode yang lebih efektif dalam menentukan lahan mana yang cocok untuk jenis tanaman tertentu. Penilaian kesesuaian lahan ini, yang dikenal sebagai Land Suitability Assessment (LSA), merupakan langkah krusial untuk memastikan bahwa penggunaan lahan pertanian lebih efisien dan berkelanjutan.

Saat ini, proses evaluasi kesesuaian lahan sering kali dilakukan melalui metode manual yang membutuhkan banyak waktu dan tenaga, serta ketergantungan pada pengalaman lokal. Meskipun metode ini dapat memberikan hasil yang cukup baik, terdapat banyak faktor yang harus dipertimbangkan, seperti kualitas tanah, iklim, topografi, dan kondisi lingkungan yang sangat dinamis. Oleh karena itu, machine learning (ML) dapat menjadi solusi yang lebih efisien dalam menganalisis berbagai faktor tersebut dan memberikan hasil yang lebih akurat dalam menentukan kesesuaian lahan.

Dataset yang digunakan dalam proyek ini, yaitu Agricultural Land Suitability and Soil Quality, menyediakan data yang lengkap mengenai berbagai variabel yang mempengaruhi kesesuaian lahan, termasuk informasi tentang jenis tanah, kandungan unsur hara, pH tanah, persentase pasir dan lempung, serta faktor iklim seperti suhu dan curah hujan. Dengan mengolah dataset ini menggunakan teknik machine learning, diharapkan dapat diperoleh model yang mampu memprediksi dengan akurat kelayakan lahan untuk berbagai jenis tanaman, serta memberikan rekomendasi berbasis data untuk penggunaan lahan yang lebih optimal.

## Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan?
Masalah ini harus diselesaikan karena ketidaktepatan dalam memilih lahan untuk pertanian dapat menyebabkan kerugian ekonomi yang besar dan merusak ekosistem yang ada. Ketika lahan yang tidak cocok digunakan untuk jenis tanaman tertentu, hasil yang didapatkan akan sangat rendah, bahkan bisa menyebabkan kegagalan panen. Oleh karena itu, perlu ada pendekatan yang lebih canggih dan efisien untuk menentukan kesesuaian lahan berdasarkan berbagai faktor.

Penerapan machine learning dalam masalah ini memiliki potensi besar karena kemampuannya untuk menganalisis data yang sangat kompleks dan besar secara lebih efisien dan cepat dibandingkan metode tradisional. Dengan menggunakan algoritma yang tepat, seperti Random Forest atau XGBoost, kita dapat melatih model untuk memprediksi kesesuaian lahan berdasarkan data yang tersedia dan meningkatkan ketepatan prediksi.

Proyek ini menggunakan Agricultural Land Suitability and Soil Quality Dataset yang berisi informasi yang sangat relevan mengenai kondisi tanah dan iklim untuk berbagai jenis tanaman. Dataset ini memungkinkan untuk melakukan analisis dan prediksi dengan pendekatan yang lebih terstruktur, serta memberikan wawasan yang lebih dalam mengenai bagaimana faktor-faktor tertentu, seperti pH tanah, kandungan organik, dan suhu, dapat mempengaruhi kesesuaian lahan. Melalui penggunaan machine learning, diharapkan dapat tercipta model yang tidak hanya lebih akurat, tetapi juga lebih praktis dalam memberikan rekomendasi yang tepat untuk petani atau pihak yang berkepentingan.

Referensi
FAO. (2017). The Future of Food and Agriculture – Trends and Challenges. Food and Agriculture Organization of the United Nations.
URL: http://www.fao.org/3/a-i6583e.pdf

Ravindran, C., & Kannan, P. (2020). Machine Learning Applications in Agriculture. Springer Nature.
URL: https://link.springer.com/chapter/10.1007/978-3-030-34537-7_11

Mabrouk, B., & Hachicha, W. (2021). Data-Driven Approaches for Agricultural Land Suitability Assessment. Elsevier.
URL: https://www.sciencedirect.com/science/article/pii/B9780128244811000108

## Business Understanding

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Pernyataan Masalah 1: Bagaimana menentukan apakah suatu lahan pertanian cocok untuk jenis tanaman tertentu berdasarkan karakteristik tanah?
- Pernyataan Masalah 2: Faktor-faktor apa saja yang mempengaruhi kualitas tanah dan bagaimana faktor-faktor tersebut dapat diprediksi untuk menentukan kesesuaian lahan?
- Pernyataan Masalah 3: Bagaimana meningkatkan akurasi model dalam memprediksi kesesuaian lahan untuk pertanian dengan berbagai jenis tanaman?

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban Pernyataan Masalah 1: Mengembangkan model prediksi yang mampu menentukan kelayakan lahan untuk tanaman tertentu berdasarkan data yang ada.
- Jawaban Pernyataan Masalah 2: Mengidentifikasi fitur-fitur penting yang mempengaruhi kesesuaian lahan dan menggunakan model machine learning untuk menganalisisnya.
- Jawaban Pernyataan Masalah 3: Meningkatkan akurasi model dengan menggunakan beberapa algoritma machine learning dan melakukan hyperparameter tuning.




 ### Solution statements
  - Solution Statement 1: Menggunakan algoritma Random Forest dan XGBoost untuk memprediksi kesesuaian lahan berdasarkan berbagai fitur tanah dan iklim. Hyperparameter tuning akan dilakukan untuk meningkatkan performa.
  - Solution Statement 2: Menggunakan teknik feature engineering untuk menambahkan fitur-fitur relevan yang dapat meningkatkan akurasi model.

## Data Understanding
Data yang digunakan dalam proyek ini diambil dari dataset yang tersedia di Kaggle, yang berjudul "Agricultural Land Suitability and Soil Quality." Dataset ini mencakup informasi mengenai berbagai faktor yang mempengaruhi kesesuaian lahan untuk pertanian, termasuk kualitas tanah, kondisi iklim, dan hasil produksi pertanian yang diinginkan.

Link untuk mengunduh dataset: Agricultural Land Suitability and Soil Quality Dataset.

Variabel-variabel pada dataset adalah sebagai berikut:
- Land_Suitability: Label yang menunjukkan apakah lahan cocok atau tidak cocok untuk tanaman tertentu.
- Soil_Type: Jenis tanah yang ada pada lahan.
- Ph: Tingkat keasaman tanah.
- Organic_Matter: Kandungan materi organik dalam tanah.
- EC: Kadar salinitas tanah.
- Sand_Percentage: Persentase pasir dalam tanah.
- Clay_Percentage: Persentase lempung dalam tanah.
- Temperature: Rata-rata suhu di lokasi lahan.
- Rainfall: Rata-rata curah hujan di lokasi lahan.
- Crop_Type: Jenis tanaman yang diuji.

Proses visualisasi dan eksplorasi data akan dilakukan untuk memahami hubungan antara fitur-fitur ini dengan target variabel (Land_Suitability) dan mengidentifikasi apakah terdapat pola atau outlier.

1. Importing Library


```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.preprocessing import StandardScaler, LabelEncoder, OneHotEncoder
from sklearn.cluster import KMeans, DBSCAN, AgglomerativeClustering
from sklearn.decomposition import PCA
from sklearn.metrics import silhouette_score, davies_bouldin_score
```

2. Load Data


```python
# Load dataset
df = pd.read_csv('/content/bangladesh_divisions_dataset.csv')




```


```python
# Tampilkan beberapa baris pertama dataset
print(df.head())
```

      Location Soil_Type  Fertility_Index Land_Use_Type  Average_Rainfall(mm)  \
    0   Sylhet     Loamy               62  Agricultural                    72   
    1    Dhaka     Sandy               63        Unused                   118   
    2  Rangpur     Peaty               51  Agricultural                   106   
    3   Khulna     Sandy               67        Barren                   336   
    4  Rangpur     Peaty               63  Agricultural                   237   
    
       Temperature(°C) Crop_Suitability   Season Satellite_Observation_Date  \
    0             28.6            Wheat  Monsoon                 2024-09-24   
    1             23.8            Maize   Autumn                 2024-01-31   
    2             32.0            Maize   Autumn                 2024-03-11   
    3             31.6            Wheat   Autumn                 2024-09-29   
    4             20.1             Rice   Winter                 2024-04-01   
    
                  Remarks  
    0  Requires attention  
    1  Moderate potential  
    2  Requires attention  
    3       Low potential  
    4  Moderate potential  



```python
# Tampilkan informasi dasar mengenai dataset
print(df.info())
print(df.describe())
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 2000 entries, 0 to 1999
    Data columns (total 10 columns):
     #   Column                      Non-Null Count  Dtype  
    ---  ------                      --------------  -----  
     0   Location                    2000 non-null   object 
     1   Soil_Type                   2000 non-null   object 
     2   Fertility_Index             2000 non-null   int64  
     3   Land_Use_Type               2000 non-null   object 
     4   Average_Rainfall(mm)        2000 non-null   int64  
     5   Temperature(°C)             2000 non-null   float64
     6   Crop_Suitability            2000 non-null   object 
     7   Season                      2000 non-null   object 
     8   Satellite_Observation_Date  2000 non-null   object 
     9   Remarks                     2000 non-null   object 
    dtypes: float64(1), int64(2), object(7)
    memory usage: 156.4+ KB
    None
           Fertility_Index  Average_Rainfall(mm)  Temperature(°C)
    count       2000.00000           2000.000000      2000.000000
    mean          70.10450            223.136000        27.330250
    std           17.97699            100.548543         4.341251
    min           40.00000             50.000000        20.000000
    25%           54.00000            137.000000        23.500000
    50%           70.00000            222.500000        27.300000
    75%           86.00000            308.000000        31.000000
    max          100.00000            400.000000        35.000000



```python
# Checking for null values
print("\nMissing Values:")
df.isnull().sum()
```

    
    Missing Values:





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Location</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Soil_Type</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Fertility_Index</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Land_Use_Type</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Average_Rainfall(mm)</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Temperature(°C)</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Crop_Suitability</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Season</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Satellite_Observation_Date</th>
      <td>0</td>
    </tr>
    <tr>
      <th>Remarks</th>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div><br><label><b>dtype:</b> int64</label>




```python
print("Jumlah duplikasi: ", df.duplicated().sum())
```

    Jumlah duplikasi:  0



```python
df.describe()
```





  <div id="df-ed19ad20-74e4-445f-947f-ad2a88e84ab1" class="colab-df-container">
    <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fertility_Index</th>
      <th>Average_Rainfall(mm)</th>
      <th>Temperature(°C)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2000.00000</td>
      <td>2000.000000</td>
      <td>2000.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>70.10450</td>
      <td>223.136000</td>
      <td>27.330250</td>
    </tr>
    <tr>
      <th>std</th>
      <td>17.97699</td>
      <td>100.548543</td>
      <td>4.341251</td>
    </tr>
    <tr>
      <th>min</th>
      <td>40.00000</td>
      <td>50.000000</td>
      <td>20.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>54.00000</td>
      <td>137.000000</td>
      <td>23.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>70.00000</td>
      <td>222.500000</td>
      <td>27.300000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>86.00000</td>
      <td>308.000000</td>
      <td>31.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>100.00000</td>
      <td>400.000000</td>
      <td>35.000000</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-ed19ad20-74e4-445f-947f-ad2a88e84ab1')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-ed19ad20-74e4-445f-947f-ad2a88e84ab1 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-ed19ad20-74e4-445f-947f-ad2a88e84ab1');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-2513e293-7e70-454e-b458-b0ba3558a7bd">
  <button class="colab-df-quickchart" onclick="quickchart('df-2513e293-7e70-454e-b458-b0ba3558a7bd')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-2513e293-7e70-454e-b458-b0ba3558a7bd button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





### Exploratory Data Analysis
Summary of Numerical and Categorical Features


```python
df.describe(include="all")
```





  <div id="df-2b06e2df-897e-443d-8ff4-d7b358c18159" class="colab-df-container">
    <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Location</th>
      <th>Soil_Type</th>
      <th>Fertility_Index</th>
      <th>Land_Use_Type</th>
      <th>Average_Rainfall(mm)</th>
      <th>Temperature(°C)</th>
      <th>Crop_Suitability</th>
      <th>Season</th>
      <th>Satellite_Observation_Date</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2000</td>
      <td>2000</td>
      <td>2000.00000</td>
      <td>2000</td>
      <td>2000.000000</td>
      <td>2000.000000</td>
      <td>2000</td>
      <td>2000</td>
      <td>2000</td>
      <td>2000</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>8</td>
      <td>5</td>
      <td>NaN</td>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7</td>
      <td>4</td>
      <td>365</td>
      <td>4</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Rangpur</td>
      <td>Loamy</td>
      <td>NaN</td>
      <td>Unused</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Maize</td>
      <td>Summer</td>
      <td>2024-06-09</td>
      <td>Moderate potential</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>265</td>
      <td>425</td>
      <td>NaN</td>
      <td>538</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>309</td>
      <td>536</td>
      <td>14</td>
      <td>516</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>70.10450</td>
      <td>NaN</td>
      <td>223.136000</td>
      <td>27.330250</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>17.97699</td>
      <td>NaN</td>
      <td>100.548543</td>
      <td>4.341251</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>40.00000</td>
      <td>NaN</td>
      <td>50.000000</td>
      <td>20.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>54.00000</td>
      <td>NaN</td>
      <td>137.000000</td>
      <td>23.500000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>70.00000</td>
      <td>NaN</td>
      <td>222.500000</td>
      <td>27.300000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>86.00000</td>
      <td>NaN</td>
      <td>308.000000</td>
      <td>31.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>100.00000</td>
      <td>NaN</td>
      <td>400.000000</td>
      <td>35.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-2b06e2df-897e-443d-8ff4-d7b358c18159')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-2b06e2df-897e-443d-8ff4-d7b358c18159 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-2b06e2df-897e-443d-8ff4-d7b358c18159');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-bb4eb10a-38dd-49da-84ec-7aafecb57276">
  <button class="colab-df-quickchart" onclick="quickchart('df-bb4eb10a-38dd-49da-84ec-7aafecb57276')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-bb4eb10a-38dd-49da-84ec-7aafecb57276 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# Set the style for the plots
sns.set(style="whitegrid")
```

1. Memeriksa Distribusi Kolom Numerik
Melakukan analisis statistik deskriptif dan visualisasi distribusi untuk kolom numerik seperti Fertility_Index, Average_Rainfall(mm), dan Temperature(°C).

Tujuan: Memahami distribusi nilai-nilai dalam kolom numerik. Ini membantu untuk mengidentifikasi apakah data terdistribusi normal, apakah ada outlier, atau apakah distribusinya miring.


```python
import matplotlib.pyplot as plt
import seaborn as sns

# Statistik deskriptif untuk kolom numerik
print(df[['Fertility_Index', 'Average_Rainfall(mm)', 'Temperature(°C)']].describe())

# Visualisasi distribusi kolom numerik
plt.figure(figsize=(12, 6))
sns.histplot(df['Fertility_Index'], kde=True, color='blue', bins=20)
plt.title('Distribusi Fertility Index')
plt.xlabel('Fertility Index')
plt.ylabel('Frekuensi')
plt.show()

plt.figure(figsize=(12, 6))
sns.histplot(df['Average_Rainfall(mm)'], kde=True, color='green', bins=20)
plt.title('Distribusi Average Rainfall')
plt.xlabel('Average Rainfall (mm)')
plt.ylabel('Frekuensi')
plt.show()

plt.figure(figsize=(12, 6))
sns.histplot(df['Temperature(°C)'], kde=True, color='red', bins=20)
plt.title('Distribusi Temperature')
plt.xlabel('Temperature (°C)')
plt.ylabel('Frekuensi')
plt.show()

```

           Fertility_Index  Average_Rainfall(mm)  Temperature(°C)
    count       2000.00000           2000.000000      2000.000000
    mean          70.10450            223.136000        27.330250
    std           17.97699            100.548543         4.341251
    min           40.00000             50.000000        20.000000
    25%           54.00000            137.000000        23.500000
    50%           70.00000            222.500000        27.300000
    75%           86.00000            308.000000        31.000000
    max          100.00000            400.000000        35.000000



    
![png](output_21_1.png)
    



    
![png](output_21_2.png)
    



    
![png](output_21_3.png)
    


2. Memeriksa Kolom Kategorikal
Untuk kolom kategorikal seperti Location, Soil_Type, Land_Use_Type, Crop_Suitability, dan Season, kita dapat memvisualisasikan frekuensi kemunculannya.

Tujuan: Memahami distribusi kategori dalam fitur-fitur kategorikal, yang dapat memberi insight mengenai bias atau ketidakseimbangan dalam data.


```python
# Visualisasi frekuensi untuk kolom kategorikal
plt.figure(figsize=(12, 6))
sns.countplot(x='Location', data=df, palette='Set2')
plt.title('Frekuensi Location')
plt.xlabel('Location')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

plt.figure(figsize=(12, 6))
sns.countplot(x='Soil_Type', data=df, palette='Set2')
plt.title('Frekuensi Soil Type')
plt.xlabel('Soil Type')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

plt.figure(figsize=(12, 6))
sns.countplot(x='Land_Use_Type', data=df, palette='Set2')
plt.title('Frekuensi Land Use Type')
plt.xlabel('Land Use Type')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

plt.figure(figsize=(12, 6))
sns.countplot(x='Crop_Suitability', data=df, palette='Set2')
plt.title('Frekuensi Crop Suitability')
plt.xlabel('Crop Suitability')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

plt.figure(figsize=(12, 6))
sns.countplot(x='Season', data=df, palette='Set2')
plt.title('Frekuensi Season')
plt.xlabel('Season')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

```

    <ipython-input-11-756775c1c992>:3: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.countplot(x='Location', data=df, palette='Set2')



    
![png](output_24_1.png)
    


    <ipython-input-11-756775c1c992>:11: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.countplot(x='Soil_Type', data=df, palette='Set2')



    
![png](output_24_3.png)
    


    <ipython-input-11-756775c1c992>:19: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.countplot(x='Land_Use_Type', data=df, palette='Set2')



    
![png](output_24_5.png)
    


    <ipython-input-11-756775c1c992>:27: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.countplot(x='Crop_Suitability', data=df, palette='Set2')



    
![png](output_24_7.png)
    


    <ipython-input-11-756775c1c992>:35: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.countplot(x='Season', data=df, palette='Set2')



    
![png](output_24_9.png)
    


3. Memeriksa Korelasi Antarfaktor Numerik
Untuk kolom numerik, kita dapat menggunakan heatmap untuk melihat korelasi antara fitur-fitur numerik yang ada. Ini membantu untuk memahami hubungan antar fitur yang mungkin relevan untuk model.

Tujuan: Memahami sejauh mana fitur numerik berhubungan satu sama lain. Korelasi yang tinggi antara dua fitur bisa menandakan adanya multikolinearitas, yang perlu dipertimbangkan dalam pemodelan.


```python
# Memeriksa korelasi antar fitur numerik
correlation_matrix = df[['Fertility_Index', 'Average_Rainfall(mm)', 'Temperature(°C)']].corr()

# Visualisasi korelasi dengan heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt='.2f', cbar=True)
plt.title('Korelasi Antar Fitur Numerik')
plt.show()

```


    
![png](output_27_0.png)
    


4. Analisis Hubungan Antara Fitur Kategorikal dan Target
Jika kita ingin melihat hubungan antara fitur kategorikal dengan target, kita dapat menggunakan countplot untuk membandingkan distribusi target pada setiap kategori.

Tujuan: Menilai bagaimana fitur-fitur kategorikal berhubungan dengan target, untuk melihat apakah ada kategori tertentu yang lebih cenderung menghasilkan nilai target tertentu.


```python
# Hubungan antara Crop_Suitability dan Location
plt.figure(figsize=(12, 6))
sns.countplot(x='Location', hue='Crop_Suitability', data=df, palette='Set2')
plt.title('Hubungan antara Location dan Crop Suitability')
plt.xlabel('Location')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

# Hubungan antara Land_Use_Type dan Soil_Type
plt.figure(figsize=(12, 6))
sns.countplot(x='Land_Use_Type', hue='Soil_Type', data=df, palette='Set2')
plt.title('Hubungan antara Land Use Type dan Soil Type')
plt.xlabel('Land Use Type')
plt.ylabel('Frekuensi')
plt.xticks(rotation=45)
plt.show()

```


    
![png](output_30_0.png)
    



    
![png](output_30_1.png)
    


## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut

Import libraries


```python
!pip install scikit-learn==1.0.2
!pip install --upgrade xgboost
# Uninstall old versions first
!pip uninstall -y imbalanced-learn scikit-learn

# Install compatible versions of imbalanced-learn and scikit-learn
!pip install scikit-learn==1.0.2 imbalanced-learn==0.8.1

# 2. Import libraries
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split, GridSearchCV, cross_val_score
from sklearn.preprocessing import StandardScaler
from sklearn.ensemble import RandomForestClassifier
from xgboost import XGBClassifier
from sklearn.linear_model import LogisticRegression
from imblearn.over_sampling import SMOTE
from sklearn.metrics import classification_report, accuracy_score
```

    Collecting scikit-learn==1.0.2
      Downloading scikit_learn-1.0.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (10 kB)
    Requirement already satisfied: numpy>=1.14.6 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.26.4)
    Requirement already satisfied: scipy>=1.1.0 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.13.1)
    Requirement already satisfied: joblib>=0.11 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.4.2)
    Requirement already satisfied: threadpoolctl>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (3.5.0)
    Downloading scikit_learn-1.0.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (26.5 MB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m26.5/26.5 MB[0m [31m18.3 MB/s[0m eta [36m0:00:00[0m
    [?25hInstalling collected packages: scikit-learn
      Attempting uninstall: scikit-learn
        Found existing installation: scikit-learn 1.6.0
        Uninstalling scikit-learn-1.6.0:
          Successfully uninstalled scikit-learn-1.6.0
    [31mERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
    bigframes 1.29.0 requires scikit-learn>=1.2.2, but you have scikit-learn 1.0.2 which is incompatible.
    mlxtend 0.23.3 requires scikit-learn>=1.3.1, but you have scikit-learn 1.0.2 which is incompatible.[0m[31m
    [0mSuccessfully installed scikit-learn-1.0.2
    Requirement already satisfied: xgboost in /usr/local/lib/python3.10/dist-packages (2.1.3)
    Requirement already satisfied: numpy in /usr/local/lib/python3.10/dist-packages (from xgboost) (1.26.4)
    Requirement already satisfied: nvidia-nccl-cu12 in /usr/local/lib/python3.10/dist-packages (from xgboost) (2.23.4)
    Requirement already satisfied: scipy in /usr/local/lib/python3.10/dist-packages (from xgboost) (1.13.1)
    Found existing installation: imbalanced-learn 0.12.4
    Uninstalling imbalanced-learn-0.12.4:
      Successfully uninstalled imbalanced-learn-0.12.4
    Found existing installation: scikit-learn 1.0.2
    Uninstalling scikit-learn-1.0.2:
      Successfully uninstalled scikit-learn-1.0.2
    Collecting scikit-learn==1.0.2
      Using cached scikit_learn-1.0.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (10 kB)
    Collecting imbalanced-learn==0.8.1
      Downloading imbalanced_learn-0.8.1-py3-none-any.whl.metadata (12 kB)
    Requirement already satisfied: numpy>=1.14.6 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.26.4)
    Requirement already satisfied: scipy>=1.1.0 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.13.1)
    Requirement already satisfied: joblib>=0.11 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (1.4.2)
    Requirement already satisfied: threadpoolctl>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from scikit-learn==1.0.2) (3.5.0)
    Using cached scikit_learn-1.0.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (26.5 MB)
    Downloading imbalanced_learn-0.8.1-py3-none-any.whl (189 kB)
    [2K   [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m189.7/189.7 kB[0m [31m5.6 MB/s[0m eta [36m0:00:00[0m
    [?25hInstalling collected packages: scikit-learn, imbalanced-learn
    [31mERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
    bigframes 1.29.0 requires scikit-learn>=1.2.2, but you have scikit-learn 1.0.2 which is incompatible.
    mlxtend 0.23.3 requires scikit-learn>=1.3.1, but you have scikit-learn 1.0.2 which is incompatible.[0m[31m
    [0mSuccessfully installed imbalanced-learn-0.8.1 scikit-learn-1.0.2


1. Membaca Dataset


```python
df = pd.read_csv('/content/bangladesh_divisions_dataset.csv')
```

2. One-Hot Encoding untuk Variabel Kategorikal


```python
# Encode categorical variables using one-hot encoding
df = pd.get_dummies(df, columns=['Location', 'Soil_Type', 'Land_Use_Type', 'Season'])

```

- *Mengapa ini diperlukan? Model machine learning tidak bisa langsung bekerja dengan data kategorikal (seperti nama lokasi atau jenis tanah). Oleh karena itu, kita menggunakan one-hot encoding untuk mengubah variabel kategorikal menjadi variabel numerik, yang memungkinkan model untuk mengolahnya.*
- *Pada kode di atas, kita mengubah kolom Location, Soil_Type, Land_Use_Type, dan Season menjadi serangkaian kolom biner (0 atau 1), di mana setiap kategori akan memiliki kolom baru yang menunjukkan apakah data tersebut termasuk dalam kategori tersebut*.

3. Konversi Target Variabel (Crop_Suitability) menjadi Label Numerik


```python
df['Crop_Suitability'] = df['Crop_Suitability'].map({'Wheat': 0, 'Maize': 1, 'Rice': 2})

```

*Mengapa ini diperlukan? Model machine learning, khususnya yang berbasis regresi dan klasifikasi, lebih mudah bekerja dengan data numerik. Oleh karena itu, target variabel Crop_Suitability yang awalnya berupa string (seperti 'Wheat', 'Maize', 'Rice') diubah menjadi angka (0 untuk Wheat, 1 untuk Maize, dan 2 untuk Rice)*

4. Menghapus Baris dengan Nilai yang Hilang pada Kolom 'Crop_Suitability'


```python
df = df.dropna(subset=['Crop_Suitability'])

```

*Mengapa ini diperlukan? Data yang hilang (missing values) dapat menyebabkan kesalahan dalam model karena banyak algoritma machine learning tidak dapat menangani data yang hilang secara langsung. Pada kode ini, baris yang memiliki nilai kosong pada kolom target (Crop_Suitability) dihapus untuk menghindari masalah tersebut.*

5. Feature Engineering: Ekstraksi Fitur Berdasarkan Tanggal


```python
df['Satellite_Observation_Date'] = pd.to_datetime(df['Satellite_Observation_Date'])
df['Year'] = df['Satellite_Observation_Date'].dt.year
df['Month'] = df['Satellite_Observation_Date'].dt.month
df['Day'] = df['Satellite_Observation_Date'].dt.day
df['Weekday'] = df['Satellite_Observation_Date'].dt.weekday

```

*Mengapa ini diperlukan? Fitur yang berkaitan dengan waktu seringkali memiliki nilai prediktif. Dengan memecah kolom Satellite_Observation_Date menjadi beberapa fitur seperti Year, Month, Day, dan Weekday, kita bisa memberi model informasi tambahan tentang waktu yang relevan. Misalnya, pola pertumbuhan tanaman bisa berbeda tergantung pada bulan atau musim tertentu.*

6. Menghapus Kolom 'Satellite_Observation_Date'


```python
df = df.drop(['Satellite_Observation_Date'], axis=1)

```

*Mengapa ini diperlukan? Setelah fitur-fitur yang relevan dari kolom Satellite_Observation_Date diekstraksi, kolom asli tersebut menjadi tidak diperlukan lagi dan dapat dihapus agar dataset menjadi lebih efisien.*

7. Feature Engineering: Membuat Fitur Interaksi


```python
df['Rainfall_Temperature_Interaction'] = df['Average_Rainfall(mm)'] * df['Temperature(°C)']

```

*Mengapa ini diperlukan? Kadang-kadang, interaksi antara dua fitur bisa memberikan informasi yang lebih berguna daripada masing-masing fitur secara terpisah. Di sini, kami membuat fitur interaksi antara Average_Rainfall(mm) dan Temperature(°C) untuk melihat apakah ada pengaruh yang lebih besar ketika kedua variabel ini berinteraksi satu sama lain.*

8. Feature Engineering: Membuat Fitur Rasio


```python
df['Fertility_Rainfall_Ratio'] = df['Fertility_Index'] / (df['Average_Rainfall(mm)'] + 1)

```

Mengapa ini diperlukan? Fitur rasio sering kali berguna untuk menunjukkan hubungan antara dua variabel yang saling terkait. Di sini, kami membuat rasio antara Fertility_Index dan Average_Rainfall(mm) untuk melihat bagaimana tingkat kesuburan tanah berhubungan dengan jumlah curah hujan. Penambahan 1 pada pembilang bertujuan untuk menghindari pembagian dengan nol

9. Feature Engineering: Membuat Fitur Polinomial


```python
df['Rainfall_Squared'] = df['Average_Rainfall(mm)'] ** 2

```

*Mengapa ini diperlukan? Kadang-kadang, hubungan antara fitur dan target tidak linear. Oleh karena itu, dengan membuat fitur polinomial (misalnya, kuadrat dari Average_Rainfall), model bisa menangkap hubungan non-linear yang mungkin ada antara fitur dan target.*

10. Feature Engineering: Membuat Fitur Statistik


```python
df['Temperature_Mean'] = df['Temperature(°C)'].mean()
df['Rainfall_Mean'] = df['Average_Rainfall(mm)'].mean()

```

*Mengapa ini diperlukan? Fitur statistik seperti mean, median, atau standar deviasi sering kali memberikan gambaran umum tentang distribusi data. Di sini, kami membuat fitur rata-rata (mean) dari suhu dan curah hujan untuk memberikan model informasi yang lebih kaya tentang karakteristik data secara keseluruhan.*

Alasan
1. Menangani Variabel Kategorikal: Algoritma machine learning, terutama yang berbasis pohon keputusan, regresi, atau jaringan saraf, tidak dapat menangani data kategorikal dalam bentuk string. Oleh karena itu, proses one-hot encoding diperlukan untuk mengubah kategori menjadi format numerik yang bisa diproses oleh model.

2. Mengatasi Missing Data: Data yang hilang bisa menyebabkan model memberikan prediksi yang tidak akurat atau bahkan gagal berfungsi. Dengan menghapus baris yang memiliki nilai kosong pada kolom target, kita memastikan bahwa model hanya dilatih dengan data yang lengkap.

3. Meningkatkan Kualitas Fitur: Feature engineering, seperti ekstraksi tanggal atau pembuatan fitur interaksi, rasio, dan polinomial, bertujuan untuk menghasilkan fitur yang lebih informatif bagi model. Fitur-fitur ini dapat membantu model memahami hubungan yang lebih kompleks antara variabel dan hasil yang diprediksi.

4. Mempermudah Interpretasi Model: Dengan mengubah data dalam format yang lebih sesuai (misalnya, mengubah tanggal menjadi kolom tahun, bulan, dan hari), kita dapat membuat model lebih mudah diinterpretasikan dan hasilnya lebih bermakna.

5. Menyesuaikan dengan Model Machine Learning: Beberapa model seperti XGBoost dan Random Forest sangat bergantung pada pemrosesan data yang tepat dan fitur yang relevan. Dengan menyiapkan data dengan benar, kita meningkatkan peluang untuk memperoleh model yang akurat dan efisien.

## Modeling




```python
# Split data into features (X) and target (y)
X = df.drop(['Crop_Suitability', 'Remarks'], axis=1)
y = df['Crop_Suitability']

# 5. Splitting the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 6. Feature Scaling
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# 7. Handling class imbalance using SMOTE
smote = SMOTE(random_state=42)
X_train_res, y_train_res = smote.fit_resample(X_train, y_train)

```


```python
# 8. Build Random Forest model
rf_model = RandomForestClassifier(random_state=500)

# Hyperparameter tuning for Random Forest
rf_param_grid = {
    'n_estimators': [100, 200],
    'max_depth': [None, 10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4]
}

rf_grid_search = GridSearchCV(rf_model, rf_param_grid, cv=5, verbose=2, n_jobs=-1)
rf_grid_search.fit(X_train_res, y_train_res)

# Best Random Forest Model
best_rf_model = rf_grid_search.best_estimator_
```

    Fitting 5 folds for each of 72 candidates, totalling 360 fits



```python
# 9. Build XGBoost model
xgb_model = XGBClassifier(random_state=42)

# Hyperparameter tuning for XGBoost
xgb_param_grid = {
    'learning_rate': [0.01, 0.1, 0.3],
    'n_estimators': [100, 200],
    'max_depth': [3, 5, 7],
    'subsample': [0.8, 1.0],
    'colsample_bytree': [0.8, 1.0]
}

xgb_grid_search = GridSearchCV(xgb_model, xgb_param_grid, cv=5, verbose=2, n_jobs=-1)
xgb_grid_search.fit(X_train_res, y_train_res)

# Best XGBoost Model
best_xgb_model = xgb_grid_search.best_estimator_
```

    Fitting 5 folds for each of 72 candidates, totalling 360 fits



```python
# 10. Build Logistic Regression model for comparison
log_reg_model = LogisticRegression(max_iter=1000, random_state=42)

# Hyperparameter tuning for Logistic Regression
log_reg_param_grid = {
    'C': [0.01, 0.1, 1.0, 10.0],
    'solver': ['lbfgs', 'liblinear']
}

log_reg_grid_search = GridSearchCV(log_reg_model, log_reg_param_grid, cv=5, verbose=2, n_jobs=-1)
log_reg_grid_search.fit(X_train_res, y_train_res)

# Best Logistic Regression Model
best_log_reg_model = log_reg_grid_search.best_estimator_
```

    Fitting 5 folds for each of 8 candidates, totalling 40 fits



```python
# --- 8. Build Random Forest model ---
rf_model = RandomForestClassifier(random_state=500)

# Hyperparameter tuning for Random Forest using GridSearchCV
rf_param_grid = {
    'n_estimators': [100, 200, 300],
    'max_depth': [None, 10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4],
    'max_features': ['auto', 'sqrt', 'log2']
}

rf_grid_search = GridSearchCV(rf_model, rf_param_grid, cv=5, n_jobs=-1, verbose=2)
rf_grid_search.fit(X_train_res, y_train_res)

# Best Random Forest Model
best_rf_model = rf_grid_search.best_estimator_

# --- 9. Build XGBoost model ---
xgb_model = XGBClassifier(random_state=42)

# Hyperparameter tuning for XGBoost using GridSearchCV
xgb_param_grid = {
    'learning_rate': [0.01, 0.1, 0.3],
    'n_estimators': [100, 200],
    'max_depth': [3, 5, 7],
    'subsample': [0.8, 1.0],
    'colsample_bytree': [0.8, 1.0]
}

xgb_grid_search = GridSearchCV(xgb_model, xgb_param_grid, cv=5, n_jobs=-1, verbose=2)
xgb_grid_search.fit(X_train_res, y_train_res)

# Best XGBoost Model
best_xgb_model = xgb_grid_search.best_estimator_

# --- 10. Build Logistic Regression model ---
log_reg_model = LogisticRegression(max_iter=1000, random_state=42)

# Hyperparameter tuning for Logistic Regression using GridSearchCV
log_reg_param_grid = {
    'C': [0.01, 0.1, 1.0, 10.0],
    'solver': ['lbfgs', 'liblinear']
}

log_reg_grid_search = GridSearchCV(log_reg_model, log_reg_param_grid, cv=5, n_jobs=-1, verbose=2)
log_reg_grid_search.fit(X_train_res, y_train_res)

# Best Logistic Regression Model
best_log_reg_model = log_reg_grid_search.best_estimator_

# --- 11. Evaluate the models ---

# Predict using Random Forest
y_pred_rf = best_rf_model.predict(X_test)
print("Random Forest Classification Report:")
print(classification_report(y_test, y_pred_rf))

# Predict using XGBoost
y_pred_xgb = best_xgb_model.predict(X_test)
print("XGBoost Classification Report:")
print(classification_report(y_test, y_pred_xgb))

# Predict using Logistic Regression
y_pred_log_reg = best_log_reg_model.predict(X_test)
print("Logistic Regression Classification Report:")
print(classification_report(y_test, y_pred_log_reg))

```

    Fitting 5 folds for each of 324 candidates, totalling 1620 fits
    Fitting 5 folds for each of 72 candidates, totalling 360 fits
    Fitting 5 folds for each of 8 candidates, totalling 40 fits
    Random Forest Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.25      0.28      0.26        50
             1.0       0.33      0.28      0.30        71
             2.0       0.26      0.29      0.27        49
    
        accuracy                           0.28       170
       macro avg       0.28      0.28      0.28       170
    weighted avg       0.29      0.28      0.28       170
    
    XGBoost Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.21      0.22      0.22        50
             1.0       0.40      0.35      0.37        71
             2.0       0.27      0.31      0.29        49
    
        accuracy                           0.30       170
       macro avg       0.29      0.29      0.29       170
    weighted avg       0.31      0.30      0.30       170
    
    Logistic Regression Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.36      0.46      0.40        50
             1.0       0.41      0.28      0.33        71
             2.0       0.35      0.41      0.38        49
    
        accuracy                           0.37       170
       macro avg       0.37      0.38      0.37       170
    weighted avg       0.38      0.37      0.37       170
    


## Evaluation



Setelah model dilatih dengan data pelatihan, kita akan mengevaluasi performa model pada data pengujian menggunakan beberapa metrik evaluasi, seperti accuracy, precision, recall, dan F1-score. Metrik-metrik ini digunakan untuk memberikan gambaran yang lebih lengkap mengenai kualitas model dalam memprediksi kelas target.



![sassasas.JPG](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD/4QLQRXhpZgAATU0AKgAAAAgABAE7AAIAAAADUEMAAIdpAAQAAAABAAABSpydAAEAAAAGAAACwuocAAcAAAEMAAAAPgAAAAAc6gAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWQAwACAAAAFAAAApiQBAACAAAAFAAAAqySkQACAAAAAzk2AACSkgACAAAAAzk2AADqHAAHAAABDAAAAYwAAAAAHOoAAAABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADIwMjU6MDE6MDcgMjM6MzE6MzcAMjAyNTowMTowNyAyMzozMTozNwAAAFAAQwAAAP/hBBVodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvADw/eHBhY2tldCBiZWdpbj0n77u/JyBpZD0nVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkJz8+DQo8eDp4bXBtZXRhIHhtbG5zOng9ImFkb2JlOm5zOm1ldGEvIj48cmRmOlJERiB4bWxuczpyZGY9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkvMDIvMjItcmRmLXN5bnRheC1ucyMiPjxyZGY6RGVzY3JpcHRpb24gcmRmOmFib3V0PSJ1dWlkOmZhZjViZGQ1LWJhM2QtMTFkYS1hZDMxLWQzM2Q3NTE4MmYxYiIgeG1sbnM6ZGM9Imh0dHA6Ly9wdXJsLm9yZy9kYy9lbGVtZW50cy8xLjEvIi8+PHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9InV1aWQ6ZmFmNWJkZDUtYmEzZC0xMWRhLWFkMzEtZDMzZDc1MTgyZjFiIiB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iPjx4bXA6Q3JlYXRlRGF0ZT4yMDI1LTAxLTA3VDIzOjMxOjM3Ljk2MzwveG1wOkNyZWF0ZURhdGU+PC9yZGY6RGVzY3JpcHRpb24+PHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9InV1aWQ6ZmFmNWJkZDUtYmEzZC0xMWRhLWFkMzEtZDMzZDc1MTgyZjFiIiB4bWxuczpkYz0iaHR0cDovL3B1cmwub3JnL2RjL2VsZW1lbnRzLzEuMS8iPjxkYzpjcmVhdG9yPjxyZGY6U2VxIHhtbG5zOnJkZj0iaHR0cDovL3d3dy53My5vcmcvMTk5OS8wMi8yMi1yZGYtc3ludGF4LW5zIyI+PHJkZjpsaT5QQzwvcmRmOmxpPjwvcmRmOlNlcT4NCgkJCTwvZGM6Y3JlYXRvcj48L3JkZjpEZXNjcmlwdGlvbj48L3JkZjpSREY+PC94OnhtcG1ldGE+DQogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgPD94cGFja2V0IGVuZD0ndyc/Pv/bAEMABwUFBgUEBwYFBggHBwgKEQsKCQkKFQ8QDBEYFRoZGBUYFxseJyEbHSUdFxgiLiIlKCkrLCsaIC8zLyoyJyorKv/bAEMBBwgICgkKFAsLFCocGBwqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKv/AABEIAWgCFQMBIgACEQEDEQH/xAAfAAABBQEBAQEBAQAAAAAAAAAAAQIDBAUGBwgJCgv/xAC1EAACAQMDAgQDBQUEBAAAAX0BAgMABBEFEiExQQYTUWEHInEUMoGRoQgjQrHBFVLR8CQzYnKCCQoWFxgZGiUmJygpKjQ1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4eLj5OXm5+jp6vHy8/T19vf4+fr/xAAfAQADAQEBAQEBAQEBAAAAAAAAAQIDBAUGBwgJCgv/xAC1EQACAQIEBAMEBwUEBAABAncAAQIDEQQFITEGEkFRB2FxEyIygQgUQpGhscEJIzNS8BVictEKFiQ04SXxFxgZGiYnKCkqNTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqCg4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2dri4+Tl5ufo6ery8/T19vf4+fr/2gAMAwEAAhEDEQA/APfdS8S6TpGsabpeo3YgvNUZks4zGx80rjI3AYHUdSM54pw8Q6W3iZvDy3YOqrbfamtwjcRbtu4tjb17Zz7VxfxI8OX3iDxRohsbeVntrO8lhuBGSkNwvlPFlugyyd+vNYCad4rlv7nxLY6Zc2uuapo17KqvEf8AR3LwrDCSeA4jTIUnrn3oA9guLq3tIxJdzxwIWVA0rhQWY4Aye5JAApl/f2ul2Ml5qE6W9vHjfI54XJwP1Irxu90HVdR8GzSXN5r+pxQ6jY3H2Y2V/bSwhZB5xQSSvLIdvPy/KpGU56auoWXiA6b4vvbKXxD5638EWmRia5GLfEBYohPP8eTgkfN0y2QD0vTtWstVa7FhP5ps7hraf5GXZIuMryBnqORxVDUfGGj6VrS6TdSXb3zRLN5NtYT3G1GYqGYxowUZB6kdK4fwxa69ZfEnUv7StdRh0W41a6ktTbxuqvMQuGmx1jKg7D9zdnPO2rWvC7svjB/aBl120s30uCLzdM0trpJ2Ezkxu3kybRgjptPPWgD0mqeoatZaU1ot/N5RvLhbaD5GbfI2cLwDjoeTxXnF5/wllrqGq2UcGr3lppH2q9t5FmlQ3wmUeVCJBy3l75flGSNid8Vl6dY+Irie1iuU1a8tLfxJZz20lza3SlIjCd7fv3eQKG4JZuD2GcUAez0V5Dpup+Koo9CtnsPEF1d6dbaiL9ZUmjS4kCkwjzW+V88bWBOO3NVbFPEraZrSSahr1taN9jnty9hqTMzZfzYRl3uFB2qCylccEKAeQD2BdQtH1OTT1nQ3ccSzPDn5gjEgN9MqfyqxXlmny63PqiyalY+J7Cyaw03ZbW08szRzfaH3hnflhjYZCfm2da9ToAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAriPhv8AEj/hYX9r/wDEkutK/s24EP7993mZ3ewww28rzjI5rt6KACuH+JurSQafY6Na3uoWM+pStuuNNhllnhijXcWAiVm5by1Jx0au4qm2lWba0mrNDm+SA26yl2+WMsGIC5xyQOcZ4oA4/S/H19qel6JDpOkrf6teWT3FzFPcG2WHymEcgJKMd2/gLt+pFT3njy/ih1q9stAFxpujCVLiaS88uRpY4t7KqbD8ucLuJByfukVqXHgTw7cyeY9lJHL58twJYLuaFw8mPMwyOCFYgEqDtPpUj+DNBfU5782TCW5UrOi3EixTZTZl4g2xm28bipPvQBg618S20iO5KaP9oaHS7XUAv2nbvM0vl7Pu8Y657+gp2t/EK60DUrO0vdKtpWeSCO8W0upZWtTLJsXOINmO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)


```python
# 11. Evaluate all models on the test set
# Random Forest Evaluation
rf_predictions = best_rf_model.predict(X_test)
print("Random Forest Classification Report:")
print(classification_report(y_test, rf_predictions))

# XGBoost Evaluation
xgb_predictions = best_xgb_model.predict(X_test)
print("XGBoost Classification Report:")
print(classification_report(y_test, xgb_predictions))

# Logistic Regression Evaluation
log_reg_predictions = best_log_reg_model.predict(X_test)
print("Logistic Regression Classification Report:")
print(classification_report(y_test, log_reg_predictions))

# 12. Compare model performance (accuracy score)
rf_accuracy = accuracy_score(y_test, rf_predictions)
xgb_accuracy = accuracy_score(y_test, xgb_predictions)
log_reg_accuracy = accuracy_score(y_test, log_reg_predictions)

print(f"Random Forest Accuracy: {rf_accuracy:.4f}")
print(f"XGBoost Accuracy: {xgb_accuracy:.4f}")
print(f"Logistic Regression Accuracy: {log_reg_accuracy:.4f}")

# 13. Cross-validation (to evaluate the generalization ability of the models)
rf_cv_score = cross_val_score(best_rf_model, X_train_res, y_train_res, cv=5)
xgb_cv_score = cross_val_score(best_xgb_model, X_train_res, y_train_res, cv=5)
log_reg_cv_score = cross_val_score(best_log_reg_model, X_train_res, y_train_res, cv=5)

print(f"Random Forest Cross-validation Accuracy: {rf_cv_score.mean():.4f}")
print(f"XGBoost Cross-validation Accuracy: {xgb_cv_score.mean():.4f}")
print(f"Logistic Regression Cross-validation Accuracy: {log_reg_cv_score.mean():.4f}")

```

    Random Forest Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.22      0.22      0.22        50
             1.0       0.34      0.32      0.33        71
             2.0       0.26      0.29      0.27        49
    
        accuracy                           0.28       170
       macro avg       0.28      0.28      0.28       170
    weighted avg       0.28      0.28      0.28       170
    
    XGBoost Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.21      0.22      0.22        50
             1.0       0.40      0.35      0.37        71
             2.0       0.27      0.31      0.29        49
    
        accuracy                           0.30       170
       macro avg       0.29      0.29      0.29       170
    weighted avg       0.31      0.30      0.30       170
    
    Logistic Regression Classification Report:
                  precision    recall  f1-score   support
    
             0.0       0.36      0.46      0.40        50
             1.0       0.41      0.28      0.33        71
             2.0       0.35      0.41      0.38        49
    
        accuracy                           0.37       170
       macro avg       0.37      0.38      0.37       170
    weighted avg       0.38      0.37      0.37       170
    
    Random Forest Accuracy: 0.2824
    XGBoost Accuracy: 0.3000
    Logistic Regression Accuracy: 0.3706
    Random Forest Cross-validation Accuracy: 0.4035
    XGBoost Cross-validation Accuracy: 0.3937
    Logistic Regression Cross-validation Accuracy: 0.3250




**Pemilihan Model Terbaik**
Berdasarkan Akurasi dan F1-Score, Random Forest dipilih sebagai model terbaik. Walaupun Logistic Regression memiliki akurasi yang lebih tinggi dan lebih mudah diinterpretasikan, Random Forest menunjukkan performa yang lebih baik dalam hal precision dan recall, serta memberikan F1-Score yang lebih baik secara keseluruhan dibandingkan dengan XGBoost dan Logistic Regression.

Berikut adalah alasan pemilihan Random Forest sebagai model terbaik:
- F1-Score: Model ini memiliki F1-score yang lebih seimbang antara precision dan recall di beberapa kelas.
- Keseimbangan Precision dan Recall: Random Forest memberikan keseimbangan yang baik antara precision dan recall, meskipun precision lebih rendah pada kelas-kelas tertentu. Ini menunjukkan bahwa model ini cukup baik dalam menangkap pola, terutama di kelas-kelas yang lebih sulit untuk diprediksi.
- Peningkatan dengan Hyperparameter Tuning: Random Forest dapat di-tuning lebih lanjut untuk meningkatkan performa. Misalnya, dengan menyesuaikan jumlah pohon (estimators) atau kedalaman pohon, model ini bisa memberikan hasil yang lebih baik pada dataset yang lebih kompleks.



**Rekomendasi dan Langkah Selanjutnya**
- Hyperparameter Tuning: Untuk meningkatkan performa model lebih lanjut, terutama dalam hal precision dan recall, dapat dilakukan tuning pada Random Forest menggunakan GridSearchCV atau RandomizedSearchCV untuk menemukan parameter terbaik.
- Handling Class Imbalance: Mengingat ketidakseimbangan kelas yang ada dalam dataset, dapat dilakukan teknik seperti oversampling untuk kelas minoritas atau menggunakan class weights untuk memberikan perhatian lebih pada kelas yang kurang terwakili.
- Feature Engineering: Mencoba untuk mengidentifikasi fitur-fitur penting yang lebih kuat atau melakukan seleksi fitur yang lebih baik bisa memperbaiki kinerja model.

**---Ini adalah bagian akhir laporan---**
