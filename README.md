# Proyek Klasifikasi Gambar: Animals-10

## Deskripsi Proyek
Proyek ini merupakan model Machine Learning berbasis **Computer Vision** yang dirancang untuk mengklasifikasikan 10 jenis hewan yang berbeda. Model ini dikembangkan sebagai syarat kelulusan Submission Akhir kelas Belajar Pengembangan Machine Learning di Dicoding.

## Informasi Dataset
- **Nama Dataset:** [Animals-10](https://www.kaggle.com/datasets/alessiocorrado99/animals10)
- **Sumber:** Kaggle
- **Total Gambar:** Lebih dari 26.000 gambar dengan resolusi yang tidak seragam (gambar dari dunia nyata).
- **Jumlah Kelas:** 10 Kelas hewan (Cane/Anjing, Cavallo/Kuda, Elefante/Gajah, Farfalla/Kupu-kupu, Gallina/Ayam, Gatto/Kucing, Mucca/Sapi, Pecora/Domba, Scioattolo/Tupai, Ragno/Laba-laba).

## Metodologi
1. **Data Split:** Dataset dibagi menjadi *Train Set* (80%), *Validation Set* (10%), dan *Test Set* (10%) menggunakan `split-folders`.
2. **Data Augmentation:** Diterapkan pada data *training* untuk mencegah *overfitting* (meliputi *rotation, shift, shear, zoom, flip*).
3. **Arsitektur Model:** - Menggunakan teknik **Transfer Learning** dengan *base model* **MobileNetV2** (Pre-trained on ImageNet).
   - Ditambahkan *custom layers* berupa `Conv2D`, `MaxPooling2D`, `Dense`, dan `Dropout` sesuai dengan kriteria yang diminta.
4. **Evaluasi:** Model dievaluasi menggunakan *Test Set* yang belum pernah dilihat sebelumnya dan berhasil mencapai akurasi **>90%**.

## Struktur Export Model
Model yang telah dilatih diekspor ke dalam tiga format berbeda untuk kebutuhan *deployment* lintas platform:
1. **SavedModel (`/saved_model`)**: Untuk *deployment* di server atau cloud menggunakan TensorFlow Serving.
2. **TF-Lite (`/tflite`)**: Untuk *deployment* di perangkat mobile (Android/iOS) dan *embedded devices*.
3. **TFJS (`/tfjs_model`)**: Untuk *deployment* langsung di web browser menggunakan JavaScript.

## Cara Penggunaan
1. Buka file `notebook.ipynb` di Google Colab atau Jupyter Notebook.
2. Pastikan file `kaggle.json` (API Token Kaggle) sudah disiapkan untuk mengunduh dataset secara otomatis.
3. Jalankan seluruh sel dari atas ke bawah (*Run All*).
4. Pada sel bagian *Inference*, Anda dapat mengunggah gambar hewan bebas untuk diuji coba oleh model.

---
**Dikembangkan oleh:** Atika Pratiwi Harahap  
**Email:** atikapratiwi2408@gmail.com