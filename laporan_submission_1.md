# Laporan Proyek Machine Learning - Shelomita

## — Domain Proyek

Dalam dunia pendidikan, salah satu acuan dalam menentukan kualitas suatu instansi adalah melalui beberapa penilaian yang dilakukan oleh lembaga bereputasi. Salah satu penilaian yang digunakan sebagai referensi di dunia pendidikan tinggi adalah QS World University Ranking [1].

QS World University Ranking adalah sebuah sistem pemeringkatan institusi pendidikan tinggi yang dikembangkan oleh QS Quacquarelli Symonds, salah satu perusahaan dunia yang berfokus dalam pendidikan tinggi [2]. Metodologi yang digunakan untuk menganalisis data untuk pemeringkatan ini adalah dengan melakukan survei, bekerja sama dengan institusi terkait, dan juga menggunakan sumber data yang tersedia secara publik untuk mendapatkan metode evaluasi dan pembandingan kualitas universitas dunia berdasarkan indikator terpilih.

Terdapat 6 indikator utama yang awalnya digunakan untuk melakukan pemeringkatan universitas dunia, yaitu _Academic Reputation, Employer Reputation, Faculty Student Ratio, Citations per Faculty, International Faculty Ratio,_ dan _International Student Ratio_[2]. Di tahun 2023 ini, terdapat 3 indikator baru yang ditambahkan dalam penilaian _QS World University Ranking 2024_, yaitu _International Research Network, Employment Outcomes,_ dan _Sustainability._ Penambahan ketiga indikator baru ini merupakan respon QS World University Ranking dalam menanggapi kebutuhan global, terutama untuk isu keamanan sosial dan iklim, interkoneksi riset secara global, dan juga peningkatan penerimaan kerja lulusan [3].

Penelitian dari Elwabab [4] membawa indikator penilaian berbagai universitas dunia ini menjadi selangkah lebih detail. Dalam penelitiannya, diungkapkan bahwa berdasarkan indikator-indikator tersebut, berbagai universitas dapat dikelompokkan menurut capaian tujuannya. Penelitian ini menggunakan metode clustering yang membagi universitas menjadi 4 kelompok dengan capaian indikator QS World University Ranking. Berdasarkan kesimpulan dari penelitian ini, kelompok capaian tujuan tersebut dapat digunakan sebagai basis untuk penentuan keputusan oleh instansi perguruan tinggi dalam menyelaraskan tujuannya secara internasional dan terstruktur.

Penelitian yang dilakukan berdasarkan data QS World University Ranking 2022 ini pada saat ini sudah kurang relevan, dikarenakan terdapat penambahan 3 indikator utama pada data QS World University Ranking 2024. Perubahan jumlah universitas yang diangkat dalam QS World University Ranking juga terjadi setiap tahunnya, dimana peningkatan jumlahnya dapat dilihat seperti pada gambar di bawah ini.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/d1b5ca76-7259-4358-a84b-d1f44e76f719)
<p align="center">Gambar 1. Jumlah Universitas dalam QS World University Ranking Menurut Tahun</p>

Adanya penambahan indikator utama dan peningkatan jumlah universitas yang diangkat membuat keterbaruan data menjadi berkurang, sehingga untuk mengetahui bagaimana perkembangan capaian universitas dunia saat ini, dapat melakukan analisis cluster dengan data indikator terbaru QS University Ranking 2024.

Berdasarkan hasil kelompok dalam analisis cluster dapat ditunjukkan berbagai kelompok capaian indikator penilaian QS World University Ranking 2024 yang kedepannya dapat menjadi acuan bagi instansi pendidikan tinggi dalam menyelaraskan tujuannya dalam peningkatan mutu pendidikan.

## — Business Understanding

Sebagai upaya untuk meningkatkan kualitas satuan pendidikan, perhatian khusus diberikan oleh satuan pendidikan terkait maupun pemerintah dalam menyusun tujuan dan capaian pembelajaran. Universitas selaku lembaga pendidikan tinggi juga tidak tertinggal dalam kompetisi kualitas ini, sehingga dalam pelaksanaannya dibentuk strategi untuk mengidentifikasi area-area yang membutuhkan peningkatan kualitas.

Dalam mengukur kualitas universitas ini, terdapat salah satu media yang telah banyak digunakan secara global yaitu dengan menggunakan peringkat atau _ranking._ Berdasarkan pemeringkatan universitas secara global yang dilakukan oleh _QS World University Ranking_ dan indikatornya, dapat dilakukan pengelompokan universitas berdasarkan capaian dari indikator tersebut. Dengan menggunakan kelompok berdasarkan indikator yang telah terpercaya secara global, maka identifikasi area-area yang penting untuk ditingkatkan dapat menjadi lebih terukur.

Selain itu, pengelompokan universitas ini juga berguna bagi calon mahasiswa, khususnya mahasiswa internasional maupun nasional yang tertarik untuk mendaftar di universitas. Dengan melihat kelompok capaian indikator tersebut, calon mahasiswa dapat menentukan universitas yang ingin dituju mempertimbangkan bagaimana kinerja universitas yang dia inginkan dalam mencapai indikator internasional yang telah ada.

### Problem Statements

Berdasarkan latar belakang tersebut, dapat disusun rumusan masalah analisis sebagai berikut:
- Bagaimana kelompok capaian indikator QS World University Ranking?
- Apakah kecenderungan yang mempengaruhi setiap kelompok capaian indikator QS World University Ranking?
- Bagaimana pengaruh setiap kelompok capaian indikator tersebut dalam menyusun strategi peningkatan mutu pendidikan tinggi?

### Goals

