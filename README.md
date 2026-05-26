# Breast Cancer Classification

Proyek ini berisi implementasi klasifikasi citra USG kanker payudara menggunakan deep learning dengan dua model utama, yaitu DenseNet121 dan Xception. Notebook ini mencakup proses penggabungan dataset, preprocessing citra, training model, evaluasi performa, dan visualisasi interpretasi model menggunakan Grad-CAM.

## Tujuan

Membangun model klasifikasi untuk membedakan citra ke dalam tiga kelas:

- benign
- malignant
- normal

## Isi Proyek

Notebook ini melakukan tahapan berikut:

1. Install library yang dibutuhkan.
2. Mount Google Drive untuk mengambil dataset zip.
3. Ekstraksi dataset Kaggle dan Mendeley.
4. Menggabungkan dataset ke folder kelas yang seragam.
5. Membagi data menjadi train, validation, dan test.
6. Menampilkan contoh citra mentah.
7. Melatih model pada data mentah sebagai baseline.
8. Menerapkan preprocessing citra dengan median blur dan CLAHE.
9. Melatih DenseNet121 dan Xception pada data yang sudah diproses.
10. Membandingkan hasil training, confusion matrix, classification report, dan weighted F1-score.
11. Menampilkan area fokus model dengan Grad-CAM.

## Struktur Dataset

Dataset hasil penggabungan dan split akan tersusun seperti berikut:

```text
dataset_split/
├── train/
│   ├── benign/
│   ├── malignant/
│   └── normal/
├── val/
│   ├── benign/
│   ├── malignant/
│   └── normal/
└── test/
	├── benign/
	├── malignant/
	└── normal/
```

## Metode

### 1. Penggabungan Dataset

Notebook membaca dataset dari dua sumber:

- Kaggle BUSI
- Mendeley dataset

File kemudian disalin ke folder gabungan sesuai kelasnya masing-masing.

### 2. Preprocessing

Preprocessing yang digunakan meliputi:

- Resize citra
- Normalisasi
- Median blur untuk mengurangi noise
- CLAHE untuk meningkatkan kontras citra

### 3. Augmentasi Data

Untuk training digunakan augmentasi seperti:

- Random rotation
- Horizontal flip
- Vertical flip

### 4. Model yang Digunakan

- DenseNet121
- Xception

### 5. Evaluasi

Performa model dievaluasi menggunakan:

- Accuracy
- Loss
- Confusion matrix
- Classification report
- Weighted F1-score

### 6. Interpretabilitas

Grad-CAM digunakan untuk menampilkan area citra yang paling berpengaruh terhadap prediksi model.

## Kebutuhan Environment

Pastikan environment sudah memiliki library berikut:

- torch
- torchvision
- timm
- opencv-python
- numpy
- matplotlib
- seaborn
- scikit-learn
- pillow
- split-folders
- grad-cam

## Cara Menjalankan

1. Pastikan file dataset zip sudah ada di Google Drive sesuai path pada notebook.
2. Buka notebook `Tugas Coding Humic.ipynb`.
3. Jalankan sel secara berurutan dari atas ke bawah.
4. Tunggu proses ekstraksi, penggabungan dataset, training, dan evaluasi selesai.
5. Hasil model terbaik akan disimpan dalam file `.pth`.

## Output yang Dihasilkan

Setelah notebook selesai dijalankan, akan diperoleh:

- Dataset yang sudah digabung dan dibagi
- Model terlatih DenseNet121
- Model terlatih Xception
- Grafik perbandingan training
- Confusion matrix
- Laporan klasifikasi
- Skor weighted F1
- Visualisasi Grad-CAM

## Catatan

- Notebook ini dibuat untuk dijalankan di Google Colab atau environment Python yang mendukung PyTorch.
- Jika lokasi dataset berbeda, sesuaikan path pada bagian ekstraksi dan penggabungan dataset.
- Jika ingin memakai notebook ini di komputer lokal, bagian mount Google Drive dapat dihapus atau disesuaikan.

## Nama File Terkait

- `Tugas Coding Humic.ipynb`
- `model_densenet121.pth`

