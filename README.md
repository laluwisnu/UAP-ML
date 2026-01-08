# UAP-ML

Semantic Image Search & Classification
Proyek ini dibuat untuk memenuhi tugas Ujian Akhir Praktikum (UAP) Pembelajaran Mesin. Aplikasi ini mengintegrasikan pencarian gambar berdasarkan teks (Semantic Search) dengan klasifikasi gambar menggunakan tiga arsitektur Deep Learning yang berbeda.

👥 Profil
Nama: [Lalu Muhammad Wisnu Yusuf]
Mata Kuliah: Praktikum Pembelajaran Mesin


📄 Deskripsi Proyek
Aplikasi ini memungkinkan pengguna untuk memasukkan prompt teks, kemudian sistem akan mencari gambar yang relevan dari dataset COCO. Gambar tersebut kemudian diklasifikasikan menggunakan model yang dipilih oleh pengguna untuk memverifikasi akurasi prediksi model terhadap label asli.

🛠️ Arsitektur Model
Proyek ini menggunakan 3 variasi model untuk perbandingan performa:

Base CNN: Model sederhana yang dibangun dari nol.

MobileNetV2: Model Pre-trained yang dioptimalkan untuk perangkat mobile/ringan.

ResNet50: Model Pre-trained dengan residual connections untuk akurasi tinggi.

📁 Struktur File
Plaintext

.
├── app.py                      # Script utama Streamlit
├── metadata_final.csv          # Metadata dataset (Path, Label, Caption)
├── model_base_cnn.keras        # Model Base CNN (Format Keras 3)
├── model_mobilenet.weights.h5  # Bobot Model MobileNetV2
├── model_resnet.keras          # Model ResNet50
├── val2017/                    # Folder berisi dataset gambar COCO
└── README.md                   # Dokumentasi ini
⚙️ Prasyarat (Prerequisites)
Pastikan Anda memiliki Python 3.9 atau versi yang lebih baru. Install library yang dibutuhkan menggunakan perintah berikut:

Bash

pip install streamlit tensorflow pandas pillow numpy
🚀 Cara Menjalankan
Pastikan semua file model dan folder val2017 berada di direktori yang sama dengan app.py.

Buka terminal atau command prompt.

Jalankan perintah:

Bash

streamlit run app.py
Buka alamat URL yang muncul (biasanya http://localhost:8501) di browser Anda.

💡 Cara Penggunaan
Pilih model yang ingin digunakan pada bagian Sidebar.

Masukkan kata kunci atau kalimat pada kolom input (contoh: "a person riding a motorcycle").

Sistem akan mendeteksi label dan menampilkan gambar yang sesuai.

Lihat hasil prediksi model dan bandingkan dengan caption asli gambar.
