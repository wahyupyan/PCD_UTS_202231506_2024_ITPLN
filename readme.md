# PROJECT UTS PENGOLAHAN CITRA 2024 IT PLN

Pada project UTS pengolahan citra kali ini akan dibahas deteksi warna pada citra, urutkan ambang batas terkecil sampai dengan terbesar.
## 1. DETEKSI WARNA PADA CITRA
- Pertama kita import library seperti code dibawah ini :

import cv2
import numpy as np
import matplotlib.pyplot as plt

-	Kode tersebut mengimpor tiga pustaka yang berbeda:
1. cv2: OpenCV untuk pemrosesan citra.
2. matplotlib.pyplot as plt: Matplotlib untuk membuat plot dan grafik.
3. numpy as np: NumPy untuk komputasi numerik.

- Kemudian membaca data gambar dengan code dibawa ini :
  img = cv2.imread('uts.jpg')
  img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  hsv_img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

-	Coding tersebut bertujuan untuk membaca file gambar "parking_lot.jpeg" dan menyimpannya dalam variabel img menggunakan OpenCV.

- sedangkan cv2.cvtColor(img, cv2.COLOR_BGR2RGB): Ini adalah fungsi yang digunakan untuk mengubah ruang warna gambar. Dalam hal ini, gambar yang dibaca sebelumnya (img) dikonversi dari format BGR (Blue-Green-Red) ke format RGB (Red-Green-Blue). Karena OpenCV membaca gambar dalam format BGR secara default, tetapi dalam banyak kasus, kita lebih suka menggunakan format RGB.

- sedangkan cv2.cvtColor(img, cv2.COLOR_BGR2HSV): Ini adalah fungsi yang sama untuk mengubah ruang warna, tetapi kali ini mengonversi dari BGR ke HSV (Hue-Saturation-Value). HSV adalah model warna yang sangat berguna dalam pengolahan citra, terutama untuk deteksi warna, karena memisahkan informasi warna (hue), kejenuhan (saturation), dan nilai (value/brightness).

- Kemudian mendefinisikan warna dari semua warna

![App Screenshot](range_warna.png)

- semua itu mendefinisikan tingkat keterangannya dan ke gelapannya

- lalu Deklarasi warna yang akan digunakan

![App Screenshot](deteksi_warna.png)

- semua ini warna ini akan digunakan untuk mendeteksi warna yang telah ditentukan


## Tampilkan gambar dan hasil deteksi warna

![App Screenshot](gambar original.png)

- ini gambar original dengan cara menampilkannya code sebagai berikut :

![App Screenshot](./uts/Screenshots/code_gambar original.png)

### Penjelasan
plt.figure(figsize=(30, 8)): Ini membuat sebuah figure baru untuk menampung plot. figsize=(30, 8) menentukan ukuran figure dalam satuan inch. Ukuran tersebut adalah 30x8 inch.

plt.subplot(1, 4, 1): Ini menentukan bahwa kita akan memiliki grid plot 1 baris dan 4 kolom, dan kita akan memplot pada subplot ke-1.

plt.imshow(img_rgb): Ini menampilkan gambar img_rgb di subplot yang telah ditentukan sebelumnya.

plt.title('Original Image'): Ini memberikan judul pada plot, dalam hal ini "Original Image".

plt.axis('off'): Ini menghilangkan sumbu x dan y pada plot.

plt.show(): Ini menampilkan plot yang telah dibuat.


## Deteksi warna biru

![App Screenshot](./uts/Screenshots/deteksi_warna_biru.png)

- ini gambar deteksi warna biru dengan cara menampilkannya code sebagai berikut :

![App Screenshot](./uts/Screenshots/code_deteksi_warna_biru.png)

### Penjelasan
plt.figure(figsize=(30, 8)): Seperti sebelumnya, ini membuat sebuah figure baru dengan ukuran 30x8 inch.

plt.subplot(1, 4, 2): Ini menentukan bahwa kita akan memiliki grid plot 1 baris dan 4 kolom, dan kita akan memplot pada subplot ke-2.

plt.imshow(mask_blue_inv, cmap='gray'): Ini menampilkan gambar mask_blue_inv di subplot yang telah ditentukan sebelumnya. Bedanya, cmap='gray' mengatur colormap menjadi grayscale, yang berarti gambar akan ditampilkan dalam skala keabuan.

plt.title('Deteksi Warna Blue'): Memberikan judul pada plot, kali ini judulnya adalah "Deteksi Warna Blue".

plt.axis('off'): Menghilangkan sumbu x dan y pada plot, sama seperti sebelumnya.

plt.show(): Menampilkan plot yang telah dibuat.


## Deteksi warna merah

![App Screenshot](./uts/Screenshots/deteksi_warna_merah.png)

- ini gambar deteksi warna biru dengan cara menampilkannya code sebagai berikut :

![App Screenshot](./uts/Screenshots/code_deteksi_warna_merah.png)

### Penjelasan
plt.figure(figsize=(30, 8)): Membuat sebuah figure baru dengan ukuran 30x8 inch, seperti sebelumnya.

plt.subplot(1, 4, 3): Menentukan subplot ke-3 dalam grid plot 1 baris dan 4 kolom.

plt.imshow(mask_red_inv, cmap='gray'): Menampilkan gambar hasil deteksi warna merah, mask_red_inv, di subplot yang telah ditentukan sebelumnya. Dengan cmap='gray', gambar ditampilkan dalam skala keabuan (grayscale).

