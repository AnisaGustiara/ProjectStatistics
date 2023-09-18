# ProjectStatistics
Analisis Tarif Total Taksi dengan Model Regresi Linear
Artikel ini merupakan bagian dari penyelesaian course Statistics for Business dari pacmann. Analisa ini digunakan sebagai syarat penyelesaian course dan sebagai portofolio sehingga saya sangat terbuka untuk kritik dan saran yang membangun (anisagustiara@gmail.com).
Latar Belakang
Kenyamanan, keamanan dan efisiensi waktu menjadi alasan bagi para pengguna taksi untuk menggunakan taksi ketika menjalani aktivitas sehari-hari. Banyak faktor yang mempengaruhi dalam penentuan harga tarif taksi yang perlu dibayarkan oleh pelanggan. Oleh karena itu, pada penelitian ini akan digunakan statistik untuk mengetahui harga total pembayaran/ tarif yang harus dikeluarkan oleh pelanggan taksi serta mengetahui faktor apa saja yang berpengaruh terhadap besar kecilnya total biaya / total tarif taksi.
Problem
1. Variabel apa saja yang memiliki pengaruh dalam penentuan tarif taksi?
2. Apakah total tarif taksi dengan durasi perjalanan di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan durasi perjalanan di bawah rata-ratanya?
3. Apakah total tarif taksi dengan jarak di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jarak di bawah rata-ratanya?
4. Apakah total tarif taksi dengan jumlah penumpang di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jumlah penumpang di bawah rata-ratanya?
5. Apakah total tarif taksi dengan tarif dasar di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan tarif dasar di bawah rata-ratanya?
6. Apakah total tarif taksi dengan adanya biaya tambahan adalah lebih tinggi dari total tarif taksi dengan tidak ada biaya tambahan?
7. Apakah total tarif taksi dengan adanya lonjakan harga adalah lebih tinggi dari total tarif taksi dengan yang tidak ada lonjakan harga?
8. Apakah total tarif taksi dengan mendapat tip adalah lebih tinggi dari total tarif taksi dengan tidak ada tip?
9. Model regresi linear seperti apa yang didapatkan?

Dataset
Dataset yang dipakai dalam analisis / penelitian ini adalah data taxi price yang didapatkan  dari kaggle. Dataset terdiri dari 8 kolom dengan 209673 data record.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/adab5d58-fa84-455c-935c-57c1b49b63f7)
Data Cleaning
Sebelum dilakukan analisis data, dataset yang akan digunakan akan di threatment dengan data cleansing terlebih dahulu agar data didapat hasil analisis yang optimal. Pertama, lakukan pengecekan pada missing value.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/8329d5e5-6208-4153-a421-34a69a3b4d8e)
Berdasarkan gambar, diketahui bahwa tidak terdapat missing value untuk setiap kolom yang ada pada dataset. Kedua, lakukan pengecekan untuk data duplikat.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/58c7a8de-2bb0-454d-a74c-91826192b31b)
Berdasarkan gambar, diketahui bahwa terdapat 4325 data duplikat yang kemudian data duplikat tersebut di hapus dari dataset. Ketiga, pengecekan data outlier.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/72ab7175-c335-4bd5-885a-f0f2c943cf77)
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/64bd3d25-bb92-4492-b285-16cd772033fd)
Berdasarkan gambar, data outlier terdapat pada kolom distance_traveler yang kemudian untuk data outlier dilakukan penghapusan. Terakhir atau keempat, mengganti type data kolom agar memudahkan dalam penggunaan data nantinya.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/f8383b47-0584-4560-b370-88787379e7ac)
Berdasarkan gambar, data yang di ganti type data nya adalah untuk kolom num_of_passangers dan surge_applied.