Berdasarkan rumusan masalah tersebut akan dicapai tujuan sebagai berikut:
- Mengetahui kelompok capaian indikator QS World University Ranking untuk universitas-universitas di dunia
- Mengetahui kecenderungan yang mempengaruhi kelompok capaian indikator QS World Ranking 2024
- Mengetahui pengaruh kelompok capaian indikator dalam menyusun strategi peningkatan mutu pendidikan tinggi

### Solution statements

Untuk menyelesaikan masalah dan mencapai tujuan diatas, akan dibuat analisis _cluster_ dengan algoritma KMeans untuk mendapatkan kelompok capaian indikator QS World University Ranking 2024. Kelompok capaian indikator ini kemudian dapat dianalisis secara deskriptif untuk menunjukkan karakteristik masing-masing kelompok yang berguna untuk menentukan unsur yang menonjol untuk masing-masing kelompok.

Pemilihan jumlah _cluster_ terbaik akan dilakukan dengan menggunakan _elbow method_ untuk mendapatkan _cluster_ dengan _inertia_ yang baik sehingga jumlah kelompok yang dihasilkan dapat merepresentasikan data dengan baik.

Dalam mengevaluasi performa model, digunakan ...

## — Data Understanding

Data yang digunakan dalam proyek ini bersumber dari [QS World University Rankings 2024](https://www.kaggle.com/datasets/joebeachcapital/qs-world-university-rankings-2024) yang diunduh melalui platform Kaggle.

Data tersebut menunjukkan penilaian dari 1497 Universitas di dunia, dengan rincian fiturnya sebagai berikut, seperti bersumber dari [2].
<p align="center">Tabel 1. Fitur Data dan Keterangannya</p>

| Kolom | Keterangan |
|-------|-----------|
| 2024 Rank | Peringkat universitas di tahun 2024 |
| 2023 Rank | Peringkat universitas di tahun 2023 |
| Institution Name | Nama universitas |
| Country Code | Kode negara |
| Country | Negara asal universitas |
| Size | Daya tampung universitas |
| Focus | Pembagian fakultas |
| Age | Lama berdirinya universitas |
| RES. | Frekuensi riset |
| Status | Status universitas |
| Academic Reputation Score | Skor reputasi mahasiswa dan riset universitas |
| Academic Reputation Rank | Peringkat global reputasi akademik |
| Employer Reputation Score | Skor reputasi lulusan |
| Employer Reputation Rank | Peringkat global reputasi lulusan |
| Faculty Student Score | Skor rasio perbandingan tenaga pendidik dengan mahasiswa |
| Faculty Student Rank | Peringkat global rasio perbandingan tenaga pendidik dengan mahasiswa |
| Citations per Faculty Score | Skor intensitas dan volume riset yang dilakukan di universitas |
| Citations per Faculty Rank | Peringkat global intensitas dan volume riset yang dilakukan di universitas |
| International Faculty Score | Skor rasio tenaga pendidik internasional |
| International Faculty Rank | Peringkat global rasio tenaga pendidik internasional |
| International Students Score | Skor rasio mahasiswa internasional |
| International Students Rank | Peringkat global rasio mahasiswa internasional |
| International Research Network Score | Skor kerjasama riset internasional |
| International Research Network Rank | Peringkat global kerjasama riset internasional |
| Employment Outcomes Score | Skor indeks lulusan dan tingkat penerimaan kerja |
| Employment Outcomes Rank | Peringkat global indeks lulusan dan tingkat penerimaan kerja |
| Sustainability Score | Skor komitmen dalam menjaga SDG dan lingkungan |
| Sustainability Rank | Peringkat global komitmen dalam menjaga SDG dan lingkungan |
| Overall Score | Jumlah skor 9 indikator terbobot |

Pada data terdapat 4 variabel kategorik yaitu Size, Focus, Age, dan RES. dengan penjelasan seperti berikut.
- Size (Daya tampung universitas)
  <p align="center">Tabel 2. Kategori Size (Daya Tampung Universitas) dan Kelasnya</p>
  
  | Size | Keterangan |
  |------|------------|
  | XL | > 30.000 mahasiswa |
  | L | >= 12.000 mahasiswa |
  | M | >= 5.000 mahasiswa |
  | S | < 5.000 mahasiswa |
- Focus (Pembagian fakultas)
  <p align="center">Tabel 3. Kategori Focus (Pembagian Fakultas) dan Kelasnya</p>
  
  | Focus | Keterangan |
  |------|------------|
  | FC (Fully comprehensive) | 5 fakultas + fakultas kedokteran |
  | CO (Comprehensive) | 5 fakultas |
  | FO (Focused) | 3 - 4 fakultas |
  | SP (Specialist) | 2 atau kurang fakultas |
- Age (Lama berdirinya universitas)
  <p align="center">Tabel 4. Kategori Age (Lama Berdirinya Universitas) dan Kelasnya</p>
  
  | Age | Keterangan |
  |------|------------|
  | New | < 10 tahun |
  | Young | 10 - 24 tahun |
  | Established | 25 - 49 tahun |
  | Mature | 50 - 99 tahun |
  | Historic | > 100 tahun |
- RES. (Frekuensi riset)
  <p align="center">Tabel 5. Kategori RES. (Pembagian Frekuensi Riset) dan Kelasnya</p>
  
  | RES | Keterangan |
  |------|------------|
  | VH | Sangat tinggi |
  | MI | Tinggi |
  | MD | Medium |
  | LO | Rendah |

Variabel kategorik ini dapat berguna jika dianalisis hubungan antara fitur-fitur pada data dengan peringkat universitas atau skor total indikatornya. Tetapi karena proyek ini berfokus pada 9 indikator utama dari QS World University Ranking, analisis dari fitur kategoriknya belum diperlukan.

Untuk lebih mengeksplor data, dapat dilakukan beberapa visualisasi seperti di bawah ini.

### Analisis universitas berdasarkan negara asal
Dari 195 negara di dunia, hanya 104 negara memiliki universitas yang berperingkat global QS. Distribusi dari universitas berdasarkan negaranya adalah seperti berikut.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/29230160-bb7a-4a11-8cff-9060ca606b0b)
<p align="center">Gambar 2. Jumlah Universitas dalam QS World University Ranking Menurut Negara Asal</p>

