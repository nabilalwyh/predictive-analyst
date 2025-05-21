# Laporan Proyek Machine Learning - Nabila Alawiyah

## Domain Proyek
Obesitas adalah kondisi medis yang ditandai oleh akumulasi lemak tubuh yang berlebihan, yang dapat meningkatkan risiko berbagai penyakit kronis seperti diabetes tipe 2, penyakit jantung, hipertensi, dan beberapa jenis kanker. Di Indonesia, obesitas telah menjadi masalah kesehatan masyarakat yang signifikan, dengan prevalensi yang terus meningkat dalam beberapa tahun terakhir.

Berdasarkan data Riset Kesehatan Dasar (Riskesdas) 2018, prevalensi obesitas pada penduduk dewasa di Indonesia mencapai 21,8%, meningkat dari 14,8% pada tahun 2013 . Peningkatan ini menunjukkan tren yang mengkhawatirkan, mencerminkan perubahan pola hidup masyarakat yang cenderung kurang aktif secara fisik dan mengonsumsi makanan tinggi kalori.

Dampak ekonomi dari obesitas juga signifikan. Obesitas menyita 8-16% anggaran biaya kesehatan nasional, dan pada tahun 2016, dampak total (langsung dan tidak langsung) dari obesitas diperkirakan sebesar 2-4 miliar dolar AS . Biaya ini mencakup perawatan medis, kehilangan produktivitas, dan beban pada sistem kesehatan secara keseluruhan.

Melihat tren peningkatan prevalensi obesitas dan dampaknya yang luas, diperlukan upaya kolaboratif antara pemerintah, masyarakat, dan sektor swasta untuk mengatasi krisis kesehatan ini secara komprehensif dan berkelanjutan. Intervensi berbasis komunitas, kampanye kesehatan, dan regulasi industri makanan menjadi langkah strategis untuk menekan laju peningkatan obesitas di Indonesia.

## Business Understanding

### Problem Statements
Rumusan masalah dari latar belakang diatas adalah:
1.  Faktor apa saja yang paling berpengaruh terhadap tingkat obesitas seseorang?
2. Bagaimana cara memanfaatkan informasi pola hidup guna memprediksi kategori diabetes pada seseorang?
3. Bagaimana riwayat obesitas dari keluarga memengaruhi level diabetes seseorang?

### Goals
Berdasarkan problem statements, berikut tujuan yang ingin dicapai pada proyek ini.
1. Mengetahui faktor apa saja yang paling berpengaruh terhadap tingkat obesitas seseorang
2. Mengetahui cara memanfaatkan informasi pola hidup guna memprediksi kategori diabetes pada seseorang
3. Mengetahui hubungan bagaimana riwayat obesitas dari keluarga memengaruhi level diabetes seseorang

### Solution statements
1. Melakukan analisis statistik atau membangun model machine learning untuk mengukur seberapa kuat hubungan dan kontribusi tiap faktor terhadap target (tingkat obesitas), sehingga faktor-faktor utama yang paling berpengaruh dapat diidentifikasi.
2. Menerapkan berbagai algoritma machine learning dan membandingkan hasil performanya untuk menemukan model dengan akurasi terbaik dalam memprediksi tingkat obesitas berdasarkan riwayat kesehatan dan aktivitas seseorang, kemudian menggunakan model terbaik tersebut untuk melakukan prediksi (inference).
3. Melakukan analisis menggunakan variable terkait, untuk memahami kaitan antara riwayat obesitas keluarga dengan tingkat diabetes yang dialami oleh seseorang

### Metodologi
Tujuan yang ingin dicapai dalam proyek ini adalah memprediksi level diabetes seseorang berdasarkan penelitian yang ada. Metodologi prediktif yang digunakan berfokus pada pembangunan model klasifikasi dengan level diabetes sebagai target utama.

### Metrik
Metrik yang digunakan untuk mengevaluasi seberapa baik model klasifikasi merupakan confusion matrix. confusion matrix merupakan suatu metode yang digunakan untuk melakukan perhitungan akurasi pada konsep data mining.

