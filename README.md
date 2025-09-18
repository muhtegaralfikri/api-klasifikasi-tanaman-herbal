# Rancang Bangun Aplikasi Web untuk Identifikasi Tanaman Herbal dan Non-Herbal Menggunakan Algoritma KNN yang Dioptimasi dengan PSO

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Flask](https://img.shields.io/badge/Flask-3.0-black.svg)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Repositori ini berisi kode sumber untuk backend API dari aplikasi web **Plant.ID**. Aplikasi ini berfungsi untuk mengidentifikasi jenis daun tanaman berdasarkan gambar yang diunggah oleh pengguna, membedakan antara 3 jenis tanaman herbal dan 3 jenis tanaman pangan (non-herbal).

## 🌿 Deskripsi

Backend ini dibangun menggunakan **Python** dengan framework **Flask**. Tugas utamanya adalah menerima file gambar, melakukan pra-pemrosesan dengan mengekstrak fitur warna rata-rata (Average RGB), dan kemudian mengklasifikasikannya menggunakan model **K-Nearest Neighbors (KNN)**. Nilai K untuk model KNN ini telah dioptimalkan sebelumnya menggunakan algoritma **Particle Swarm Optimization (PSO)** untuk mendapatkan akurasi terbaik.

API ini dirancang untuk di-deploy sebagai layanan web terpisah dan diakses oleh frontend (misalnya, Next.js).

## ✨ Fitur Utama

- Menerima input gambar daun dalam format JPG, PNG, atau JPEG.
- Melakukan ekstraksi fitur warna (Average RGB) secara *real-time*.
- Menggunakan model `scikit-learn` KNN (`.pkl`) yang sudah dilatih untuk klasifikasi multi-kelas.
- Mengembalikan hasil prediksi nama tanaman dalam format JSON yang ringan.
- Dilengkapi dengan CORS untuk memungkinkan akses dari aplikasi frontend.

## 🛠️ Teknologi yang Digunakan

- **Bahasa**: Python 3
- **Framework**: Flask
- **Machine Learning**: Scikit-learn, Pyswarms, Pandas, NumPy
- **Image Processing**: Pillow
- **Server Produksi**: Gunicorn

## 🔌 Dokumentasi API

Endpoint utama dari API ini adalah `/predict`.

- **URL**: `/predict`
- **Method**: `POST`
- **Request Body**: `multipart/form-data`
  - **Key**: `file`
  - **Value**: File gambar daun (e.g., `daun_katuk.jpg`)

---

#### Contoh Respons Sukses

Jika gambar berhasil diproses, API akan mengembalikan status `200 OK` dengan body JSON:

```json
{
  "prediksi": "Katuk"
}
```

#### Contoh Respons Error
Jika terjadi kesalahan (misalnya, tidak ada file yang diunggah), API akan mengembalikan status `400 Bad Request` atau `500 Internal Server Error` dengan body JSON:

```JSON

{
  "error": "Tidak ada file yang diunggah"
}
```

## 🚀 Setup dan Instalasi Lokal
Untuk menjalankan API ini di lingkungan lokal:

Clone repositori ini:

Bash

git clone [https://github.com/muhtegaralfikri/api-klasifikasi-tanaman-herbal.git](https://github.com/muhtegaralfikri/api-klasifikasi-tanaman-herbal.git)
cd api-klasifikasi-tanaman-herbal
(Opsional tapi direkomendasikan) Buat dan aktifkan virtual environment:

Bash

python -m venv ven
# Windows
.\venv\Scripts\activate
# MacOS/Linux
source venv/bin/activate
Instal semua dependensi:

Bash

pip install -r requirements.txt
Jalankan aplikasi Flask:

Bash

flask --app api run
Server akan berjalan di http://127.0.0.1:5000.

## 📂 Struktur Proyek
.
├── api.py                # File utama aplikasi Flask
├── model_multiclass.pkl  # Model KNN yang sudah dilatih
├── requirements.txt      # Daftar dependensi Python
└── .gitignore            # File yang diabaikan oleh Git
## 👥 Tim Pengembang
Proyek ini disusun oleh:

Fauzan Azhari Rahman (105841109622)

Muh. Tegar Al Fikri (105841110722)

Muhammad Dzulfikar Hidayat (105841107822)

## 🎓 Acknowledgments
Proyek ini dikerjakan untuk memenuhi tugas mata kuliah Pemrograman Web pada Program Studi Informatika, Fakultas Teknik, Universitas Muhammadiyah Makassar.

Dosen Pengampu: Darniati, S.Kom., M.T.