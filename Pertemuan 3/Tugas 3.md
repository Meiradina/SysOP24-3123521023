# Operation System Boor Process
![WhatsApp Image 2024-03-03 at 14 54 01_cec33aa4](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/fb0995f4-fcb0-430e-8539-06432a524765)

Power ON adalah proses awal pada saat menyalakan komputer, yaotu pada saat menekan tombol ON, untuk memulai proses boot. 

BIOS / POST (Power On Self Test): adalah prosesTahapan yang paling awal adalah menyalakan komputer dengan menekan tombol ON pada CPU yang mana akan menyuplai listrik ke komponen-komponen utama komputer.

Boot adalah proses dimana saat sistem komputer akan membaca seluruh hardware dan software guna memastikan bahwa komputer siap dinyalakan.

Bootloader :Yaitu tahap mencari sistem operasi pada hard drive dan mulai memuat sistem operasi yang ditemukan, seperti Linux, macOS, atau Windows.

Sistem Operasi : Pada langkah ini, sistem operasi dimuat ke dalam memori utama. Kemudian sistem operasi mulai bekerja dan mengeksekusi semua file dan instruksi awal.

Dekstop : Pada tahap ini yang merupakan tampilan grafis utama dari sistem operasi. Pengguna dapat menjalankan program, membuka file, dan mengelola komputer dari desktop.

# Mengidentifikasi CPU Laptop  


### CPU
![WhatsApp Image 2024-03-03 at 15 25 15_745c85b0](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/3971c122-8e9d-421d-b41b-1b0ce607739e) 

Tab CPU memuat informasi prosesor, core speed, dan cache :
1. Prosesor 
Menggunakan processor Intel Core i5 8350U dengan specification Intel Intel ® Core ™ i5-8350U CPU @ 1.70GHz.
2. Core Speed 
Kecepatan clock pada saat ini pada inti prosesor adalah 798.05 MHz dan bus speed yang menghubungkan prosesor ke memori dan perangkat lain adalah 99.76 MHz.
3. Cache
L1 data memiliki ukuran "4 x 32 KByte 8-way", L2 inst. memiliki ukuran "4 x 32 KByte 8-way", level 2 memiliki ukuran "4 x 256 KBytes 4-way", level 3 memiliki ukuran " 6 MBytes 12-way" laptop ini menggunakan 4 cores dan 1 soket.


### MAINBOARD
![WhatsApp Image 2024-03-03 at 15 25 14_ce9c4598](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/cbb4d421-c7dd-4f9d-8b7d-a63093286163)

Tab mainboard memuat informasi motherboard dan bios : 
1. Motherboard
Manufacturer yaitu HP, dengan model 83B3, spesifikasi bus yaitu PCI-Express 3.0 (8.0 GT/S), menggunakan chipset intel Kaby Lake Rev. 08 dan southbridge Intel Coffe Lake-U/Y PCH Rev.21.
2. BIOS
menggunakan brandHP, versi Q78 Ver. -01.26.00, dan dibuat pada 10/02/2023.


### MEMORY
![WhatsApp Image 2024-03-03 at 15 25 15_7568639a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/97fd66b9-e66f-4f34-9cf1-cca9bc63002e)

Tab memory memuat informasi general dan timings :
1.	General
General ber-tipe DDR 4 dengan channel # single, memory pada laptop ini berukuran 16 GBytes, dengan uncore frequency 498.8 MHz. 
2.	Timings
Terdiri dari :
-	DRAM frequency 664.9 MHz
-	FSB:DRAM 3:20
-	CAS# Latency (CL) 10.0 clocks
-	RAS# to CAS# Delay (tRCD) 10 clocks
-	RAS# Precharge (tRP) 10 clocks
-	Cycle Time (tRAS) 28 clocks
-	Row Refresh Cyde Time (tRFC) 234 clocks
-	Command Rate (CR) 2T


### SDP
![WhatsApp Image 2024-03-03 at 15 25 15_40044ae2](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/b326f2b7-9f58-4684-bb44-b34d623f7b2d)

Tab SPD memuat informasi memory slot selection dan timings table : 
1.	Terpasang 2 slot memory yang berukuran 16 GBytes, dengan model Manuf Samsung. Bernomor seri 38580731.
2.	Pada timings table memiliki Frequency, CAS# Latency, RAS# to CAS#, RAS# Precharge, tRAS, tRC dan Voltage yang memiliki 4 macam yang berbeda-beda.


### GRAPHICS
![WhatsApp Image 2024-03-03 at 15 25 17_310314c5](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/6062839f-c733-4dd5-98fc-962a06ef99d6)

Tab Graphics memuat informasi GPU, laptop ini menggunakan GPU Intel ® UHD Graphics 620 dengan Board Manuf Hewlett-Packard dengan revisi 7.


### BENCH 
![WhatsApp Image 2024-03-03 at 15 25 16_d4af148c](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/6e4cde8e-672b-4cee-8e86-ce5b10abe056)

Tab bench memuat informasi bahwa laptop ini menggunakan Benchmark versi 17.01.64.


### ABOUT 
![WhatsApp Image 2024-03-03 at 15 25 17_a3e90419](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/821d94f8-8b9c-45ec-8b48-fa93b11d2b47)

Tab about memuat informasi tentang CPUID dan laptop ini menggunakan Microsoft Windows 11 Home single Language (x64), version 23H2, Build 22631.3155 Directx 12.0.
