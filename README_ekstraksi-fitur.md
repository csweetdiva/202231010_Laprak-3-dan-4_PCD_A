# Ekstraksi Fitur
### 1. Import Library 
Ada 4 library yang saya pakai dalam deteksi tepi dan garis ini, yaitu OpenCV (cv2), NumPy, Matplotlib, dan skimage. Setiap library mempunyai fungsinya masing-masing yang akan saya jabarkan di bawah ini.

- OpenCV (cv2) adalah library untuk pemrosesan gambar dan video.
- NumPy adalah library untuk komputasi numerik di Python.
- Matplotlib adalah library untuk visualisasi data.
- skimage adalah library untuk pemrosesan dan analisis gambar. skimage.feature mencakup fungsi graycomatrix dan graycoprops digunakan untuk ekstraksi fitur berbasis Gray-Level Co-occurrence Matrix (GLCM) dari gambar. GLCM adalah metode yang digunakan dalam analisis tekstur untuk menggambarkan hubungan spasial antara nilai-nilai piksel dalam gambar.
### 2. Pemrosesan Gambar
Pertama-tama, saya menggunakan fungsi coffee() dari modul skimage.data untuk memuat gambar kopi yang disediakan secara bawaan dalam paket scikit-image. Setelah itu, gambar ini saya konversi dari RGB ke HSV menggunakan cvtColor. Kemudian, saya membandingkan gambar RGB dengan gambar HSV dalam satu figure menggunakan fungsi-fungsi dari library Matplotlib.
### 3. Pencarian Nilai Rata-Rata dan Standar Deviasi
Saya menggunakan np.mean dan np.std untuk mencari rata-rata dan standar deviasi dari gambar HSV tadi. Ini bertujuan untuk memberikan informasi mengenai distribusi nilai piksel dari gambar tersebut.
### 4. Mengambil 3 Saluran Warna Secara Terpisah
Saya mengambil saluran warna secara terpisah, mulai dari hue sebagai indeks pertama (0), lalu saturation (1), dan value (2).
### 5. Pencarian GLCM Tiap Saluran Warna.
GLCM tiap warna akan mendapat input dari variabel gambar tiap saluran warna. Beberapa parameter yang perlu diisi adalah sebagai berikut.
- distances=[1]: jarak antara pasangan piksel yang akan diperhitungkan dalam GLCM. Dalam codingan ini, jaraknya adalah 1 piksel.
- angles=[0]: arah atau sudut di mana pasangan piksel akan diperhitungkan. Sudut 0 derajat mengacu pada arah horizontal.
- levels=256: jumlah tingkat keabuan yang digunakan dalam GLCM. Untuk gambar dengan kedalaman bit 8 (8-bit), jumlah tingkatnya adalah 256.
- symmetric=True: menentukan apakah GLCM harus disimetriskan (menganggap pasangan (i, j) sama dengan (j, i)).
- normed=True: menentukan apakah GLCM harus dinormalisasi untuk menghasilkan distribusi probabilitas.
### 6. Penampilan Nilai-Nilai Ekstraksi Fitur
- Kontras (Contrast): mengukur perbedaan intensitas antara pasangan piksel dalam GLCM. Nilai kontras yang lebih tinggi menunjukkan bahwa terdapat perbedaan yang signifikan antara intensitas piksel yang terpisah oleh jarak dan arah tertentu.
- Disimilaritas (Dissimilarity): mengukur sejauh mana pasangan piksel dalam GLCM berbeda satu sama lain. Nilai dissimilarity yang lebih tinggi menunjukkan bahwa terdapat lebih banyak perbedaan antara intensitas piksel yang terpisah.
- Homogenitas (Homogeneity): mengukur seberapa dekat distribusi nilai piksel dalam GLCM dengan diagonal (yang menunjukkan homogenitas intensitas). Nilai homogenitas yang lebih tinggi menunjukkan bahwa intensitas piksel yang terpisah memiliki kemiripan yang lebih besar.
- Energi (Energy): mengukur homogenitas atau keseragaman distribusi nilai piksel dalam GLCM. Nilai energi yang lebih tinggi menunjukkan bahwa distribusi intensitas piksel lebih konsisten.
- Korelasi (Correlation): mengukur sejauh mana intensitas piksel dalam GLCM saling berkorelasi secara linier. Nilai korelasi yang lebih tinggi menunjukkan bahwa terdapat hubungan linier yang lebih kuat antara intensitas piksel yang terpisah.
