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
| Variabel                          | Keterangan                                                                                         | Contoh Jawaban |
| --------------------------------- | -------------------------------------------------------------------------------------------------- | -------------- |
| Gender                            | Jenis kelamin                                                                                      | Female / Male |
| Age                               | Usia (dalam tahun)                                                                                 | 21.0            |
| Height                            | Tinggi badan (dalam meter)                                                                         | 1.8        |
| Weight                            | Berat badan (dalam kilogram)                                                                       | 68.6        |
| family\_history\_with\_overweight | Apakah ada anggota keluarga yang menderita atau pernah menderita kelebihan berat badan?            | Yes / no        |
| FAVC                              | Apakah sering mengonsumsi makanan berkalori tinggi?                                                | Yes / no        |
| FCVC                              | Apakah biasanya mengonsumsi sayuran dalam makanan?                                                 | Yes / no        |
| NCP                               | Berapa kali makan utama yang dikonsumsi setiap hari?                                               | 1 - 4        |
| CAEC                              | Seberapa sering makan makanan di antara waktu makan utama?                                         | no, sometimes, frequently, always         |
| SMOKE                             | Apakah merokok?                                                                                    | Yes / no        |
| CH2O                              | Berapa banyak air yang diminum setiap hari?                                                        | 1 - 3        |
| SCC                               | Apakah memantau jumlah kalori yang dikonsumsi setiap hari?                                         | Yes / no        |
| FAF                               | Seberapa sering melakukan aktivitas fisik?                                                         | 0 - 3        |
| TUE                               | Seberapa sering menggunakan perangkat teknologi (misal: ponsel, video game, TV, komputer) setiap hari? | 0 - 2        |
| CALC                              | Seberapa sering mengonsumsi alkohol?                                                               | no, sometimes, frequently, always         |
| MTRANS                            | Moda transportasi yang biasa digunakan sehari-hari                                                 | Public_Transportation, Walking, Automobile, Motorbike, Bike         |
| NObeyesdad                        | Tingkat obesitas (target prediksi)                                                                 | Normal_Weight, Overweight_level_I, Overweight_level_II, Obesity_Type_I, Obesity_Type_II, Obesity_Type_III
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

#### 1. Mengetahui hubungan level obesitas dengan riwayat kelebihan berat badan
<p align="center">
  <img src="https://github.com/user-attachments/assets/346d24c2-46dc-447d-b6ed-b3efe423d895" width="600"/>
</p>

  > **Insight:**
  > - Mayoritas penderita obesitas memiliki riwayat keluarga overweight
  >
  > - Orang tanpa riwayat keluarga overweight lebih banyak berada di kategori berat badan kurang (Insufficient Weight)

#### 2. Mengetahui hubungan level obesitas dengan umur
<p align="center">
  <img src="https://github.com/user-attachments/assets/79b7d659-6e15-4c04-949a-ba5942b54a92" width="600"/>
</p>

  > **Insight:**
  > - Obesitas bisa terjadi di segala usia, tetapi lebih umum pada usia 20–35 tahun
  > - Kategori Obesity_Type_III paling terkonsentrasi di usia sekitar 21–27 tahun
  > - Usia muda memiliki variasi status berat badan yang tinggi, mulai dari kekurangan hingga kelebihan berat badan.

#### 3. Mengetahui hubungan level obesitas dengan pola konsumsi makan
<p align="center">
  <img src="https://github.com/user-attachments/assets/00a4ab93-1270-4189-99b9-3b9da5645fe2" width="1000"/>
</p>

  > **Insight:**
  > - Konsumsi makanan berkalori tinggi (FAVC) berkorelasi positif dengan peningkatan tingkat obesitas.
  > - Meskipun kebiasaan ngemil lebih sering ditemukan pada individu obesitas (terutama tipe ringan hingga sedang), namun kategori Insufficient Weight juga menunjukkan frekuensi ngemil yang tinggi, yang menunjukkan bahwa frekuensi ngemil saja tidak cukup menjelaskan obesitas — perlu dilihat juga jenis camilan dan pola konsumsi lainnya.
  > - Rata-rata semua kategori obesitas memiliki jumlah makan utama sekitar 3 kali/hari, mirip dengan kategori berat badan normal. Tapi, Insufficient Weight memiliki sebaran nilai lebih tinggi (hingga 4× sehari).
  > - Konsumsi sayur tidak signifikan membedakan level obesitas; banyak individu obesitas tetap mengonsumsi sayur.
  > - Faktor yang paling kuat berhubungan dengan obesitas dari visualisasi ini adalah FAVC (makanan tinggi kalori), diikuti oleh CAEC (ngemil di luar waktu makan utama). Sedangkan jumlah makan utama (NCP) dan konsumsi sayur (FCVC) memiliki pengaruh yang tidak begitu jelas terhadap level obesitas berdasarkan grafik ini.
 
