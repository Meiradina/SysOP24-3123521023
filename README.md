# TUGAS 4 

## TUGAS PENDAHULUAN:

## Jawablah pertanyaan-pertanyaan di bawah ini :

1. Apa yang dimaksud redirection? <br> 
   Redirection adalah proses mengubah sumber input atau tujuan output standar dari suatu perintah. Dalam sistem operasi berbasis Unix, setiap perintah diinisialisasi dengan tiga aliran data standar: satu aliran input (standard input), dan dua aliran output (standard output dan standard error). Aliran ini secara default terhubung ke konsol (keyboard dan layar teks). <br> 
3. Apa yang dimaksud pipeline? <br>
   Pipeline adalah konsep yang memungkinkan eksekusi intruksi atau operasi secara efisien dan terkoordinasi. Biasanya melibatkan beberaoa tahap dan fase, dimana setiap tahap memproses data atau intruksi dan akan mengirimlannya ke tahap berikutnya pada pipeline. Ini memungkinkan untuk eksekusi paralel dan seringkali asinkron, di mana setiap tahap dapat bekerja secara independen sambil memanfaatkan data yang sedang diproses oleh tahap sebelumnya. <br> 
5. Apa yang dimaksud perintah di bawah ini : <br> 
    echo, cat, more, sort, grep, wc, cut, uniq <br>
   * echo : Untuk menampilkan text. 
   * cat : Untuk melihat isi file. 
   * more : Untuk membuka file satu per satu. 
   * sort : Untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter. 
   * grep : Untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan.  
   * wc : Untuk menghitung jumlah baris, kata dan karakter dari baris-baris masukan yang diberikan kepadanya.
   * cut : Untuk mengambil  kolom tertentu dan baris-baris masukannya, yang ditentukan pada opinion -c.
   * uniq : Untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, biasanya digabungkan dalam pipeline dengan sort.


### Percobaan 

1. Login sebagai user.
2. Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
3. Selesaikan soal-soal latihan.

## Percobaan 1 : File descriptor

1. Output ke layar (standar output), input dari system (kernel)
    ```
    $ ps
    ```
    ![WhatsApp Image 2024-03-18 at 21 56 11_6d69e0bf](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f78053f9-15f1-47d6-91b9-d673d202eced)

2. Output ke layar (standar output), input dari keyboard (standard input)
   ```
    $ cat
    hallo, apa khabar
    hallo, apa khabar
    exit dengan ^d
    exit dengan ^d
    [Ctrl-d]
   ```
   ![WhatsApp Image 2024-03-18 at 21 58 23_79712084](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/ff456ca7-7614-425d-a87c-38a7ab0f90d1)

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
   ```
   $ mkdir mydir
   $ mkdir mydir **(Terdapat pesan error)**
   ```
   ![WhatsApp Image 2024-03-18 at 21 59 19_8300f76a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/a7492aa6-d3e8-4569-bdaa-efe2868641d5)