## Data Understanding
Dataset yang digunakan untuk memprediksi tingkat diabetes seseorang diambil dari platform open source Kaggle dan dipublikasikan oleh fatemehmehrparvar. Dataset ini mencakup data untuk memperkirakan tingkat obesitas pada individu yang berasal dari negara Meksiko, Peru, dan Kolombia, berdasarkan kebiasaan makan dan kondisi fisik mereka. Dataset ini terdiri dari 17 atribut dan 2111 data entri, di mana setiap entri telah diberi label pada variabel kelas NObesity (Tingkat Obesitas). Label tersebut mengklasifikasikan data ke dalam kategori: 
- Kekurangan Berat Badan,
- Berat Normal,
- Kelebihan Berat Level I,
- Kelebihan Berat Level II,
- Obesitas Tipe I,
- Obesitas Tipe II,
- Obesitas Tipe III.

### Variabel-variabel yang memengaruhi level diabetes seseorang adalah sebagai berikut:
| Variabel                      | Keterangan                                                                                             |
|-------------------------------|--------------------------------------------------------------------------------------------------------|
| Gender                       | Jenis kelamin                                                                                          |
| Age                          | Usia (dalam tahun)                                                                                     |
| Height                       | Tinggi badan (dalam meter)                                                                             |
| Weight                       | Berat badan (dalam kilogram)                                                                           |
| family_history_with_overweight | Apakah ada anggota keluarga yang menderita atau pernah menderita kelebihan berat badan?                |
| FAVC                         | Apakah sering mengonsumsi makanan berkalori tinggi?                                                    |
| FCVC                         | Apakah biasanya mengonsumsi sayuran dalam makanan?                                                     |
| NCP                          | Berapa kali makan utama yang dikonsumsi setiap hari?                                                   |
| CAEC                         | Apakah mengonsumsi makanan di antara waktu makan utama?                                                |
| SMOKE                        | Apakah merokok?                                                                                        |
| CH2O                         | Berapa banyak air yang diminum setiap hari?                                                             |
| SCC                          | Apakah memantau jumlah kalori yang dikonsumsi setiap hari?                                             |
| FAF                          | Seberapa sering melakukan aktivitas fisik?                                                             |
| TUE                          | Berapa lama menggunakan perangkat teknologi (misal: ponsel, video game, TV, komputer) setiap hari?      |
| CALC                         | Seberapa sering mengonsumsi alkohol?                                                                   |
| MTRANS                       | Moda transportasi yang biasa digunakan sehari-hari                                                     |
| NObeyesdad                   | Tingkat obesitas (target prediksi)                                                                     |

### Exploratory Data Analysis - Univariate Analysis
Melakukan Univariate Analysis untuk numerical dan categorical features.

#### 1. Numerical Features

Numerical Features pada dataset ini terdiri atas: ['Age', 'Height', 'Weight', 'FCVC', 'NCP', 'CH2O', 'FAF', 'TUE']

<p align="center">
  <img src="https://github.com/user-attachments/assets/5763ba41-1a43-42b7-ae39-8884b98c1b64" width="1000"/>
</p>