EDA (Exploratory Data Analysis)
Setelah data siap, kemudian dilakukan analisis EDA yaitu analisis awal untuk mengetahui gambaran umum dari data yang digunakan.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/e92ce80f-4b49-4329-a9cc-8dc58bfb3463)
Berdasarkan catplot di atas untuk kolom total tarif dan trip duration menunjukkan bahwa trip_duration yang lama belum tentu memiliki total tarif yang tinggi yang terlihat dimana banyak titik trip_duration yang berada di daerah yang tinggi namun rentang tarifnya di daerah yang cukup rendah.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/cf104dfb-9c69-417b-9093-3659ead72ab1)
Berdasarkan catplot kolom total tarif dan distance_traveled terlihat bahwa grafik menunjukkan semakin tinggi jaraknya maka semakin tinggi juga total tarif.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/4cac5513-8828-4026-94a9-10cb89542ce9)
Berdasarkan stripplot kolom total tarif dan jumlah penumpang di atas menunjukkan bahwa banyaknya penumpang tidak bisa dijadikan patokan tingginya total tarif.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/ccae8a6f-918b-40a0-aec3-37662cc98a4e)
Berdasarkan scatterplot di atas pada kolom tarif dasar dan total tarif menunjukkan bahwa semakin tinggi tarif dasar maka semakin tinggi juga total tarif nya. Hal ini terlihat dari bentuk grafik yang linear ke atas.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/cd885cf6-c9aa-435f-ba86-3eee6c0419b8)
Berdasarkan scatterplot di atas pada kolom tip dan total tarif menunjukkan bahwa grafik dengan tip adalah 0 memiliki total tarif yang stabil dengan nilai yang rendah ataupun tinggi. sedangkan tip dengan nilai di atas 0 dapat menaikkan total tarif yang didapat.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/49cb25ac-0dbc-47b7-8a3e-4f8f1dcf31f1)
Berdasarkan scatterplot total tarif dan biaya tambahan menunjukkan bahwa grafik dengan biaya tambahan adalah 0 memiliki total tarif yang stabil dengan nilai yang rendah ataupun tinggi. sedangkan biaya tambahan dengan nilai di atas 0 dapat menaikkan total tarif yang didapat.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/a9806536-f5dd-4fea-a083-f26a99012347)
Berdasarkan catplot total tarif dan lonjakan harga menunjukkan bahwa lonjakan harga yang bernilai no memiliki total tarif yang lebih rendah dari lonjakan harga bernilai yes.

Statistics Test
Setelah melihat dari analisis awal sebelumnya, pada tahap ini akan dilakukan uji asumsi sebagai berikut:
1. Apakah total tarif taksi dengan durasi perjalanan di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan durasi perjalanan di bawah rata-ratanya.
2. Apakah total tarif taksi dengan jarak di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jarak di bawah rata-ratanya.
3. Apakah total tarif taksi dengan jumlah penumpang di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jumlah penumpang di bawah rata-ratanya.
4. Apakah total tarif taksi dengan tarif dasar di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan tarif dasar di bawah rata-ratanya.
5. Apakah total tarif taksi dengan adanya biaya tambahan adalah lebih tinggi dari total tarif taksi dengan tidak ada biaya tambahan.
6. Apakah total tarif taksi dengan adanya lonjakan harga adalah lebih tinggi dari total tarif taksi dengan yang tidak ada lonjakan harga.
7. Apakah total tarif taksi dengan mendapat tip adalah lebih tinggi dari total tarif taksi dengan tidak ada tip.

Uji statistik untuk total tarif taksi dengan durasi perjalanan di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan durasi perjalanan di bawah rata-ratanya.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan durasi perjalanan di atas rata-ratanya ≤  total tarif taksi dengan durasi perjalanan di bawah rata-ratanya
H1 : total tarif taksi dengan durasi perjalanan di atas rata-ratanya > total tarif taksi dengan durasi perjalanan di bawah rata-ratanya
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/8a77c80d-90ee-4b8d-b32e-c567cd3f691c)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.0) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan durasi perjalanan di atas rata-ratanya lebih tinggi dari total tarif taksi dengan durasi perjalanan di bawah rata-ratanya.

