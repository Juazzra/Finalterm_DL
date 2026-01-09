Fine-Tuning T5 for Generative Question Answering (SQuAD)
Repository Name: finetuning-t5-question-answering

Identitas Mahasiswa
Nama: Juandra Alghifary
NIM: 1103220165

1. Deskripsi Proyek
Proyek ini bertujuan untuk melakukan fine-tuning pada model T5-Base (Text-to-Text Transfer Transformer) untuk menyelesaikan tugas Question Answering (QA) menggunakan dataset SQuAD. Berbeda dengan model ekstraktif seperti BERT, pendekatan ini menggunakan paradigma Generative QA di mana model belajar untuk menghasilkan teks jawaban secara langsung berdasarkan konteks dan pertanyaan yang diberikan.

Tujuan Utama:
Meningkatkan pemahaman praktis mengenai arsitektur Encoder-Decoder pada Transformers.
Mengimplementasikan pipeline NLP end-to-end mulai dari preprocessing teks hingga evaluasi model generatif.
Melakukan pemrosesan data dengan format Text-to-Text khusus untuk model T5.

2. Dataset & Model
Dataset: Stanford Question Answering Dataset (SQuAD) via HuggingFace Hub.
Model: t5-base (Encoder-Decoder Transformer).
Format Input: "question: [Pertanyaan] context: [Paragraf Context]".
Format Target: "[Teks Jawaban]".

3. Konfigurasi Pelatihan
Model dilatih dengan parameter berikut untuk efisiensi dan akurasi:
Epoch: 3
Batch Size: 8
Learning Rate: 2e-5
Mixed Precision: fp16=True (untuk efisiensi memori GPU)
Strategy Sampling: Menggunakan subset 2.000 sampel untuk mempercepat proses demonstrasi.

5. Struktur Repository
Sesuai dengan persyaratan tugas, repository ini memiliki struktur sebagai berikut:
├── README.md               # Dokumentasi utama proyek
├── finetuning-t5-question-answering.ipynb             # File Jupyter Notebook (.ipynb)
├── REPORT_TASK2_SQUAD_T5.md            #Laporan dokumentasi implementasi (.md)

4. Cara Penggunaan
Install dependensi: pip install transformers datasets evaluate accelerate.
Buka notebook di folder notebooks/ menggunakan Google Colab atau Jupyter.
Jalankan sel pelatihan atau muat model yang sudah dilatih untuk mencoba inferensi interaktif.
