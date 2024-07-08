# Deteksi Tepi dan Garis

## I. Deteksi Tepi
### 1. Import Library
   Ada 4 library yang saya pakai dalam deteksi tepi dan garis ini, yaitu OpenCV (cv2), NumPy, Matplotlib, dan skimage. Setiap library mempunyai fungsinya masing-masing yang akan saya jabarkan di bawah ini.
   - OpenCV (cv2) adalah library untuk pemrosesan gambar dan video.
   - NumPy adalah library untuk komputasi numerik di Python.
   - Matplotlib adalah library untuk visualisasi data.
   - skimage adalah library untuk pemrosesan dan analisis gambar.
### 2. Pembacaan Gambar
Pembacaan gambar menggunakan fungsi imread dari library OpenCV (cv2) dan disimpan dalam variabel image. Untuk gambar yang dipakai berformat jpg.
### 3. Penampilan Gambar 
Penampilan gambar menggunakan fungsi imshow dari library OpenCV (cv2). Tampilan gambar akan berbentuk jendela berjudul 'Gambar parkir'.
### 4. Konversi Saluran Warna Gambar
Gambar yang memiliki format BGR dikonversi menjadi Grayscale menggunakan fungsi cvtColor. 
### 5. Deteksi Tepi
Gambar grayscale tadi akan dideteksi tepinya menggunakan algoritma Canny. Algoritma Canny dirancang untuk bekerja dengan gambar grayscale. Parameter 100 dan 150 adalah nilai ambang bawah dan ambang atas untuk deteksi tepi. Parameter ini menentukan batas bawah dan batas atas untuk intensitas gradien yang akan dianggap sebagai tepi.
- Piksel dengan gradien intensitas di bawah threshold pertama (100) akan dibuang (tidak dianggap sebagai tepi).
- Piksel dengan gradien intensitas di atas threshold kedua (150) akan dianggap sebagai tepi.
- Piksel dengan gradien intensitas di antara kedua threshold akan dianggap sebagai tepi hanya jika mereka terhubung dengan piksel yang intensitasnya di atas threshold kedua.
### 6. Perbandingan Gambar Grayscale dengan Gambar Deteksi Tepi
Saya membandingkan gambar grayscale dengan gambar hasil deteksi garis dalam satu figure, yang memudahkan untuk melihat perbedaan antara keduanya dengan menggunakan fungsi-fungsi dari library Matplotlib.

## II. Deteksi Garis
### 1. Import Library
Library yang dipakai sama dengan library-library sebelumnya.
### 2. Deteksi Garis
Pendeteksian garis pada gambar yang sama menggunakan fungsi HoughLinesP dari library OpenCV (cv2). Ada beberapa parameter yang diisi, yaitu:
- Edges: hasil gambar deteksi tepi tadi.
- 1: resolusi jarak dalam piksel.
- np.pi/180: resolusi sudut dalam radian.
- 50: threshold, jumlah minimum titik yang diperlukan untuk mendeteksi sebuah garis. Setidaknya harus ada 50 titik yang terletak pada satu garis agar garis tersebut terdeteksi.
- maxLineGap = 7: jarak maksimum antara dua titik yang masih dapat dianggap sebagai satu garis. Dua titik dengan jarak kurang dari atau sama dengan 7 piksel akan dianggap sebagai bagian dari garis yang sama.

Untuk threshold dan maxLineGap sendiri harus disesuaikan agar dapat mendeteksi garis secara akurat.
### 3. Menggambar Garis Terdeteksi
Garis gambar yang sudah terdeteksi digambar ulang dengan ketebalan garis = 3. Bisa dibilang garis tersebut mengalami overlay/ditimpa. 
### 4. Perbandingan Gambar Grayscale dengan Gambar Deteksi Garis
Saya membandingkan gambar grayscale dengan gambar hasil deteksi garis dalam satu figure, yang memudahkan untuk melihat perbedaan antara keduanya dengan menggunakan fungsi-fungsi dari library Matplotlib.