plt.title('Deteksi Warna Red'): Memberikan judul pada plot, kali ini judulnya adalah "Deteksi Warna Red".

plt.axis('off'): Menghilangkan sumbu x dan y pada plot, sama seperti sebelumnya.

plt.show(): Menampilkan plot yang telah dibuat.


## Deteksi warna hijau

![App Screenshot](./uts/Screenshots/deteksi_warna_hijau.png)

- ini gambar deteksi warna biru dengan cara menampilkannya code sebagai berikut :

![App Screenshot](./uts/Screenshots/code_deteksi_warna_hijau.png)

### Penjelasan
plt.figure(figsize=(30, 8)): Membuat sebuah figure baru dengan ukuran 30x8 inch.

plt.subplot(1, 4, 4): Menentukan subplot ke-4 dalam grid plot 1 baris dan 4 kolom.

plt.imshow(mask_green_inv, cmap='gray'): Menampilkan gambar hasil deteksi warna hijau, mask_green_inv, di subplot yang telah ditentukan sebelumnya. Dengan cmap='gray', gambar ditampilkan dalam skala keabuan (grayscale).

plt.title('Deteksi Warna Green'): Memberikan judul pada plot, kali ini judulnya adalah "Deteksi Warna Green".

plt.axis('off'): Menghilangkan sumbu x dan y pada plot.

plt.show(): Menampilkan plot yang telah dibuat.


## 2. URUTKAN AMBANG BATAS TERKECIL SAMAPAI DENGAN TERBESAR
- berikut urutkan ambang batas terkecil samapi dengan terbesar

### None
  ![App Screenshot](./uts/Screenshots/none.png)

### blue
  ![App Screenshot](./Screenshots/blue.png)

### red-blue
  ![App Screenshot](./Screenshots/red-blue.png)

### red-green-blue
  ![App Screenshot](./Screenshots/red-green-blue.png)
  

## Hasil Nilai Ambang
  ![App Screenshot](./Screenshots/hasil_ambang.png)

### Penjelasan

hue_channel = hsv_img[:,:,0]: Ini mengambil saluran Hue (saluran pertama) dari gambar yang telah dikonversi ke ruang warna HSV.

_, blue_thresh = cv2.threshold(hue_channel, 100, 130, cv2.THRESH_BINARY): Ini menemukan ambang batas untuk warna biru dengan menggunakan thresholding pada saluran Hue. Nilai threshold yang digunakan di sini adalah 100 hingga 130.

_, red1_thresh = cv2.threshold(hue_channel, 0, 10, cv2.THRESH_BINARY): Ini menemukan ambang batas untuk warna merah (bagian 1) dengan menggunakan thresholding pada saluran Hue. Karena rentang Hue untuk merah terletak di dekat 0 dan 180 (karena sifat lingkaran dari model warna HSV), thresholding dilakukan pada nilai 0 hingga 10.

_, red2_thresh = cv2.threshold(hue_channel, 170, 180, cv2.THRESH_BINARY): Ini menemukan ambang batas untuk warna merah (bagian 2) dengan menggunakan thresholding pada saluran Hue. Karena sifat lingkaran dari model warna HSV, nilai threshold diletakkan di antara 170 hingga 180.

_, green_thresh = cv2.threshold(hue_channel, 40, 80, cv2.THRESH_BINARY): Ini menemukan ambang batas untuk warna hijau dengan menggunakan thresholding pada saluran Hue. Rentang Hue untuk hijau biasanya berkisar antara 40 hingga 80.

all_thresholds = np.unique(np.concatenate((blue_thresh, red1_thresh, red2_thresh, green_thresh))): Menggabungkan semua ambang batas yang telah ditemukan untuk setiap warna, dan kemudian menghapus duplikatnya menggunakan np.unique.

sorted_thresholds = np.sort(all_thresholds): Mengurutkan ambang batas dari yang terkecil hingga yang terbesar.

print("Ambang Batas Terkecil hingga Terbesar:"): Mencetak pesan untuk memberi tahu bahwa hasil berikutnya adalah ambang batas yang telah diurutkan.

print(sorted_thresholds): Mencetak ambang batas yang telah diurutkan.

## Histogram
untuk menampilkan histogram pada gambar cukup lakukan code pada gambar dibawah ini lalu hasilnya kan seperti ini :

### Hasil Histogram
![App Screenshot](./Screenshots/histogram.png)

### Penjelasan
- Cara 1 menggunakan hist():
axs[0,0].imshow(img): Ini menampilkan gambar asli pada subplot (0,0).
axs[0,1].hist(img.ravel(),256,[0,256]): Ini menghitung dan menampilkan histogram gambar menggunakan fungsi hist() dari matplotlib. img.ravel() digunakan untuk meratakan array gambar menjadi satu dimensi. Argumen lainnya adalah jumlah bin (256) dan rentang nilai (0-256).


- Cara 2 menggunakan calcHist():
hist = cv2.calcHist([img],[0],None,[256],[0,256]): Ini menghitung histogram gambar menggunakan fungsi calcHist() dari OpenCV. Argumen pertama adalah daftar gambar, argumen kedua adalah indeks saluran warna (0 untuk grayscale), argumen ketiga adalah mask (None untuk gambar lengkap), argumen keempat adalah jumlah bin, dan argumen kelima adalah rentang nilai.
axs[1,0].imshow(img): Menampilkan gambar asli pada subplot (1,0).
axs[1,1].plot(hist): Ini menampilkan plot histogram yang telah dihitung menggunakan calcHist().

# the end