Berdasarkan data tersebut juga dapat dibentuk peta visualisasi untuk jumlah universitas berperingkat di setiap negara.

![newplot](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/b8870685-99e4-45ce-88ce-9b124e748e6d)
<p align="center">Gambar 3. Jumlah Universitas dalam QS World University Ranking Menurut Negara Asal dalam Peta</p>

Universitas _QS World Ranking 2024_ didominasi berasal dari Amerika Serikat, Inggris, China, Jerman, dan Rusia.

Dapat dilihat pula, tidak seluruh negara di dunia memiliki universitas yang diangkat dalam QS World Ranking 2024. Banyak universitas dari Afrika yang tidak diangkat dalam penilaian sehingga hasil analisis tidak dapat merefleksikan kualitas pendidikan tinggi di seluruh dunia.

## — Data Preparation

Dalam mempersiapkan data untuk analisis, dilakukan langkah-langkah sebagai berikut.

### Menangani missing value
Pada data masih terdapat _missing value_ atau nilai yang hilang, dengan jumlahnya untuk masing-masing fitur seperti berikut.
<p align="center">Tabel 6. Indikator dan Jumlah Data Hilang</p>

| Indikator | Jumlah Missing Value |
|----------|---------|
| Academic Reputation Score | 0 |
| Employer Reputation Score | 1 |
| Faculty Student Score | 24 |
| Citations per Faculty Score | 24 |
| International Faculty Score | 126 |
| International Students Score | 80 |
| International Research Network Score | 4 |
| Employment Outcomes Score | 24 |
| Sustainability Score | 100 |

Karena masih terdapat nilai yang hilang pada data, penggantian nilai harus dilakukan supaya bisa dilanjutkan dengan analisis. Melihat dari data yang memiliki urutan peringkat, dapat diasumsikan bahwa universitas dengan peringkat yang berdekatan memiliki skor indikator yang mirip. Oleh karena itu, diperlukan metode penanganan data hilang yang sesuai dengan karakteristik tersebut. Salah satu metode penanganan nilai hilang yang sesuai dengan karakteristik ini adalah _K-Nearest Neigbor Imputation_. 

Dikarenakan data memiliki urutan ranking, diasumsikan universitas dengan ranking yang berdekatan memiliki skor indikator yang mirip, sehingga dalam menangani missing value digunakan imputasi K-Nearest Neighbor. Metode ini memberikan nilai kepada data hilang dengan menemukan sampel yang "terdekat" dari data tersebut dan merata-ratakannya [5]. Metode _K-Nearest Neighbor Imputer_ ini dapat diakses dalam _library_ sklearn.

```
from sklearn.impute import KNNImputer

knn_imputer = KNNImputer(n_neighbors=4, weights="uniform")
```

Dalam analisis ini digunakan imputasi K-Nearest Neighbor dengan parameter k = 4, artinya ditinjau 4 data yang berdekatan dengan data yang hilang tersebut untuk dirata-ratakan nilainya. Selain itu juga digunakan parameter _"weights"_ dimana parameter ini mengukur jarak antara tiap sampel yang diambil, yaitu berdistribusi uniform.

Imputasi data ini dilakukan dengan melakukan transformasi pada fitur sasaran. Kemudian apabila telah dihasilkan _dataset_ tanpa nilai hilang, maka pengolahan data tersebut sudah berhasil.

Dari proses penggantian data hilang tersebut diperoleh hasil statistik deskriptif seperti berikut.

<p align="center">Tabel 7. Statistik Deskriptif Setelah Imputasi Data Hilang</p>

| | Academic Reputation Score |	Employer Reputation Score	| Faculty Student Score |	Citations per Faculty Score	| International Faculty Score	| International Students Score	| International Research Network Score	| Employment Outcomes Score	| Sustainability Score |
|------|------|-----|------|------|-----|-----|-----|-----|-----|
| count |	1497.000000	| 1497.000000	| 1497.000000	| 1497.000000	| 1497.000000	| 1497.000000	| 1497.000000	| 1497.000000	| 1497.000000 |
| mean	| 20.083155	| 19.758395	| 28.579416	| 23.877446	| 30.902263	| 25.541455	| 23.935791	| 19.943750	| 25.379370 |
| std	| 22.284590	| 23.681035	| 27.565228	| 27.765553	| 32.732346	| 29.998562	| 30.291268	| 19.972002	| 29.915974 |
| min	| 1.600000	| 1.000000	| 1.000000	| 1.000000	| 1.000000	| 1.000000	| 1.000000	| 1.000000	| 1.000000 |
| 25%	| 6.000000	| 4.075000	| 7.600000	| 2.800000	| 4.775000	| 3.200000	| 1.200000	| 8.300000	| 1.500000 |
| 50%	| 10.900000	| 9.450000	| 17.150000	| 10.900000	| 16.800000	| 11.950000	| 6.950000	| 11.900000	| 11.700000 |
| 75%	| 23.100000	| 25.425000	| 41.100000	| 37.425000	| 44.325000	| 34.650000	| 40.225000	| 22.000000	| 38.400000 |
| max	| 100.000000	| 100.000000	| 100.000000	| 100.000000	| 100.000000	| 100.000000	| 100.000000	| 100.000000 |	100.000000 |

Berdasarkan hasil tersebut dapat dilihat seluruh data telah berjumlah 1497, yaitu tidak terdapat nilai yang kosong. Selain itu, nilai minimum dan maksimum data juga telah berada pada rentang yang sesuai yaitu 1-100, sehingga tidak perlu dilakukan penanganan _outlier_ pada data.

