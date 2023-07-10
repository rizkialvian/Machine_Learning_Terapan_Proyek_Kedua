$\frac{a}{b}$

# Laporan Proyek Machine Learning - Rizki Alvian

## Sistem Rekomendasi Buku Berdasarkan Preferensi dan Rating Pengguna

![Ilustrasi Buku](https://github.com/rizkialvian/Machine_Learning_Terapan_Proyek_Kedua/blob/93f920a10aae001caeda1b92694bccbaeb2fdafa/img/book.png?raw=true)

## Project Overview
Membaca merupakan cara bagi setiap orang untuk mendapatkan pengetahuan dan wawasan baru tentang banyak hal. Informasi tentang berbagai jenis buku telah tersedia secara luas di Internet dan dapat diakses oleh banyak orang. Informasi tentang berbagai macam buku banyak beredar di internet, namun minat baca di Indonesia masih tergolong rendah. Menurut data survei tahun 2016 yang dilakukan oleh Central Connecticut State University berjudul “Peringkat Negara dengan Tingkat Melek Huruf Tertinggi di Dunia”, Indonesia menempati urutan ke-60 dari 61 negara dalam hal minat membaca. Temuan menunjukkan bahwa minat baca di Indonesia masih relatif rendah dibandingkan negara lain seperti Singapura dan Malaysia. Keadaan ini tentunya mempengaruhi pemahaman terhadap ilmu pengetahuan dan teknologi. Selain itu, jika dampak dari kurangnya membaca di kalangan generasi muda ini semakin besar, maka akan berdampak negatif bagi negara, dan tidak menutup kemungkinan berdampak juga pada sumber daya manusia yang mana menjadi aset yang berkontribusi dalam membangung bangsa Indonesia [1].

Saat ini masyarakat memiliki akses ke berbagai macam buku yang tersedia dari penyedia layanan buku, seperti Gramedia, dan lain-lain. Penggunaan sistem rekomendasi dapat dimanfaatkan karena banyak informasi buku yang tersedia secara luas sehingga memudahkan pembaca buku untuk menemukan buku yang sesuai dengan kriterianya. Ini memudahkan pengguna mendapatkan referensi baru, tergantung pada kategori buku yang diminati pembaca sebelumnya. Selain itu, sistem rekomendasi juga berperan penting dalam banyak layanan aplikasi online. Kinerja sistem pemberi rekomendasi dapat berdampak pada kesuksesan komersl banyak perusahaan dalam hal pendapatan dan kepuasan pengguna [2].

Sistem rekomendasi memiliki tiga kategori model yang dapat digunakan, yaitu Content Based Filtering, Collaborative Filtering, dan Hybrid Recommender System [3]. Collaborative Filtering digunakan untuk mengidentifikasi kesamaan antara pengguna dan memberikan rekomendasi artikel yang relevan. Sistem akan merekomendasikan item yang disukai grup dari pengguna serupa lainnya. Content Based Filtering adalah sistem yang memberikan rekomendasi kepada pengguna berdasarkan preferensi pengguna dan hubungan antar deskripsi item. Ini dilakukan dengan memilih item yang paling mirip dengan item yang disukai pengguna. Hybrid Recommender System menggabungkan teknik Collaborative Filtering dan teknik Content Based Filtering. Keakuratan sistem ini umumnya lebih tinggi dari dua sistem sebelumnya. Hal ini karena Collaborative Filtering memiliki kekurangan yaitu mengandalkan preferensi dan konten pengguna lain, yang menimbulkan masalah dalam memberikan rekomendasi artikel yang lebih kompleks.

Sistem rekomendasi merupakan solusi yang dapat mengatasi masalah pencarian buku yang sesuai dengan keinginan pembaca dan dapat menambah referensi pengetahuan tentang buku lain yang sejenis. Dengan mengukur kemiripan dari setiap buku, sistem dapat memberikan skor yang digunakan sebagai dasar untuk memberikan rekomendasi sesuai dengan deskripsi buku tersebut. Melalui sistem rekomendasi ini diharapkan dapat menambah referensi baru berdasarkan buku yang diminati sebelumnya [4]

## Business Understanding
### Problem Statements
Berdasarkan project overview diatas, penulis menguraikan problem statement sebagai berikut:
* Bagaimana membangun sebuah sistem rekomendasi berdasarkan data dari kumpulan buku yang tersedia?
* Bagaimana mengolah data buku, pengguna, dan ulasan sehingga dapat digunakan sebagai informasi dalam sistem rekomendasi?
* Bagaimana akurasi yang diperoleh dari sistem rekomendasi yang telah dibangun?

### Goals
Berdasarkan problem statement diatas, penulis menguraikan goals sebagai berikut:
* Dapat mengetahui proses membangun sistem rekomendasi berdasarkan data dari kumpulan buku yang tersedia.
* Dapat mengetahui proses mengolah data buku, pengguna, dan ulasan dalam sistem rekomendasi.
* Dapat mengetahui akrasi sistem rekomendasi yang telah dibangun.

### Solution Approach
Beberapa ringkasan solusi yang dapat penulis lakukan diantaranya adalah sebagai berikut:
* Pre-processing data, pada tahapan ini akan dilakukan analisis karakteristik dari data books, users, dan ratings sebelum masuk tahap preparation.
* Preparation data, pada tahapan ini akan dilakukan pemilihan fitur-fitur dari data yang diperlukan, seperti mengisi data kosong pada publisher dan author pada data buku, menghapus data dengan rating 0 pada data rating, dan mengisi missing value menggunakan modus Age pada data user.
* Solusi yang diberikan bergantung dari hasil rekomendasi yang ingin dicapai.
  * Popularity based recommendation

    Sistem rekomendasi berbasis popularitas bekerja dengan tren. Misalnya, jika produk yang biasanya dibeli oleh semua pengguna baru, produk tersebut kemungkinan besar akan menyarankan item tersebut kepada pengguna yang baru yang baru saja mendaftar. Teknik yang digunakan adalah weighted scoring.
    
  * Singular Value Decomposition

    Salah satu cara untuk mengatasi masalah skalabilitas dan ketersebaran yang ditimbulkan oleh collaborative filtering (CF) adalah dengan memanfaatkan model faktor laten untuk menangkap kesamaan antara pengguna dan item. Metrik yang umum adalah root mean square error (RMSE). Semakin rendah RMSE, semakin baik kinerjanya.
    
  * Model-Based Collaborative filtering Recommendation

    Merekomendasikan buku berdasarkan riwayat transaksi pengguna (peringkat) dan menggunakan model pembelajaran mesin SVD untuk memprediksi dan menghitung peringkat yang diberikan pengguna ke buku lain. Kelemahan dari Collaborative filtering adalah tidak dapat merekomendasikan item tanpa riwayat transaksi.
    
## Data Understanding
Data yang penulis gunakan diperoleh dari situs web Kaggle, yaitu salah satu situs yang terkenal di dunia Data Science dan Machine Learning yang terdiri dari lebih dari 6000 dataset yang dapat diunduh dalam format CSV. Data yang digunakan adalah 'Book Recommendation Dataset', dimana terdapat 3 data didalamnya yaitu books, ratings, dan users yang masing-masing data disimpan dalam format CSV.

Ringkasan singkat data yang digunakan adalah sebagai berikut:

| Info | Keterangan |
| ---- | ---------- |
| Sumber | Kaggle |
| Nama data | Book Recommendation Dataset |
| Link | https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset |
| Usability | 10.00 |
| Lisensi | CC0: Public Domain |
| Ukuran data | 107 MB |

### Overview Data Books
Data books terdiri dari 271360 baris dan 8 kolom. Didalam data books.csv terdapat informasi Book-Title, Book-Author, Year-Of-Publication, Image-URL-S, Image-URL-M, Image-URL-L, dan Publisher.

| ISBN |	Book-Title |	Book-Author |	Year-Of-Publication |	Publisher |	Image-URL-S |	Image-URL-M |	Image-URL-L |
| ---- | ---------- | ----------- | ------------------- | --------- | ----------- | ----------- | ----------- |
|	0195153448 |	Classical Mythology	| Mark P. O. Morford |	2002	| Oxford University Press	| http://images.amazon.com/images/P/0195153448.0...	| http://images.amazon.com/images/P/0195153448.0...	| http://images.amazon.com/images/P/0195153448.0... |
|	0002005018	| Clara Callan	| Richard Bruce Wright	| 2001	| HarperFlamingo Canada	| http://images.amazon.com/images/P/0002005018.0...	| http://images.amazon.com/images/P/0002005018.0...	| http://images.amazon.com/images/P/0002005018.0... |
|	0060973129	| Decision in Normandy	| Carlo D'Este	| 1991	| HarperPerennial	| http://images.amazon.com/images/P/0060973129.0...	| http://images.amazon.com/images/P/0060973129.0...	| http://images.amazon.com/images/P/0060973129.0... |
|	0374157065	| Flu: The Story of the Great Influenza Pandemic	| Gina Bari Kolata	| 1999	| Farrar Straus Giroux	| http://images.amazon.com/images/P/0374157065.0...	| http://images.amazon.com/images/P/0374157065.0...	| http://images.amazon.com/images/P/0374157065.0... |
|	0393045218	| The Mummies of Urumchi	| E. J. W. Barber	| 1999	| W. W. Norton Company	| http://images.amazon.com/images/P/0393045218.0...	| http://images.amazon.com/images/P/0393045218.0...	| http://images.amazon.com/images/P/0393045218.0... |

### Overview Data Ratings
Data ratings terdiri dari 1149780 baris dan 3 kolom. Didalam data ratings.csv terdapat informasi User-ID, ISBN, dan Book-Rating.

| User-ID	| ISBN	| Book-Rating |
| ------- | ---- | ----------- |
| 276725	| 034545104X	| 0 |
| 276726	| 0155061224	| 5 |
| 276727	| 0446520802	| 0 |
| 276729	| 052165615X	| 3 |
| 276729	| 0521795028	| 6 |

### Overview Data Users
Data users terdiri dari 278858 baris dan 3 kolom. Didalam data users.csv terdapat informasi User-ID,	Location, dan	Age.

| User-ID	| Location	| Age |
| ------- | -------- | --- |
| 1	| nyc, new york, usa	| NaN |
| 2	| stockton, california, usa	| 18.0 |
| 3	| moscow, yukon territory, russia	| NaN |
| 4	| porto, v.n.gaia, portugal	| 17.0 |
| 5	| farnborough, hants, united kingdom	| NaN |

## Data Preparation
Pada tahapan ini, penulis akan melakukan proses transformasi pada data sehingga menjadi bentuk yang cocok dalam proses pemodelan. Terdapat beberapa tahapan yang perlu dilakukan pada data preparation, diantaranya adalah sebagai berikut:

* Handling Missing Value
Pada proses handling missing value, misalnya data umur ada yang null, data rating bernilai 0. Caranya adalah dengan menghapus atau mengganti data tersebut dengan nilai lain.

* Encoding
Melakukan encoding data pada UserID dan Book Title supaya dapat dibaca oleh model dengan baik.

## Modeling
### Popularity based recommendation
Digunakan untuk menggabungkan informasi rata-rata rating dan jumlah rating yang diterima per buku dengan menerapkan weighted rating, kemudian memilih 10 produk terbaik. 

Persamaan weighted rating

![Persamaan weighted rating](https://github.com/rizkialvian/Machine_Learning_Terapan_Proyek_Kedua/blob/7d72cdf934c3d3cf25b01ee4a94cc44c4d04f173/img/persamaan%20weighted%20rating.PNG?raw=true)

Keterangan:
* W : weighted rating
* v : jumlah rating diterima per buku
* R : rata-rata rating per buku
* C : rata-rata rating seluruh buku
* m : minimal jumlah rating yang diterima

Berikut ini adalah hasil rekomendasi dengan menerapkan weighted rating:

| No | Book Title	| Weighted Rating |
| -- | ---------- | --------------- |
| 1 | Harry Potter and the Chamber of Secrets Postcard Book	| 9.682203 |
| 2 | Postmarked Yesteryear: 30 Rare Holiday Postcards	| 9.619622 |
| 3 | Dilbert: A Book of Postcards	| 9.603672 |
| 4 | The Two Towers (The Lord of the Rings, Part 2)	| 9.557596 |
| 5 | The Giving Tree	| 9.547958 |
| 6 | The Sneetches and Other Stories	| 9.505509 |
| 7 | Fox in Socks (I Can Read It All by Myself Beginner Books)	| 9.503443 |
| 8 | Uncle John's Supremely Satisfying Bathroom Reader (Uncle John's Bathroom Reader)	| 9.450565 |
| 9 | Natural California: A Postcard Book	| 9.450565 |
| 10 | Calvin and Hobbes	| 9.425196 |

### Model-Based Collaborative filtering Recommendation
Dilakukan training data user buku dengan model SVD dari library Surprise yang selanjutnya 10 buku dengan prediksi rating tertinggi akan diurutkan. Berikut ini adalah hasil rekomendasi yang diperoleh:

| No | ISBN	| Book Title	| Book Author	| Publisher	| Estimate Score |
| -- | ---- | ---------- | ----------- | --------- | -------------- |
| 1 | 0345417127	| The Crow: Shattered Lives Broken Dreams	| J. O'Barr	Del Rey Books	| 8.151110 |
| 2 | 0835911071	| Star Trek Next Generation: Contamination	| John Vornholt	Globe Fearon	| 8.113014 |
| 3 | 3596148642	| Austerlitz.	| Winfried G. Sebald	Fischer (Tb.), Frankfurt	| 8.100955 |
| 4 | 8478887121	| LA Nochevieja | De Montalbano (Narrativa)	Andrea Camilleri	Salamandra	| 8.077965 |
| 5 | 0553443410	| A Prince for Jenny (Loveswept, No 656)	| Peggy Webb	Loveswept	| 8.074810 |
| 6 | 0373033346	| Sensible Wife (Harlequin Romance, No 3334)	| Jessica Hart	Harlequin |	8.068090 |
| 7 | 0451114876	| The Mystery of the Black Diamonds	Phyllis | A. Whitney	New Amer Library (Mm)	| 8.062611 |
| 8 | 1565652061	| The Diabetes Sports and Exercise Book: How to | Claudia Graham	McGraw-Hill	| 8.058640 |
| 9 | 0373691467	| Heatwave	| Jamie Denton	Harlequin	| 8.051578 |
| 10 | 0393307921	| Arrogance	| Joanna Scott	Simon Schuster	| 8.051044 |

## Evaluation
### Root Mean Squared Error (RMSE)
Root Mean Square Error adalah  metode pengukuran dengan mengukur perbedaan nilai dari prediksi sebuah model sebagai estimasi atas nilai yang diobservasi. Keakuratan metode estimasi kesalahan pengukuran ditandai dengan adanya nilai RMSE yang kecil. Metode estimasi yang mempunyai Root Mean Square Error (RMSE) lebih kecil dikatakan lebih akurat daripada metode estimasi yang mempunyai Root Mean Square Error (RMSE) lebih besar

![RMSE](https://github.com/rizkialvian/Machine_Learning_Terapan_Proyek_Kedua/blob/a05eef0ba5ef675c1905b464894ef64b73b780be/img/rmse.PNG?raw=true)

Keterangan:
* n : ukuran sampel
​* At : nilai data aktual ke-t
* Ft : nilai data peramalan ke-t

### Mean Absolute Error (MAE)
Mean Absolute Error adalah rata-rata selisih mutlak nilai aktual dengan nilai prediksi. MAE digunakan untuk mengukur keakuratan suatu model statistik dalam melakukan prediksi.

![MAE](https://github.com/rizkialvian/Machine_Learning_Terapan_Proyek_Kedua/blob/a05eef0ba5ef675c1905b464894ef64b73b780be/img/mae.PNG?raw=true)

Keterangan:
* n : ukuran sampel
​* Ai : nilai data aktual ke-i
* Fi : nilai data peramalan ke-i

## Kesimpulan
Hasil perolehan Root Mean Squared Error (RMSE) dan Mean Absolute Error (MAE) adalah sebagai berikut:

| Nama | Nilai |
| ---- | ----- |
| RMSE | 1,2671 |
| MAE | 1,6387 |

Dari tahapan-tahapan yang sudah dilakukan sebelumnya, diperoleh nilai rata-rata RMSE sebesar 1,2671 dan nilai rata-rata MAE sebesar 1,6387. Sehingga dapat disimpulkan bahwa model ini nilai error cukup kecil, yang berarti model tersebut dapat dikatakan baik. Hal ini dibuktikan juga dengan hasil rekomendasi buku yang cukup baik dan sesuai kategori.

## Referensi

[1] [Fajar, R. P. A. L., Wiguna, A. C., Oktari, D., & de Eloisa Tobing, J. A. (2022). Problematika Literasi Membaca Pada Generasi Penerus Bangsa Dalam Menghadapi Abad 21. Naturalistic: Jurnal Kajian dan Penelitian Pendidikan dan Pembelajaran, 7(1), 1478-1489.](http://www.journal.umtas.ac.id/index.php/naturalistic/article/view/2172)

[2] [Wei, J., He, J., Chen, K., Zhou, Y., & Tang, Z. (2016, August). Collaborative filtering and deep learning based hybrid recommendation for cold start problem. In 2016 IEEE 14th Intl Conf on Dependable, Autonomic and Secure Computing, 14th Intl Conf on Pervasive Intelligence and Computing, 2nd Intl Conf on Big Data Intelligence and Computing and Cyber Science and Technology Congress (DASC/PiCom/DataCom/CyberSciTech) (pp. 874-877). IEEE.](https://ieeexplore.ieee.org/abstract/document/7588947/)

[3] [Zhang, S., Yao, L., Sun, A., & Tay, Y. (2019). Deep learning based recommender system: A survey and new perspectives. ACM computing surveys (CSUR), 52(1), 1-38.](https://dl.acm.org/doi/abs/10.1145/3285029)

[4] [Rymmai, R. G., & Saleema, J. S. (2017). Book Recommendation using Cosine Similarity. International Journal of Advanced Research in Computer Science, 8(3).](https://search.ebscohost.com/login.aspx?direct=true&profile=ehost&scope=site&authtype=crawler&jrnl=09765697&AN=122961231&h=g9lStjqi8Q3om0hiUlFYXZmCQuFHM8Lt7Sa%2BQ%2BESIfbbZN7vJ9fF6gfgpSdPINcHE57Jt9aInCH80DRuOmc1Mg%3D%3D&crl=c)
