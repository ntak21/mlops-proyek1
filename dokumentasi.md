# Submission 1: Spam Email Classification

Nama: Ariftra Rahmawati
Username dicoding: ntaa21

| | Deskripsi |
| ----------- | ----------- |
| Dataset | [Spam Email](https://https://www.kaggle.com/datasets/mfaisalqureshi/spam-email) |
| Masalah | Klasifikasi email sebagai spam atau non-spam merupakan tantangan penting dalam manajemen email. Dengan semakin banyaknya email yang diterima setiap hari, penting untuk memisahkan email yang relevan dan penting dari yang tidak diinginkan. Email spam bisa mengganggu produktivitas, menimbulkan risiko keamanan melalui phishing, dan membebani sistem email. Oleh karena itu, diperlukan sistem klasifikasi yang efektif untuk secara otomatis mengidentifikasi email spam, sehingga pengguna hanya menerima email yang benar-benar penting di kotak masuk mereka. Sistem ini harus dapat mengenali berbagai pola dan karakteristik email spam serta terus belajar dan beradaptasi dengan teknik-teknik baru yang digunakan oleh pengirim spam.|
| Solusi machine learning | Membuat model deep learning untuk klasifikasi email sebagai spam atau non-spam secara otomatis. Model deep learning yang dikembangkan akan dilatih menggunakan dataset yang berisi berbagai email yang telah dikategorikan sebagai spam atau non-spam.|
| Metode pengolahan | Dataset diproses dengan cara mengubah label dari string menjadi format integer, yaitu dengan menetapkan label spam sebagai 1 dan non-spam sebagai 0. Selain itu, preprocessing juga melibatkan konversi semua fitur teks menjadi huruf kecil untuk memastikan konsistensi dan memudahkan analisis. |
| Arsitektur model |Model machine learning yang digunakan pada proyek ini adalah model jaringan saraf untuk klasifikasi biner. Lapisan TextVectorization akan mengubah teks menjadi urutan angka yang kemudian diproses menjadi vektor embedding menggunakan lapisan Embedding. Kemudian GlobalAveragePooling1D digunakan untuk mengurangi dimensi dengan tetap mempertahankan informasi penting. Lapisan Dense dengan 64 neuron dan aktivasi ReLU diikuti oleh lapisan lain dengan 32 neuron dan aktivasi ReLU digunakan untuk menangkap pola non-linear dalam data. Output akhir dihasilkan oleh lapisan Dense dengan satu neuron dan aktivasi sigmoid, yang menghasilkan probabilitas antara 0 dan 1 untuk klasifikasi biner.|
| Metrik evaluasi | Metrik evaluasi pada model ini adalah BinaryAccuracy yang didapatkan dengan tools loss binary_crossentropy dan dioptimalkan menggunakan Adam optimizer dengan tingkat pembelajaran yang ditentukan oleh hyperparameter. BinaryAccuracy mengukur persentase prediksi yang benar dari model dibandingkan dengan label sebenarnya dalam data validasi. |
| Performa model | Model tersebut menghasilkan val_binary_accuracy sebesar 0.9774|
