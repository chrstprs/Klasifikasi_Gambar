# Proyek Klasifikasi Gambar Hewan 

##  Review

Proyek ini bertujuan untuk membangun model klasifikasi gambar hewan menggunakan pendekatan Convolutional Neural Network (CNN) dengan teknik transfer learning. Klasifikasi gambar hewan adalah aplikasi penting dalam computer vision, dan proyek ini dirancang untuk mengenali berbagai jenis hewan seperti *butterfly*, *chicken*, *dog*, *horse*, dan *spider* berdasarkan citra digital. Dengan memanfaatkan model pre-trained seperti *MobileNetV2* dan *EfficientNetV2B0*, pelatihan dilakukan secara efisien dengan akurasi sangat tinggi (>99%). Proyek ini dibangun menggunakan Python dengan pustaka *deep learning* seperti TensorFlow dan Keras, dan seluruh proses pelatihan serta evaluasi dilakukan di *Google Colab* dengan akselerasi GPU.

Proyek ini merupakan bagian dari submission untuk *Kelas Belajar Pengembangan Machine Learning Dicoding* oleh *Damianus Christopher Samosir*. Mari kita jelajahi bagaimana model ini mencapai prediksi dengan tingkat kepercayaan luar biasa: **99,99% untuk butterfly**, **100% untuk chicken**, **100% untuk dog**, **99,95% untuk horse**, dan **100% untuk spider**! 🎉

---

## Library

Proyek ini menggunakan berbagai pustaka Python untuk mendukung pengolahan data, pembangunan model, evaluasi, dan visualisasi. Berikut adalah pustaka utama yang digunakan:

- *TensorFlow (2.18.0)*: Framework utama untuk membangun, melatih, dan mengevaluasi model CNN.
- *Keras*: Antarmuka tingkat tinggi untuk merancang arsitektur model dengan mudah.
- *NumPy*: Untuk manipulasi array dan operasi numerik.
- *Pandas*: Untuk pengolahan data tabular (jika diperlukan).
- *Matplotlib*: Untuk visualisasi plot akurasi dan *loss*.
- *Seaborn*: Untuk visualisasi *heatmap* yang lebih menarik.
- *PIL (Pillow)*: Untuk pemrosesan dan manipulasi gambar.
- *os, zipfile, shutil, pathlib*: Untuk manipulasi file dan direktori.
- *google.colab*: Untuk integrasi dengan Google Colab, termasuk unggah file dan akses dataset.

Dependensi lengkap dapat dilihat di file requirements.txt, yang dapat dihasilkan dengan perintah:
```bash
!pip freeze > requirements.txt
```

---

## Pembagian Data

Dataset *Animals-10* (diunduh dari [Kaggle](https://www.kaggle.com/datasets/alessiocorrado99/animals10)) berisi ribuan gambar hewan, yang dibagi menjadi tiga bagian:
- *Training Set*: ~70% dari total gambar untuk melatih model.
- *Validation Set*: ~20% dari total gambar untuk memantau performa selama pelatihan.
- *Test Set*: ~10% dari total gambar untuk evaluasi akhir pada data yang belum pernah dilihat.

*Augmentasi data* diterapkan pada training set menggunakan *ImageDataGenerator* untuk meningkatkan keragaman citra dan mencegah overfitting. Teknik augmentasi meliputi:
- Rotasi acak (hingga 20 derajat).
- Horizontal flip.
- Zoom acak.
- Pergeseran piksel (lebar dan tinggi).
- Normalisasi piksel (rescaling ke rentang 0-1).

---

## Model

Model dibangun menggunakan arsitektur *Sequential* dengan mengadopsi transfer learning dari *MobileNetV2* dan *EfficientNetV2B0* sebagai feature extractor. Beberapa lapisan awal model pre-trained dibekukan untuk mempertahankan bobot yang telah dilatih, sementara lapisan lainnya di-*fine-tune* untuk menyesuaikan dengan dataset. Lapisan tambahan ditambahkan untuk klasifikasi:
- *GlobalAveragePooling2D*: Mengurangi dimensi fitur.
- *Dropout (0.5)*: Mencegah *overfitting*.
- *Dense*: Lapisan keluaran dengan aktivasi *softmax* untuk kelas hewan.

*Konfigurasi Pelatihan*:
- *Loss Function*: Categorical Crossentropy untuk klasifikasi multi-kelas.
- *Optimizer*: Adam dengan learning rate adaptif.
- *Metrik*: Akurasi.

*Callback* digunakan untuk optimasi pelatihan:
- *EarlyStopping*: Menghentikan pelatihan jika *val_accuracy* tidak meningkat setelah beberapa epoch.
- *ModelCheckpoint*: Menyimpan model terbaik berdasarkan *val_loss*.

---

## Cara Menjalankan

### 1️. Install Dependensi
Pastikan Anda memiliki Python dan semua library yang diperlukan dengan menjalankan perintah berikut:
```bash
pip install -r requirements.txt
```

### 2️. Jalankan Model untuk Inferensi
Gunakan model yang telah dilatih untuk melakukan prediksi pada gambar baru:
```bash
python predict.py --image_path "images/sample.jpg"
```

### 3️. Konversi Model ke Format Lain
#### Konversi ke TFLite
```bash
python convert_to_tflite.py
```

#### Konversi ke TensorFlow.js
```bash
tensorflowjs_converter --input_format=keras model.h5 tfjs_model
```

---

## Hasil Evaluasi

Model menunjukkan performa luar biasa dengan *akurasi >99%* pada data uji, jauh melampaui syarat minimum. Hasil inferensi pada gambar uji menunjukkan tingkat kepercayaan yang sangat tinggi:
- *Butterfly*: 99,99%
- *Chicken*: 100,0%
- *Dog*: 100,0%
- *Horse*: 99,95%
- *Spider*: 100,0%

*Evaluasi* dilakukan dengan:
- *Confusion Matrix*: Menunjukkan prediksi seimbang tanpa bias antar kelas.
- *Classification Report*: Presisi, *recall*, dan F1-score tinggi untuk semua kelas.
- *Plot Akurasi dan Loss*: Menunjukkan konvergensi model yang stabil tanpa tanda *overfitting*.

Hasil ini membuktikan bahwa model mampu menggeneralisasi dengan baik pada data baru, menjadikannya solusi yang andal untuk klasifikasi gambar hewan.

---

## Kesimpulan

Dengan memanfaatkan transfer learning dari *MobileNetV2* dan *EfficientNetV2B0* serta augmentasi data yang efektif, model CNN dalam proyek ini berhasil mengklasifikasikan gambar hewan dengan akurasi sangat tinggi (>99%). Hasil evaluasi menunjukkan bahwa model tidak hanya akurat, tetapi juga mampu menggeneralisasi dengan baik pada data yang belum pernah dilihat. Proyek ini menunjukkan kekuatan transfer learning dalam menyelesaikan tugas klasifikasi citra secara efisien, bahkan dengan dataset yang kompleks seperti Animals-10.

---

## Tentang Saya

- *Nama*: Damianus Christopher Samosir
- *Email*: christophersamosir@gmail.com
- *ID Dicoding*: MC189D5Y0821