### Feature scaling
Ketika bekerja dengan algoritma berbasis jarak, seperti KMeans _clustering,_ data perlu dibawa ke skala yang sama supaya perbedaan rentang pada data tidak memberikan bobot yang lebih ketika digunakan untuk mengukur jaraknya. Untuk membawa data ke rentang 0-1 dilakukan _feature scaling_ dengan MinMaxScaler yang terdapat pada library sklearn.

Berikut adalah statistik deskriptif dari data setelah dilakukan _feature scaling_.

<p align="center">Tabel 8. Statistik Deskriptif Setelah Skala Fitur</p>

| | Academic Reputation Score	| Employer Reputation Score	| Faculty Student Score	| Citations per Faculty Score	| International Faculty Score	| International Students Score	| International Research Network Score	| Employment Outcomes Score	| Sustainability Score |
|------|------|-----|------|------|-----|-----|-----|-----|-----|
| count|	1497.000000	|1497.000000|	1497.000000|	1497.000000	|1497.000000	|1497.000000	|1497.000000|	1497.000000	|1497.000000 |
| mean	|0.188379	|0.190021	|0.279070	|0.231607|	0.302552|	0.248340|	0.232151|	0.191900|	0.246761 |
| std	|0.227365|	0.240038|	0.278967|	0.281070|	0.331011|	0.303356|	0.306421|	0.202750|	0.302630 |
| min|	0.000000	|0.000000|	0.000000|	0.000000|	0.000000|	0.000000|	0.000000| 0.000000|	0.000000 |
| 25%|0.044715	|0.031313|	0.066667|	0.018182|	0.038384|	0.022222|	0.002020|	0.073737|	0.005051 |
| 50%	|0.094512|	0.085859|	0.163636|	0.100000|	0.159596|	0.111111|	0.060606|	0.110101|	0.108081 |
| 75%	|0.218496|	0.247475|	0.405051|	0.368687|	0.438384|	0.341414|	0.396970|	0.212121|	0.377778 |
| max	|1.000000|	1.000000|	1.000000|	1.000000|	1.000000|	1.000000|	1.000000|	1.000000|	1.000000 |

Dapat dilihat setelah dilakukan _feature scaling_ data menjadi berada dalam rentang 0-1 dan variansi dalam data menjadi tidak terlalu besar dibandingkan sebelum dilakukan _feature scaling_.

### EDA Setelah Preparation

Setelah dilakukan persiapan pada data, dapat dilakukan visualisasi dari nilai-nilai 9 indikator.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/af5584fa-003a-4cf6-9e60-7616c27a96fc)
<p align="center">Gambar 4. Visualisasi Histogram 9 Indikator</p>

Berdasarkan visualisasi tersebut, dapat terlihat bahwa seluruh indikator memiliki kecenderungan condong _(skew)_ ke kanan, dimana nilai mediannya lebih kecil daripada rata-ratanya. Karena pemodelan yang dilakukan adalah _unsupervised learning_ yaitu _KMeans clustering_ kecondongan distribusi ini tidak akan terlalu berpengaruh pada model sehingga analisis dapat dilanjutkan ke tahap selanjutnya.

## — Modeling

Dalam memodelkan data digunakan algoritma KMeans yang terdapat dalam library sklearn. Algoritma KMeans sendiri adalah algoritma yang mengelompokkan _cluster_ berdasarkan kedekatannya dengan _centroid_ atau pusat yang adalah rata-rata dari beberapa sampel dalam kelompok tersebut [6].

Langkah-langkah dalam pengerjaan _clustering_ dengan algoritma KMeans adalah sebagai berikut.
1. Kelompokkan data berdasarkan K jumlah _cluster_ awal
2. Iterasi seluruh data sehingga semua data masuk ke _cluster_ dengan rata-rata yang terdekat. Jarak ini diukur dengan jarak Euclid atau akar dari selisih pada sumbu x dan y-nya. Selanjutnya hitung pusat rata-rata baru dari _cluster_ tersebut.
3. Ulangi langkah ke-2 hingga seluruh data telah masuk ke _cluster_ yang ada

Di tahap pertama, digunakan jumlah _cluster_ inisiasi (awal) berdasarkan jumlah kelompok yang telah diteliti sebelumnya[4], yaitu sebanyak 4 kelompok. Sintaks untuk melakukan pemodelan KMeans adalah sebagai berikut. Setelah dilakukan pembentukan model, kemudian model tersebut digunakan untuk mengelompokkan data yang ada dengan _model.fit_.

Pada pemodelan ini digunakan parameter _n-clusters,_ yaitu jumlah _cluster_ inisiasi yang digunakan sebanyak 4 kelompok, _random_state_ yang menunjukkan keadaan acak supaya analisis bisa direplikasi, dan _n-init_ yaitu jumlah iterasi yang dilakukan dalam model yang jumlahnya disesuaikan otomatis oleh komputer.

```
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=4, random_state=0, n_init='auto')

kmeans.fit(qsdata_scaled)
```

Namun, kelemahan dari model KMeans adalah tidak bisa langsung ditentukan jumlah cluster terbaik berdasarkan nilai awal tersebut. Iterasi harus dilakukan dengan banyak nilai _cluster_ pada algoritma KMeans untuk mengetahui hasil terbaiknya. Salah satu cara untuk menentukan jumlah _cluster_ terbaik adalah dengan menggunakan _elbow method._

