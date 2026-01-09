Task 1: Fine-Tuning BERT for Text Classification and NLI
Repository ini berisi implementasi fine-tuning model BERT (Bidirectional Encoder Representations from Transformers) untuk menyelesaikan berbagai paradigma klasifikasi teks: klasifikasi berita (single-label), deteksi emosi (multi-label), dan Natural Language Inference (NLI).

📌 Gambaran Proyek
Tujuan utama dari tugas ini adalah menerapkan arsitektur Transformer encoder-only (khususnya BERT) pada tiga jenis permasalahan NLP yang berbeda menggunakan ekosistem Hugging Face (transformers, datasets, evaluate).

Sub-Task & Dataset
Klasifikasi Berita (AG News): Memetakan artikel berita pendek ke dalam 4 kategori: World, Sports, Business, atau Sci/Tech.
Deteksi Emosi (GoEmotions): Klasifikasi multi-label untuk mendeteksi satu atau lebih dari 28 emosi dalam sebuah teks.
Natural Language Inference (MNLI): Menentukan hubungan logika antara dua kalimat (Premise dan Hypothesis) sebagai Entailment, Neutral, atau Contradiction.

🛠️ Metodologi
1. Model & Arsitektur
Base Model: bert-base-uncased.
Tokenisasi: Menggunakan AutoTokenizer dengan max_length=128, serta penerapan truncation dan padding.

2. Konfigurasi Training (Hyperparameters)
Berdasarkan eksperimen, konfigurasi berikut digunakan untuk mendapatkan hasil optimal:
Learning Rate: 2e-5.
Batch Size: 8.
Epochs: 3.
Weight Decay: 0.01.
Optimizer: AdamW (Default dari Trainer API).

3. Penanganan Data Khusus
Multi-Label (GoEmotions): Label diubah menjadi format One-Hot Encoding (float32) dan dilatih menggunakan fungsi loss BCEWithLogitsLoss.

Isu Label -1 (MNLI): Ditemukan label -1 pada subset test_matched yang menyebabkan error CUDA. Solusi dilakukan dengan mengalihkan data evaluasi ke subset validation_matched yang memiliki label valid (0, 1, 2).

🚀 Cara Menjalankan
Instalasi Dependensi:
Bash
pip install -r requirements.txt
Atau instal manual:
Bash
pip install transformers datasets evaluate accelerate scikit-learn matplotlib seaborn
Training: Buka salah satu file di folder notebooks/ menggunakan Google Colab atau Jupyter Notebook. Pastikan akselerator GPU (T4 atau lebih tinggi) aktif.

Inference: Contoh penggunaan model untuk prediksi berita:

Python
from transformers import pipeline
classifier = pipeline("text-classification", model="./path_to_model")
result = classifier("Apple announced the new iPhone with AI chip.")
print(result) # Expected: Sci/Tech
