# Laporan Proyek Machine Learning - Shelomita

## Domain Proyek

Dalam dunia pendidikan, salah satu acuan dalam menentukan kualitas suatu instansi adalah melalui beberapa penilaian yang dilakukan oleh lembaga bereputasi. Salah satu penilaian yang digunakan sebagai referensi di dunia pendidikan tinggi adalah QS World University Ranking. Indikator yang digunakan sebagai penilaian pada QS University Rangking mencakup reputasi akademik, reputasi tenaga kependidikan, publikasi kampus, jumlah mahasiswa internasional, dan penerimaan kerja lulusan. Berbagai universitas unggulan di dunia menjadikan indikator penilaian tersebut sebagai acuan untuk mempertahankan kualitasnya.

Penelitian dari [Elwabab](https://www.mdpi.com/2227-7099/10/9/209) (2022) membawa indikator penilaian berbagai universitas dunia ini menjadi selangkah lebih detail. Dalam penelitiannya, diungkapkan bahwa berdasarkan indikator-indikator tersebut, berbagai universitas dapat dikelompokkan menurut capaian tujuannya. Pengelompokan ini dilakukan dengan metode clustering, dimana dihasilkan kelompok universitas yang lebih terfokus pada publikasi, kelompok universitas yang terfokus pada pengembangan mahasiswa, kelompok universitas yang berhasil mengembangkan seluruh indikator, dan kelompok universitas yang kurang berhasil mengembangkan indikator.

Penelitian tersebut dilakukan berdasarkan data QS University Ranking pada tahun 2022, dimana saat ini data tersebut sudah kurang relevan karena telah terdapat data terbaru pada tahun 2023. Oleh karena itu, untuk mengetahui bagaimana perkembangan capaian universitas dunia pada saat ini, kita dapat melakukan analisis cluster pada data indikator QS University Ranking tahun 2023.

Berdasarkan hasil kelompok dalam analisis cluster dapat ditunjukkan berbagai kelompok capaian indikator penilaian QS World University Ranking yang kedepannya dapat menjadi acuan bagi instansi pendidikan tinggi dalam menyelaraskan tujuannya dalam peningkatan mutu pendidikan.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang tersebut, dapat disusun rumusan masalah analisis sebagai berikut:
- Bagaimana kelompok capaian indikator QS World University Ranking?
- Apakah kecenderungan yang berpengaruh pada setiap kelompok capaian indikator QS World University Ranking?

### Goals

Berdasarkan rumusan masalah tersebut akan dicapai tujuan sebagai berikut:
- Mengetahui kelompok capaian indikator QS World University Ranking untuk universitas-universitas di dunia
- Mengetahui kecenderungan yang mempengaruhi kelompok capaian indikator QS World Ranking 2023

### Solution statements

Untuk menyelesaikan masalah dan mencapai tujuan diatas, akan dibuat analisis cluster dengan algoritma KMeans untuk mendapatkan kelompok capaian indikator QS World University Ranking.

Evaluasi pemilihan jumlah cluster terbaik akan dilakukan dengan menggunakan elbow method untuk mendapatkan cluster dengan inertia yang baik sehingga jumlah kelompok yang dihasilkan dapat merepresentasikan data dengan baik.

## Data Understanding

Data yang digunakan dalam proyek ini bersumber dari [QS World University Rankings 2023](https://www.kaggle.com/datasets/jkanthony/world-university-rankings-202223) yang diunduh melalui platform Kaggle.

Data tersebut menunjukkan penilaian dari 1422 Universitas di dunia, dengan 8 indikator utama yang menjadi fokus dari proyek ini, yaitu
- ar score : Academic Reputation Score
- er score : Employer Reputation Score
- fsr score : Faculty Student Score
- cpf score : Citations per Faculty Score
- ifr score : International Faculty Score
- isr score : International Students Score
- irn score : International Research Score
- ger score : Employment Outcome Score

Karena ke-8 indikator tersebut merupakan fitur numerik, dilakukan visualisasi dengan plot histogram untuk melihat distribusi data. Telihat dari visuaslisasi fiturnya, 7 dari 8 indikator selain International Research Score memiliki kecenderungan skew kanan karena mediannya lebih kecil dari meannya. Namun dikarenakan metode yang kita gunakan dalam analisis adalah unsupervised learning yaitu clustering KMeans, kecenderungan skew dalam distribusi dalam data tidak terlalu berdampak terhadap model.

## Data Preparation

Dalam mempersiapkan data untuk analisis, dilakukan langkah-langkah sebagai berikut.

- Menangani missing value
Dikarenakan data memiliki urutan ranking, diasumsikan universitas dengan ranking yang berdekatan memiliki skor indikator yang mirip, sehingga dalam menangani missing value digunakan imputasi K-Nearest Neighbor.

- Feature scaling
Untuk membawa data ke rentang 0-1 dilakukan feature scaling dengan MinMaxScaler yang terdapat pada library sklearn. Hal ini dilakukan supaya tidak terdapat variansi yang cukup besar dalam data.

## Modeling

Dalam memodelkan data digunakan algoritma KMeans yang terdapat dalam library sklearn. Dengan menggunakan elbow method, terbentuk 4 cluster kelompok capaian indikator QS World University Ranking.

Berdasarkan hasil analisis, 4 kelompok yang terbentuk adalah:
- Kelompok universitas dengan capaian riset internasional (International Research) tinggi
- Kelompok universitas dengan capaian akademik internasional (International Faculty, International Students, dan International Research) tinggi
- Kelompok universitas dengan capaian seluruh indikator tinggi
- Kelompok universitas dengan capaian seluruh indikator rendah

Dari hasil pengelompokan tersebut, dilakukan pemetaan dengan menggunakan geopandas untuk mengamati sebaran setiap kelompok berdasarkan negaranya. Dikarenakan banyak universitas pada Top 1500 World University Ranking yang berasal dari Amerika Serikat, Inggris, China, Jepang, dan Rusia, negara-negara tersebut mendominasi dalam pemetaan setiap kelompok.

## Evaluation

Evaluasi yang digunakan untuk pemilihan cluster terbaik adalah dengan elbow method, dimana terdapat trade off antara jumlah cluster dengan inertia model, yang jika nilainya semakin rendah maka model akan semakin baik dalam memodelkan data. Dengan elbow method dipilih jumlah cluster optimum pada siku grafik yaitu 4 cluster, dimana inertianya cukup rendah namun jumlah clusternya tidak terlalu banyak.

Inertia dari model tersebut adalah 448.0545560896285.

Berdasarkan pemodelan yang dilakukan dengan KMeans sebelumnya, telah terjawab rumusan masalah dan tujuan dari analisis ini, yaitu:

Universitas-universitas Top 1500 QS World University Ranking dapat dikelompokkan menjadi 4 kelompok berdasarkan fokus capaiannya:
- Universitas dengan fokus capaian riset internasional
- Universitas dengan fokus capaian akademik internasional
- Universitas dengan capaian indikator tinggi
- Universitas dengan capaian indikator rendah

Negara-negara seperti Amerika Serikat, Inggris, China, Jepang, dan Rusia menjadi negara yang mendominasi dalam setiap kelompok. Kurangnya data mengenai universitas di Afrika maupun sebagian Asia membuat hasil analisis ini kurang inklusif untuk menunjukkan kualitas seluruh universitas di dunia.

Universitas-universitas dengan peringkat tinggi menunjukkan kualitas yang sangat baik, dimana termasuk ke kelompok dengan capaian indikator tinggi di seluruh 8 indikator penilaian yang ada.

Namun, untuk mencapai capaian indikator yang baik tidak selalu berasal dari universitas dengan peringkat dunia tinggi. Hal ini dibuktikan dengan rentang yang beragam pada kelompok capaian riset internasional dan capaian akademik internasional. Sehingga hal ini dapat digunakan sebagai pertimbangan masyarakat maupun pihak terkait untuk mengambil keputusan maupun kebijakan untuk meningkatkan capaian indikator untuk masing-masing universitas.

Institusi pendidikan tinggi dapat meningkatkan sitasi dan riset internasionalnya untuk dapat meningkatkan capaian indikator riset internasionalnya. Selain itu, keterbukaan akademis untuk kancah internasional juga menjadi pertimbangan besar dalam penilaian QS World University Ranking, sehingga instansi pendidikan tinggi dapat menyusun tujuannya dalam rangka mencapai indikator akademik internasional.