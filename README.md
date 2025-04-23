# Laporan Proyek Pertama - Aryadi Belo Rerung
## Domain Project
Proyek ini berada dalam domain ekonomi dan bisnis, khususnya pada proses rekrutmen dan manajemen sumber daya manusia. Perusahaan fiktif XYZ tengah membuka lowongan pekerjaan dan membutuhkan sistem yang dapat membantu memperkirakan kisaran gaji yang sesuai bagi calon pelamar. Untuk itu, proyek ini berfokus pada pembangunan model prediktif yang dapat memberikan estimasi gaji berdasarkan pengalaman kerja kandidat. Dengan adanya prediksi yang lebih akurat, perusahaan diharapkan dapat mengambil keputusan yang lebih objektif dan efisien dalam menetapkan tawaran gaji, serta menciptakan keselarasan antara kualifikasi pelamar dan kompensasi yang diberikan.

## Latar Belakang
Dalam dunia kerja yang kompetitif saat ini, penetapan gaji yang adil dan kompetitif menjadi tantangan utama bagi perusahaan. Salah satu faktor yang sering digunakan dalam menentukan besaran gaji adalah pengalaman kerja. Secara umum, semakin lama seseorang bekerja di bidang tertentu, semakin tinggi pula ekspektasi gaji yang dimilikinya. Namun, pendekatan ini tidak selalu mencerminkan produktivitas atau kontribusi aktual dari seorang karyawan.

Sebuah studi yang diterbitkan oleh Harvard Business Review mengungkapkan bahwa tidak terdapat korelasi signifikan antara pengalaman kerja sebelumnya dengan kinerja di pekerjaan baru. Bahkan, pengalaman yang luas tidak selalu menjamin keberhasilan atau produktivitas yang lebih tinggi di lingkungan kerja yang berbeda . Hal ini menunjukkan bahwa penilaian gaji berdasarkan pengalaman semata dapat menimbulkan ketidakakuratan dalam kompensasi dan potensi ketidakadilan dalam sistem remunerasi.