_Elbow method_ menggunakan plot dari _inertia_ model, atau seberapa baik model tersebut dalam menjelaskan data, dimana secara umum semakin kecil _inertia_ model, maka hasil pengelompokkannya akan semakin baik. Namun, semakin banyak jumlah cluster maka _inertia_ akan semakin menurun, sehingga harus dipilih jumlah _cluster_ yang dapat menjelaskan data dengan baik, namun tidak terlalu banyak sehingga menyebabkan _over-fitting,_ yaitu model yang memiliki performa baik dengan data latih namun tidak bisa menjelaskan data yang belum ditemui. Cara untuk memilih _cluster_ ini adalah dengan memilih _elbow_ atau siku dari kurva, dimana _elbow_ tersebut menunjukkan titik potong optimisasi matematis yang menunjukkan penurunan _inertia_ tidak lagi menguntungkan dalam segi _cost_ model.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/bb4efcbb-ba5c-4ed7-8cea-9ea496073e8c)
<p align="center">Gambar 5. Hasil Plot Elbow Method Berdasarkan Jumlah Cluster terhadap Inertia Model</p>

Berdasarkan hasil yang didapatkan melalui _elbow method_ tersebut, dapat dilihat siku dari kurvanya berada pada jumlah _cluster_ sebanyak 2 kelompok. Untuk selanjutnya, dapat dilakukan pemodelan KMeans dengan _n-cluster_ = 2 untuk mengelompokkan universitas di dunia seperti di bawah ini.
```
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=2, random_state=0, n_init='auto')

kmeans.fit(qsdata_scaled)
cluster_labels = kmeans.labels_
```

## — Evaluation

Untuk melakukan evaluasi kebaikan pembagian kelompok dari algoritma KMeans, digunakan Davies-Bouldin index. Davies-Bouldin index adalah penghitungan kesamaan antar _cluster_ dengan _cluster_ yang mirip [8]. Semakin rendah indeks DBI menunjukkan semakin rendahnya rata-rata kesamaan antar _cluster_, sehingga menunjukkan _cluster_ tersebut sudah terpisah dengan baik dan hasil _clustering_ yang dilakukan sudah baik. Untuk menghitung indeks DBI bisa dilakukan dengan _library_ scikitlearn.

Hasil dari visualisasi jumlah _cluster_ dan indeks DBI-nya adalah sebagai berikut.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/19f24adc-08ab-4814-9f0b-6d982a7519f4)
<p align="center">Gambar 6. Hasil Plot indeks DBI Berdasarkan Jumlah Cluster</p>

Berdasarkan hasil pada gambar tersebut, diketahui jumlah _cluster_ dengan indeks DBI yang paling rendah adalah sebanyak 2 kelompok. Hal ini mendukung hasil pemilihan _cluster_ terbaik yang telah dilakukan dengan _elbow method_ sebelumnya.

Ukuran dari indeks DBI pada _n-cluster = 2_ adalah 1.1479158683894037. Sementara _inertia_ dari model tersebut, yang digunakan dalam _elbow method_ adalah 448.0545560896285. Dari angka tersebut dapat diketahui untuk jumlah _cluster_ sebanyak 2 kelompok telah menghasilkan kelompok yang terbagi dengan baik, yaitu memiliki indeks DBI yang rendah dan juga telah memiliki _inertia_ yang optimum sehingga telah mampu memodelkan data yang ada dengan cukup baik.

## — Interpretasi & Analisis

Berdasarkan pemodelan yang dilakukan dengan KMeans sebelumnya, telah terbentuk 2 kelompok universitas berdasarkan capaian indikator QS World Ranking 2024. Untuk mengetahui karakteristik dari kelompok tersebut, dapat dianalisis berdasarkan salah satu statistik deskriptifnya seperti berikut ini.

<p align="center">Tabel 9. Median 9 Indikator Berdasarkan Kelompok Cluster</p>

| Cluster | Academic Reputation Score	| Employer Reputation Score	| Faculty Student Score	| Citations per Faculty Score	| International Faculty Score	| International Students Score	| International Research Network Score	| Employment Outcomes Score	| Sustainability Score |
|------|------|-----|------|------|-----|-----|-----|-----|-----|								
|0	|44.05	|38.0	|32.65	|50.0	|75.9	|51.9	|66.35	|31.0	|73.6|
|1	|8.30	|6.5	|14.60	|5.9	|9.1	|5.9	|2.40	|9.9	|3.8|

Statistik deskriptif yang digunakan untuk mengaggregasi data adalah median. Dikarenakan terdapat kecenderungan _skew_ kanan pada data seperti yang telah diamati sebelumnya, rata-rata tidak menunjukkan pusat data yang sebenarnya dikarenakan nilainya yang akan tertarik ke kanan akibat rentang data yang lebar ke kana. Median digunakan supaya terdapat gambaran mengenai pusat nilai tengah dari masing-masing indikator dan tidak terpengaruh nilai-nilai yang condong ke kanan.

Dari tabel median 9 indikator tersebut, dapat terlihat untuk kelompok pertama atau _cluster 0_ memiliki kecenderungan median seluruh indikator yang tinggi. Sementara untuk kelompok kedua atau _cluster 1_ memiliki kecenderungan median seluruh indikator yang rendah.

Dapat diamati pula korelasi antara seluruh indikator dan kelompok _cluster_ terhadap skor terbobot pemeringkatan seperti pada dibawah ini.

![correlation](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/5f2097c4-fb39-4154-9ee7-715d884f9da9)
<p align="center">Gambar 7. Korelasi Indikator dan Cluster terhadap Overall Score</p>

Dapat diketahui indikator yang berhubungan sangat kuat secara positif (korelasi > 0.8) dengan _overall score_ adalah _academic reputation score,_ selain itu indikator lain juga memiliki hubungan kuat (0.6 < korelasi < 0.8) dengan _overall score_ adalah _employer reputation score, sustainability score, international research network score, citations per faculty score_ dan _employment outcomes score_ selain itu _cluster_ juga berkorelasi kuat negatif dengan _overall score,_ dimana ditunjukkan cluster awal memiliki _overall score_ tinggi dan _cluster_ akhir memiliki _overall score_ rendah. Selain itu indikator yang lain memiliki hubungan yang sedang (0.4 < korelasi < 0.6) dengan _overall score._ Seluruh indikator menunjukkan korelasi yang cukup kuat dengan _overall score_ sehingga seluruh indikator dapat digunakan sebagai pertimbangan dalam analisis.