## Percobaan 2 : Pembelokan (redirection)
1. Pembelokan standar output
   ```
    $ cat 1> myfile.txt
    Ini adalah teks yang saya simpan ke file myfile.txt
   ```
   ![WhatsApp Image 2024-03-18 at 21 59 38_2bc80888](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f8bf43d4-c937-4aa7-ba5e-fefeca3e3090)

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
   ```
    $ cat 0< myfile.txt
    $ cat myfile.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 00 00_c72261b6](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/80ef8c4e-cc94-43ab-bd36-665ea1c3aef0)

3. Pembelokan standar error untuk disimpan di file
   ```
    $ mkdir mydir (Terdapat pesan error)
    $ mkdir mydir 2> myerror.txt
    $ cat myerror.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 10 05_11633f65](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f05221ca-6af9-412c-b23c-26ee61580d2b)

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
   ```
    $ ls filebaru (Terdapat pesan error)
    $ ls filebaru 2> out.txt
    $ cat out.txt
    $ ls filebaru 2> out.txt 2>&
    $ cat out.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 11 03_a68fc6ef](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/2e2faa34-f8a1-4408-acdb-e106e42cfff4)

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
   ```
   $ echo “mencoba menulis file” 1> baru
   $ cat filebaru 2> baru 1>&
   $ cat baru
   ```
   ![WhatsApp Image 2024-03-18 at 22 14 51_40791395](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/2fe35e4f-1540-46eb-9af4-fab6666360c9)

6. Notasi >> (append)
   ```
   $ echo “kata pertama” > surat
   $ echo “kata kedua” >> surat
   $ echo “kata ketiga” >> surat
   $ cat surat
   $ echo “kata keempat” > surat
   $ cat surat
   ```
   ![WhatsApp Image 2024-03-18 at 22 15 18_6895af34](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/9cf53bb3-faaa-4efe-8630-d37fdc326131)

7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
   ```
   $ cat <<++
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   ++
   $ cat <<%%%
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   %%%
   ```
   ![WhatsApp Image 2024-03-18 at 22 17 53_334e03f5](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/7b870ed4-dd24-4ccf-82df-4954f8176069)

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
  ```
  $ cat myfile.txt – surat
  ```
![WhatsApp Image 2024-03-18 at 22 21 01_ee478bba](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/c228ff8f-c749-419d-b753-4aa5e69779b2)

## Percobaan 3 : Pipa (pipeline)

1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
   ```
   $ who
   $ who | sort
   $ who | sort –r
   $ who > tmp
   $ sort tmp
   $ rm tmp
   $ ls –l /etc | more
   $ ls –l /etc | sort | more
   ```
   ![WhatsApp Image 2024-03-18 at 22 21 25_018c2cb3](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/8acf4b4c-61ed-4e9b-99a8-b40c2cde5f62)

2. Untuk membelokkan standart output ke file, digunakan operator ">"
   ```
   $ echo hello
   $ echo hello > output
   $ cat output
   ```
   ![WhatsApp Image 2024-03-18 at 22 34 54_654dee0a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/d5578a29-24f4-4cdd-8215-bc6f036f2fef)

   
3. Untuk menambahkan output ke file digunakan operator ">>"
   ```
   $ echo bye >> output
   $ cat output
   ```
   ![WhatsApp Image 2024-03-18 at 22 35 24_f581c63a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/7a7b8179-75c4-4f5e-a3e5-f85ad9d1052a)

4. Untuk membelokkan standart input digunakan operator "<"
   ```
   $ cat < output
   ```
   ![WhatsApp Image 2024-03-18 at 22 35 42_ef730020](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/05b015ad-35eb-409c-a1b6-c5f604cbb0da)

5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
   ```
   $ cat < output > out
   $ cat out
   $ cat < output >> out
   $ cat out
   $ cat < output > output
   $ cat output
   $ cat < out >> out (Proses tidak berhenti)
   [Ctrl-c]
   $ cat out
   ```
   ![WhatsApp Image 2024-03-18 at 22 36 33_3ef087ba](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/5a1a2400-e7e7-4e0c-a1bc-af632f556adc)


## Percobaan 4 : Filter
1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
   ```
    $ w –h | grep <user>
    $ grep <user> /etc/passwd
    $ ls /etc | wc
    $ ls /etc | wc –l
    $ cat > kelas1.txt
    Badu
    Zulkifli
    Yulizir
    Yudi
    Ade
    [Ctrl-d]
    $ cat > kelas2.txt
    Budi
    Gama
    Asep
    Muchlis
    [Ctrl-d]
    $ cat kelas1.txt kelas2.txt | sort
    $ cat kelas1.txt kelas2.txt > kelas.txt
    $ cat kelas.txt | sort | uniq
   ```
   ![WhatsApp Image 2024-03-18 at 22 52 47_3d21b520](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/d80e3a9f-1fb3-4907-9807-7cdf4bd43353)
   ![WhatsApp Image 2024-03-18 at 22 47 15_86cffcd9](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/a7283229-28db-4ce5-819c-a02f8b5d4f14)
   ![WhatsApp Image 2024-03-18 at 22 47 36_5fe7b8b6](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/1e06765b-2a04-43b2-ae10-03987bcc0eb2)

## LATIHAN:

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output   ke file baru.
2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
3. Urutkan file baru dengan cara membelokkan standard input.
4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
6. Urutkan kalimat berikut :
   ```
   Jakarta
   Bandung
   Surabaya
   Padang
   Palembang
   Lampung
   ```
  Dengan menggunakan notasi **here document (<@@@ ...@@@)** . [HINT](https://www.geeksforgeeks.org/how-to-use-here-document-in-bash-programming/)
  

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
   ```
    $ cat > hello.txt
    dog cat
    cat duck
    dog chicken
    chicken duck
    chicken cat
    dog duck
    [Ctrl-d]
    $ cat hello.txt | sort | uniq
    $ cat hello.txt | grep “dog” | grep –v “cat”
   ```
## LAPORAN RESMI:

1. Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan    tampilannya.
2. Kerjakan latihan diatas dan analisa hasilnya
3. Berikan kesimpulan dari praktikum ini.
