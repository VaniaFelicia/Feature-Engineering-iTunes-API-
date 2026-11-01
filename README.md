Feature Engineering Judul Lagu (Billboard Hot 100 dan iTunes API)

Penyusun: Eifellyne Putri Widayanto (011) dan Vania Felicia Gita Wulandari (058).

Deskripsi

Proyek ini mengambil judul lagu dari dua sumber, membersihkannya melalui text preprocessing, lalu mengubah judul lagu iTunes menjadi fitur numerik melalui feature engineering dan menganalisis hasilnya. Sumber pertama adalah tangga lagu Billboard Hot 100 yang diambil dengan scraping HTML menggunakan requests dan BeautifulSoup, sebanyak 100 lagu. Sumber kedua adalah iTunes Search API yang dipanggil untuk lagu Taylor Swift, sebanyak 20 lagu.

Tahapan

Pertama, data dari kedua sumber digabung menjadi 120 judul lagu. Kedua, teks dibersihkan dengan menghapus tag HTML, hashtag, URL dan email, tanda baca, serta emoji, kemudian diubah ke huruf kecil, di-stemming dengan Porter Stemmer, dan dihapus stopword bahasa Inggrisnya. Ketiga, untuk feature engineering hanya data iTunes API (20 judul) yang dipakai, yaitu kolom prepro dari baris bersumber iTunes API. Judul yang kosong setelah preprocessing dibuang terlebih dahulu. Keempat, feature engineering Part 1 dilakukan dengan One Hot Encoding, Bag of Words, dan TF-IDF pada data iTunes tersebut. Kelima, feature engineering Part 2 dilakukan dengan Word2Vec (CBOW) dan FastText (Skip-Gram) pada data iTunes yang sama, lengkap dengan visualisasi UMAP. Keenam, seluruh metode dibandingkan dalam bagian analisis.

Singkatnya, preprocessing dilakukan pada gabungan 120 judul (Billboard dan iTunes), sedangkan feature engineering hanya memakai data iTunes API.

Hasil singkat

Matriks Part 1 berukuran 42 kata, dengan sparsity 94,64 persen, dan 39 dari 42 kata hanya muncul satu kali. Word2Vec dan FastText menghasilkan vektor berdimensi 100 dengan kosakata 46 kata. Skor kemiripan kata tertinggi rendah pada kedua model, yaitu 0,219 untuk Word2Vec dan 0,212 untuk FastText, dan kata yang dianggap mirip tidak bermakna karena datanya hanya sekitar 20 judul pendek. Untuk data sekecil ini, TF-IDF paling mudah ditafsirkan, sedangkan Word2Vec dan FastText baru bermanfaat jika datanya jauh lebih besar.
