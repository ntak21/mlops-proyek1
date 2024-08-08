
# Anemia Detection Machine Learning Pipeline

Nama: Ariftra Rahmawati
Username Dicoding: ntaa21

| | Deskripsi |
| ----------- | ----------- |
| Dataset | [Anemia Dataset](https://www.kaggle.com/datasets/biswaranjanrao/anemia-dataset) |
| Masalah | Anemia adalah kondisi umum di mana tubuh kekurangan sel darah merah atau hemoglobin yang cukup, menyebabkan kelelahan dan gangguan kesehatan lainnya. Jika tidak ditangani, anemia bisa berakibat fatal. Dengan meningkatnya prevalensi anemia, terutama pada kelompok rentan seperti wanita hamil dan anak-anak, sistem deteksi dini yang efisien dan mudah diakses cukup diperlukan. |
| Solusi machine learning | Solusi yang akan dibuat adalah model machine learning berbasis neural network untuk memprediksi kemungkinan seseorang mengalami anemia. Model ini akan menggunakan berbagai fitur seperti jenis kelamin, hemoglobin, MCH (Hemoglobin Korpuskel Rata-rata), MCHC (Konsentrasi Hemoglobin Korpuskel Rata-rata), dan MCV (Volume Korpuskel Rata-rata)|
| Metode pengolahan | Metode pengolahan data yang digunakan yaitu transformasi fitur-fitur kategorikal menjadi one-hot encoding dan normalisasi fitur-fitur numerik ke rentang [0, 1]. Pada pipeline TFX digunakan komponen-komponen berikut: `CsvExampleGen`, `StatisticsGen`, `SchemaGen`, `ExampleValidator`, `Transform`, `Trainer`, `Evaluator`, dan `Pusher`. |
| Arsitektur model | Arsitektur model yang digunakan adalah neural network dengan beberapa lapisan tersembunyi. Keras Tuner digunakan untuk mengatur jumlah unit pada setiap lapisan serta tingkat pembelajaran yang optimal. Terdapat tiga lapisan tersembunyi dengan jumlah unit yang bervariasi antara 128, 256, dan 512 untuk lapisan pertama, 32, 64, dan 128 untuk lapisan kedua, serta 8, 16, dan 32 untuk lapisan ketiga. Lapisan output menggunakan aktivasi sigmoid untuk prediksi biner. |
| Metrik evaluasi | Metrik yang digunakan untuk mengevaluasi performa model adalah akurasi biner. Selain itu, digunakan juga metrik `AUC`, `Precision`, `Recall`, dan `ExampleCount` untuk evaluasi yang lebih komprehensif.|
| Performa model | Model yang dibuat menunjukkan performa yang baik dengan akurasi validasi yang tinggi pada data evaluasi. Model ini dilatih menggunakan optimasi Adam dengan hyperparameter terbaik yang dipilih oleh Keras Tuner. Pada training, didapatkan akurasi biner 0.9886. |
| Opsi deployment | Model yang telah dilatih akan dideploy sebagai layanan web menggunakan TensorFlow Serving. Model ini dapat diakses melalui endpoint REST API yang memungkinkan pengguna untuk mengirimkan data pasien dan menerima prediksi stroke secara real-time. |
| Web app | [anemia-detection](https://humble-success-production.up.railway.app/v1/models/anemia-detection-model/metadata |
| Monitoring | Monitoring dilakukan untuk memastikan model yang telah dideploy berfungsi dengan baik dan memberikan prediksi yang akurat. Monitoring dilakukan dengan menggunakan prometheus. |