Gambar di atas dapat diinterpretasikan sebagai berikut.
1. Plot jumlah berdasarkan `Gender` menunjukkan bahwa jumlah responden pria dan wanita relatif seimbang.
2. Plot jumlah berdasarkan `Family History with Overweight` menunjukkan bahwa mayoritas responden memiliki riwayat keluarga yang mengalami kelebihan berat badan.
3. Plot jumlah berdasarkan `High Caloric Food Consumption (FAVC)` menunjukkan bahwa sebagian besar responden sering mengonsumsi makanan tinggi kalori.
4. Plot jumlah berdasarkan `Food Consumption Between Meals (CAEC)` menunjukkan bahwa sebagian besar responden kadang-kadang mengonsumsi camilan di antara waktu makan.
5. Plot jumlah berdasarkan `Smoke` menunjukkan bahwa mayoritas responden tidak merokok.
6. Plot jumlah berdasarkan `Calorie Monitoring (SCC)` menunjukkan bahwa sebagian besar responden tidak memantau jumlah kalori yang mereka konsumsi.
7. Plot jumlah berdasarkan `Alcohol Consumption Frequency (CALC)` menunjukkan bahwa sebagian besar responden kadang-kadang mengonsumsi alkohol, disusul oleh mereka yang tidak mengonsumsinya sama sekali.
8. Plot jumlah berdasarkan `Mode of Transportation (MTRANS)` menunjukkan bahwa mayoritas responden menggunakan transportasi umum dalam kegiatan sehari-hari.
9. Plot jumlah berdasarkan `Obesity Levels (NObeyesdad)` menunjukkan distribusi kelas yang cukup merata, dengan kategori Overweight Level II sebagai yang paling banyak, diikuti oleh Obesity Type III.

#### 2. Categorical Features
Categorical Features pada dataset ini terdiri atas: ['Gender', 'family_history_with_overweight', 'FAVC', 'CAEC', 'SMOKE', 'SCC', 'CALC', 'MTRANS', 'NObeyesdad']

<p align="center">
  <img src="https://github.com/user-attachments/assets/4b4ed0ff-a075-4a64-b6a1-176714991d84" width="1000"/>
</p>

Gambar di atas dapat diinterpretasikan sebagai berikut.
1. Histogram dari `Height` menunjukkan distribusi yang mendekati normal,
2. Histogram dari `Weight` memiliki distribusi yang lebih bervariasi.
3. Histogram `FCVC` (frekuensi konsumsi sayur) menunjukkan tren kuat pada nilai 2 dan 3, yang berarti sebagian besar responden cukup sering mengonsumsi sayur.
4. Histogram `NCP` (jumlah makan per hari) menunjukkan mayoritas responden makan 3 kali sehari.
5. Histogram dari `CH2O` (konsumsi air) menunjukkan mayoritas responden minum sekitar 2 liter air per hari.
6. Histogram `FAF` (frekuensi aktivitas fisik) menunjukkan bahwa sebagian besar responden memiliki tingkat aktivitas fisik yang rendah, mendekati angka 0.
7. Histogram `TUE` (durasi penggunaan teknologi) juga menunjukkan nilai yang rendah pada sebagian besar responden, yang mengindikasikan bahwa mereka jarang menggunakan perangkat teknologi dalam keseharian.
8. Histogram `Age` memiliki distribusi yang miring ke kanan (right-skewed), yang berarti sebagian besar responden berusia muda, atau berada di bawah rata-rata usia keseluruhan.

### Exploratory Data Analysis - Multivariate Analysis
Melakukan Multivariate Analysis untuk menganalisis hubungan antar variabel

#### 1. Membandingkan kondisi level obesitas dengan riwayat kelebihan berat badan
<p align="center">
  <img src="https://github.com/user-attachments/assets/346d24c2-46dc-447d-b6ed-b3efe423d895" width="600"/>
</p>

  > **Insight:**
  > - Mayoritas penderita obesitas memiliki riwayat keluarga overweight
  >
  > - Orang tanpa riwayat keluarga overweight lebih banyak berada di kategori berat badan kurang (Insufficient Weight)

#### 2. Membandingkan level obesitas dengan umur
<p align="center">
  <img src="https://github.com/user-attachments/assets/79b7d659-6e15-4c04-949a-ba5942b54a92" width="600"/>
</p>

  > **Insight:**
  > - Obesitas bisa terjadi di segala usia, tetapi lebih umum pada usia 20–35 tahun
  > - Kategori Obesity_Type_III paling terkonsentrasi di usia sekitar 21–27 tahun
  > - Usia muda memiliki variasi status berat badan yang tinggi, mulai dari kekurangan hingga kelebihan berat badan.

