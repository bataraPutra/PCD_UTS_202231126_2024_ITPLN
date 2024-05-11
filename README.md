
# PCD_UTS_202231126_2024_ITPLN

Project ini adalah hasil pengerjaan UTS Pengolahan Citra Digital_D, dimulai dari : 

- Pengambilan citra
- Deteksi warna citra
- Menghitung nilai ambang batas warna citra

Project ini ditujukan kepada pengajar Pengolahan Citra Digital_D, agar dapat dinilai selesai.
## Authors

- ananda batara putra 202231126

## Dokumentasi

 Ikuti petunjuk soal dan ambil foto pada selembar kertas yang bertuliskan nama lengkap peserta dengan  warna merah, hijau, dan biru, dengan instruktur akan menentukan aturan lain.
 - bahan citra = mobil.jpeg
 Setelah menyiapkan karya seni dan mengedit gambar, peserta akan diinstruksikan  untuk memanipulasi keseluruhan gambar menggunakan pemrograman Python.
 - algoritma dan teori: 
 1. Ambil gambar dan buat file Phyton baru.
 2. Impor perpustakaan dan muat file gambar. File gambar sebelumnya berada di lokasi yang sama dengan file Phyton.
 3. Selanjutnya, proses gambar untuk memanipulasi tingkat kontras.
 Hal ini meningkatkan kontras gambar dengan menampilkan tingkat kontras dalam bentuk histogram yang menyesuaikan dengan variabel Beta.
 
 Variabel beta ini mengacu pada parameter yang digunakan dalam transformasi gamma.
 Transformasi gamma merupakan fungsi nonlinier yang  mengubah nilai piksel pada suatu gambar.
 Transformasi ini didefinisikan sebagai: 
 
 O=I^β 
 β=var beta 
 
 Dimana I adalah nilai piksel masukan, O adalah nilai piksel keluaran, dan β adalah variabel gamma.
 Anda dapat mengontrol kecerahan dan kontras gambar dengan menyesuaikan nilai β.
 Saat variabel beta meningkat, transformasi gamma meningkat, sehingga terjadi perubahan pada  tingkat kontras gambar.
 Peningkatan beta biasanya menghasilkan gambar yang lebih cerah dengan kontras yang lebih tinggi.
 Namun, jika Anda menyetelnya terlalu tinggi, Anda mungkin kehilangan detail di area yang redup atau gelap.
 
 4. Program mendeteksi satu warna  RGB (merah, hijau, biru) pada gambar dengan menentukan nilai yang "menentukan rentang warna pada gambar yang sebelumnya dimanipulasi pada skala HSV.

'hsv = cv2.cvtColor(image, cv2.COLOR_RGB2HSV)
lower_warna=np.array([])
upper_warna=np.array([]);'

lalu menggunakan teknik masking untuk menyaring warna lain selain target warna

'var[(mask_not_targetwarna != 0)]= [0-255, 0-255, 0-255];'

Teknik masking dalam pengeditan gambar membatasi area tertentu dalam gambar yang akan diproses atau diproses., ini digunakan untuk mengabaikan atau membiarkan area lain apa adanya.
Hal ini dilakukan dengan menerapkan mask atau "topeng" pada gambar.Hal ini memungkinkan Anda menentukan area  mana yang akan dan tidak akan diterapkan operasi atau efeknya.
 Operasi penyembunyian menggabungkan gambar asli dan masker untuk menghasilkan gambar yang diinginkan. Misalnya, Anda dapat menerapkan masker ke gambar menggunakan operasi  AND bitwise.
 Dalam proses ini, setiap piksel pada gambar yang dihasilkan akan memiliki nilai piksel asli jika nilai piksel pada mask di lokasi terkait adalah 1, atau hitam (0) jika mask berwarna hitam (0).
 mewakili gambar dalam format histogram seperti sebelumnya.
 
 5.  Terakhir, manipulasi ambang batas gambar dengan memasukkan fungsi yang menghitung ambang batas menggunakan semua program pengenalan warna sebelumnya dan cukup menambahkan:
 
 "# Fungsi untuk mencari nilai ambang batas warna hijau
def find_warna_threshold(image):
    hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    hist = cv2.calcHist([hsv], [0], None, [180], [0, 180])
    warna_threshold = np.argmax(hist)
    return warna_threshold"

'#Mencari nilai ambang batas warna

warna_threshold = find_warna_threshold(image)'
 
 Berdasarkan hasil eksperimen, Semua warna memiliki ambang batas 114 . Hal ini mungkin terjadi karena filter yang digunakan memfilter warna dalam warna abu-abu. Pengambangan warna  adalah teknik yang digunakan dalam pemrosesan gambar untuk mengidentifikasi piksel dalam gambar yang memiliki nilai warna tertentu atau berada dalam rentang warna tertentu.Teknik ini berguna untuk segmentasi gambar.

 Tujuannya adalah untuk mengisolasi objek atau area tertentu dalam suatu gambar berdasarkan warna.
 Ambang batas dapat ditentukan secara manual berdasarkan pemahaman  warna yang  diidentifikasi, atau  secara adaptif berdasarkan histogram gambar menggunakan metode pemrosesan gambar seperti metode Otsu atau ambang batas adaptif.

