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

  CPU atau Central Processing Unit yang terdapat pada PC, terhubung ke semua perangkat lain yang membuatnya menjadi berfungsi. Sebagai contoh, pada video referensi 1, menggunakan jam untuk menghitung bagaimana CPU akan melewati langkah yang disebut siklus "Fetch-Execute". Dimana siklus tersebut terdiri dari proses Fetch - Decode - Execute.
![CPU1](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f745f01b-3a01-4346-91fe-1835579a51bd)
  Pada CPU, memiliki 3 register, yaitu Programme Counter untuk melacak siklus instruksi, Instruction Register untuk memuat instruksi dari memori, kemudian Accumulator. 
  
  Lalu, membuat tabel RAM(Memori Akses Acak) untuk menyimpan instruksi dan nilai apapun yang akhirnya dihitung. RAM juga digunakan untuk menyimpan jawaban akhir/nilai keluaran dari proses eksekusi ini. 
 
  Pada setiap detik jam(click), CPU akan melakukan ketiga proses secara bergantian dan berulang. Berawal dari Fetch(mengambil intruksi dari alamat memori),Decode(memecahkan kode instruksi), dan kemudian Execute(menjalankan intruksi)
  
  1. Click pertama, Programme Counter diatur ke 0, sehingga CPU mengambil instruksi pada alamat 0 di memori lalu memasukkannya ke Instruction Register.
![CPU2](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/59dde577-6299-4332-ac43-b528d5c69525)
  2. Click kedua, berpindah ke Decode. CPU menerjemahkan instruksi. Intruksinya adalah LOAD dan alamatnya adalah 6. Jadi, CPU akan memuat nilai di alamat ke 6 ke dalam Accumulator.
![CPU3](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/a31eb170-aa10-4790-924b-80ca096f1b92)
  3. Click ketiga, hasil dari terjemahan CPU dari Decode tadi. Hasilnya adalah 1.
![CPU4](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/707925a8-40de-4b3d-8f77-324c1d7b319d)
  4. Click keempat, kembali ke Fetch. Penghitung program bertambah, dan CPU akan mengambil intruksi di bit memori berikutnya. 
  ![CPU5](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/51facd1f-ec99-4ecd-a8a1-35514e93dc41)
  5. Click Kelima, Decode. CPU kembali menerjemahkan intruksi, kali ini intruksinya ADD dan alamatnya adalah 7. 
  ![CPU6](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/dc680dd4-e483-4365-9dbe-58f89293a527)
  6. Click Keenam, Execute. CPU mengeksekusi intruksi, hasilnya adalah 1. Tetapi, karena pada accumulator sudah terdapat nilai 1, maka ditambahkan menjadi 2. 
![CPU7](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/7d26ca62-f066-485d-b716-3cbc48b90df0)
  7. Click Ketujuh, Fetch. Lokasi memori berikutnya yaitu no 2. 
  ![CPU8](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/57a4a7b6-0b5e-44b8-9e61-bb32f0aaf982)
  8. Click Kedelapan, Decode. Instruksi untuk STORE, memasukkan nilai yang ada di alamat 6 ke accumulator. 
![CPU9](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/e965c9f2-ad2b-4da1-9a57-8b17d8c36538)
  9. Click Kesembilan, Execute. Accumulator memuat nilai 2, maka alamat 6 sekarang memiliki nilai 2. 
![CPU10](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/9cfb3365-2060-49e2-b605-2537c5ce930d)
  10. Click Kesepuluh, Fetch. Meenggunakan intruksi baru, yaitu JUMP. Dengan menggunakan alamat sesuai dengan intruksi. 
![CPU11](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/ca5ece1b-1e2a-46d8-83ca-97cebdd762c6)
 11. Click Kesebelas, Decode. JUMP ke alamat 1.
 ![CPU12](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/7ea3c3f8-a8a3-4450-a759-9e7b647f9258)
  12. Click Keduabelas, Execute. Programme Counter kembali ke 1. Maka proses akan kembali lagi berulang.
![CPU13](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/df878b3b-48d7-46a7-8ab4-9de3806ec9cd)



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







   
   
