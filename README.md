# Proyek-Klasifikasi-Gambar-Hewan

## 📝 Overview
```
Proyek ini bertujuan untuk membangun model klasifikasi gambar hewan menggunakan pendekatan Convolutional Neural Network (CNN) dengan transfer learning.
Klasifikasi gambar hewan merupakan salah satu aplikasi penting dalam computer vision, dan proyek ini dirancang untuk mengenali jenis hewan berdasarkan citra digital.
Dengan memanfaatkan model pre-trained seperti MobileNetV2 dan EfficientNetV2B0, proses pelatihan dapat dilakukan secara efisien sambil mencapai akurasi tinggi.
Proyek ini dibangun menggunakan Python dengan pustaka deep learning seperti TensorFlow dan Keras, dan seluruh proses pelatihan serta evaluasi dilakukan di Google Colab.
```

## 📂 Split Data
```
Dataset gambar hewan, yang diunduh dari Kaggle (dataset animals10), dibagi menjadi tiga bagian: training set, validation set, dan test set.
Pembagian ini memastikan model dapat belajar dari data pelatihan, memvalidasi performa selama pelatihan, dan diuji pada data yang belum pernah dilihat.
Augmentasi data diterapkan pada data pelatihan menggunakan ImageDataGenerator untuk meningkatkan keragaman citra dan mencegah overfitting.
Teknik augmentasi meliputi rotasi acak, zoom, horizontal flip, dan pergeseran piksel.
```

## 🧠 Model
```
Model menggunakan arsitektur Sequential dengan lapisan Conv2D, MaxPooling2D, dan mengadopsi transfer learning dengan model pre-trained seperti MobileNetV2 dan EfficientNetV2B0 sebagai feature extractor.
Lapisan tambahan seperti GlobalAveragePooling2D, Dropout, dan Dense ditambahkan untuk menyesuaikan dengan jumlah kelas hewan dalam dataset.
Model dikompilasi menggunakan optimizer Adam dengan learning rate yang diatur secara adaptif.
Callback seperti EarlyStopping dan ModelCheckpoint digunakan untuk memantau pelatihan dan menyimpan model terbaik berdasarkan performa validasi.
```

## 📊 Hasil Evaluasi
```
Model menunjukkan performa luar biasa dengan akurasi prediksi mendekati 100% untuk semua kelas yang diuji, termasuk butterfly (99,99%), chicken (100%), dog (100%), horse (99,95%), dan spider (100%).
Evaluasi dilakukan dengan menampilkan hasil prediksi pada gambar uji, yang menunjukkan bahwa model mampu mengenali kelas hewan dengan sangat akurat.
Hasil ini menunjukkan bahwa model seimbang dan tidak bias terhadap kelas tertentu, dengan performa yang sangat baik pada data baru.
```

## ✅ Kesimpulan
```
Dengan memanfaatkan transfer learning dan augmentasi data yang efektif, model CNN dalam proyek ini berhasil mengklasifikasikan gambar hewan dengan akurasi sangat tinggi.
Hasil evaluasi menunjukkan bahwa model tidak hanya akurat, tetapi juga mampu menggeneralisasi dengan baik pada data yang belum pernah dilihat.
Proyek ini menunjukkan kekuatan transfer learning dalam menyelesaikan tugas klasifikasi citra secara efisien, bahkan dengan dataset yang kompleks.
Model ini dapat menjadi fondasi untuk pengembangan sistem klasifikasi gambar hewan lebih lanjut atau aplikasi computer vision di domain lain.
```
