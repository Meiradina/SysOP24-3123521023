# Tugas 3

1. Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program.

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


  3. Lakukan clone ke github. Compile dan eksekusi sesuai petunjuk.
     ![WhatsApp Image 2024-03-18 at 14 54 38_10478118](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/38ecb322-6b3a-4026-9f36-5191d76258a2)

  - $ make
  - $ make clean
  - $ sudo make istall
  - $ sudo make uninstall
    ![WhatsApp Image 2024-03-18 at 15 04 41_810e98bc](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/97a199c7-0f04-48e7-8e5d-0bd5f93b91bb)

  - $ iops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 11 01_197cf035](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/4d783078-f831-418d-8976-792aefa3266a)
    
  - $ flops64 $(nproc)
    ![WhatsApp Image 2024-03-18 at 15 12 25_cb6a4880](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/6310426b-8b63-41b2-8586-4b1f1bb6eea9)




   
   