#### 4. Mengetahui hubungan level obesitas dengan kebiasaan merokok dan konsumsi alkohol
<p align="center">
  <img src="https://github.com/user-attachments/assets/db3eed58-8d94-4557-9451-b516e6eb8ff0" width="1000"/>
</p>

  > **Insight:**
  > - Level obesitas seseorang tidak ditentukan dengan kebiasaan merokok.
  > - Konsumsi alkohol kadang-kadang (Sometimes) paling banyak terjadi pada semua kategori obesitas, termasuk kategori obesitas tertinggi (Obesity_Type_III). Responden yang tidak minum alkohol (CALC = no) mendominasi beberapa kategori awal (seperti Normal_Weight dan Obesity_Type_I), tetapi jumlahnya menurun drastis pada level obesitas paling tinggi.

#### 5. Mengetahui hubungan level obesitas dengan Moda transportasi yang biasa digunakan sehari-hari
<p align="center">
  <img src="https://github.com/user-attachments/assets/e694aa4a-6418-4508-8ecb-a92b036a17c1" width="600"/>
</p>

  > **Insight:**
  > - Transportasi yang tidak aktif secara fisik (seperti public transportation dan mobil pribadi) lebih umum digunakan oleh individu dengan tingkat obesitas lebih tinggi. Sebaliknya, orang yang memilih berjalan kaki atau bersepeda cenderung memiliki berat badan normal atau malah kurang.

#### 6. Mengetahui hubungan level obesitas dengan kebiasaan memantau kalori
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

### Data Quality Verification
#### Memeriksa data duplikat
##### 1. Menghitung jumlah data duplikat
<p align="center">
  <img src="https://github.com/user-attachments/assets/091b34fa-5d68-4769-82cc-457ce857027d" width="300"/>
</p>

  > Berdasarkan program di atas, maka diketahui bahwa terdapat 24 data duplikat.

#### Memeriksa data missing value
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

#### Memeriksa Outliers dengan IQR Method
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
  <img src="https://github.com/user-attachments/assets/23a7f903-4084-4591-b1c0-19a6cdc0bad2" width="1000"/>
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

## Data Preparation
### Data Cleaning
#### Menangani Data Duplikat
##### 1. Menampilkan baris data yang duplikat 
<p align="center">
  <img src="https://github.com/user-attachments/assets/afd8eed2-7105-4cce-b8a8-0f0f5bf9e561" width="1000"/>
</p>
  
  > Dari hasil di atas, terlihat bahwa ada data-data tersebut memang terduplikasi. Oleh karena itu, data duplikat ini akan dihapus.

##### 2. Menghapus baris data yang duplikat 
<p align="center">
  <img src="https://github.com/user-attachments/assets/ffda9ec5-f11e-4c8d-b365-1d57fc476151" width="300"/>
</p>
  
  > Setelah program di atas dijalankan, maka sudah tidak ada lagi data yang duplikat.

#### Menangani Missing Value
##### 1. Menangani nilai nan pada data kategorikal feature
<p align="center">
  <img src="https://github.com/user-attachments/assets/6de8abba-36cf-4f16-9466-4757188c72d1" width="1000"/>
</p>

  > Program di atas digunakan untuk mengganti nilai yang dianggap missing tapi bukan np.nan menjadi np.nan, lalu menghapusnya dengan program berikut.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f36df395-3f34-4b92-8b99-1a437d04cddc" width="300"/>
</p>

### Encoding Categorical
Encoding Kategorikal dilakukan terhadap variabel yang hanya berisi antara `yes` (iya) dan `no` (tidak), yaitu pada variable:
* `FAVC` (Apakah sering mengonsumsi makanan berkalori tinggi?),
* `SCC` (Apakah memantau jumlah kalori yang dikonsumsi setiap hari?),
* `SMOKE` (Apakah merokok?),
* `family_history_with_overweight` (Apakah ada anggota keluarga yang menderita atau pernah menderita kelebihan berat badan?)
Berikut adalah program untuk melakukan encoding categorical.
<p align="center">
  <img src="https://github.com/user-attachments/assets/157877a4-2663-4520-9c33-f0e06d66f473" width="800"/>
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
  <img src="https://github.com/user-attachments/assets/84d79ee1-7611-407f-a01a-b0d4c87dd8a3" width="800"/>