Uji statistik untuk total tarif taksi dengan jarak di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jarak di bawah rata-ratanya.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan jarak di atas rata-ratanya ≤ total tarif taksi dengan jarak di bawah rata-ratanya
H1 : total tarif taksi dengan jarak di atas rata-ratanya > total tarif taksi dengan jarak di bawah rata-ratanya
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/16528faf-a45f-425e-8e96-46ed75f1a09a)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.0) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan jarak di atas rata-ratanya lebih tinggi dari total tarif taksi dengan jarak di bawah rata-ratanya.

Uji statistik untuk total tarif taksi dengan jumlah penumpang di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jumlah penumpang di bawah rata-ratanya.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan jumlah penumpang di atas rata-ratanya ≤ total tarif taksi dengan jumlah penumpang di bawah rata-ratanya
H1 : total tarif taksi dengan jumlah penumpang di atas rata-ratanya > total tarif taksi dengan jumlah penumpang di bawah rata-ratanya
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/4e20264a-1cc3-4c72-a034-d0ece26aa06a)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan jumlah penumpang di atas rata-ratanya lebih tinggi dari total tarif taksi dengan jumlah penumpang di bawah rata-ratanya.

Uji statistik untuk total tarif taksi dengan tarif dasar di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan tarif dasar di bawah rata-ratanya.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan tarif dasar di atas rata-ratanya ≤ total tarif taksi dengan tarif dasar di bawah rata-ratanya
H1 : total tarif taksi dengan tarif dasar di atas rata-ratanya > total tarif taksi dengan tarif dasar di bawah rata-ratanya
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/252e6f4e-f195-4aa9-ad71-21adcab36407)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.0) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan tarif dasar di atas rata-ratanya lebih tinggi dari total tarif taksi dengan tarif dasar di bawah rata-ratanya.

Uji statistik untuk total tarif taksi dengan adanya biaya tambahan adalah lebih tinggi dari total tarif taksi dengan tidak ada biaya tambahan.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan adanya biaya tambahan ≤ total tarif taksi dengan tidak ada biaya tambahan
H1 : total tarif taksi dengan adanya biaya tambahan > total tarif taksi dengan tidak ada biaya tambahan
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.01) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan adanya biaya tambahan lebih tinggi dari total tarif taksi dengan tidak ada biaya tambahan

Uji statistik untuk total tarif taksi dengan adanya lonjakan harga adalah lebih tinggi dari total tarif taksi dengan yang tidak ada lonjakan harga.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan adanya lonjakan harga ≤ total tarif taksi dengan yang tidak ada lonjakan harga
H1 : total tarif taksi dengan adanya lonjakan harga > total tarif taksi dengan yang tidak ada lonjakan harga
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/94051600-dc79-44ae-a4f3-3d2039a56032)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.0) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan adanya lonjakan harga lebih tinggi dari total tarif taksi dengan yang tidak ada lonjakan harga.

Uji statistik untuk total tarif taksi dengan mendapat tip adalah lebih tinggi dari total tarif taksi dengan tidak ada tip.
Uji yang digunakan adalah uji-T dengan 2 sampel dengan hipotesis sebagai berikut.
H0 : total tarif taksi dengan mendapat tip ≤ total tarif taksi dengan tidak ada tip
H1 : total tarif taksi dengan mendapat tip > total tarif taksi dengan tidak ada tip
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/2edc1754-7fa5-4d84-98ab-013329988776)
Dari pengujian menggunakan python di atas didapatkan hasil bahwa nilai p value (0.0) adalah kurang dari alpha (0.05) sehingga menolak H0 yang berarti total tarif taksi dengan mendapat tip lebih tinggi dari total tarif taksi dengan tidak ada tip.

Korelasi
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/65360a22-00a8-43f8-91cc-74da8bfcf761)
Hasil pengujian korelasi pada tabel menunjukkan hubungan antar variabel dengan ditunjukkan nilai hubungannya. Dari tabel diketahui bahwa terdapat variabel yang memiliki nilai korelasi > 0,8 yang mana hal ini mengindikasikan bahwa terjadi multikolinearitas. Sehingga kolom variabel yang memiliki korelasi diatas 0,8 dikeluarkan.

