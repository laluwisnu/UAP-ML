# UAP-ML

🖼️ COCO Semantic Image Search - UAP Pembelajaran Mesin
Proyek ini adalah aplikasi web berbasis Streamlit yang memungkinkan pengguna mencari gambar dari dataset COCO menggunakan prompt teks. Aplikasi ini mengintegrasikan tiga model Deep Learning (CNN) untuk melakukan klasifikasi gambar secara real-time.

🌟 Fitur Utama
Semantic Search: Mencari kategori gambar (misal: person, motorcycle, dog) langsung dari kalimat input pengguna.

Multi-Model Evaluation: Membandingkan hasil prediksi dari 3 arsitektur berbeda:

Base CNN: Arsitektur sederhana buatan sendiri.

MobileNetV2: Model pretrained yang ringan dan cepat.

ResNet50: Model pretrained yang lebih dalam dan akurat.

Metadata Integration: Menampilkan caption asli dari dataset COCO untuk memberikan konteks pada gambar.

🏗️ Struktur Folder
Pastikan struktur folder Anda terlihat seperti ini agar aplikasi berjalan lancar:

Plaintext

UAP_NILAI/
├── app.py                     # File utama aplikasi Streamlit
├── metadata_final.csv         # File CSV berisi path gambar, label, dan caption
├── model_base_cnn.keras       # Model Base CNN (Full Model)
├── model_mobilenet.weights.h5 # Bobot Model MobileNetV2
├── model_resnet.keras         # Model ResNet50 (Full Model)
├── val2017/                   # Folder berisi kumpulan gambar dataset COCO
└── README.md                  # Dokumentasi proyek
🚀 Cara Instalasi & Menjalankan
1. Persiapan Environment
Pastikan Anda sudah menginstal Python (disarankan versi 3.10+). Buat virtual environment untuk menjaga kebersihan library:

Bash

python -m venv env
env\Scripts\activate  # Untuk Windows
2. Instalasi Library
Instal semua dependensi yang diperlukan melalui terminal:

Bash

pip install streamlit tensorflow pandas pillow numpy
3. Menjalankan Aplikasi
Jalankan perintah berikut di folder proyek:

Bash

streamlit run app.py
🧠 Alur Kerja Aplikasi
Input: User memasukkan teks (contoh: "I see a person with a dog").

Matching: Aplikasi mengekstrak kata kunci (label) dari teks tersebut.

Retrieval: Sistem mengambil sampel gambar yang relevan dari metadata_final.csv.

Inference: Gambar diproses oleh model yang dipilih di sidebar untuk diprediksi labelnya.

Output: Menampilkan gambar, skor kepercayaan model (% confidence), dan caption asli.

🛠️ Detail Arsitektur Model (MobileNetV2)
Untuk mengatasi masalah kompatibilitas versi, model MobileNetV2 dibangun menggunakan metode Reconstruct & Load Weights:

Base: MobileNetV2 (Feature Extractor)

Global Average Pooling: Reduksi dimensi.

Dense Layer (128 units): Lapisan tersembunyi dengan aktivasi ReLU.

Output Layer (5 units): Softmax untuk klasifikasi multi-kelas.