### Universitas dengan capaian indikator tinggi

Universitas-universitas yang terkelompok dalam _Cluster 0_ menunjukkan median seluruh indikator yang tinggi. Berikut adalah daftar 10 universitas dengan peringkat teratas yang tergabung dalam kelompok capaian indikator tinggi.

<p align="center">Tabel 10. 10 Universitas dengan Capaian Indikator Tinggi Menurut Peringkat</p>

|Institution Name|Country|2024 Rank|Overall Score|
|-----|------|-----|-----|
|Massachusetts Institute of Technology (MIT)|United States|1|1000.0|
|University of Cambridge|United Kingdom|	2|	992.0|
|University of Oxford|	United Kingdom|	3|	989.0|
|Harvard University|	United States|	4|	983.0|
|Stanford University|	United States|	5|	981.0|
|Imperial College London|	United Kingdom|	6|	978.0|
|ETH Zurich - Swiss Federal Institute of Technology|	Switzerland|	7|	933.0|
|National University of Singapore (NUS)|	Singapore|	8|	927.0|
|UCL|	United Kingdom|	9|	924.0|
|University of California, Berkeley (UCB)|	United States|	10|	904.0|

Dapat dilihat universitas-universitas tersebut memiliki skor terbobot seluruh indikator yang tinggi dan hal tersebut terefleksi dalam peringkatnya yang tinggi secara global. Dari data 10 universitas tertinggi tersebut dapat diamati asal universitas yang didominasi dari Amerika Serikat, dan Inggris. Hal ini ternyata juga terlihat ketika diurutkan menurut jumlah universitas setiap negara, dimana universitas dengan capaian indikator tinggi kebanyakan berasal dari Amerika Serikat, Inggris, Australia, Jerman dan Kanada.

<p align="center">Tabel 11. 5 Negara dengan Universitas Berindikator Tinggi Terbanyak</p>

|Clusters|	Country|	count|
|-----|------|-----|
|0|	United States|	65|
|0|	United Kingdom|	55|
|0|	Australia|	27|
|0|	Germany|	20|
|0|	Canada|	18|

Jika divisualisasikan dalam peta, distribusi jumlah universitas dengan capaian indikator tinggi menurut negaranya adalah sebagai berikut.

![high indicator](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/95597d34-284f-4b5f-a14e-cf4acf3f033e)
<p align="center">Gambar 8. Visualisasi Distribusi Universitas dengan Capaian Indikator Tinggi Menurut Negara</p>

Dikarenakan tidak semua universitas di dunia bisa diangkat dalam QS World University Ranking 2024, khususnya universitas yang berasal dari negara-negara di Afrika, jumlah universitas dengan capaian indikator tinggi kebanyakan hanya didominasi oleh negara-negara Amerika Utara maupun Eropa.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/afb54bf1-77c5-40be-8de7-59d43486930d)
<p align="center">Gambar 9. Word Cloud Frekuensi Negara dengan Universitas dengan Capaian Indikator Tinggi</p>

Berdasarkan kelompok dengan capaian indikator tinggi ini dapat dianalisis statistik deskriptifnya seperti berikut.

<p align="center">Tabel 12. Statistik Deskriptif Universitas dengan Capaian Indikator Tinggi</p>

| Cluster | Academic Reputation Score	| Employer Reputation Score	| Faculty Student Score	| Citations per Faculty Score	| International Faculty Score	| International Students Score	| International Research Network Score	| Employment Outcomes Score	| Sustainability Score | Clusters | 2024 Rank | Overall Score |
|------|------|-----|------|------|-----|-----|-----|-----|-----|-----|-----|-----|
|count | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.000000 | 360.0 | 360.000000 | 360.000000|
|mean | 48.623889 | 44.714167 | 41.048056 | 52.250556 | 65.758889 | 54.297778 | 62.175000 | 40.946944 | 68.006470 | 0.0 | 197.377778 | 507.516667|
|std | 27.779756 | 30.060173 | 31.363576 | 28.021173 | 33.101697 | 32.576892 | 28.647547 | 27.214603 | 25.661396 | 0.0 | 130.356685 | 187.148905|
|min | 5.800000 | 3.100000 | 2.300000 | 1.700000 | 2.700000 | 1.400000 | 1.000000 | 6.700000 | 1.200000 | 0.0 | 1.000000 | 199.000000|
|25% | 25.425000 | 19.000000 | 13.000000 | 29.450000 | 37.075000 | 24.550000 | 39.950000 | 18.975000 | 50.900000 | 0.0 | 90.750000 | 359.750000|
|50% | 44.050000 | 38.000000 | 32.650000 | 50.000000 | 75.900000 | 51.900000 | 66.350000 | 31.000000 | 73.600000 | 0.0 | 181.000000 | 479.500000|
|75% | 69.550000 | 70.025000 | 65.150000 | 74.450000 | 96.850000 | 87.000000 | 87.325000 | 58.250000 | 90.525000 | 0.0 | 289.250000 | 616.500000|
|max | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 0.0 | 595.000000 | 1000.000000|

Dapat dilihat dari statistik deskriptif tersebut, terdapat 360 universitas yang masuk dalam kelompok universitas dengan capaian indikator tinggi. Universitas-universitas tersebut juga memiliki peringkat dengan rentang diatas yaitu peringkat 1-595. Namun jika dilihat masih banyak nilai minimum pada setiap indikator yang sangat rendah, sehingga meskipun universitas tersebut telah termasuk pada universitas dengan capaian indikator tinggi, masih terdapat indikator-indikator yang perlu ditingkatkan untuk meningkatkan kualitas universitas.

