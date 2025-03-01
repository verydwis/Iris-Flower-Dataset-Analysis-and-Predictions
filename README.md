# Iris-Flower-Dataset-Analysis-and-Predictions

Jika Anda memiliki latar belakang data sciece, Anda pasti sudah familier dengan [Iris Dataset](https://media.geeksforgeeks.org/wp-content/uploads/20240923162510/Iris.csv). Jika belum, jangan khawatir, kami akan membahasnya di sini.

Dataset Iris dianggap sebagai Hello World untuk ilmu data. Dataset ini berisi lima kolom yaitu – Petal Length, Petal Width, Sepal Length, Sepal Width, and Species Type. Iris adalah tanaman berbunga, para peneliti telah mengukur berbagai fitur dari bunga iris yang berbeda dan mencatatnya secara digital.

# Getting Information about the Dataset
![image](https://github.com/user-attachments/assets/3ac1809e-2d4d-43f9-9dc8-7dde2c5f67c5)

Kita dapat melihat bahwa hanya satu kolom yang memiliki data kategoris dan semua kolom lainnya bertipe numerik dengan entri bukan Null.

Mari kita dapatkan ringkasan statistik cepat dari kumpulan data menggunakan metode **describe()**. Fungsi describe() menerapkan perhitungan statistik dasar pada kumpulan data seperti nilai ekstrem, jumlah titik data, deviasi standar, dll. Setiap nilai yang hilang atau nilai NaN secara otomatis dilewati. Fungsi describe() memberikan gambaran yang baik tentang distribusi data.

![image](https://github.com/user-attachments/assets/744a511a-14d8-4d0f-b92c-103045f25694)

Kita dapat melihat jumlah setiap kolom beserta nilai rata-rata, deviasi standar, nilai minimum dan maksimumnya.

# Data Visualization

## Visualizing the target column
Kolom target kita adalah kolom Spesies karena pada akhirnya kita hanya akan membutuhkan hasil berdasarkan spesies saja. Mari kita lihat plot hitungan untuk spesies.
![image](https://github.com/user-attachments/assets/315379b2-fa2c-4e0a-9301-2eeea04ca464)

## Relation between variables
Kita akan melihat hubungan antara panjang kelopak dan lebar kelopak dan juga antara panjang kelopak dan lebar kelopak.

![image](https://github.com/user-attachments/assets/506341c8-3a56-4820-ad8e-a7fe8c4fea6c)

Dari plot di atas, kita dapat menyimpulkan bahwa – 

- Spesies Setosa memiliki panjang kelopak yang lebih kecil tetapi lebar kelopak yang lebih besar.
- Spesies Versicolor terletak di tengah-tengah dua spesies lainnya dalam hal panjang dan lebar sepal
- Spesies Virginica memiliki panjang sepal yang lebih besar tetapi lebar sepal lebih kecil.

Mari kita plot semua hubungan kolom menggunakan pairplot. Ini dapat digunakan untuk analisis multivariat.

![image](https://github.com/user-attachments/assets/9c15aa61-9255-46b0-9909-d618bb284240)
Kita dapat melihat banyak jenis hubungan dari plot ini seperti spesies Setosa memiliki lebar dan panjang kelopak terkecil. Ia juga memiliki panjang daun bunga terkecil tetapi lebar daun bunga lebih besar. Informasi semacam itu dapat dikumpulkan tentang spesies lainnya.

## Histogram
Histogram memungkinkan melihat distribusi data untuk berbagai kolom. Histogram dapat digunakan untuk analisis univariat maupun bivariat.

![image](https://github.com/user-attachments/assets/332559a3-20a4-4ac5-8d98-9451b3f3d2f0)

Dari grafik di atas, kita dapat melihat bahwa :
- Frekuensi panjang sepal tertinggi berada pada kisaran 30 sampai 35 yaitu antara 5,5 sampai 6
- Frekuensi tertinggi dari lebar sepal adalah sekitar 70 yaitu antara 3,0 dan 3,5
- Frekuensi panjang kelopak tertinggi adalah sekitar 50 yaitu antara 1 dan 2
- Frekuensi lebar kelopak tertinggi berada pada angka 40 sampai 50 yaitu antara 0,0 sampai 0,5
  
# Histogram dengan Plot Distplot
Distplot pada dasarnya digunakan untuk kumpulan observasi univarian dan memvisualisasikannya melalui histogram, yaitu hanya satu observasi dan oleh karena itu kita memilih satu kolom tertentu dari kumpulan data.

![image](https://github.com/user-attachments/assets/57b73858-1a26-4813-b219-f4165372983b)

Dari grafik di atas, kita dapat melihat bahwa :

- Dalam kasus Sepal Length, terdapat banyak sekali tumpang tindih.
- Dalam kasus Sepal Width juga, terdapat sejumlah besar tumpang tindih.
- Dalam kasus Panjang Kelopak, jumlah tumpang tindihnya sangat sedikit.
- Dalam kasus Petal Width (Lebar Kelopak), jumlah tumpang tindihnya juga sangat sedikit.

Jadi kita dapat menggunakan Panjang Kelopak dan Lebar Kelopak sebagai fitur klasifikasi.

## Penanganan Korelasi
Pandas d**ataframe.corr()** digunakan untuk menemukan korelasi berpasangan dari semua kolom dalam kerangka data. Setiap nilai NA secara otomatis dikecualikan. Untuk setiap kolom tipe data non-numerik dalam kerangka data, nilai tersebut diabaikan.
![image](https://github.com/user-attachments/assets/70104315-5f59-4f0f-b7bc-273d157a39a5)

## Heatmaps
Heatmaps adalah teknik visualisasi data yang digunakan untuk menganalisis kumpulan data sebagai warna dalam dua dimensi. Pada dasarnya, Heatmaps menunjukkan korelasi antara semua variabel numerik dalam kumpulan data. Dengan kata lain, kita dapat memetakan korelasi yang ditemukan di atas menggunakan Heatmaps.
![image](https://github.com/user-attachments/assets/c9ffbe01-37c8-4bd9-bb4c-1c5a921dc454)
Dari grafik di atas, kita dapat melihat bahwa –

- Lebar kelopak dan panjang kelopak memiliki korelasi yang tinggi. 
- Panjang kelopak dan lebar kelopak memiliki korelasi yang baik.
- Lebar Kelopak dan Panjang Kelopak memiliki korelasi yang baik.

## Box Plots
![image](https://github.com/user-attachments/assets/75f15ff7-1d21-403a-94d2-8e659f39cde5)
Dari grafik di atas, kita dapat melihat bahwa :

- Spesies Setosa memiliki fitur terkecil dan kurang terdistribusi dengan beberapa outlier.
- Spesies Versicolor memiliki ciri-ciri rata-rata.
- Spesies Virginica memiliki fitur tertinggi

## Handling Outliers
Outlier adalah item/objek data yang menyimpang secara signifikan dari objek lainnya (yang disebut normal). Outlier dapat disebabkan oleh kesalahan pengukuran atau eksekusi. Analisis untuk mendeteksi outlier disebut sebagai penambangan outlier. Ada banyak cara untuk mendeteksi outlier, dan proses penghapusannya adalah kerangka data yang sama seperti menghapus item data dari kerangka data panda.

![image](https://github.com/user-attachments/assets/6d722233-b524-4528-b874-7c644aaf2627)

Pada grafik di atas, nilai di atas 4 dan di bawah 2 bertindak sebagai outlier.

## Removing Outliers
Untuk membuang outlier, seseorang mesti mengikuti proses yang sama dalam membuang entri dari himpunan data menggunakan posisi persisnya dalam himpunan data, sebab dalam semua metode pendeteksian outlier di atas, hasil akhirnya adalah daftar semua item data yang memenuhi definisi outlier menurut metode yang digunakan.

![image](https://github.com/user-attachments/assets/23a73201-0ca6-4248-b9ab-78b13096dcd8)









