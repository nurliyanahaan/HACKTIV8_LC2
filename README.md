[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8246182&assignment_repo_type=AssignmentRepo)
# Live Code 2

# Instruction

Live Code ini dikerjakan dalam format ***notebook*** isi *notebook* harus mengikuti *outline* di bawah ini:
1. Perkenalan\
   Bab pengenalan harus diisi dengan identitas
2. **Judul/Penanda Soal**\
    Sediakan *Cell* Markdown sebelum cell import pustaka yang berisi nomor soal dan judul problem yang dikerjakan di tiap soalnya. Tiap soal mengikuti format nomor 2-6.
3. *Import* pustaka yang dibutuhkan\
   *Cell* pertama pada *notebook* **harus berisi dan hanya berisi** semua *library* yang digunakan dalam *project*.
4. *Data Loading*\
   Bagian ini berisi proses *data loading* yang kemudian dilanjutkan dengan *explorasi data* secara sederhana.
5. *Mathematical Calculations*\
   Bagian ini berisi proses pengolahan data dengan perhitungan matematis yang diperlukan.
6. Hasil\
   Pada bab terakhir ini berisi jawaban dari pertanyaan soal.
7. Simpan notebook dengan nama file `h8p0lc2-batch-nama_panggilan.ipyb`, contoh: `h8p0lc2-rmt016-fahmi.ipynb`

---

# Problems

## Problem 1
Kamu sedang mencari rumah dan akan memilih satu dari dua pilihan rumah dengan harga yang cukup berbeda. Sekilas, kedua rumah sama karakteristiknya, namun kamu ingin memastikan kembali apakah rumah yang lebih mahal patut dibeli atau tidak. Berikut data kedua rumah:


|Rumah|Luas Tanah|Luas Bangunan|Jumlah Lantai|Jumlah Kamar Tidur|Jumlah Kamar Mandi|Ada Halaman Belakang?|Ada Parkir Mobil dan Motor?|Dekat Dengan Pusat Kota?|Harga|
|--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| Rumah 1 | 100  | 240 |3|3|2|0|1|1|800|
| Rumah 2 | 120 | 200 |2|2|2|1|1|1|600|

**Keterangan:**
- Pada kolom `Jumlah Kamar Tidur`, `Jumlah Kamar Mandi`, `Ada Halaman Belakang?`, `Ada Parkir Mobil dan Motor?`, serta `Dekat Dengan Pusat Kota?` bernilai biner yaitu `1: Ya` dan `0: Tidak`.
- Kolom `harga` dalam satuan `ratus juta`.

Buatlah vektor yang merupakan representasi masing-masing rumah berdasarkan tabel di atas dengan `mengecualikan kolom harga` dan hitung cosine similarity antar kedua vektor. Kemudian *jawab pertanyaan berikut* di **markdown**:

a. Apakah kedua rumah mirip? jika iya, mengapa dan jika tidak, mengapa (jawab berdasarkan hasil perhitungan cosine similaritynya)? Dan keputusan yang akhirnya kamu pilih, rumah 1 atau rumah 2? apa pertimbangannya?

b. Jika meninjau dua buah vektor dan dihitung cosine similaritynya (cos theta), jelaskan secara singkat, jelas, padat apa makna cosine similarity yang bernilai 0 dan 1 (tinjau dari posisi dua vektor di koordinat kartesian)?

c. Mengapa cosine similarity harus melibatkan vektor bukan matriks?

---
## Problem 2

Kamu diberikan tugas untuk menganalisis harga sewa apartemen di Argentina per Januari 2015. Gunakan kemampuan statistikamu untuk menganalisis data yang tersedia!

### Dataset Description