#### 3. Membandingkan level obesitas dengan pola konsumsi makan
<p align="center">
  <img src="https://github.com/user-attachments/assets/00a4ab93-1270-4189-99b9-3b9da5645fe2" width="1000"/>
</p>

  > **Insight:**
  > - Konsumsi makanan berkalori tinggi (FAVC) berkorelasi positif dengan peningkatan tingkat obesitas.
  > - Meskipun kebiasaan ngemil lebih sering ditemukan pada individu obesitas (terutama tipe ringan hingga sedang), namun kategori Insufficient Weight juga menunjukkan frekuensi ngemil yang tinggi, yang menunjukkan bahwa frekuensi ngemil saja tidak cukup menjelaskan obesitas — perlu dilihat juga jenis camilan dan pola konsumsi lainnya.
  > - Rata-rata semua kategori obesitas memiliki jumlah makan utama sekitar 3 kali/hari, mirip dengan kategori berat badan normal. Tapi, Insufficient Weight memiliki sebaran nilai lebih tinggi (hingga 4× sehari).
  > - Konsumsi sayur tidak signifikan membedakan level obesitas; banyak individu obesitas tetap mengonsumsi sayur.
  > - Faktor yang paling kuat berhubungan dengan obesitas dari visualisasi ini adalah FAVC (makanan tinggi kalori), diikuti oleh CAEC (ngemil di luar waktu makan utama). Sedangkan jumlah makan utama (NCP) dan konsumsi sayur (FCVC) memiliki pengaruh yang tidak begitu jelas terhadap level obesitas berdasarkan grafik ini.
 
#### 4. Membandingkan kondisi level obesitas dengan kebiasaan merokok dan konsumsi alkohol
<p align="center">
  <img src="https://github.com/user-attachments/assets/db3eed58-8d94-4557-9451-b516e6eb8ff0" width="1000"/>
</p>

  > **Insight:**
  > - Level obesitas seseorang tidak ditentukan dengan kebiasaan merokok.
  > - Konsumsi alkohol kadang-kadang (Sometimes) paling banyak terjadi pada semua kategori obesitas, termasuk kategori obesitas tertinggi (Obesity_Type_III). Responden yang tidak minum alkohol (CALC = no) mendominasi beberapa kategori awal (seperti Normal_Weight dan Obesity_Type_I), tetapi jumlahnya menurun drastis pada level obesitas paling tinggi.

#### 5. Membandingkan kondisi level obesitas dengan Moda transportasi yang biasa digunakan sehari-hari
<p align="center">
  <img src="https://github.com/user-attachments/assets/e694aa4a-6418-4508-8ecb-a92b036a17c1" width="600"/>
</p>

  > **Insight:**
  > - Transportasi yang tidak aktif secara fisik (seperti public transportation dan mobil pribadi) lebih umum digunakan oleh individu dengan tingkat obesitas lebih tinggi. Sebaliknya, orang yang memilih berjalan kaki atau bersepeda cenderung memiliki berat badan normal atau malah kurang.

#### 6. Membandingkan kondisi level obesitas dengan kebiasaan memantau kalori
<p align="center">
  <img src="https://github.com/user-attachments/assets/a251a912-c017-46f1-81d0-843e90cab49e" width="600"/>
</p>

  > **Insight:**
  > - Responden dengan level obesitas tipe 3 tidak ada yang melakukan perhitungan jumlah kalori, sementara pada level lainnya beberapa melakukan hal tersebut.

#### 7. Mengetahui distribusi BMI
<p align="center">
  <img src="https://github.com/user-attachments/assets/4319c8a2-3300-4808-8093-563e762f28e9" width="600"/>
</p>

  > **Insight:**
  > - Semakin tinggi level obesitas, semakin tinggi pula nilai median dan sebaran BMI-nya.
  > - BMI merupakan indikator yang sangat kuat dan konsisten dalam membedakan level obesitas.