### Universitas dengan capaian indikator rendah

Universitas-universitas yang terkelompok dalam _Cluster 1_ menunjukkan median seluruh indikator yang rendah. Berikut adalah daftar 10 universitas dengan peringkat terbawah yang tergabung dalam kelompok capaian indikator rendah.

<p align="center">Tabel 13. 10 Universitas Terendah dengan Capaian Indikator Rendah</p>

|Institution Name|Country|2024 Rank|Overall Score|
|-----|------|-----|-----|
| University of Ibadan	Nigeria	|1401+	|19.813646|
|University of Kragujevac	| Serbia	|1401+|	3.922222 |
|University of Lagos|	Nigeria|	1401+|	18.780312|
|University of Lampung|	Indonesia|	1401+|	5.047705|
| University of Mataram|	Indonesia|	1401+|	4.969928|
|University of Oradea|	Romania|	1401+|	3.422222|
|University of Stavanger|	Norway|	1401+|	21.524757|
|University Politehnica of Timisoara, UPT|	Romania|	1401+|	3.833333|
|Western Washington University|	United States|	1401+|	7.458817|
|Zürcher Hochschule Winterthur|	Switzerland|	1401+|	18.735868|

Dapat dilihat universitas-universitas tersebut memiliki skor terbobot seluruh indikator yang rendah dan hal tersebut terefleksi dalam peringkatnya yang rendah secara global.

<p align="center">Tabel 14. 5 Negara dengan Universitas Berindikator Rendah Terbanyak</p>

|Clusters|	Country|	count|
|-----|------|-----|
|1	|United States|	134|
|1	|China (Mainland)	|62|
|1	|Russia	|46|
|1	|India	|44|
|1	|Japan	|43|

Jika divisualisasikan dalam peta, distribusi jumlah universitas dengan capaian indikator rendah menurut negaranya adalah sebagai berikut.

![low indicator](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/4cf0a110-03be-4d17-b73e-54be340887b5)
<p align="center">Gambar 10. Visualisasi Distribusi Universitas dengan Capaian Indikator Rendah Menurut Negara</p>

Dikarenakan tidak semua universitas di dunia bisa diangkat dalam QS World University Ranking 2024, khususnya universitas yang berasal dari negara-negara di Afrika, jumlah universitas dengan capaian indikator rendah tidak merepresentasikan seluruh universitas di dunia.

![image](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/ed7d2e71-187a-4a7d-8b1d-a901f16eab37)
<p align="center">Gambar 11. Word Cloud Frekuensi Negara dengan Universitas dengan Capaian Indikator Rendah</p>

Berdasarkan kelompok dengan capaian indikator rendah ini dapat dianalisis statistik deskriptifnya seperti berikut.

<p align="center">Tabel 15. Statistik Deskriptif Universitas dengan Capaian Indikator Rendah</p>

| Cluster | Academic Reputation Score	| Employer Reputation Score	| Faculty Student Score	| Citations per Faculty Score	| International Faculty Score	| International Students Score	| International Research Network Score	| Employment Outcomes Score	| Sustainability Score | Clusters | 2024 Rank | Overall Score |
|------|------|-----|------|------|-----|-----|-----|-----|-----|-----|-----|-----|
|count | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.000000 | 1137.0 | 1.137000e+03 | 1137.000000|
|mean | 11.116799 | 11.927451 | 24.695400 | 14.961916 | 19.932221 | 16.494770 | 11.890441 | 13.365219 | 11.948466 | 1.0 | 4.623436e+06 | 65.341321|
|std | 8.756602 | 14.120173 | 25.084454 | 20.900897 | 23.715972 | 22.548048 | 18.545403 | 10.649414 | 14.751371 | 0.0 | 5.185946e+06 | 105.542933|
|min | 1.600000 | 1.000000 | 1.000000 | 1.000000 | 1.000000 | 1.000000 | 1.000000 | 1.000000 | 1.000000 | 1.0 | 1.760000e+02 | 2.644444|
|25% | 5.500000 | 3.400000 | 6.500000 | 2.200000 | 3.600000 | 2.500000 | 1.100000 | 7.800000 | 1.200000 | 1.0 | 1.401000e+03 | 8.536594|
|50% | 8.300000 | 6.500000 | 14.600000 | 5.900000 | 9.100000 | 5.900000 | 2.400000 | 9.900000 | 3.800000 | 1.0 | 8.018500e+05 | 13.800000|
|75% | 13.600000 | 13.800000 | 34.100000 | 18.400000 | 30.952662 | 24.300000 | 14.300000 | 14.600000 | 22.700000 | 1.0 | 1.001120e+07 | 23.355556|
|max | 69.500000 | 96.800000 | 100.000000 | 100.000000 | 100.000000 | 100.000000 | 98.200000 | 91.400000 | 80.600000 | 1.0 | 1.201140e+07 | 485.000000|

Dapat dilihat dari statistik deskriptif tersebut, terdapat 1137 universitas yang masuk dalam kelompok universitas dengan capaian indikator rendah. Universitas-universitas tersebut juga memiliki peringkat dengan rentang dibawah yaitu peringkat 176-1401+. Dengan melihat indikator yang kurang pada masing-masing universitas dengan capaian indikator rendah ini, dapat dilakukan pengambilan keputusan yang terarah.

### Analisis Overall Score

Nilai keseleruhan dapat dianalisis untuk mendapatakan gambaran yang mempengaruhi supaya dapat mendapatkan nilai keseluruhan yang tinggi.

![overall score](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/0bf0d12e-b104-42a0-97fe-30aff5e43122)
<p align="center">Gambar 12. Distribusi Rata-rata Nilai Keseluruhan Universitas Berdasarkan Negara</p>

Nilai keseluruhan juga dapat dikelompokkan berdasarkan 10 peringkat teratas dan 10 peringkat terbawah seperti di bawah ini.

