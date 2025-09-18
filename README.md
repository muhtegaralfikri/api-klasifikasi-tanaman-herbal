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

```Bash
git clone [https://github.com/muhtegaralfikri/api-klasifikasi-tanaman-herbal.git](https://github.com/muhtegaralfikri/api-klasifikasi-tanaman-herbal.git)
cd api-klasifikasi-tanaman-herbal
```
#### 1. (Opsional tapi direkomendasikan) Buat dan aktifkan virtual environment:

```Bash

python -m venv ven
```

#### 2. Instal semua dependensi:

```Bash

pip install -r requirements.txt
```
#### 3.Jalankan aplikasi Flask:
```Bash

flask --app api run
```
Server akan berjalan di `http://127.0.0.1:5000`.

## 📂 Struktur Proyek
```
.
├── api.py               
├── model_multiclass.pkl  
├── requirements.txt
├── .gitignore
└── README.md            
```