</p>

### Dataset akhir yang sudah melalui tahap data preparation
<p align="center">
  <img src="https://github.com/user-attachments/assets/a6696e54-76eb-4b6c-8fb6-7fcb6b10136a" width="1000"/>
</p>

### Data Splitting
Target pada dataset ini adalah variabel `NObeyesdad` untuk mengetahui akurasi prediksi dari NObeyesdad, maka akan menghapus kolom tersebut dari data dan assign kolom tersebut ke variabel baru. Selanjutnya, melakukan split data dengan skema data training sebesar 80% untuk melatih model dan 20% untuk menguji model.
<p align="center">
  <img src="https://github.com/user-attachments/assets/08875066-dc77-4c86-bd28-58c6a5b991f0" width="1000"/>
</p>

### Normalisasi
Algoritma machine learning memiliki performa lebih baik dan konvergen lebih cepat ketika dimodelkan pada data dengan skala relatif sama atau mendekati distribusi normal. Proses scaling dan normalisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma dengan range 0 hingga 1 dan menyeragamkan karena memiliki satuan yang berbeda pada tiap fitur.
#### 1. Melakukan normalisasi pada data training
<p align="center">
  <img src="https://github.com/user-attachments/assets/75a7f387-1077-4186-8e3f-c57eb71185fc" width="1000"/>
</p>

#### 2. Melakukan normalisasi pada data testing 
<p align="center">
  <img src="https://github.com/user-attachments/assets/3096de0b-90b1-425d-a0e5-d2ff10125f25" width="1000"/>
</p>

## Modeling
### 1. Algoritma XGBoost
XGBoost (Extreme Gradient Boosting) adalah algoritma machine learning berbasis teknik gradient boosting yang sangat populer dan efisien untuk masalah klasifikasi dan regresi. Inti dari XGBoost adalah membangun model secara bertahap dengan cara menggabungkan banyak decision tree secara berurutan, di mana setiap pohon baru bertujuan untuk memperbaiki kesalahan (residual error) yang dihasilkan oleh model sebelumnya. Dalam model ini, parameter yang digunakan adalah: 
- max_depth = 5. Menentukan kedalaman maksimum dari setiap pohon keputusan. Pohon dengan kedalaman lebih dalam dapat menangkap pola yang lebih kompleks, tapi juga berisiko menyebabkan overfitting. Dengan max_depth=5, model dibatasi agar setiap pohon tidak terlalu dalam sehingga lebih general.
- learning_rate. Mengatur besar langkah (step size) setiap pohon baru saat memperbarui model. Learning rate kecil berarti model belajar secara perlahan, mengurangi risiko overfitting, namun memerlukan lebih banyak pohon (n_estimators). Sebaliknya, learning rate besar mempercepat pembelajaran tapi risiko overfitting meningkat.
- n_estimators = 168. Jumlah total pohon keputusan yang akan dibangun. Semakin banyak pohon, semakin kompleks model dan biasanya akurasi meningkat, tapi waktu komputasi juga lebih lama.
- random_state = 9. Mengatur seed untuk pengacakan sehingga hasil pelatihan bisa direproduksi (konsisten) saat dijalankan ulang.
- n_jobs = -1. Mengatur berapa banyak core CPU yang digunakan saat pelatihan. Nilai -1 artinya menggunakan seluruh core yang tersedia untuk mempercepat proses training.

### 2. Algoritma SVM
Support Vector Machine (SVM) adalah algoritma supervised learning yang populer untuk klasifikasi dan regresi. Tujuan utama SVM adalah mencari sebuah hyperplane (garis atau bidang pemisah) terbaik yang dapat memisahkan kelas-kelas data dengan margin terbesar. Margin ini adalah jarak terdekat antara hyperplane dengan titik data dari masing-masing kelas. Dalam model ini, parameter yang digunakan adalah: 
- kernel='rbf'. Menentukan tipe kernel yang digunakan, di sini adalah Radial Basis Function yang memungkinkan model membentuk batas pemisah non-linear yang fleksibel.
- random_state=42. Menetapkan seed untuk pengacakan internal agar proses pelatihan bersifat deterministik dan hasilnya bisa direproduksi secara konsisten di setiap eksekusi ulang.

