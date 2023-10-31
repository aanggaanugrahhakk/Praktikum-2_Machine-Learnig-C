
# Naive Bayes

Naive Bayes adalah algoritma pembelajaran terawasi yang digunakan untuk tugas klasifikasi. Algoritma ini didasarkan pada teorema Bayes dan mengasumsikan bahwa fitur-fiturnya tidak bergantung satu sama lain dan tidak ada korelasi antar fitur.

Library yang digunakan:
- panda: Ini adalah pustaka manipulasi data yang populer di Python. Library ini menyediakan struktur data untuk menyimpan dan memanipulasi kumpulan data besar secara efisien, serta alat untuk membersihkan, menggabungkan, dan membentuk ulang data. Pustaka ini sering digunakan dalam analisis data dan alur kerja pembelajaran mesin.
- train_test_split: Ini adalah fungsi dari modul model_selection milik scikit-learn. Fungsi ini digunakan untuk membagi dataset menjadi set pelatihan dan pengujian untuk pembelajaran mesin. Fungsi ini mengambil dataset dan ukuran pengujian, dan mengembalikan dua set data: satu untuk melatih model dan satu lagi untuk menguji akurasi model.
- GaussianNB: Ini adalah kelas dari modul naive_bayes milik scikit-learn. Kelas ini digunakan untuk mengimplementasikan algoritma Gaussian Naive Bayes untuk klasifikasi. Algoritma ini didasarkan pada teorema Bayes dan mengasumsikan bahwa fitur-fiturnya independen dan terdistribusi secara normal. Algoritma ini sering digunakan dalam klasifikasi teks dan tugas penyaringan spam.

Penjelasan penyelesaian Naive Bayes yang digunakan di skrip:

- Mengimpor library pandas: Baris pertama skrip mengimpor library pandas dan memberinya alias 'pd'.
- Membaca file CSV: Baris kedua skrip membaca file CSV bernama emails.csv dan menyimpannya dalam DataFrame pandas bernama emails.
- Menampilkan DataFrame: Baris ketiga skrip menampilkan DataFrame emails.
- Menampilkan informasi tentang DataFrame: Baris keempat skrip menampilkan informasi tentang DataFrame emails, termasuk jumlah baris, kolom, dan tipe data.
- Menampilkan ringkasan statistik DataFrame: Baris kelima dari skrip menampilkan ringkasan statistik DataFrame email, termasuk jumlah, rata-rata, deviasi standar, nilai minimum, dan nilai maksimum.
- Membagi data ke dalam set pelatihan dan pengujian: Baris keenam hingga kesembilan dari skrip membagi DataFrame email menjadi set pelatihan dan pengujian menggunakan fungsi train_test_split dari modul model_selection milik scikit-learn. Fungsi ini membagi data menjadi 75% data pelatihan dan 25% data pengujian.
- Membuat model Gaussian Naive Bayes: Baris kesepuluh dari skrip membuat model Gaussian Naive Bayes menggunakan kelas GaussianNB dari modul naive_bayes milik scikit-learn.
- Menyesuaikan model dengan data pelatihan: Baris kesebelas dari skrip menyesuaikan model Gaussian Naive Bayes dengan data pelatihan menggunakan metode fit.
- Membuat prediksi pada data pengujian: Baris kedua belas dari skrip membuat prediksi pada data pengujian menggunakan metode predict.
- Menghitung akurasi model: Baris ketiga belas dari skrip menghitung akurasi model menggunakan fungsi accuracy_score dari modul metrik scikit-learn.

Skrip ini tampaknya mencoba membangun model klasifikasi menggunakan algoritma Gaussian Naive Bayes untuk memprediksi apakah sebuah email adalah spam atau bukan. Namun, ada beberapa masalah dengan kode tersebut.

Pertama, skrip tersebut membuang kolom dari DataFrame 'email' beberapa kali, yang berarti variabel 'x' dan 'y' tidak diberi nilai yang benar.

