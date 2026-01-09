Fine-Tuning Phi-2 for Text Summarization (XSum)

Nama: Juandra Alghifary
NIM: 1103220165
Kelas: TK-46-02
Mata Kuliah: Deep Learning for NLP

1. Tujuan Repositori
Repositori ini berisi proyek implementasi fine-tuning model bahasa besar (Large Language Model) untuk tugas Abstractive Text Summarization. Fokus utama dari tugas ini adalah meningkatkan kemampuan model Microsoft Phi-2 dalam menghasilkan ringkasan berita yang singkat, padat, dan koheren menggunakan dataset XSum.

2. Ringkasan Proyek
Proyek ini mengimplementasikan paradigma Decoder-only LLM dengan teknik QLoRA (Quantized Low-Rank Adaptation). Pendekatan ini dipilih agar model sebesar 2.7 miliar parameter dapat dilatih secara efisien pada perangkat keras dengan VRAM terbatas (Google Colab T4 GPU).

Model dilatih dengan format Instruction Tuning (Alpaca Style) untuk mengubah perilaku model dasar (Base Model) dari sekadar pelanjut teks menjadi asisten peringkas berita.

3. Deskripsi Model dan Hasil Metriks
Model yang Digunakan
Base Model: microsoft/phi-2 (2.7B Parameters).
Metode Training: QLoRA 4-bit (NF4 Quantization).
Target Modules: q_proj, k_proj, v_proj, dense, fc1, fc2.
Dataset: EdinburghNLP/xsum (Extreme Summarization).

Hasil Metriks (Training)
Pelatihan dilakukan sebanyak 250 steps (1 epoch) dengan ukuran subset 1.000 data.
Initial Training Loss: ~2.41.
Final Training Loss: 1.89.

4. Struktur Repositori dan Navigasi
│── finetuning-phi2-text-summarize.ipynb    # Notebook proses training & evaluasi
│──finetuning-phi2-report.md               # Laporan detail metodologi & analisis
└── README.md                                   # Dokumentasi utama (file ini)

6. Cara Menjalankan Notebook
Pastikan Anda memiliki lingkungan Python 3.10+ dan akses ke GPU (minimal T4 16GB).
Instal dependensi yang diperlukan:
Bash
pip install -r requirements.txt
Buka file di folder notebooks/ menggunakan Google Colab atau Jupyter Lab.
Jalankan sel secara berurutan, mulai dari instalasi library khusus (peft, bitsandbytes, trl) hingga bagian inferensi.
