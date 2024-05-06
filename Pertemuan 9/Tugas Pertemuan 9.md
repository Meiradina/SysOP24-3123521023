## Perbedaan CISC dan RISC

CISC (Complex Instruction Set Computing) dan RISC (Reduced Instruction Set Computing) adalah dua pendekatan arsitektur prosesor yang berbeda dalam desain instruksi komputer. 
Perbedaan dari keduanya adalah : 
- CISC : Memiliki sedikit komponen, tetapi instruksi Program Banyak/Complex
- RISC : Memiliki banyak komponen, tetapi Instruksi Program Sedikit/Sederhana

## Fork : Parent - Child Process

- Melakukan clonning repo : https://github.com/ferryastika/operatingsystem.git
- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/50f14295-d2f9-40bd-9ea0-fe5f5225729d)
  - Menginstall compiler gcc g++ sebelum menjalankan fork
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/2a2b264f-4415-4af3-817c-e5627772b456)
  - Untuk menjalankan fork, lakukan perintah g++ fork01.cpp -o fork01.exe.
  Perintah tersebut digunakan untuk menjalankan program c++ pada fork01.cpp menggunakan compiler g++ dan menghasilkan output fork01.exe.
  Kemudian, untuk menjalankannya lakukan pperintah ./fork01.exe.
- Fork01.c
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/ced88419-6af0-44ea-bddb-c316eb9574fd)
    - Analisa :
    Output setelah menjalankan fork01.exe yaitu menampilkan PID, PPID, dan UID secara berurutan. Setelah mencetak proses pertama, program akan berhenti selama 3 detik kemudian mencetak proses kedua. Berlanjut sampai program selesai mencetak 3 proses. Pada proses pertama, disebut child proses lalu proses kedua parent dan proses ketika merupalam owner proses. 

- Fork02.c
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/21934d0f-131f-4a03-a1d4-98a1646f3d8a)
  - Analisa :
  Output untuk fork02 adalah program melakukan proses berulang kali tanpa henti dengan menampilkan pesan yang mencatat PID masing-masing proses.

- Fork03.c
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/ddf97380-6d33-4e3d-917e-1623069bb687)
  - Analisa :
  Output dari fork03 hanya menampilkan proses dengan PID dari masing-masing.

### Orphan.c
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/57a278a1-184d-40c8-8c1f-96c0f0780d55)
  - Analisa : 
  Output dari proses orphan.c adalah menjalankan parent process lalu setelah parent selesai akan berlanjut menjalankan child process. 

### Zombie.c
![image](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/ebe0643f-8888-46f4-9893-f994283b9a56)
  - Analisa : 
  Process ini terjadi karena adanya child process yang sudah terminated tanpa sepengetahuan parent process. Sehingga parent process tidak mencetak process yang masih dijalankan oleh child process. 



