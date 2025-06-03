<p align="center"> <img src="URL_GAMBAR_BANNER" alt="Smart City Bengkulu" width="100%" /> 
</p>

# 🚦 Smart City: Sistem Prediksi & Navigasi Kemacetan Bengkulu

Proyek ini merupakan bagian dari pengembangan sistem Smart City untuk Kota Bengkulu. Sistem ini bertujuan memberikan **peringatan dini terhadap kemacetan lalu lintas** dan merekomendasikan **rute alternatif** secara visual melalui peta interaktif.

## 📌 Studi Kasus

> Kota Bengkulu ingin mengembangkan sistem navigasi cerdas berbasis AI yang dapat memprediksi dan memperingatkan kemacetan secara visual, serta memberikan rekomendasi rute alternatif kepada masyarakat secara interaktif dan informatif.

---

## 🧠 Model AI yang Digunakan: Algoritma Dijkstra + Penalti Kemacetan

🔍 Prediksi Kemacetan
Menggunakan dua model pembelajaran mesin untuk memprediksi tingkat kepadatan lalu lintas:

Random Forest Regressor
Cocok untuk data tabular dan statis. Memberikan prediksi cepat dan akurat terhadap kondisi jalan pada waktu tertentu.

LSTM (Long Short-Term Memory)
Digunakan untuk data deret waktu (time series) seperti volume kendaraan per jam/menit. Mampu mengenali pola jangka panjang dalam data historis lalu lintas.

🧭 Navigasi Rute
Menggunakan algoritma:

Dijkstra
Efisien untuk mencari jalur terpendek dari titik awal ke tujuan.
→ Dimodifikasi dengan penalti kemacetan untuk memprioritaskan jalan yang lebih lancar.

---

## 📊 Jenis, Sumber Data, dan Preprocessing

- **Data jalan**: OpenStreetMap (diakses dengan `osmnx`)
- **Geolokasi pengguna**: Lokasi awal & tujuan dimasukkan manual lalu dikonversi menjadi koordinat dengan geopy
- **Kemacetan**: **Data dummy** yang disimulasikan berdasarkan node tertentu secara statis

### 📌 Catatan tentang data dummy:
> Kemacetan tidak diambil dari sumber real-time. Data ini **hanya simulasi** dan tidak mencerminkan kondisi aktual di Kota Bengkulu. Diperlukan integrasi API eksternal untuk mendukung prediksi kemacetan nyata.

---

## 📈 Strategi Evaluasi Model

- Evaluasi dilakukan dengan data historis lalu lintas menggunakan MSE (Mean Squared Error) sebagai metrik utama untuk prediksi kepadatan.  
- Akurasi dan recall digunakan untuk menilai kemampuan deteksi kemacetan.  
- Validasi model secara berkala dengan data real-time saat integrasi API selesai.

## 🚀 Pengembangan Lanjutan

- Integrasi data real-time dari sensor dan kamera lalu lintas.  
- Pengiriman notifikasi peringatan kemacetan ke pengguna secara langsung.  
- Pengembangan aplikasi mobile interaktif untuk kemudahan akses masyarakat.  
- Integrasi dengan sistem transportasi publik dan layanan ridesharing.

---

## 👥 Tim Pengembang

Ketua  :
Khaylilla Shafaraly Irnanda (G1A023079)

Member :
Aurel Moura Athanafisah  (G1A023001)   
Waridhania As Syifa      (G1A023075)   

---

## 📍 Daftar Lokasi yang Dapat Diakses

| No | Lokasi Populer (Patokan)     |
| -- | ---------------------------- |
| 5  | SD Negeri 5 Kota Bengkulu    |
| 8  | Pantai Panjang               |
| 9  | SMPN 07 Kota Bengkulu        |
| 10 | Pasar Panorama               |
| 11 | Pasar Minggu                 |
| 12 | Universitas Bengkulu (UNIB)  |
| 13 | SMPIT Iqra Bengkulu          |
| 14 | Masjid Raya Baitul Izza      |

💡 Gunakan nama lokasi persis seperti tertulis untuk hasil terbaik

---

## ⚙️ Alur Sistem

<img src="https://raw.githubusercontent.com/username/repo-name/main/assets/alur-sistem.png" alt="Alur Sistem Smart City" width="100%" />

---

Berikut versi **rapi dan ringkas** dari penjelasan tadi, yang cocok dimasukkan ke dalam file `README.md` proyek kamu:

---

## 📊 Evaluasi Performa Sistem Prediksi Kemacetan

### 🔍 Deskripsi Pengujian

Kami melakukan percobaan sebanyak **5 kali** dengan lokasi peta yang berbeda-beda (Map 1 hingga Map 5) untuk mengevaluasi performa sistem prediksi kemacetan berbasis AI. Setiap percobaan mengukur waktu eksekusi dari awal pemuatan peta hingga seluruh fitur aktif sepenuhnya.


---

### ✅ Strategi Evaluasi Model

Evaluasi dilakukan dengan pendekatan kuantitatif menggunakan:

* **Waktu Eksekusi Total (Total Execution Time / TET)**
* **Rata-rata Waktu Eksekusi (Mean Execution Time / MET)**
* **Indeks Performa Relatif (Relative Performance Index / RPI)**

Strategi ini bertujuan untuk:

* Menilai efisiensi sistem dari sisi waktu respons.
* Membandingkan efektivitas tampilan peta dalam memuat data kemacetan.
* Mengidentifikasi variasi peta yang optimal untuk pengembangan final.

---

### 📈 Hasil Evaluasi

| Map   | Total Waktu Eksekusi (detik) | RPI (%)       |
| ----- | ---------------------------- | ------------- |
| Map 1 | 206.18                       | -27.26%       |
| Map 2 | 153.73                       | +5.12%        |
| Map 3 | 156.09                       | +3.67%        |
| Map 4 | **141.69**                   | **+12.57%** ✅ |
| Map 5 | 156.44                       | +3.45%        |

* **MET (Mean Execution Time):** `162.03 detik`
* **Map 4** memberikan performa terbaik dan direkomendasikan sebagai dasar pengembangan.

---

## 🚀 Ayo mulai!  
Jalankan kode, dan nikmati pengalaman navigasi yang lebih pintar untuk Kota Bengkulu.  
**Menuju kota cerdas yang lebih nyaman dan efisien.**