Di sisi lain, penerapan teknologi seperti machine learning dalam proses rekrutmen dan penetapan gaji menawarkan pendekatan yang lebih objektif dan data-driven. Dengan menganalisis berbagai variabel seperti pendidikan, keterampilan, lokasi kerja, dan faktor lainnya, model prediktif dapat memberikan estimasi gaji yang lebih akurat dan adil. Sebuah penelitian menunjukkan bahwa penggunaan model machine learning dalam prediksi gaji dapat meningkatkan efisiensi proses rekrutmen dan membantu perusahaan dalam menetapkan kompensasi yang sesuai dengan kualifikasi kandidat [1](https://www.researchgate.net/publication/386139334_Enhancing_Salary_Prediction_Accuracy_with_Advanced_Machine_Learning_Models)


Oleh karena itu, proyek ini bertujuan untuk mengembangkan model prediktif yang dapat memperkirakan kisaran gaji berdasarkan berbagai faktor relevan, tidak hanya pengalaman kerja. Dengan demikian, diharapkan perusahaan dapat membuat keputusan yang lebih tepat dalam proses rekrutmen dan penetapan gaji, serta menciptakan sistem kompensasi yang lebih adil dan transparan.

## Business Understanding
### Problem Statements
- Bagaimana cara memprediksi kisaran gaji calon karyawan berdasarkan pengalaman kerja dan variabel relevan lainnya secara akurat menggunakan algoritma machine learning?
- Model machine learning apa yang memberikan hasil prediksi paling optimal dalam memperkirakan gaji berdasarkan pengalaman kerja, tingkat pendidikan, dan faktor-faktor lainnya?

### Goals
- Mengembangkan model machine learning yang dapat memperkirakan kisaran gaji calon karyawan berdasarkan pengalaman kerja dan fitur pendukung lainnya secara efektif dan efisien.
- Membandingkan performa beberapa algoritma machine learning untuk menentukan model terbaik dalam memprediksi gaji yang sesuai bagi perusahaan.

### Solution Statement
- Untuk menjawab tantangan dalam menentukan kisaran gaji calon karyawan berdasarkan pengalaman kerja, proyek ini mengusulkan pembangunan sistem prediktif berbasis machine learning menggunakan algoritma Linear Regression dan Random Forest Regressor. Sistem ini akan dilatih menggunakan [dataset](https://www.kaggle.com/datasets/suyog17/salary-prediction) yang diperoleh dari Kaggle, yang berisi data historis mengenai pengalaman kerja dan besaran gaji yang diberikan. Melalui proses pelatihan model dan evaluasi performa, solusi ini diharapkan mampu membantu Perusahaan XYZ dalam memberikan estimasi gaji yang akurat dan adil terhadap calon tenaga kerja, berdasarkan pengalaman kerja yang mereka miliki. Model dengan performa terbaik akan dipilih sebagai dasar sistem prediksi, yang dapat mendukung pengambilan keputusan dalam proses rekrutmen perusahaan secara data-driven.
- Mean Squared Error (MSE) akan digunakan sebagai metrik evaluasi. Secara umum, MSE mengukur sejauh mana hasil prediksi berbeda dari nilai sebenarnya. Oleh karena itu, setiap model yang digunakan akan dievaluasi dengan metrik ini, dan model dengan nilai MSE terbaik akan dipilih sebagai solusi terbaik untuk prediksi gaji.

## Data Understanding
#### 1. Jumlah Data dan Kondisi Data
Dataset yang digunakan dalam proyek ini terdiri dari 5000 baris data dengan dua kolom: Years of Experience dan Salary. Setiap baris mewakili seorang calon karyawan dengan informasi mengenai pengalaman kerja (Years of Experience) dan gaji yang diterima (Salary). Data ini telah diperiksa untuk memastikan tidak ada nilai yang hilang (missing values) dan outlier.

#### 2. Sumber Data
Dataset ini dapat diakses melalui tautan berikut:
[Salary Prediction](https://www.kaggle.com/datasets/suyog17/salary-prediction)

#### 3. Variabel/Fitur pada Dataset
- Years_of_Experience: Kolom ini mencatat jumlah tahun pengalaman kerja yang dimiliki oleh setiap calon karyawan. Fitur ini bersifat numerik dan menjadi variabel input utama dalam model prediksi gaji.

- Salary: Kolom ini mencatat gaji yang diterima oleh calon karyawan sesuai dengan jumlah pengalaman kerja mereka. Fitur ini bersifat numerik dan merupakan variabel target yang ingin diprediksi oleh model.

## Data Preparation
1. Data Split
Dataset yang tersedia dibagi menjadi dua bagian, yaitu data pelatihan dan data pengujian dengan rasio pembagian sebesar 80% untuk data pelatihan dan 20% untuk data pengujian. Proses ini dilakukan menggunakan fungsi train_test_split yang tersedia pada pustaka scikit-learn.
2.  Standarisasi Data
Setelah data pelatihan dipisahkan, dilakukan proses standarisasi pada fitur-fitur data menggunakan StandardScaler dari pustaka scikit-learn. Teknik ini bertujuan untuk menyamakan skala dari setiap fitur sehingga model dapat lebih mudah mempelajari pola data tanpa terpengaruh oleh perbedaan skala antar fitur.

## Modeling
Pada tahap Modeling, dua model machine learning digunakan untuk memprediksi gaji berdasarkan pengalaman kerja, yaitu Linear Regression dan Random Forest Regressor.

- Linear Regression digunakan untuk memodelkan hubungan linier antara variabel Years of Experience dan Salary. Model ini dilatih menggunakan data pelatihan dan kemudian digunakan untuk melakukan prediksi pada data uji.

- Random Forest Regressor adalah model ensemble yang terdiri dari banyak pohon keputusan, yang dapat menangani hubungan non-linier lebih baik dibandingkan Linear Regression. Model ini juga dilatih dengan data pelatihan dan digunakan untuk prediksi pada data uji.

## Evaluation
Pada tahap Evaluation, metrik yang digunakan untuk mengukur kinerja kedua model adalah Mean Squared Error (MSE). Metrik ini dipilih karena masalah yang dihadapi adalah regresi, yaitu memprediksi nilai kontinu (gaji), sehingga MSE menjadi pilihan yang tepat untuk menilai seberapa dekat hasil prediksi dengan nilai sebenarnya.

- Metrik Evaluasi:
Mean Squared Error (MSE) mengukur rata-rata kuadrat selisih antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik model dalam memprediksi data yang ada.

- Hasil Proyek:
Setelah mengevaluasi kedua model menggunakan MSE, model yang memiliki nilai MSE lebih kecil menunjukkan prediksi yang lebih akurat. Dengan demikian, model dengan MSE terkecil dipilih sebagai model terbaik untuk memprediksi kisaran gaji berdasarkan pengalaman kerja.

Hasil evaluasi ini memberikan gambaran tentang seberapa efektif model dalam memecahkan masalah yang diajukan, yakni memprediksi gaji yang sesuai dengan pengalaman kerja calon pekerja di perusahaan XYZ.


![image](https://user-images.githubusercontent.com/72861300/190839123-c90fba7a-3cfe-4e62-984e-3a672ed1aef9.png)  