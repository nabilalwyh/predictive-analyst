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
Melakukan Univeariate Analysis untuk numerical dan categorical features.

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
  <img src="https://github.com/user-attachments/assets/00a4ab93-1270-4189-99b9-3b9da5645fe2" width="600"/>
</p>

  > **Insight:**
  > - Konsumsi makanan berkalori tinggi (FAVC) berkorelasi positif dengan peningkatan tingkat obesitas.
  > - Meskipun kebiasaan ngemil lebih sering ditemukan pada individu obesitas (terutama tipe ringan hingga sedang), namun kategori Insufficient Weight juga menunjukkan frekuensi ngemil yang tinggi, yang menunjukkan bahwa frekuensi ngemil saja tidak cukup menjelaskan obesitas — perlu dilihat juga jenis camilan dan pola konsumsi lainnya.
  > - Rata-rata semua kategori obesitas memiliki jumlah makan utama sekitar 3 kali/hari, mirip dengan kategori berat badan normal. Tapi, Insufficient Weight memiliki sebaran nilai lebih tinggi (hingga 4× sehari).
  > - Konsumsi sayur tidak signifikan membedakan level obesitas; banyak individu obesitas tetap mengonsumsi sayur.
  > - Faktor yang paling kuat berhubungan dengan obesitas dari visualisasi ini adalah FAVC (makanan tinggi kalori), diikuti oleh CAEC (ngemil di luar waktu makan utama). Sedangkan jumlah makan utama (NCP) dan konsumsi sayur (FCVC) memiliki pengaruh yang tidak begitu jelas terhadap level obesitas berdasarkan grafik ini.
 
#### 4. Membandingkan kondisi level obesitas dengan kebiasaan merokok dan konsumsi alkohol
<p align="center">
  <img src="https://github.com/user-attachments/assets/db3eed58-8d94-4557-9451-b516e6eb8ff0" width="600"/>
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

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

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