### 3. Algoritma Random Forest
Random Forest adalah algoritma ensemble learning yang digunakan untuk klasifikasi dan regresi. Algoritma ini menggabungkan banyak pohon keputusan (decision trees) secara bersamaan untuk membuat prediksi yang lebih akurat dan stabil dibandingkan menggunakan satu pohon saja. Dalam model ini, parameter yang digunakan adalah: 
- n_estimators=100: artinya akan membangun sebanyak 100 pohon dalam proses pelatihan. Semakin banyak jumlah pohon, biasanya model menjadi lebih akurat dan stabil karena hasil akhir merupakan agregasi dari banyak pohon, namun waktu pelatihan juga akan lebih lama.
- Parameter criterion="entropy" menunjukkan bahwa pemisahan data di setiap simpul pohon akan didasarkan pada nilai information gain, yang berasal dari teori informasi. Entropy digunakan untuk mengukur ketidakpastian, dan model akan berusaha meminimalkan ketidakpastian ini di setiap split data. Meskipun proses ini sedikit lebih lambat dibandingkan dengan kriteria lain seperti Gini, pemilihan entropy sering kali memberikan hasil prediksi yang lebih baik dalam kasus tertentu.
- max_depth=10: Menentukan kedalaman maksimum setiap pohon dalam hutan. ini diterapkan untuk mencegah overfitting, yaitu kondisi ketika model terlalu menyesuaikan diri terhadap data pelatihan dan tidak mampu menggeneralisasi dengan baik terhadap data baru. Dengan membatasi kedalaman, model hanya boleh membelah data hingga 10 tingkat saja, sehingga pola yang dipelajari cukup dalam namun tidak terlalu kompleks.
- random_state=50: digunakan untuk memastikan hasil pelatihan model bisa direproduksi. Dalam konteks pembelajaran mesin, penggunaan random state yang tetap akan menghasilkan hasil yang konsisten setiap kali model dijalankan, karena proses internal seperti pemilihan sampel acak akan menggunakan seed yang sama.
- n_jobs=-1: Menentukan jumlah inti (cores) yang digunakan untuk menghitung. Jika diatur ke -1, model akan menggunakan semua inti yang tersedia, sehingga mempercepat proses pelatihan.

## Evaluation
Dalam proyek ini, evaluasi model dilakukan dengan menggunakan confusion matrix, akurasi, dan f1 score sebagai metrik penilaian untuk setiap model. Sebelum itu, akan dijelaskan terlebih dahulu cara menghitung akurasi dan f1 score serta cara memanfaatkan confusion matrix.
### Penjelasan Confusion Matrix:
Confusion matrix adalah sebuah tabel yang digunakan untuk menggambarkan performa model klasifikasi, khususnya dalam kasus klasifikasi biner maupun multi-kelas. Tabel ini memperlihatkan perbandingan antara hasil prediksi model dengan label sebenarnya.
<p align="center">
  <img src="https://github.com/user-attachments/assets/cae06f2c-285d-44aa-9e31-8d4db42b37c1" width="1000"/>
</p>

**Penjelasan masing-masing istilah:**
- True Positive (TP): Jumlah data yang benar-benar positif dan diprediksi sebagai positif.
- False Positive (FP): Jumlah data yang sebenarnya negatif tetapi diprediksi sebagai positif (disebut juga Type I Error).
- True Negative (TN): Jumlah data yang benar-benar negatif dan diprediksi sebagai negatif.
- False Negative (FN): Jumlah data yang sebenarnya positif tetapi diprediksi sebagai negatif (Type II Error).

**Dari confusion matrix, dapat dihitung metrik evaluasi:**
- Akurasi = (TP + TN) / (TP + TN + FP + FN)
    → Mengukur seberapa banyak prediksi yang benar dibandingkan total prediksi.
- Precision = TP / (TP + FP)
    → Mengukur seberapa akurat model saat memprediksi kelas positif.
- Recall = TP / (TP + FN)
    → Mengukur kemampuan model dalam menemukan semua data positif.
- F1 Score = 2 × (Precision × Recall) / (Precision + Recall)
    → Rata-rata harmonis antara precision dan recall, berguna saat distribusi kelas tidak seimbang.

**Contoh penerapan:**
  
