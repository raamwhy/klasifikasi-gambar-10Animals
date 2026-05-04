# Submission Proyek Klasifikasi Gambar (Animals-10)

## Ramdhan Wijaya (3337230033)

- Dataset: Animals-10 dari Kaggle dengan total 26.179 gambar.
- Jumlah kelas: 10 kelas.
- Link Dataset: https://www.kaggle.com/datasets/viratkothari/animal10
- Split data: Train/Validation/Test dengan rasio 70/15/15.
- Arsitektur model: Transfer learning MobileNetV2 + head CNN (Conv2D/Pooling/Dense) dalam Sequential.
- Callback: EarlyStopping, ReduceLROnPlateau, ModelCheckpoint.
- Evaluasi: Menampilkan akurasi dan loss untuk train/validation/test.
- Visualisasi: Plot accuracy dan loss selama training.
- Konversi model: SavedModel, TF-Lite, dan TFJS.
- Inference: Menggunakan model TF-Lite dan SavedModel.

## Struktur Folder

```
submission/
├── tfjs_model/
├── tflite/
├── saved_model/
├── notebook.ipynb
├── README.md
└── requirements.txt
```

## Cara Menjalankan

1. Upload folder proyek ke Colab/Drive.
2. Pastikan dataset tersedia di salah satu path berikut:
   - ./Animals-10
   - ../Animals-10
   - /content/Animals-10
   - /content/drive/MyDrive/Animals-10
3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Requirements & Dependencies

Notebook ini membutuhkan package berikut dengan versi spesifik:

| Package | Version | Fungsi |
|---------|---------|--------|
| **tensorflow** | == 2.21.0 | Deep Learning Framework (Model Training) |
| **numpy** | == 1.26.4 | Numerical Computing (compatible with Python 3.12) |
| **matplotlib** | >= 3.7.0 | Visualization (Training Curves, Confusion Matrix) |
| **scikit-learn** | >= 1.3.0 | Classification Report, Class Weights |
| **Pillow** | >= 9.5.0 | Image Loading & Processing |

**Python Version:** >= 3.10 (Tested pada Python 3.10.12)

### Installation di Google Colab:
```bash
!pip install -r requirements.txt
```

### Atau Install Manual:
```bash
!pip install tensorflow==2.21.0 numpy==1.26.4 matplotlib>=3.7.0 scikit-learn>=1.3.0 Pillow>=9.5.0 seaborn>=0.12.0
```

## Model Export & Inference

Notebook ini mengekspor model terlatih dalam 3 format:

### 1. SavedModel (`saved_model/`)
- File: `saved_model.pb` + `variables/` + `assets/`

### 2. TF-Lite (`tflite/`)
- File: `model.tflite` + `label.txt`

### 3. TFJS (`tfjs_model/`)
- File: `model.json` + weight shards (`.bin`)

