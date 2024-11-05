


# Klasifikasi Batu-Gunting-Kertas

## Deskripsi
Proyek ini bertujuan untuk membuat model klasifikasi gambar yang mampu mengenali tiga jenis gestur tangan: batu, gunting, dan kertas.

## Data
### Sumber data

|   |  KETERANGAN |
|--|--|
|  Nama Dataset |  Rock-Paper-Scissor   |
|  Sumber  |  [dicodingacademy](https://github.com/dicodingacademy/assets/releases/tag/release)|
|  Jumlah data |  Rock: 726, Paper: 750, Scissors: 712  |


### Preprocessing

####  Augmentation

**Parameter-parameter yang digunakan:**
-   **`rescale = 1./255`:** Semua nilai piksel dalam gambar akan dibagi dengan 255. Ini untuk menormalkan nilai piksel menjadi rentang 0-1, yang merupakan format yang umum digunakan dalam jaringan saraf tiruan.
-   **`rotation_range=20`:** Gambar akan diputar secara acak dengan sudut maksimal 20 derajat.
-   **`width_shift_range=0.2`:** Gambar akan digeser secara horizontal secara acak sejauh maksimal 20% dari lebar gambar.
-   **`height_shift_range=0.2`:** Gambar akan digeser secara vertikal secara acak sejauh maksimal 20% dari tinggi gambar.
-   **`shear_range=0.2`:** Gambar akan diberi efek "miring" (shear) secara acak.
-   **`zoom_range=0.2`:** Gambar akan diperbesar atau diperkecil secara acak sebesar maksimal 20%.
-   **`horizontal_flip=True`:** Gambar akan dibalik secara horizontal secara acak (dicerminkan).
-   **`vertical_flip=True`:** Gambar akan dibalik secara vertikal secara acak (dibalik atas bawah).
-   **`fill_mode='nearest'`:** Ketika gambar dimodifikasi (diputar, digeser, dll.), akan ada piksel baru yang perlu diisi. Parameter ini menentukan bagaimana piksel baru tersebut diisi. `nearest` artinya piksel baru akan diisi dengan nilai piksel terdekat.




## Model
### Arsitektur

Model yang digunakan adalah model Sequential dengan deskripsi sebagai berikut:

-   **`tf.keras.layers.Conv2D`:** Lapisan ini melakukan konvolusi, yaitu proses mendeteksi pola atau fitur dalam gambar. Angka-angka seperti 16, 32, dan 64 menunjukkan jumlah filter yang digunakan untuk mendeteksi fitur.
-   **`tf.keras.layers.MaxPooling2D`:** Lapisan ini meringkas informasi dari lapisan sebelumnya untuk mengurangi jumlah parameter dan mempercepat pelatihan.
-   **`tf.keras.layers.Flatten`:** Lapisan ini mengubah data dari bentuk 2D (gambar) menjadi 1D (vektor), agar bisa diproses oleh lapisan fully connected.
-   **`tf.keras.layers.Dense`:** Lapisan ini adalah lapisan fully connected, di mana setiap neuron terhubung ke semua neuron pada lapisan sebelumnya. Lapisan ini akan membuat keputusan akhir, misalnya mengklasifikasikan gambar menjadi beberapa kategori.


Akurasi, RMSprop, dan categorical crossentropy adalah tiga komponen penting dalam pelatihan model pembelajaran mesin, khususnya untuk masalah klasifikasi multi-kelas. Akurasi digunakan untuk mengukur seberapa baik model dalam memprediksi kelas yang benar. RMSprop, sebagai algoritma optimasi, berperan dalam memperbarui bobot model secara efisien agar nilai loss dapat diminimalkan. Sedangkan, categorical crossentropy berfungsi sebagai fungsi kerugian yang menghitung perbedaan antara distribusi probabilitas yang diprediksi oleh model dengan distribusi probabilitas yang sebenarnya. Ketiga komponen ini bekerja sama untuk memastikan model dapat belajar dari data pelatihan dan menghasilkan prediksi yang akurat.



## Hasil

![image](https://github.com/user-attachments/assets/506db08b-b511-49e3-9ded-6bbad3d2d14a)

![image](https://github.com/user-attachments/assets/2ad6f6ab-faaa-4872-84c7-55d6f84160f5)


**Menguji Model dengan Data baru**

![image](https://github.com/user-attachments/assets/b911cd8f-f14a-4af3-9aee-588961d507bd)