### 1. Algoritma XGBoost
<p align="center">
  <img src="https://github.com/user-attachments/assets/c22ceb33-a882-4de4-ab66-c8e663e5c7e3" width="1000"/>
</p>

Menggunakan XGBoost dimaknai:
- 59 responden dengan kondisi Insufficient Weight telah diklasifikasikan dengan benar.
- 38 responden dengan kondisi Normal Weight telah diklasifikasikan dengan benar.
- 68 responden dengan kondisi Obesity Type I telah diklasifikasikan dengan benar, sementara 4 responden Obesity Type I diklasifikasikan salah sebagai Obesity Type II.
- 59 responden dengan kondisi Obesity Type II telah diklasifikasikan dengan benar.
- 80 responden dengan kondisi Obesity Type III telah diklasifikasikan dengan benar.
- 45 responden dengan kondisi Overweight Level I telah diklasifikasikan dengan benar.
- 64 responden dengan kondisi Overweight Level II telah diklasifikasikan dengan benar, namun ada 1 responden Overweight Level II yang salah diklasifikasikan sebagai Normal Weight.

### 2. Algoritma SVM
<p align="center">
  <img src="https://github.com/user-attachments/assets/e8a92b68-bf70-4deb-bfad-89c991748a54" width="1000"/>
</p>

Menggunakan SVM dimaknai:
1. 58 responden dengan kondisi Insufficient Weight telah diklasifikasikan dengan benar, sementara 1 responden salah diklasifikasikan sebagai Normal Weight.
2. 22 responden dengan kondisi Normal Weight telah diklasifikasikan dengan benar, namun:
  * 5 responden salah diklasifikasikan sebagai Insufficient Weight.
  * 11 responden salah diklasifikasikan sebagai Overweight Level I.
3. 65 responden dengan kondisi Obesity Type I telah diklasifikasikan dengan benar, sementara:
  * 4 responden salah diklasifikasikan sebagai Obesity Type II.
  * 3 responden salah diklasifikasikan sebagai Overweight Level II.
4. 59 responden dengan kondisi Obesity Type II telah diklasifikasikan dengan benar.
5. 75 responden dengan kondisi Obesity Type III telah diklasifikasikan dengan benar, sementara 5 responden salah diklasifikasikan sebagai Obesity Type II.
6. 41 responden dengan kondisi Overweight Level I telah diklasifikasikan dengan benar, namun 4 responden salah diklasifikasikan sebagai Overweight Level II.
7. 54 responden dengan kondisi Overweight Level II telah diklasifikasikan dengan benar, namun:
  * 2 responden salah diklasifikasikan sebagai Obesity Type I.
  * 9 responden salah diklasifikasikan sebagai Overweight Level I.


### 3. Algoritma Random Forest
<p align="center">
  <img src="https://github.com/user-attachments/assets/398bec10-6e8c-440e-99aa-eac4261b2019" width="1000"/>
</p>

Menggunakan Random Forest dimaknai:
- 38 responden dengan kondisi Normal Weight telah diklasifikasikan dengan benar.
- 42 responden dengan kondisi Overweight Level I telah diklasifikasikan dengan benar, namun 2 responden salah diklasifikasikan sebagai Normal Weight, dan 1 responden sebagai Overweight Level II.
- 62 responden dengan kondisi Overweight Level II telah diklasifikasikan dengan benar, sementara 1 responden salah diklasifikasikan sebagai Normal Weight, dan 2 responden sebagai Overweight Level I.
- 71 responden dengan kondisi Obesity Type I telah diklasifikasikan dengan benar, sementara 1 responden salah diklasifikasikan sebagai Insufficient Weight.
- 58 responden dengan kondisi Insufficient Weight telah diklasifikasikan dengan benar, sementara 1 responden salah diklasifikasikan sebagai Normal Weight.
- 59 responden dengan kondisi Obesity Type II telah diklasifikasikan dengan benar.
- 80 responden dengan kondisi Obesity Type III telah diklasifikasikan dengan benar.

### Kelebihan dan Kekurangan Setiap Algoritma

| Algoritma               | Kelebihan                                                                                           | Kekurangan                                                                                           |
|-------------------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **Random Forest**       | - Tidak mudah overfitting<br>- Mampu menangani data non-linear dan fitur dalam jumlah besar         | - Model kompleks dan sulit diinterpretasi<br>- Memerlukan memori dan waktu komputasi yang besar       |
| **XGBoost Classifier**  | - Akurasi tinggi<br>- Mendukung regularisasi untuk mengurangi overfitting<br>- Cocok untuk data tidak seimbang | - Proses training lebih lama<br>- Membutuhkan tuning hyperparameter yang cukup kompleks               |
| **Support Vector Machine (SVM)** | - Efektif untuk data high-dimensional<br>- Cocok untuk dataset kecil dengan margin antar kelas yang jelas | - Kurang efisien pada dataset besar<br>- Pemilihan kernel dan parameter cukup sulit dan sensitif      |

