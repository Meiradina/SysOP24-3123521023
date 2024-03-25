# Tugas 3

## 1. Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program.

  Siklus CPU adalah proses repetitif yang dilakukan CPU untuk menjalankan intruksi program. Pada siklus CPU terdiri dari tiga tahap utama, yaitu Fetch, Decode, dan Execute. 
  
   a. Fetch
  Pada fetch, CPU mengambil intruksi dari memori utama (RAM) menggunakan alamat yang disediakan oleh Program Counter(PC). Kemudian intruksi tersebut disimpan dalam Register Intruksi. 
    
   b. Decode
  Intruksi yang sudah diambil saat proses fetch tadi diuraikan oleh Control Unit. Kemudian Control Unit akan mengodentifikasi jenis intruksi dan menyiapkan operasi berikutnya. 

   c. Execute 
  CPU melakukan operasi atau tindakan yang ditentukan oleh intruksi setelah Decode. Operasi tersebut dapat melibatkan penggunakan ALU(Arithmetic Logic Unit), pengambilan data dari register, atau bisa saja interaksi dengan perangkat I/0.

## Komponen Utama CPU

  - ALU: Bertanggung jawab untuk operasi matematika dan logika.
  - Register: Tempat penyimpanan sementara untuk data dan instruksi.
  - Control Unit: Mengkoordinasikan aktivitas CPU.

### Menjelaskan siklus CPU (fetch,decode,execute) dalam mengeksekusi sebuah program.

  CPU atau Central Processing Unit yang terdapat pada PC, terhubung ke semua perangkat lain yang membuatnya menjadi berfungsi. 

![CPU1](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f745f01b-3a01-4346-91fe-1835579a51bd)


### Menjelaskan peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operasi. 

a. Bahasa Pemrograman

Bahasa pemrograman adalah alat yang digunakan oleh pengembang untuk menulis kode yang dapat diinterpretasikan atau dikompilasi oleh komputer. Bahasa pemrograman memungkinkan pengembang untuk mendefinisikan algoritma dan struktur data yang diperlukan untuk menyelesaikan masalah tertentu. Bahasa pemrograman juga memfasilitasi pengembang untuk menulis kode yang dapat dibaca dan dipahami oleh manusia, serta oleh komputer.

b. Compiler

Compiler adalah program yang mengubah kode sumber yang ditulis dalam bahasa pemrograman menjadi kode mesin yang dapat dijalankan oleh komputer. Proses ini melibatkan beberapa tahap, termasuk analisis sintaks, analisis semantik, optimasi kode, dan pembuatan kode mesin. Compiler memungkinkan kode yang ditulis dalam bahasa pemrograman tingkat tinggi untuk dijalankan pada berbagai platform dan sistem operasi.

c. Sistem Operasi

Sistem operasi (OS) adalah perangkat lunak yang mengelola sumber daya komputer, seperti memori, CPU, dan perangkat keras lainnya. Sistem operasi menyediakan antarmuka antara pengguna dan perangkat keras komputer, memungkinkan pengguna untuk menjalankan aplikasi dan mengelola file. Sistem operasi juga bertanggung jawab untuk menjalankan perangkat lunak yang dikompilasi oleh compiler, memastikan bahwa perangkat lunak berjalan dengan efisien dan aman.


 ## 3. Lakukan clone ke https://github.com/ferryastika/flops-iops. Compile dan eksekusi sesuai petunjuk.
  ![WhatsApp Image 2024-03-18 at 14 54 38_10478118](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/38ecb322-6b3a-4026-9f36-5191d76258a2)

  - $ make
  - $ make clean
  - $ sudo make istall
  - $ sudo make uninstall
    ![WhatsApp Image 2024-03-18 at 15 04 41_810e98bc](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/97a199c7-0f04-48e7-8e5d-0bd5f93b91bb)

### Percobaan 1
  - $ iops64 $(nproc)
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 29 20_df8858c8](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/13b4a9b8-15cc-4fed-b7dd-2c4fabec06f3)

 ### Percobaan 2
  - $ iops64 $(nproc)
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 29 59_9db3b945](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/128335b5-3ddb-4dfb-8bde-b278a06ef475)

 ### Percobaan 3
  - $ iops64 $(nproc)
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 35 37_65854ab0](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/b90c6cc5-273f-4001-8e61-aff0b44c141f)

 ### Percobaan 4
  - $ iops64 $(nproc)
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 38 47_de2302e9](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/87c37058-b2da-4b29-afe1-f0333e71aa57)


 ### Percobaan 5
  - $ iops64 $(nproc)
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 42 29_0740704e](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/46688e21-ae42-4850-b1a7-5429fbd9cc1d)

### PERBANDINGAN EKSEKUSI 
![WhatsApp Image 2024-03-18 at 16 58 06_0fade674](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/d37f161c-7d47-4aea-8a3e-05c03b30501d)

- Analisa : Berdasarkan perbandingan diatas, bisa dilihat bahwa $iops64 dan $flops64 yang dimiliki Azza lebih tinggi daripada Meira dan Nurus. Hal itu menunjukkan bahwa Pc yang dimiliki Azza memiliki performa yang lebih tinggi dibanding lainnya. Itu berarti PC Azza mampu menangani beban kerja IO yang lebih berat dengan efisien dan mampu menyelesaikan tugas komputasi dengan cepat dibandingkan dengan PC yang dimiliki Nurus dan Meira.

- Kesimpulan : Sebuah PC akan lebih mampu menangani beban kerja yang lebih berat apabila mempunyai rata-rata $iops64 yang lebih tinggi. Begitu pula bila PC tersebut juga memiliki rata-rata $flops64 yang tinggi. Maka berarti, PC tersebut memiliki performa yang baik dan akan lebih efisien ketika menangani tugas-tugas komputasi yang dapat melibatkan IO ataupun operasi floating.   



## 4. Apabila Debian VM mu masih belum terdapat packeage gcc, make dan git, lakukan instalasi dan catat setiap langkahnya!

- $ su -l
- $ apt install make
  
  ![WhatsApp Image 2024-03-18 at 16 33 08_d9d71d77](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/487da140-7fc4-4d25-bb0b-d80eef956b14)

- $ apt install git
  
  ![WhatsApp Image 2024-03-18 at 16 33 36_50fcfabf](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/d8614695-3c9b-4784-aa30-46490c128b1d)

- $ apt install gcc
  
  ![WhatsApp Image 2024-03-18 at 16 34 01_0bfb4aec](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/0b8e0812-5024-4356-9b2e-e2b32dff3c7f)







   
   
