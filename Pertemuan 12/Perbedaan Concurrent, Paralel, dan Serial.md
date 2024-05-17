## Concurrent vs Paralel

![Concurrent vs Paralel](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/37b270b9-b92f-4582-bfb0-0a943023d1c8)
Berdasarkan gambar, dapat diperoleh informasi seperti berikut : <br> 

**1. Pemrosesan Paralel :**<br>
  - Pada proses Paralel, dua atau lebih tugas (Task 1 dan Task 2) dijalankan secara bersamaan pada dua inti prosesor yang berbeda (core 1 dan core 2). Artinya, setiap core menjalankan satu tugas penuh dari awal hingga akhir tanpa terputus.
  - Contoh : <br>
    Dua koki memasak dua masakan berbeda pada saat yang sama. Koki pertama memasak pasta, dan koki kedua memasak sup. Keduanya memasak secara bersamaan tanpa saling bergantian.

**2. Concurrent :**
  - Pada proses concurrent, beberapa bagian dari tugas (Task 1.1, Task 1.2, dan seterusnya) dijalankan secara bergantian pada core yang sama atau berbeda. Core tersebut mengerjakan bagian-bagian kecil dari setiap tugas bergantian(multitasking).
  - Contoh : <br>
    Seorang sekretaris yang harus mengurus telepon, email, dan dokumen. Dia mengangkat telepon selama beberapa menit, kemudian memeriksa beberapa email, lalu kembali lagi untuk mengangkat telepon, dan seterusnya. Dia menangani semua tugas tersebut secara bergantian.

**3. Kombinasi Concurrent dan Paralel :** <br>
  - Pada pemrosesan ini, dua atau lebih tugas dibagi menjadi bagian-bagian kecil dan dijalankan secara bersamaan di dua core berbeda. Setiap core menjalankan bagian kecil dari beberapa tugas secara bergantian.
  - Contoh : <br>
    Dua pekerja konstruksi bekerja pada dua rumah. Satu pekerja memasang kerangka pada kedua rumah secara bergantian, sementara pekerja kedua memasang atap pada kedua rumah secara bergantian, semuanya secara bersamaan.

## Serial vs Concurrent 

![concurrent vs serial](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/e4d97d59-80c5-4436-85ad-b7226267f5d3)

**1. Serial :**
  - Pada antrian berurutan, tugas-tugas dijalankan satu per satu. Setiap tugas harus diselesaikan sebelum berganti ke tugas berikutnya.
  - Contoh : <br>
    Seorang tukang pos mengantarkan surat ke satu rumah, menyelesaikannya, lalu pergi ke rumah berikutnya, dan seterusnya. Dia menyelesaikan satu tugas sepenuhnya sebelum memulai tugas berikutnya.

**2. Concurrent :**
  - Pada antrian konkuren, beberapa tugas dapat dimulai dan dijalankan bersamaan, tetapi mungkin tidak semuanya akan selesai pada waktu yang sama. Tugas-tugas ini bisa berjalan secara tumpang tindih (overlapping).
  - Contoh : <br>
    Di sebuah restoran, koki mulai memasak beberapa hidangan pada saat yang sama. Dia mungkin mulai memasak sup (Task 0), lalu saat sup dimasak, dia mulai memanggang ayam (Task 1), dan kemudian mulai menyiapkan salad (Task 2). Semua tugas ini berjalan bersamaan tetapi tidak harus selesai pada waktu yang sama.