### Pemilihan Model Terbaik
Berdasarkan hasil evaluasi, model yang dipilih sebagai solusi adalah XGBoost. Karena model ini memiliki nilai akurasi tertinggi. 

## Kesimpulan
### 1. Mengetahui faktor apa saja yang paling berpengaruh terhadap tingkat obesitas seseorang
<p align="center">
  <img src="https://github.com/user-attachments/assets/d292fdb0-77f6-40fb-85bd-61a29c94741c" width="600"/>
</p>
Berdasarkan grafik di atas, 3 faktor yang paling memengaruhi level obesitas seseorang adalah BMI, seorang perempuan, dan sering mengonsumsi makanan tinggi kalori (FAVC)

### 2. Mengetahui cara memanfaatkan informasi pola hidup guna memprediksi kategori diabetes pada seseorang
Untuk melakukan prediksi, digunakan model dengan akurasi terbaik yaitu XGBoost, lalu melakukan inference dengan input data baru, menggunakan fungsi di bawah ini menggunakan parameter model dan label_encoder.
<p align="center">
  <img src="https://github.com/user-attachments/assets/fec424f5-031d-4923-a417-8fc07b10a825" width="600"/>
</p>

Selanjutnya, memanggil fungsi tersebut dengan mengisi parameter model_xgb, le.

<p align="center">
  <img src="https://github.com/user-attachments/assets/bd0e969e-47b6-4f55-95b6-c4546f211a74" width="600"/>
</p>

Berdasarkan data yang diinput oleh pengguna berusia 21 tahun dengan tinggi badan 1,5 meter dan berat 68 kg, diketahui bahwa pola makan sehari-harinya kurang seimbang — jarang mengonsumsi sayur (skor 1 dari 3), makan tiga kali sehari, dan mengonsumsi sekitar 2 liter air setiap hari. Aktivitas fisik tergolong rendah dengan olahraga hanya 2 jam per minggu dan waktu layar 1 jam per hari. Pengguna sering mengonsumsi makanan tinggi kalori, tidak menghitung asupan kalori, dan tidak merokok. Terdapat riwayat keluarga mengalami kelebihan berat badan, dan pengguna adalah perempuan. Tidak ada konsumsi alkohol, tidak memiliki kebiasaan ngemil di antara waktu makan, serta menggunakan motor sebagai alat transportasi utama. Berdasarkan informasi tersebut, model memprediksi bahwa individu ini masuk dalam kategori Obesitas Tipe 1.

### 3. Mengetahui hubungan bagaimana riwayat obesitas dari keluarga memengaruhi level diabetes seseorang
<p align="center">
  <img src="https://github.com/user-attachments/assets/5178d4fa-b1e6-4752-b674-c0c760c7b77d" width="600"/>
</p>
Berdasarkan analisis di atas, dapat dikeathui bahwa individu dengan riwayat obesitas keluarga memiliki kemungkinan jauh lebih besar untuk mengalami obesitas sedang hingga berat dibandingkan individu tanpa riwayat tersebut.


## Refrensi
1. Suha, G. R., & Rosyada, A. (2022). Faktor-faktor yang berhubungan dengan kejadian obesitas pada remaja umur 13–15 tahun di Indonesia (analisis lanjut data Riskesdas 2018). Ilmu Gizi Indonesia, 6(1), 43.
2. Batara, A. S. (2018). Healthy Setting Ruang Publik Perkotaan: Sebuah Konsep Terminal Sehat. CV. Social Politic Genius (SIGn).
3. Rahmani, A., & Nadhiroh, S. R. (2024). Upaya yang Dilakukan Beberapa Negara ASEAN untuk Mengatasi Obesitas Anak dan Remaja dalam Program Berbasis Sekolah: Tinjauan Sistematis. Amerta Nutrition, 8(1), 151-160.
4. Pratama, B. A. (2023). Literature Review: Faktor risiko obesitas pada remaja di indonesia. Indonesian Journal on Medical Science, 10(2).
