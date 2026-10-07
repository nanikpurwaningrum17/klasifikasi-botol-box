# Klasifikasi Botol dan Box

## Deskripsi

Proyek ini merupakan implementasi klasifikasi citra untuk membedakan
dua kelas, yaitu **botol** dan **box**.

Metode yang digunakan adalah **Transfer Learning dengan Feature
Extraction menggunakan MobileNetV3-Small pretrained ImageNet**.

## Dataset

Dataset terdiri dari:

- Botol: 50 citra
- Box: 50 citra
- Total: 100 citra

Pembagian dataset:

| Dataset | Jumlah |
|---|---:|
| Training | 80 |
| Validation | 10 |
| Testing | 10 |

## Metode

Model yang digunakan:

- Model: MobileNetV3-Small
- Pretrained weights: ImageNet
- Metode: Feature Extraction
- Input: 224 × 224 piksel
- Optimizer: Adam
- Learning rate: 0.001
- Batch size: 16
- Epoch: 20

Pada metode Feature Extraction, backbone MobileNetV3-Small
dibekukan (**freeze**). Bobot pretrained tidak diperbarui selama
training. Training dilakukan pada classifier tambahan untuk
membedakan kelas botol dan box.

## Hasil

| Metric | Hasil |
|---|---:|
| Accuracy | 1.0000 |
| Precision | 1.0000 |
| Recall | 1.0000 |
| F1-Score | 1.0000 |
| Latency | 226.76 ms/image |

Epoch terbaik berdasarkan validation accuracy:

**Epoch 1**

Validation accuracy terbaik:

**1.0000**

## Visualisasi

### Accuracy

`results/accuracy_feature_extraction.png`

### Loss

`results/loss_feature_extraction.png`

### Confusion Matrix

`results/confusion_matrix_feature_extraction.png`

## Model

Model disimpan sebagai:

`models/mobilenetv3_small_feature_extraction.keras`

## Evaluasi

Evaluasi dilakukan menggunakan data testing yang tidak digunakan
untuk training maupun pemilihan epoch terbaik.

Metrik yang digunakan adalah:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Latency

## Kesimpulan

MobileNetV3-Small digunakan sebagai feature extractor dengan bobot
pretrained ImageNet yang dibekukan. Classifier tambahan dilatih
untuk melakukan klasifikasi antara citra botol dan box.
