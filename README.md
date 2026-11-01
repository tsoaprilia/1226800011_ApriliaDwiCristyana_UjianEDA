# EDA dan Enumerasi Gigi Susu Berbasis FDI

**Aprilia Dwi Cristyana — 1226800011**

## Tentang proyek

Proyek UTS Sains Data ini mencakup EDA awal, penanganan temuan EDA, koreksi anotasi, pengujian hipotesis, analisis ketahanan, serta pelatihan dan evaluasi model deteksi dan enumerasi gigi susu pada radiograf panoramik. Target terdiri atas 20 kelas FDI: 51–55, 61–65, 71–75, dan 81–85.

Notebook yang disertakan telah dijalankan dan disimpan beserta output-nya. Pembaca dapat memeriksa output notebook serta berkas hasil di Google Drive tanpa menjalankan ulang training.

## Lokasi berkas

Berkas proyek dibagi antara GitHub dan Google Drive karena adanya batasan ukuran berkas pada repository GitHub.

- **[GitHub](https://github.com/tsoaprilia/1226800011_ApriliaDwiCristyana_UjianEDA):** kode berupa empat notebook utama, `README.md`, dan laporan PDF.
- **[Google Drive](https://drive.google.com/drive/folders/1ixSBScRA9kuaY-9KscP21o4kEbd7nrfu):** empat folder dataset sumber, satu ZIP enumerasi berlabel asli, serta hasil EDA, analisis, training, dan evaluasi yang sudah dijalankan.

**Dataset tidak disertakan di GitHub.** Empat dataset sumber di Drive tersedia sebagai folder biasa. Hanya dataset enumerasi berlabel asli yang disediakan sebagai `enumerasi_gigi_susu_252_label_asli.zip`.

Hasil run sebelumnya sudah tersedia di Drive dan dapat diperiksa tanpa menjalankan ulang notebook. Jika arsip hasil yang ingin diperiksa berbentuk ZIP, unduh lalu ekstrak terlebih dahulu.

## Isi repository GitHub

```text
README.md
00_Salinan_EDA_sebelum_UTS.ipynb
01_EDA_Penanganan_Hasil_Akhir.ipynb
02_Baseline_YOLO11n_Usulan_YOLO11m_Colab.ipynb
04_Perbandingan_YOLO11n_Asli_vs_Baseline_Patience15.ipynb
1226800011_Aprilia_Dwi_Cristyana_UjianEDA.pdf
```

## Menyiapkan folder untuk menjalankan ulang

1. Buat folder proyek bernama **`1226800011_Aprilia_UjianEDA_Revisi`**. Untuk Colab, letakkan folder tersebut di tingkat utama **Drive Saya / MyDrive**. Untuk komputer lokal, letakkan pada lokasi yang akan digunakan sebagai folder kerja.
2. Buka [Google Drive dataset dan hasil](https://drive.google.com/drive/folders/1ixSBScRA9kuaY-9KscP21o4kEbd7nrfu). Unduh empat folder dataset berikut beserta seluruh isinya, lalu letakkan di dalam folder proyek:
   - `Childrens dental caries segmentation dataset_KAGEL`
   - `Data terpilih dari Dental Paramita 11-12`
   - `Dataset PARAMITA 2026`
   - `DENTAL DATASET PARAMITA 2016-2018`
3. Unduh juga **`enumerasi_gigi_susu_252_label_asli.zip`** dari Drive, lalu letakkan di folder proyek yang sama. Pertahankan ZIP ini karena notebook mengekstraknya otomatis ke penyimpanan lokal runtime.
4. Unduh empat file notebook dari [repository GitHub](https://github.com/tsoaprilia/1226800011_ApriliaDwiCristyana_UjianEDA), lalu letakkan langsung di folder proyek. README dan laporan PDF dapat diunduh sebagai panduan.
5. Jika menggunakan Colab, salin atau unggah seluruh dataset dan notebook tersebut ke folder proyek di MyDrive. Jika menggunakan komputer lokal, atur path sesuai petunjuk eksekusi lokal di bawah.
6. Periksa susunan folder berikut, lalu jalankan notebook berurutan **00 → 01 → 02 → 04** sesuai panduan pada bagian berikutnya.

```text
1226800011_Aprilia_UjianEDA_Revisi/
├── README.md
├── 1226800011_Aprilia_Dwi_Cristyana_UjianEDA.pdf
├── 00_Salinan_EDA_sebelum_UTS.ipynb
├── 01_EDA_Penanganan_Hasil_Akhir.ipynb
├── 02_Baseline_YOLO11n_Usulan_YOLO11m_Colab.ipynb
├── 04_Perbandingan_YOLO11n_Asli_vs_Baseline_Patience15.ipynb
├── Childrens dental caries segmentation dataset_KAGEL/
├── Data terpilih dari Dental Paramita 11-12/
├── Dataset PARAMITA 2026/
├── DENTAL DATASET PARAMITA 2016-2018/
└── enumerasi_gigi_susu_252_label_asli.zip
```

Empat dataset sumber di Drive sudah berupa folder biasa. Jika Google Drive mengemas folder menjadi ZIP saat diunduh, ekstrak hasil unduhan tersebut agar kembali menjadi folder seperti susunan di atas. Hindari folder bertingkat ganda dan pertahankan nama folder sesuai path notebook.

ZIP enumerasi merupakan input anotasi awal, bukan dataset terkoreksi. Isinya mencakup folder `enumerasi gigi susu6-252-.v1i.yolov11`, citra pada `train/images`, label awal pada `train/labels`, serta `data.yaml`. Dataset terkoreksi dihasilkan oleh notebook 01 dan juga tersedia bersama hasil analisis di Drive.

## Notebook dan urutan penggunaan

| Notebook | Fungsi | Lokasi hasil |
| :---- | :---- | :---- |
| `00_Salinan_EDA_sebelum_UTS.ipynb` | EDA awal: distribusi kelas, statistik citra, usia, outlier, FDI berulang, kemiripan citra, serta demonstrasi preprocessing dan augmentasi | `hasil_EDA_awal_sebelum_UTS/` |
| `01_EDA_Penanganan_Hasil_Akhir.ipynb` | Koreksi anotasi, audit split dan duplikat, empat hipotesis, tiga analisis ketahanan, serta praktik perubahan IQR | `hasil_analisis/` |
| `02_Baseline_YOLO11n_Usulan_YOLO11m_Colab.ipynb` | Training dan evaluasi baseline YOLO11n serta usulan YOLO11m dengan HE dan brightness | `hasil_analisis/pemodelan/20261031_124203/` |
| `04_Perbandingan_YOLO11n_Asli_vs_Baseline_Patience15.ipynb` | Perbandingan YOLO11n citra asli tanpa HE dan augmentasi dengan baseline pada patience 15 | `hasil_perbandingan_dua_YOLO11n/20261031_173820/` |

### Membaca hasil tanpa menjalankan ulang

1. Baca `1226800011_Aprilia_Dwi_Cristyana_UjianEDA.pdf` yang tersedia di repository GitHub.
2. Buka output notebook 00, 01, 02, lalu 04 untuk mengikuti alur analisis.
3. Cocokkan output dengan tabel, grafik, manifest, log koreksi, dan evaluasi di Drive. Unduh dan ekstrak arsip hasil bila diperlukan.

### Menjalankan ulang di Colab

1. Siapkan folder proyek beserta empat folder dataset, ZIP enumerasi, dan notebook sesuai panduan di atas. Pastikan lokasi proyek adalah `MyDrive/1226800011_Aprilia_UjianEDA_Revisi` atau sesuaikan konfigurasi path notebook. Gunakan folder milik sendiri yang dapat ditulisi untuk menyimpan hasil run ulang.
2. Jalankan notebook 00 untuk EDA awal, lalu notebook 01 untuk koreksi dan ekspor dataset. Tunggu hingga persiapan selesai dan `RUN_COMPLETE.json` terbentuk.
3. Jalankan cell terakhir notebook 01 untuk membandingkan parameter IQR 1,5 dan 3,0.
4. Jalankan notebook 02 menggunakan runtime GPU T4 untuk melatih dan mengevaluasi kedua model.
5. Jalankan notebook 04 menggunakan GPU T4. Notebook ini memerlukan hasil baseline notebook 02. Untuk memakai hasil yang dilaporkan, unduh dan ekstrak run `20261031_124203` dari Drive pada path yang sesuai. Jika memakai run baru, sesuaikan `BASELINE_RUN`.
6. Simpan notebook agar output ikut tersimpan. Catat timestamp hasil baru; hasil pengulangan dapat berbeda dari run laporan.

Training ulang menggunakan waktu dan kuota GPU. Untuk membandingkan kondisi, pertahankan seed, batch, input size, split, dan pengaturan evaluasi yang sama.

## Dataset dan hasil koreksi

Data berasal dari koleksi Paramita yang bekerja sama dengan RSGM UNAIR serta dataset publik Kaggle.

| Sumber | Keterangan |
| :---- | :---- |
| Paramita 2016–2018 | Koleksi awal 2.039 citra; 171 kandidat diseleksi dan 121 citra digunakan pada dataset final |
| Data terpilih dari Dental Paramita 11-12 | Berisi 171 kandidat untuk menelusuri alur seleksi; 121 terpilih dan 50 tidak terpilih |
| Paramita 2026 | 69 citra kandidat; 48 digunakan pada dataset final |
| Kaggle | 100 radiograf kandidat; 83 digunakan pada dataset final |

- Seluruh 252 citra dipertahankan.
- Sebanyak 37 nomor kelas diubah pada 25 citra berdasarkan review manual.
- Satu box pada IMG0043 baris #13, sebelumnya FDI 55, dihapus. Anotasi berkurang dari 3.343 menjadi 3.342.
- Audit setelah koreksi tidak menemukan FDI berulang. Log tersedia di `hasil_analisis/tabel/log_koreksi_FDI.csv` pada Google Drive.
- Sebanyak 28 pasangan yang ditandai mirip oleh dHash telah direview dan merupakan gambar berbeda. Pemeriksaan hash piksel tidak menemukan duplikat citra lintas split.
- Outlier dipertahankan. IQR digunakan untuk penandaan dan analisis sensitivitas.
- Umur tepat diketahui pada 120 citra dengan rentang 4–12 tahun; 132 citra tidak mencantumkan umur tepat. Umur yang tidak tersedia tidak diimputasi. Umur bukan input atau target model.
- Citra dan label mentah disimpan sebagai sumber; dataset terkoreksi diekspor terpisah.

## Ringkasan hasil

| Bagian data | Jumlah citra/file | Anotasi |
| :---- | ----: | ----: |
| Dataset setelah koreksi | 252 | 3.342 |
| Train sebelum augmentasi | 175 | 2.306 |
| Validation | 50 | 709 |
| Test | 27 | 327 |
| Train setelah augmentasi | 525 | 6.918 |
| Total setelah pengolahan | 602 | 7.954 |

Jumlah citra sumber tetap 252. Train memiliki tiga versi per citra: HE dasar, brightness −15%, dan brightness +15%. Turunan augmentasi bukan pengamatan independen tambahan untuk analisis statistik.

Praktik IQR pada train menandai 12 citra pada k=1,5 dan 3 citra pada k=3,0. Dataset utama tidak berubah.

### Hasil test model

| Kondisi | Patience | Epoch aktual | mAP50 | mAP50–95 | F1 micro | Kappa |
| :---- | ----: | ----: | ----: | ----: | ----: | ----: |
| YOLO11n citra asli tanpa HE dan augmentasi | 15 | 38 | 75,01% | 39,72% | 74,62% | 0,6555 |
| Baseline YOLO11n dengan HE dan brightness | 15 | 59 | 78,89% | 42,71% | 76,05% | 0,6801 |
| Usulan YOLO11m dengan HE dan brightness | 15 | 69 | 90,34% | 53,81% | 86,99% | 0,7977 |

Pada perbandingan YOLO11n, paket pengolahan meningkatkan mAP50 sebesar 3,88 poin persen, mAP50–95 sebesar 2,99 poin persen, dan F1 micro sebesar 1,43 poin persen. Pengaruh HE dan brightness tidak dipisahkan. Hasil berasal dari satu run pada split yang sama dan belum menunjukkan kestabilan antar-seed. Augmentasi juga menambah jumlah langkah training per epoch.

## Konfigurasi dan evaluasi

Model menggunakan bobot YOLO11 pralatih, input 640 piksel, batch 8, AdamW, learning rate awal 0,001, seed 42, maksimal 80 epoch, dan patience 15. Early stopping dan pemilihan checkpoint menggunakan validation.

Baseline dan usulan menggunakan auto-orient serta HE; brightness hanya diterapkan pada train. Validation dan test tidak diaugmentasi. Kondisi citra asli pada notebook 04 tidak menggunakan HE, brightness, atau auto-orient; grayscale dan PNG digunakan untuk konsistensi format. Koordinat label disesuaikan bila metadata orientasi memerlukannya. Augmentasi tambahan flip, mosaic, mixup, dan HSV dinonaktifkan.

Prediksi dipasangkan satu-ke-satu dengan gigi acuan pada IoU ≥ 0,5. Pencocokan lokasi tidak mensyaratkan kelas yang sama agar kesalahan FDI terlihat. Confidence dipilih menggunakan F1 micro pada validation dan dikunci sebelum evaluasi test. NMS IoU adalah 0,7.

mAP berasal dari evaluasi Ultralytics sepanjang kurva precision–recall. Precision, recall, dan F1 akhir memakai confidence pilihan validation. Kappa menggunakan unit gigi acuan; prediksi berlebih dilaporkan melalui FP. Karena itu, Kappa perlu dibaca bersama FP dan FN.

## Menjalankan di komputer lokal

Siapkan Python dan Jupyter. Untuk training, gunakan NVIDIA GPU dengan driver dan PyTorch CUDA yang sesuai. Notebook pemodelan tidak otomatis melanjutkan training pada CPU.

Unduh notebook dari GitHub serta empat folder dataset dan ZIP enumerasi dari Google Drive. Susun semuanya dalam folder proyek, misalnya `D:\EDA_Colab\1226800011_Aprilia_UjianEDA_Revisi`. Pasang dependensi dasar:

```powershell
python -m pip install jupyterlab nbconvert ipykernel numpy pandas matplotlib pillow scipy pyyaml opencv-python-headless scikit-learn tzdata
```

Atur path sebelum membuka Jupyter:

```powershell
$env:FDI_MYDRIVE = 'D:\EDA_Colab'
$env:FDI_SCRATCH = 'D:\EDA_Colab\runtime'
python -m jupyter lab
```

Jalankan notebook sesuai urutan di atas. Untuk pemodelan, pastikan dependensi model pada notebook terpasang dan `torch.cuda.is_available()` bernilai `True`. Jika menggunakan baseline yang sudah selesai, unduh dan ekstrak folder run baseline dari Google Drive; jika melatih ulang, sesuaikan timestamp run yang digunakan.

## Berkas hasil penting di Google Drive

| Path folder hasil | Isi |
| :---- | :---- |
| `hasil_EDA_awal_sebelum_UTS/` | Bukti EDA sebelum penanganan |
| `hasil_analisis/tabel/` | Statistik, log koreksi, audit, hipotesis, sensitivitas, dan praktik IQR |
| `hasil_analisis/grafik/` | Grafik distribusi, kualitas citra, skema FDI, dan before–after |
| `hasil_analisis/review/` | Bukti audit dan daftar pemeriksaan |
| `hasil_analisis/overlay_koreksi/` | Perbandingan anotasi sebelum dan sesudah koreksi |
| `hasil_analisis/dataset_terkoreksi/` | Train, valid, test, `data.yaml`, dan `manifest.csv` |
| `hasil_analisis/pemodelan/20261031_124203/` | Hasil baseline dan usulan; termasuk `perbandingan_test.csv` |
| `hasil_perbandingan_dua_YOLO11n/20261031_173820/` | Hasil perbandingan citra asli dan baseline |

**Catatan:** GitHub berisi kode, README, dan laporan PDF. Dataset serta folder hasil run tersedia di [Google Drive pengumpulan](https://drive.google.com/drive/folders/1ixSBScRA9kuaY-9KscP21o4kEbd7nrfu). Hasil yang sudah tersedia dapat langsung diperiksa; jika ingin mereproduksi analisis, siapkan folder proyek dan jalankan ulang notebook sesuai panduan di atas. Unduh dan ekstrak hanya arsip hasil yang ingin diperiksa apabila masih berbentuk ZIP.
