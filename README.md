🚀 Transformer Fine-Tuning Labs: Encoder, Seq2Seq, and Decoder Architectures
Repositori ini berisi kumpulan proyek fine-tuning model Transformer untuk berbagai tugas Natural Language Processing (NLP). Proyek ini mengeksplorasi tiga paradigma utama dalam arsitektur Transformer modern: Encoder (BERT), Sequence-to-Sequence (T5), dan Decoder-only LLM (Phi-2).

📂 Daftar Proyek (Task Overview)
Repositori ini dibagi menjadi tiga bagian utama sesuai dengan arsitektur yang dipelajari:

1. Text Classification & NLI (Encoder-based)
Model: BERT-family (BERT/DistilBERT).
Dataset: AG News (Klasifikasi Berita), GoEmotions (Deteksi Emosi), atau MNLI (Natural Language Inference).
Tujuan: Melakukan pemetaan teks masukan ke dalam satu atau lebih label target untuk kategori berita, sentimen, atau hubungan logika antar kalimat.

2. Generative Question Answering (Seq2Seq-based)
Model: T5 (Text-to-Text Transfer Transformer).
Dataset: SQuAD (Stanford Question Answering Dataset).
Tujuan: Melatih model untuk menghasilkan teks jawaban berdasarkan paragraf konteks dan pertanyaan yang diberikan secara generatif.

3. Abstractive Text Summarization (Decoder-based LLM)
Model: Microsoft Phi-2 (2.7B Parameters).
Metode: QLoRA (Quantized Low-Rank Adaptation) - 4-bit Quantization.
Dataset: XSum (Extreme Summarization).

4. Instalasi & Persiapan
   # General NLP & Transformers
pip install torch transformers datasets scikit-learn pandas

  # Khusus Task 3 (QLoRA & LLM)
pip install peft bitsandbytes accelerate trl

5. Hasil Eksperimen (Highlight Task 3)
Berdasarkan implementasi pada Phi-2 Summarization:
Loss: Berhasil menurunkan training loss dari 2.41 menjadi 1.89 dalam 250 steps.
Kapasitas: Mampu merangkum berita kompleks menjadi kalimat ringkas seperti "An apparent clash between soldiers from neighbouring Ethiopia and Eritrea..." secara koheren.
Efisiensi: Menggunakan patch kompatibilitas T4 untuk melatih model 2.7B pada GPU gratisan Google Colab.

6. Identitas Mahasiswa
Nama: Juandra Alghifary
NIM: 1103220165
Kelas: TK-46-02

Catatan: Proyek ini merupakan bagian dari tugas individu mata kuliah Machine Learning/Deep Learning. Semua kode diproduksi dan dirangkum untuk memenuhi standar praktis implementasi Transformer.
