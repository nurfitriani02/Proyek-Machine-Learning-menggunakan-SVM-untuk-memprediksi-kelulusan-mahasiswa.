# SVM-Klasifikasi-Kelulusan-Mahasiswa.
Proyek Machine Learning menggunakan SVM untuk memprediksi kelulusan mahasiswa.
# 🎓 Proyek Klasifikasi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

## Deskripsi Proyek

Proyek ini bertujuan untuk membangun dan mengevaluasi model klasifikasi menggunakan **Support Vector Machine (SVM)** untuk memprediksi status kelulusan mahasiswa ('Lulus' atau 'Belum Lulus') berdasarkan berbagai fitur akademik dan non-akademik.

Analisis dilakukan melalui serangkaian langkah, mulai dari Eksplorasi Data (EDA), Preprocessing, Training Model SVM dengan berbagai kernel (Linear dan RBF), hingga Interpretasi dan *Deployment* Sederhana.

## 🗂️ Struktur File dan Dataset

Proyek ini diimplementasikan dalam format Google Colab Notebook.

| Nama File | Deskripsi |
| :--- | :--- |
| `[Nama_Notebook_Anda].ipynb` | Notebook utama yang berisi semua langkah kode (Setup, EDA, Preprocessing, Training, Evaluasi). |
| `data_kelulusan.csv` | **Dataset utama.** (Diasumsikan dimuat dari Google Drive pada path yang telah ditentukan dalam Notebook). |

### Fitur yang Digunakan (Contoh)

| Tipe | Fitur |
| :--- | :--- |
| Numerik | IPK, Total SKS, Umur, Lama studi, Nilai mata kuliah tertentu |
| Kategorikal | Status kehadiran, Keaktifan organisasi |
| Label | **Label** (Target: 'Lulus' / 'Belum Lulus') |

## 🚀 Persiapan dan Cara Menjalankan Proyek

### 1. Kebutuhan (Prerequisites)

* Akun Google Drive untuk menyimpan dataset.
* Akses ke Google Colab.
* Library Python: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`.

### 2. Langkah Eksekusi

1.  **Unggah Dataset:** Pastikan file `data_kelulusan.csv` (atau nama file Anda) telah diunggah ke Google Drive Anda.
2.  **Buka Notebook:** Buka file `.ipynb` di Google Colab.
3.  **Sesuaikan Path:** Pada **Sel 2 (Loading Dataset)**, ganti placeholder `file_path` dengan lokasi dataset Anda yang sebenarnya di Google Drive.
    ```python
    file_path = '/content/drive/MyDrive/Colab_Notebooks/data_kelulusan.csv' 
    ```
4.  **Jalankan Semua Sel:** Jalankan semua sel secara berurutan, mulai dari Bagian A hingga Bagian F. Pastikan untuk memberikan izin akses ke Google Drive saat diminta.

## 📋 Ikhtisar Metodologi

### Preprocessing
* **Missing Values:** Ditangani menggunakan `SimpleImputer` (Mean untuk numerik, Most Frequent untuk kategorikal).
* **Encoding:** Fitur kategorikal diubah menggunakan `OneHotEncoder`.
* **Scaling:** Fitur numerik di-standarisasi menggunakan `StandardScaler` (Wajib untuk SVM).
* **Split Data:** Digunakan rasio **80% Training : 20% Testing**.

### Training dan Tuning SVM
Dua model SVM dilatih dan dievaluasi:
1.  **SVM Linear Kernel**
2.  **SVM RBF (Radial Basis Function) Kernel**

Hyperparameter tuning dasar dilakukan untuk parameter `C` dan `gamma` untuk mencari kombinasi model terbaik.

## 📊 Hasil Utama dan Metrik Terbaik

Berikut adalah ringkasan hasil dari model terbaik yang ditemukan melalui *hyperparameter tuning*:

| Metrik | Nilai |
| :--- | :--- |
| **Model Terbaik** | `[Ganti dengan: Linear / RBF]` |
| **Parameter Terbaik** | C=`[Nilai C terbaik]`, gamma=`[Nilai Gamma terbaik]` |
| **Akurasi (Test Set)** | `[Nilai Akurasi Terbaik]` |
| **F1-Score (Lulus)** | `[Nilai F1-Score Lulus]` |

### Interpretasi Kunci

* **Fitur Dominan:** Fitur **IPK** dan **Nilai Mata Kuliah Tertentu** tampak menjadi prediktor paling kuat untuk status kelulusan.
* **Kecenderungan IPK Rendah:** Model mengkonfirmasi bahwa mahasiswa dengan IPK di bawah rata-rata memiliki kecenderungan tinggi untuk masuk ke kategori 'Belum Lulus'.

## ⚙️ Fungsi Prediksi Sederhana

Proyek diakhiri dengan fungsi Python sederhana `predict_status()` yang memungkinkan pengguna memasukkan nilai fitur baru dan mendapatkan prediksi status kelulusan dari model yang telah dilatih.

```python
# Contoh penggunaan fungsi
predict_status(ipk=3.8, sks=144, umur=22, lamastudi=4.0, ...) 
# Output: 'Lulus'