Kedua, baris hasil_prediksi = modelNB.predict = y_test menetapkan metode prediksi dari kelas GaussianNB ke variabel 'hasil_prediksi', yang mana hal ini tidak benar. Cara yang benar untuk membuat prediksi adalah dengan memanggil metode predict pada model yang telah dipasang, seperti ini: hasil_prediksi = modelNB.predict(x_test).

Terakhir, akurasi model dihitung dengan cara yang salah. Variabel 'hasil_prediksi' seharusnya berisi nilai yang diprediksi, bukan metode prediksi dari kelas GaussianNB. Cara yang benar untuk menghitung akurasi adalah dengan memanggil fungsi accuracy_score pada nilai yang diprediksi dan nilai aktual, seperti ini: accuracy_score(y_test, hasil_prediksi).

Berikut alur penjelasan skrip tersebut:

- Mengimpor pustaka pandas: Baris pertama skrip mengimpor pustaka pandas dan memberinya alias pd.
- Membaca file CSV: Baris kedua skrip membaca file CSV bernama emails.csv dan menyimpannya dalam DataFrame pandas bernama emails.
- Menampilkan DataFrame: Baris ketiga skrip menampilkan DataFrame emails.
- Menampilkan informasi tentang DataFrame: Baris keempat skrip menampilkan informasi tentang DataFrame emails, termasuk jumlah baris, kolom, dan tipe data.
- Menampilkan ringkasan statistik DataFrame: Baris kelima skrip menampilkan ringkasan statistik DataFrame email, termasuk jumlah, rata-rata, deviasi standar, nilai minimum, dan nilai maksimum.
- Menghapus kolom dari DataFrame: Baris keenam hingga kesebelas dari skrip menjatuhkan kolom dari DataFrame email. Variabel x ditetapkan sebagai DataFrame dengan kolom email, no, dan Prediksi yang dijatuhkan, sedangkan variabel y ditetapkan sebagai kolom email, no, dan Prediksi satu per satu.
- Menampilkan variabel x dan y: Baris kedua belas dan ketiga belas dari skrip menampilkan variabel x dan y, masing-masing.
- Membagi data ke dalam set pelatihan dan pengujian: Baris keempat belas hingga ketujuh belas dari skrip membagi variabel x dan y ke dalam set pelatihan dan pengujian menggunakan fungsi train_test_split dari modul model_selection milik scikit-learn. Fungsi ini membagi data menjadi 75% data pelatihan dan 25% data pengujian.
- Menampilkan bentuk set pelatihan dan pengujian: Baris kedelapan belas hingga dua puluh satu dari skrip menampilkan bentuk set pelatihan dan pengujian untuk variabel x dan y.
- Membuat model Gaussian Naive Bayes: Baris kedua puluh dua dari skrip membuat model Gaussian Naive Bayes menggunakan kelas GaussianNB dari modul naive_bayes milik scikit-learn.
- Menyesuaikan model dengan data pelatihan: Baris kedua puluh tiga dari skrip menyesuaikan model Gaussian Naive Bayes dengan data pelatihan menggunakan metode fit.
- Membuat prediksi pada data pengujian: Baris kedua puluh empat dari skrip membuat prediksi pada data pengujian menggunakan metode predict dari kelas GaussianNB.
- Menghitung akurasi model: Baris kedua puluh lima dari skrip menghitung akurasi model menggunakan fungsi accuracy_score dari modul metrik scikit-learn.

Sitasi:
- [1] https://towardsdatascience.com/naive-bayes-classifier-explained-50f9723571ed
- [2] https://machinelearningmastery.com/naive-bayes-classifier-scratch-python/
- [3] https://www.perplexity.ai/search/Naive-Bayes-adalah-qj__Gt2_SDWFUPC3_h4tNg?s=c
- [4] https://www.perplexity.ai/search/Jelaskan-library-berikut-akZSd9h7T1ORBHc4DnkR5g?s=c
## 🔗 Link Data Diri
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anugrahak)

## Authors

- Anugrah AK. [@aanggaanugrahhakk](https://www.github.com/aanggaanugrahhakk)


## Identitas Authors

Nama: Anugrah AK.

NIM: 202131037

Kelas: C