Regression Model
Tahap ini akan dilakukan pembuatan model dengan menggunakan varibel prediktor yang telah dilakukan pengecekan sebelumnya dan total_fare sebagai variabel outcome, didapatkan hasil sebagai berikut.
![image](https://github.com/AnisaGustiara/ProjectStatistics/assets/90565867/2cf1c99f-98c0-4175-8a59-7800aad0b779)
Berdasarkan gambar, diketahui bahwa nilai f-statistic adalah 0.0 yang dimana berada dibawah 0.05 yang menunjukkan bahwa model yang di bangun cukup bagus dan layak untuk digunakan. Selanjutnya nilai R-Square atau Koefisien Determinasi yang masuk kedalam kategori moderate yang menggambarkan bahwa model menjelaskan 36,9 %.

Interpretasi model
1. Pada variabel surge_apllied, jika variabel lain berada pada level yang sama, maka harga total tarif yang mengalami lonjakan harga memiliki total tarif yang lebih rendah sebesar 27,3596 INR dari yang tidak mengalami lonjakan harga.
2. Pada variabel trip_duration, jika variabel lain berada pada level yang sama, maka harga total tarif yang memiliki durasi perjalanan lebih lama memiliki total tarif lebih tinggi sebesar 0,0024 INR
3. Pada variabel distance_traveled, jika variabel lain berada pada level yang sama, maka harga total tarif yang memiliki jarak perjalanan lebih jauh memiliki total tarif lebih tinggi sebesar 0.0176 INR
4. Pada variabel num_of_passangers, jika variabel lain berada pada level yang sama, maka harga total tarif yang memiliki penumpang lebih banyak memiliki total tarif yang lebih tinggi sebesar 0.6870 INR
5. Pada variabel tip, jika variabel lain berada pada level yang sama, maka harga total tarif yang memiliki tip memiliki total tarif yang lebih tinggi sebesar 1.9519 INR
6. Pada variabel miscellaneous_fees, jika variabel lain berada pada level yang sama, maka harga total tarif yang memiliki biaya tambahan memiliki total tarif yang lebih tinggi sebesar 3.1746 INR

Kesimpulan dan Rekomendasi
Kesimpulan
1. Berdasarkan uji f dan uji t didapatkan hasil model regresi linear yang mementukan harga total tarif taksi dengan variabel yang terkait adalah surge_applied, trip_duration, distance_traveled, tip, miscellaneous_fees dan num_of_passangers.
Berdasarkan hasil uji statistik, total tarif taksi dengan durasi perjalanan di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan durasi perjalanan di bawah rata-ratanya.
2. Berdasarkan hasil uji statistik, total tarif taksi dengan jarak di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jarak di bawah rata-ratanya.
3. Berdasarkan hasil uji statistik, total tarif taksi dengan jumlah penumpang di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan jumlah penumpang di bawah rata-ratanya.
4. Berdasarkan hasil uji statistik, total tarif taksi dengan tarif dasar di atas rata-ratanya adalah lebih tinggi dari total tarif taksi dengan tarif dasar di bawah rata-ratanya.
5. Berdasarkan hasil uji statistik, total tarif taksi dengan adanya biaya tambahan adalah lebih tinggi dari total tarif taksi dengan tidak ada biaya tambahan.
6. Berdasarkan hasil uji statistik, total tarif taksi dengan adanya lonjakan harga adalah lebih tinggi dari total tarif taksi dengan yang tidak ada lonjakan harga.
7. Berdasarkan hasil uji statistik, total tarif taksi dengan mendapat tip adalah lebih tinggi dari total tarif taksi dengan tidak ada tip.

Rekomendasi
1. Menggunakan alternatif lain untuk mengatasi multikolinearitas seperti menambah data observasi atau mentransformasikan data ke betuk lain (logaritma natural).
2. Menggunakan K-fold validation untuk meningkatkan kualitas prediksi.
