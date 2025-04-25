# Proyek-Klasifikasi-

## 📝 Overview
```
Proyek ini bertujuan untuk membangun model klasifikasi gambar buah menggunakan pendekatan Convolutional Neural Network (CNN) dengan transfer learning.
Klasifikasi gambar adalah salah satu tantangan populer dalam bidang computer vision, dan
proyek ini dirancang untuk mengenali jenis buah berdasarkan citra digital yang diberikan.
 Dengan menggunakan model pre-trained seperti MobileNetV2 dan DenseNet121, proses pelatihan dapat dilakukan secara efisien sambil tetap mencapai hasil yang akurat.
Proyek ini dibangun menggunakan Python dan pustaka deep learning populer seperti TensorFlow dan Keras,
dan seluruh proses pelatihan serta evaluasi dilakukan menggunakan Google Colab.
```

## 📂 Split Data

```
Dataset gambar buah dibagi menjadi tiga bagian utama: training set, validation set, dan test set.
Pembagian ini dilakukan untuk memastikan bahwa model dapat belajar dari sebagian data (training), divalidasi kinerjanya selama proses pelatihan (validation),
dan akhirnya diuji performanya pada data yang benar-benar belum pernah dilihat sebelumnya (test).
Selain itu, augmentasi data diterapkan pada data pelatihan menggunakan ImageDataGenerator untuk memperkaya keragaman citra dan mencegah overfitting.
Augmentasi meliputi rotasi acak, zoom, horizontal flip, dan pergeseran piksel.
```
##  Model
```
Model Menggunakan Model Sequential, Conv2D, Pooling Layer dan mengadopsi arsitektur transfer learning, di mana model pre-trained seperti MobileNetV2
dan DenseNet121 dimanfaatkan sebagai feature extractor.
Lapisan tambahan seperti GlobalAveragePooling2D, Dropout, dan Dense digunakan di atas backbone untuk menyesuaikan dengan jumlah kelas dalam dataset buah.
Model dikompilasi menggunakan optimizer Adam dengan learning rate yang disesuaikan otomatis menggunakan ReduceLROnPlateau.
Proses pelatihan dipantau oleh beberapa callback, termasuk EarlyStopping dan ModelCheckpoint, serta sebuah callback khusus yang menghentikan pelatihan saat akurasi mencapai 98%.
```

## 📊 Hasil Evaluasi
```
Model menunjukkan performa yang sangat baik dengan akurasi pelatihan mendekati 98%, validasi sekitar 97%, dan akurasi pengujian (test) juga berada di kisaran 97%.
Selain metrik akurasi, evaluasi juga mencakup confusion matrix dan classification report yang menunjukkan bahwa model mampu mengenali semua kelas buah dengan cukup baik.
Precision, recall, dan f1-score pada masing-masing kelas juga tergolong tinggi, menunjukkan bahwa model seimbang dan tidak bias terhadap kelas tertentu.
Visualisasi confusion matrix menggunakan heatmap memberikan gambaran jelas tentang prediksi yang benar dan salah.
```

## ✅ Kesimpulan
```
Dengan memanfaatkan transfer learning dan strategi augmentasi data yang baik, model CNN dalam proyek ini berhasil mengklasifikasikan gambar buah dengan akurasi tinggi.
Hasil evaluasi menunjukkan bahwa model tidak hanya akurat, tetapi juga cukup general untuk digunakan pada data baru yang belum pernah dilihat.
Proyek ini menunjukkan potensi besar dari transfer learning dalam menyelesaikan permasalahan klasifikasi citra secara efisien,
bahkan ketika dataset yang digunakan tidak terlalu besar. Model ini dapat menjadi dasar yang kuat untuk pengembangan sistem klasifikasi gambar lebih lanjut di berbagai domain.
```
