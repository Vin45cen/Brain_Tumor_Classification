# 🧠 Brain Tumor Detection Using CNN

Sistem ini menggunakan **Convolutional Neural Network (CNN)** untuk mendeteksi apakah terdapat tumor pada citra MRI otak. Dibangun dengan TensorFlow/Keras, sistem ini melakukan klasifikasi biner: **Tumor** atau **Tidak Ada Tumor** berdasarkan input gambar.

---

## 📌 Teknologi yang Digunakan

| Teknologi                        | Deskripsi                                       |
| -------------------------------- | ----------------------------------------------- |
| **Python**                       | Bahasa pemrograman utama                        |
| **TensorFlow & Keras**           | Untuk membangun dan melatih model deep learning |
| **OpenCV**                       | Untuk manipulasi dan preprocessing gambar       |
| **PIL (Python Imaging Library)** | Membaca dan mengubah ukuran gambar              |
| **Matplotlib**                   | Untuk visualisasi hasil prediksi dan data       |
| **Google Colab**                 | Lingkungan eksekusi cloud dengan GPU            |
| **Sklearn**                      | Untuk melakukan train-test split                |

---

## 🧠 Arsitektur Model CNN

Model CNN yang digunakan terdiri dari beberapa layer utama:

```plaintext
Input: 224x224 RGB Image

[Conv2D]      - 32 filter 3x3, relu activation
[MaxPooling2D] - 2x2 pooling
[Flatten]     - Ubah matriks fitur ke vektor
[Dense]       - 256 neuron, relu activation
[Dropout]     - Dropout 50% (regularisasi)
[Dense]       - 1 neuron, sigmoid activation (binary output)
```

* **Fungsi Aktivasi ReLU** digunakan untuk menambahkan non-linearitas.
* **Sigmoid** digunakan di layer output karena ini adalah masalah klasifikasi biner.
* **Binary Crossentropy** digunakan sebagai fungsi loss.

---

## ⚙️ Cara Kerja Sistem Deteksi

1. **Preprocessing Gambar**:

   * Gambar MRI diubah ukurannya menjadi 224x224 piksel.
   * Gambar di-normalisasi ke skala \[0,1].
   * Data dilabeli: `1` untuk tumor, `0` untuk tidak ada tumor.

2. **Pelatihan Model**:

   * Dataset dibagi menjadi 80% training dan 20% testing.
   * Sebagian kecil dari training set digunakan untuk validasi.
   * Model dilatih selama 10 epoch menggunakan optimizer `Adam`.

3. **Evaluasi dan Prediksi**:

   * Model dievaluasi terhadap data testing.
   * Gambar baru yang di-upload akan diprediksi apakah mengandung tumor atau tidak berdasarkan output sigmoid.

---

## 📊 Hasil Visualisasi dan Akurasi

### 🎯 Grafik Akurasi dan Loss

Grafik accuracy
![image](https://github.com/user-attachments/assets/88be8022-bb93-4455-a9ed-f781a147299c)


Grafik loss
![image](https://github.com/user-attachments/assets/4b6e1a1c-c146-45c4-a7c2-05e538755416)


> Grafik menunjukkan peningkatan akurasi dan penurunan loss selama proses pelatihan.

---

## 🧪 Contoh Prediksi

![image](https://github.com/user-attachments/assets/b7767023-e3e1-41dd-919c-e69d6d0dc1c9)

