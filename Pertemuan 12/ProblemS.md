## Reader-Writer Problem

Masalah Readers-Writers adalah masalah klasik dalam pemrograman concurrent yang melibatkan beberapa proses pembaca(readers) dan penulis(writers) yang mengakses sumber basis data secara bersamaan. Tujuannya adalah untuk mengatur akses agar tidak terjadi konflik dan menjaga konsistensi data. 

**Masalah yang dapat terjadi :** <br> <br> 
    a. Starvation (kelaparan) : <br>
        Pembaca atau penulis tertentu mungkin terus-menerus mendapatkan prioritas akses sementara yang lain terus-menerus diabaikan. <br>
         - Solusi dari masalah : <br>
      Implementasikan strategi untuk memastikan bahwa setiap proses pembaca dan penulis memiliki kesempatan yang adil untuk mengakses sumber daya. Salah satu solusi adalah menggunakan mekanisme penjadwalan yang adil, seperti FIFO (First-In-First-Out), atau menggunakan semafor atau mutex yang dapat dikonfigurasi untuk memberikan prioritas yang adil. <br>
      
  b. Deadlock (kebuntuan):<br>
      Situasi di mana pembaca dan penulis saling menunggu sumber daya yang dipegang oleh yang lain, sehingga tidak ada dari mereka yang dapat melanjutkan. <br> 
      - Solusi dari masalah:<br> 
      Terapkan strategi untuk mencegah deadlock, seperti menjaga urutan yang konsisten dalam pengambilan sumber daya, atau menggunakan mekanisme timeout untuk membatalkan operasi yang tertunda terlalu lama.
      
  c. Race conditions (persaingan kondisi):<br>
      Kondisi di mana output dari program tergantung pada urutan akses atau eksekusi dari beberapa proses, dan hasilnya tidak bisa diprediksi secara konsisten. <br> 
      - Solusi dari masalah:<br> 
     Gunakan mekanisme sinkronisasi seperti semafor, mutex, atau kondisi untuk memastikan bahwa akses ke sumber daya bersama terkoordinasi dengan benar, sehingga menghindari hasil yang tidak terduga.

### Ilustrasi Readers-Writers Problem 
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/157e2ed7-516e-473a-ae05-b318d5090533)


## Dining Philosophers Problem

Masalah Dining Philosophers adalah salah satu masalah dalam teori sinkronisasi dan sistem terdistribusi yang mengilustrasikan tantangan sinkronasi sumber data bersama. Dalam masalah ini, sekelompok filsuf duduk di sekitar meja bundar dengan piring di depan masing-masing. Di antara setiap dua piring terdapat garpu. Filsuf-filsuf ini melakukan dua aktivitas: makan dan berpikir. Mereka menggunakan dua garpu untuk makan dan harus menunggu sampai kedua garpu tersedia sebelum mereka bisa makan. 

**Masalah yang dapat terjadi :** <br> <br> 
  a. Deadlock: Bisa terjadi ketika setiap filsuf mengambil satu garpu dan menunggu yang lainnya, sehingga tidak ada yang bisa makan. <br>
  b. Starvation: Mungkin terjadi ketika seorang filsuf selalu menunggu untuk mendapatkan kedua garpu, tetapi selalu diambil oleh filsuf lain sebelum dia bisa makan.<br>

**Solusi:** <br> <br> 
    a. Solusi Sederhana (Tanpa Deadlock): <br> 
        - Filsuf hanya boleh mengambil garpu jika kedua garpu yang berdekatan tersedia. <br> 
        - Setiap filsuf akan mengambil garpu kiri dan kanan secara bergantian.<br>
        - Jika garpu yang diminta tidak tersedia, seorang filsuf akan menempatkan kembali garpu yang sudah diambilnya dan menunggu beberapa saat sebelum mencoba lagi.
   
   b. Solusi dengan Hierarchical Resource Allocation(Hierarki Sumber Daya): <br> 
        - Memberikan nomor kepada setiap garpu. <br> 
        - Filsuf hanya dapat mengambil garpu dengan nomor yang lebih rendah terlebih dahulu, kemudian nomor yang lebih tinggi setelahnya.<br>
        - Ini menghindari siklus dalam pengambilan garpu dan mencegah deadlock.<br>
    
   c. Solusi dengan Penggunaan Semaphore: <br> 
        - Mewakili setiap garpu sebagai semaphore. <br> 
        - Ketika seorang filsuf ingin makan, dia mencoba mengunci semaphore garpu kiri dan kanan. Jika berhasil, dia makan. Jika tidak, dia menunggu sampai kedua semaphore tersedia.<br>
        - Setelah makan, dia melepaskan kedua semaphore.<br>
    
   d. Solusi dengan Waiter (Pelayan): <br> 
        - Menambahkan entitas "pelayan" yang bertanggung jawab untuk memastikan bahwa hanya beberapa filsuf yang makan pada satu waktu. <br> 
        - Filsuf harus meminta izin kepada pelayan sebelum mengambil garpu.<br>
        - Pelayan memastikan bahwa tidak ada filsuf yang berada dalam keadaan kelaparan dan tidak ada deadlock yang terjadi.<br>

### Ilustrasi Dining Philosophers Problem
![Dining Philosophers Problem](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/12c45ebe-cfe8-49cf-9c15-3f3253ec7558)


## Producer-Consumer problem dengan solusi Bounded Buffer

Masalah produsen-konsumen (producer-consumer problem) terjadi ketika ada satu atau lebih produsen yang menghasilkan data dan satu atau lebih konsumen yang mengonsumsi data tersebut. Dalam konteks bounded buffer, terdapat batasan pada ukuran buffer yang dapat menampung jumlah tertentu elemen data.

- Solusi dengan Bounded Buffer: <br> <br> 
  a. Implementasi Buffer Terbatas: Buat struktur data buffer dengan ukuran tertentu. Buffer ini akan menyimpan elemen-elemen yang dihasilkan oleh produsen dan akan dikonsumsi oleh konsumen. Jumlah maksimum elemen yang dapat disimpan dalam buffer terbatas. <br>

  b. Semafor: Gunakan dua semafor: satu untuk mengontrol akses ke buffer (misalnya, mutex), dan satu lagi untuk melacak jumlah slot kosong dalam buffer (misalnya, empty) dan jumlah slot yang berisi data (misalnya, full).<br>

  c. Operasi Produsen:<br>
    - Produsen harus mendapatkan izin (mengunci mutex) sebelum menambahkan data ke buffer.
    - Jika buffer penuh, produsen harus menunggu hingga ada slot kosong di buffer (empty > 0).
    - Setelah menambahkan data ke buffer, produsen harus meningkatkan jumlah slot yang berisi data (full) dan mengurangi jumlah slot kosong (empty).
Setelah selesai, produsen harus melepaskan izin (melepaskan mutex).<br>

  b. Operasi Konsumen:<br> 
    - Konsumen harus mendapatkan izin (mengunci mutex) sebelum mengambil data dari buffer.
    - Jika buffer kosong, konsumen harus menunggu hingga ada data yang tersedia dalam buffer (full > 0).
    - Setelah mengambil data dari buffer, konsumen harus mengurangi jumlah slot yang berisi data (full) dan meningkatkan jumlah slot kosong (empty).
    - Setelah selesai, konsumen harus melepaskan izin (melepaskan mutex).

### Ilustrasi Producer-Consumer problem dengan solusi Bounded Buffer
![producer-consumer problem dengan solusi bounded buffer](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/de5e54f6-826d-4a70-9760-620324d88035)