## Data Preparation
### Data Cleaning
#### Menangani Data Duplikat
##### 1. Menghitung jumlah data duplikat
<p align="center">
  <img src="https://github.com/user-attachments/assets/091b34fa-5d68-4769-82cc-457ce857027d" width="300"/>
</p>

  > Berdasarkan program di atas, maka diketahui bahwa terdapat 24 data duplikat.

##### 2. Menampilkan baris data yang duplikat 
<p align="center">
  <img src="https://github.com/user-attachments/assets/afd8eed2-7105-4cce-b8a8-0f0f5bf9e561" width="1000"/>
</p>
  
  > Dari hasil di atas, terlihat bahwa ada data-data tersebut memang terduplikasi. Oleh karena itu, data duplikat ini akan dihapus.

##### 3. Menghapus baris data yang duplikat 
<p align="center">
  <img src="https://github.com/user-attachments/assets/ffda9ec5-f11e-4c8d-b365-1d57fc476151" width="300"/>
</p>
  
  > Setelah program di atas dijalankan, maka sudah tidak ada lagi data yang duplikat.

#### Menangani Missing Value
##### 1. Menampilkan data missing value
<p align="center">
  <img src="https://github.com/user-attachments/assets/f5331f7b-9246-48b7-8871-c5d544ee6bd4" width="300"/>
</p>

  > Berdasarkan output sebelumnya, tidak ditemukan nilai missing pada dataset df_filtered. Namun, penting untuk memeriksa keberadaan nilai nol pada setiap kolom, karena pada fitur seperti Gender, Weight, Height, CH2O, dan FCVC, nilai 0 tidak logis secara medis maupun perilaku konsumsi. Selain itu, perlu memeriksa nilai nan atau NaN pada kolom kategorikal. Nilai nol dan nan yang secara tidak sengaja dianggap valid dapat menjadi representasi nilai yang hilang (missing) dan berisiko menurunkan performa model machine learning yang dibangun.

##### 2. Memeriksa apakah ada data umur, tinggi dan berat badan yang bernilai 0.
<p align="center">
  <img src="https://github.com/user-attachments/assets/57fc6c2a-0fe3-4c1c-a1c1-29cbdb570930" width="300"/>
</p>

  > Setelah dicek, tidak ada data dari umur, tinggi dan berat badan yang bernilai 0.

##### 3. Menangani nilai nan pada data kategorikal feature
<p align="center">
  <img src="https://github.com/user-attachments/assets/6de8abba-36cf-4f16-9466-4757188c72d1" width="1000"/>
</p>

  > Program di atas digunakan untuk mengganti nilai yang dianggap missing tapi bukan np.nan menjadi np.nan, lalu menghapusnya dengan program berikut.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f36df395-3f34-4b92-8b99-1a437d04cddc" width="300"/>
</p>

#### Menangani Outliers dengan IQR Method
##### 1. Menampilkan analisis statistik
<p align="center">
  <img src="https://github.com/user-attachments/assets/80627d43-7d0e-428e-946d-517bc24d2676" width="1000"/>
</p>

  > Fungsi `describe()` memberikan informasi statistik pada masing-masing kolom, antara lain:
  > - `Count` adalah jumlah sampel pada data.
  > - `Mean` adalah nilai rata-rata.
  > - `Std` adalah standar deviasi.
  > - `Min` yaitu nilai minimum setiap kolom.
  > - `25%` adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval dalam empat bagian sebaran yang sama.
  > - `50%` adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
  > -` 75%` adalah kuartil ketiga.
  > - `Max` adalah nilai maksimum.

##### 2. Mengecek data outlier dan memvisualisasikannya
<p align="center">
  <img src="https://github.com/user-attachments/assets/f28dc028-f949-4a82-ba0c-79664d3db88d" width="1000"/>
</p>

  > Program di atas akan menampilkan hasil visualisasi sebagai berikut:

<p align="center">
  <img src="https://github.com/user-attachments/assets/28f94a59-0b91-4356-9bd0-3960714fa053" width="1000"/>