![ranking](https://github.com/bluenemophila/world-university-ranking-2024-cluster-analysis/assets/126690692/991a87b3-14d3-4076-8dbf-13fb943c2e4b)
<p align="center">Gambar 13. 10 Teratas dan 10 Terbawah Rata-rata Nilai Keseluruhan Menurut Negara</p>

Berdasarkan visualisasi tersebut, dapat dilihat 10 negara dengan rata-rata nilai keseluruhan teratas adalah Hong Kong, Singapura, Belanda, Swedia, Denmark, Selandia baru, Qatar, Australia, dan Belgia. Sementara itu 10 negara dengan rata-rata nilai keseluruhan terbawah adalah Paraguay, Iraq, Azerbaijan, Romania, Equador, Honduras, Panama, Maroko, Sudan, dan Bolivia.

## — Kesimpulan

Berdasarkan hasil analisis dan pemodelan menggunakan algoritma KMeans, data indikator QS World University Ranking 2024 dapat digunakan untuk mengelompokkan universitas di dunia menjadi 2 kelompok, yaitu kelompok dengan capaian indikator tinggi dan kelompok dengan capaian indikator rendah.

Berdasarkan kelompok tersebut, negara-negara yang sudah memiliki banyak universitas dengan capaian indikator tinggi diantaranya adalah Amerika Serikat, Inggris, Australia, Jerman, dan Kanada. Sementara itu negara-negara dengan banyak universitas bercapaian indikator rendah adalah Amerika Serikat, China, Rusia, India, dan Jepang. Meskipun negara-negara tersebut memiliki banyak universitas dalam kelompok capaian indikator rendah, namun hal tersebut diakibatkan karena banyaknya universitas di negara tersebut yang diangkat dalam QS World University Ranking 2024. Untuk mengetahui kelompok dengan capaian rendah dapat dilakukan analisis selanjutnya dengan menggunakan skor keseluruhan.

Jika dilihat dari skor keseluruhannya, negara-negara dengan capaian indikator rendah dengan peringkat 10 terbawahnya adalah Paraguay, Iraq, Azerbaijan, Romania, Equador, Honduras, Panama, Maroko, Sudan, dan Bolivia. Hal tersebut dapat dijadikan catatan bagi universitas di negara tersebut maupun universitas lain dengan kondisi yang sama untuk dapat meninjau kembali pelaksanaan pendidikan tinggi dengan kriteria indikator yang telah dibentuk oleh QS World.

Dalam mengembangkan kualitas pendidikan tinggi, beberapa hal yang dapat didahulukan adalah fokusnya terhadap reputasi mahasiswa dan akademik, reputasi lulusan, komitmen dalam menjaga SDG dan lingkungan, riset internasional, intensitas dan volume riset di universitas, dan indeks lulusan dan penerimaan kerja. Indikator-indikator tersebut memiliki sumbangan besar terhadap skor dan peringkat universitas secara global.

Dalam penyusunan strategi peningkatan mutu pendidikan tinggi diperlukan tujuan dan landasan yang terukur. Salah satu upaya yang dilakukan dapat mengacu pada hasil QS World University Ranking 2024 ini, dimana universitas dengan skor yang masih rendah pada setiap indikator dapat memfokuskan performanya dalam indikator tersebut.

Sebagai mahasiswa pengelompokan dan skor ini juga dapat digunakan sebagai sumber untuk pengambilan keputusan, terutama bagi mahasiswa internasional, untuk melanjutkan pendidikan tingginya pada universitas dengan berbagai kualitas yang sesuai dengan harapannya.

Meskipun sudah tercapai hasil akhir yang sesuai dengan tujuan maupun rumusan masalah pada awal analisis, penelitian ini masih memiliki kelemahan, kelompok yang dihasilkan melalui pemodelan terlalu sedikit dan kurang merepresentasikan perbedaan kondisi antara setiap universitas di dunia. Selain itu, ketersediaan data yang terbatas secara geografis juga menyebabkan hasil yang kurang valid untuk merepresentasikan kualitas pendidikan tinggi di seluruh dunia. Untuk kedepannya, analisis dapat dilakukan dengan mempertimbangkan kebutuhan pengelompokan universitas maupun kebutuhan untuk melakukan prediksi berdasarkan fitur-fitur yang ada.

## — Referensi
[1] “About QS,” QS Top Universities, https://www.topuniversities.com/about-qs (accessed Sep. 19, 2023). \
[2] Bryan, “QS Ranking Methodology 2024: Ranking The Best Universities,” Britannia UK, https://britannia-study.co.uk/universities/qs-ranking-methodology/ (accessed Sep. 19, 2023). \
[3] C. OCallaghan, “QS World University Rankings methodology: Using rankings to start your university search,” Top Universities, https://www.topuniversities.com/qs-world-university-rankings/methodology (accessed Sep. 19, 2023). \
[4] R. Elbawab, “University Rankings and Goals: A Cluster Analysis,” Economies, vol. 10, no. 9, p. 209, Aug. 2022. doi:10.3390/economies10090209 \
[5] M. Kuhn and K. Johnson, Applied Predictive Modeling. New York: Springer, 2019. \
[6] R. A. Johnson and D. W. Wichern, Applied Multivariate Statistical Analysis. Upper Saddle River, NJ: Prentice Hall, 2007. \
[7] R. L. Thorndike, “Who belongs in the family?,” Psychometrika, vol. 18, no. 4, pp. 267–276, 1953. doi:10.1007/bf02289263 \
[8] D. L. Davies and D. W. Bouldin, “A Cluster Separation Measure,” IEEE Transactions on Pattern Analysis and Machine Intelligence, vol. PAMI-1, no. 2, pp. 224–227, 1979. doi:10.1109/tpami.1979.4766909 