* Pada graded challenge ini, data diakses menggunakan `bigquery-public-data` pada Google Cloud Big Query.
* Buka [Google Cloud Platform](https://console.cloud.google.com/), masuk ke BigQuery, lalu buka tab `bigquery-public-data` atau klik link [berikut](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=samples&page=dataset&_ga=2.245085957.1471931019.1642739417-486643658.1638156099) atau link [berikut](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=properati_properties_ar&t=properties_rent_201501&page=table) untuk langsung menuju ke tabel.

```{attention}
Perhatikan petunjuk penggunaan dataset!
```

1. Gunakan tabel `properties_rent_201501` pada dataset `properati_properties_ar`.
2. Buatlah query dengan kriteria sebagai berikut:
   - Pilih **HANYA** kolom `price`
   - Pilih data dengan value `operation` 'rent' dan `property_type` 'Apartement`
3. Simpan dataset dalam bentuk csv, dengan nama `h8dsft_P0LC3_<nama-students>.csv`.
4. Salin query yang telah dibuat di Google Cloud Platform, tulislah pada bagian atas notebook!
5. Tampilkan `head` dan `tail` dari dataset pada notebook!

**Clue**
Untuk mengetahui adanya anomali, kamu bisa menggunakan metode extreme value analysis. Untuk melakukan pengecekan anomali/outlier, lakukan langkah-langkah di bawah ini:
1. Lakukan perhitungan central tendency (mean, median, modus) terhadap data sebelum dideteksi adanya anomali.
2. Cek skewness data untuk mengetahui apakah data terdistribusi normal atau tidak.
3. Lakukan pengolahan data dengan menggunakan extreme value analysis.
4. Buat variabel baru yang menyimpan data yang sudah dibuang data anomalinya.

**PERTANYAAN**

**Silahkan jawab pertanyaan-pertanyaan di bawah ini berdasarkan hasil yang kamu peroleh dan tulis pada bagian hasil:**
1. Berapa rata-rata, median, dan modus dari data tersebut sebelum dihilangkan outliernya? Bagaimana kecerendungan pemusatan datanya? jelaskan jawabanmu!
2. Sebelum melakukan extreme value analysis, kamu harus melakukan pengecekan skewness dari distribusi datanya. Apakah datanya skew atau normal? jelaskan jawabanmu!
3. Ada dua teknik untuk melakukan extreme value analysis, teknik yang mana yang kamu pakai? berikan alasanmu berdasarkan data!

---

## Assignment Rubrics

### 1. Code Review
**Impementasi Code Python**
|No.|Criteria|Meet Expectations|Points|
|--- |--- |--- |--- |
|a|Vector Implementation|Dapat membuat Vector menggunakan library Numpy| 2 pts |
|b|Linear Algebra Implementation|Mampu menerapkan konsep cosine similarity dengan library NumPy| 4 pts |
|c|SQL Queries|Mampu mengambil data dengan SQL dari Big Query GCP | 5 pts |
|d|Central Tendency|Mampu menghitung mean, median, modus **tanpa menggunakan .describe()**| 3 pts |
|e|Distribution|Mampu menghitung skewness suatu data| 2 pts |
|f|Extreme Values Analysis|Mampu mendeteksi outlier menggunakan teknik tertentu| 4 pts |

### 2. Conceptual
**Menjawab Pertanyaan**
|No.|Criteria|Meet Expectations|Points|
|--- |--- |--- |--- |
|a|Linear Algebra Concept|Mampu menjawab pertanyaan secara singkat, padas, dan jelas menggunakan konsep matriks (masing-masing soal: 5 pt)| 15 pts |
|b|Statistical Concept|Mampu menjawab pertanyaan secara singkat, padas, dan jelas menggunakan konsep integral (masing-masing soal: 5 pt)| 15 pts |

### 3. Readability

|Criteria|Meet Expectations|Points|
|--- |--- |--- |
|Tertata Dengan Baik|Semua Cell Di Notebook Terdokumentasi Dengan Baik Dengan Markdown Pada Tiap Cell Untuk Penjelasan Kode.| 10 pts |

---

```{admonition} Total Points
**60**
```

---

## Score Reduction

Pengurangan poin akan diberlakukan jika Student terlambat mengumpulkan tugas yang telah diberikan. Adapun besarnya pengurangan adalah :

| Criteria | Max Points LC2 |
| --- | --- |
| Keterlambatan, mengumpulkan di antara 12.16 - 13.00 | 45 pts (75 %) |
| Keterlambatan, mengumpulkan di antara 13.01 - 18.00 | 30 pts (50 %) |
| Keterlambatan lebih dari 18.00 di hari yang sama | 0 pts (0 %) |