</p>

  > **Berikut adalah interpretasi dari boxplot di atas.**
  > - Pada kolom Age, mayoritas responden berusia antara 20 hingga 25 tahun. Terdapat sejumlah responden dengan usia di atas 35 tahun, namun nilai tersebut masih wajar secara biologis dan tidak akan dihapus dari dataset.
  > - Pada kolom `Weight`, dapat dilihat bahwa mayoritas responden memiliki berat badan di rentang 60-100 kilogram. Terdapat satu outlier, yaitu memiliki berat badan 173 kg. Meski demikian, outlier ini tidak akan dihapus karena sangat memungkinkan seseorang obesitas memiliki berat badan ekstrem.
  > - Pada kolom `Height`, dapat dilihat bahwa mayoritas responden memiliki tinggi badan di rentang 1,6-1,7 meter. Terdapat satu outlier, yaitu memiliki tinggi badan hampir 2 meter. Meski demikian, outlier ini tidak akan dihapus karena sangat memungkinkan seseorang memiliki tinggi badan tersebut.
  > - Pada kolom `NCP`, mayoritas responden makan sebanyak 3 kali sehari. Terdapat variasi jumlah makan dari 1 hingga 4 kali per hari. Nilai-nilai ini masih dianggap wajar karena dapat mencerminkan pola makan individu seperti diet tertentu atau program peningkatan massa otot.
  > - Pada kolom `CH2O`,  dapat dilihat bahwa tidak ada outlier. Rata-rata responden minum air sebanyak 1,5-2,5 liter air.
  > - Pada kolom-kolom lainnya seperti `FCVC`, `FAF`, dan `TUE`, persebaran data terlihat relatif normal dan tidak menunjukkan nilai ekstrem yang mencolok berdasarkan statistik deskriptif.
  >
  >
  > **Kesimpulan:**
  > Dari hasil analisis statistik deskriptif, dapat disimpulkan bahwa beberapa fitur seperti Age, Weight, Height, dan NCP menunjukkan keberadaan nilai yang tergolong ekstrem namun masih valid secara biologis dan kontekstual. Oleh karena itu, nilai-nilai tersebut tidak dihapus dari dataset karena tetap relevan untuk analisis obesitas. Sementara itu, fitur lain seperti CH2O, FAF, dan TUE menunjukkan distribusi data yang relatif normal tanpa adanya nilai yang mencolok sebagai outlier.

### Encoding Categorical
Encoding Kategorikal dilakukan terhadap variabel yang hanya berisi antara `yes` (iya) dan `no` (tidak), yaitu pada variable:
* `FAVC` (Apakah sering mengonsumsi makanan berkalori tinggi?),
* `SCC` (Apakah memantau jumlah kalori yang dikonsumsi setiap hari?),
* `SMOKE` (Apakah merokok?),
* `family_history_with_overweight` (Apakah ada anggota keluarga yang menderita atau pernah menderita kelebihan berat badan?)
Berikut adalah program untuk melakukan encoding categorical.
<p align="center">
  <img src="https://github.com/user-attachments/assets/157877a4-2663-4520-9c33-f0e06d66f473" width="300"/>
</p>

### One Hot Encoding 
One Hot Encoding dilakukan terhadap 4 variabel, yaitu
* Gender – Male, Female
* CALC – no, Sometimes, Frequently
* CAEC – no, Sometimes, Frequently, dll
* MTRANS – Public_Transportation, Walking, Automobile, Bike, Motorbike (atau lainnya)
karena kategori-kategori pada variabel tersebut memiliki urutan tertentu.
Berikut adalah program untuk melakukan one hot encoding.
<p align="center">
  <img src="https://github.com/user-attachments/assets/84d79ee1-7611-407f-a01a-b0d4c87dd8a3" width="300"/>
</p>

### Dataset akhir yang sudah melalui tahap data preparation
<p align="center">
  <img src="https://github.com/user-attachments/assets/a6696e54-76eb-4b6c-8fb6-7fcb6b10136a" width="1000"/>
</p>

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

