# TUGAS 4 

## TUGAS PENDAHULUAN:

## Jawablah pertanyaan-pertanyaan di bawah ini :

1. Apa yang dimaksud redirection? <br> 
   Redirection adalah proses mengubah sumber input atau tujuan output standar dari suatu perintah. Dalam sistem operasi berbasis Unix, setiap perintah diinisialisasi dengan tiga aliran data standar: satu aliran input (standard input), dan dua aliran output (standard output dan standard error). Aliran ini secara default terhubung ke konsol (keyboard dan layar teks). <br> 
2. Apa yang dimaksud pipeline? <br>
   Pipeline adalah konsep yang memungkinkan eksekusi intruksi atau operasi secara efisien dan terkoordinasi. Biasanya melibatkan beberaoa tahap dan fase, dimana setiap tahap memproses data atau intruksi dan akan mengirimlannya ke tahap berikutnya pada pipeline. Ini memungkinkan untuk eksekusi paralel dan seringkali asinkron, di mana setiap tahap dapat bekerja secara independen sambil memanfaatkan data yang sedang diproses oleh tahap sebelumnya. <br> 
3. Apa yang dimaksud perintah di bawah ini : <br> 
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
   Analisa : Menunjukkan bahwa proses identity 4699 dan 4793 dengan 0, pada cmd bash dan ps. 

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
   Analisa : Penulisan dasar di keyboard, untuk mengakhiri inputan dengan menekan tombol ctrl+d maka akan otomatis kembali ke path root.

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
   ```
   $ mkdir mydir
   $ mkdir mydir **(Terdapat pesan error)**
   ```
   ![WhatsApp Image 2024-03-18 at 21 59 19_8300f76a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/a7492aa6-d3e8-4569-bdaa-efe2868641d5)
   Analisa : Bila terjadi eror saat user menginputkan perintah $ mkdir mydir seperti gambar diatas, maka maksud pesan berikut yaitu direktori mydir yang hendak dibuat sudah tersedia/sudah ada. Sehingga terjadi error atau perintah tersebut ditolak. 

## Percobaan 2 : Pembelokan (redirection)
1. Pembelokan standar output
   ```
    $ cat 1> myfile.txt
    Ini adalah teks yang saya simpan ke file myfile.txt
   ```
   ![WhatsApp Image 2024-03-18 at 21 59 38_2bc80888](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f8bf43d4-c937-4aa7-ba5e-fefeca3e3090)
   Analisa : Membuat file baru dengan ekstensi txt, isi file yang diinputkan adalah “ini adalah teks yang saya simpan ke file myfile.txt” 

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
   ```
    $ cat 0< myfile.txt
    $ cat myfile.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 00 00_c72261b6](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/80ef8c4e-cc94-43ab-bd36-665ea1c3aef0)
   Analisa : Perintah cat myfile.txt adalah perintah untuk menampilkan isi file yang telah dibuat.

3. Pembelokan standar error untuk disimpan di file
   ```
    $ mkdir mydir (Terdapat pesan error)
    $ mkdir mydir 2> myerror.txt
    $ cat myerror.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 10 05_11633f65](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/f05221ca-6af9-412c-b23c-26ee61580d2b)
   Analisa :  2> merupakan metode pembelokan standar error untuk kemudian disimpan di file. Apabila Ketika membuat direktori yang telah dibuat “mkdir mydir” akan terjadi pesan error.

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
   ```
    $ ls filebaru (Terdapat pesan error)
    $ ls filebaru 2> out.txt
    $ cat out.txt
    $ ls filebaru 2> out.txt 2>&
    $ cat out.txt
   ```
   ![WhatsApp Image 2024-03-18 at 22 11 03_a68fc6ef](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/2e2faa34-f8a1-4408-acdb-e106e42cfff4)
   Analisa : Terjadi error karena file baru tidak ada didalam direktori, sehingga tidak ada yang   dibelokkam ke out.txt.

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
   ```
   $ echo “mencoba menulis file” 1> baru
   $ cat filebaru 2> baru 1>&
   $ cat baru
   ```
   ![WhatsApp Image 2024-03-18 at 22 14 51_40791395](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/2fe35e4f-1540-46eb-9af4-fab6666360c9)
   Analisa : Pada percobaan diatas,kalimat yang dibelokkan ke output dengan perintah echo adalah filebaru. Namun selanjutnya filebaru tersebut isinya tertindih oleh pesan error hasil pembelokan dari perintah cat filebaru yang gagal dilaksanakan.


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
   Analisa : Pada penggunaan karakter > digunakan untuk membelokkan output dari echo menjadi sebuah filebaru bernama surat. Penggunaan karakter >> digunakan untuk menyisipkan output dari echo di kelanjutan isi dari file tujuan.


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
   Analisa : Dengan menggunakan notasi here document saat melakukan perintah cat, kita tidak perlu lagi menekan ctrl+d untuk keluar dari editor untuk menyimpan teks.

8.  Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
  ```
  $ cat myfile.txt – surat
  ```
![WhatsApp Image 2024-03-18 at 22 21 01_ee478bba](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/c228ff8f-c749-419d-b753-4aa5e69779b2)
Analisa : Perintah ini akan menampilkan isi file satu persatu sesuai dengan urutan file yang sudah dimasukkan sebelumnya setelah perintah cat.

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
   Analisa : Perintah who yang diberi pipe sort akan membuat data yang ditampilkan secara urut. Perintah pipe more digunakan untuk menampilkan file lengkap beserta atributnya.Perintah pipe sort dan more digunakan untuk menampilkan file dan atribut secara lengkap dan ditampilkan secara urut.

2. Untuk membelokkan standart output ke file, digunakan operator ">"
   ```
   $ echo hello
   $ echo hello > output
   $ cat output
   ```
   ![WhatsApp Image 2024-03-18 at 22 34 54_654dee0a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/d5578a29-24f4-4cdd-8215-bc6f036f2fef)
   Analisa : Perintah echo akan menampilkan kata hello ke terminal. Selanjutnya kata hello akan dibelokkan ke output dan output dibaca akan muncul kata hello. 
   
3. Untuk menambahkan output ke file digunakan operator ">>"
   ```
   $ echo bye >> output
   $ cat output
   ```
   ![WhatsApp Image 2024-03-18 at 22 35 24_f581c63a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/7a7b8179-75c4-4f5e-a3e5-f85ad9d1052a)
   Analisa : Dengan menggunakan operator >> akan menambahlan kata bye pada output.

4. Untuk membelokkan standart input digunakan operator "<"
   ```
   $ cat < output
   ```
   ![WhatsApp Image 2024-03-18 at 22 35 42_ef730020](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/05b015ad-35eb-409c-a1b6-c5f604cbb0da)
   Analisa : Perintah cat < output akan menampilkan output semua kata” yang telah di inputkan sebelumnya pada terminal.

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
   Analisa : Penggunaan cat < output >> out digunakan untuk menambahkan file output dibaris selanjutnya dari file out. Penggunaan cat < output > output digunakan untuk menyimpan isi file output dengan diri sendiri, isi file pada output akan hilang. Penggunaan cat <  out  >>  digunakan untuk  menyisipkan isi file out kedalam baris selanjutnya dari file out itu sendiri. Proses ini akan terus  menerus  menambah baris teks karena isi file out akan terus  diperbaharui tanpa henti. Jika diberikan perintah cat out  maka baris teks isi file out tidak akan berhenti.


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
   Analisa : Penggunaan filter w -h | grep digunakan untuk menyaring informasi user.Penggunaan  filter ls /etc | wc digunakan untuk menampilkan jumlah baris,kata dan byte yang ada didalam direktori /etc. Perintah sort digunakan untuk mengurutkan data. Perintah uniq digunakan untuk menghilangkan duplikasi.

## LATIHAN:

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output   ke file baru.
![WhatsApp Image 2024-03-19 at 05 05 22_265ae78a](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/b0b2bd09-e0b8-46ab-9d2a-1399f3be4134)
Analisa : Untuk melihat daftar direktori aktif, gunakan perintah $ ls, sedangkan untuk membelokkan tampilan standard output ke file baru, gunakan ‘>

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
   ![WhatsApp Image 2024-03-19 at 05 05 51_992136a9](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/1d12db9e-befb-48b1-8373-07eb911e97fa)
   Analisa : Untuk melihat daftar lengkap dari direktori /etc/passwd, gunakan perntah $ ls, sedangkan untuk membelokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya, gunakan ‘>>’

3. Urutkan file baru dengan cara membelokkan standard input.
   ![WhatsApp Image 2024-03-19 at 05 06 25_4f7d09f4](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/3cd7a954-9f1c-49c3-8266-63aab026a9a5)
   Analisa : mengurutkan file menggunakan perintah $ sort, sedangkan untuk membelokkan standard input, gunakan ‘<’

4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
   ![WhatsApp Image 2024-03-19 at 05 06 45_59a7c2b2](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/463e1c4f-1528-4a25-a645-478a4cb9452d)
   Analisa : Mengurutkan file menggunakan perintah $ sort, sedangkan untuk membelokkan standard input, menggunakan ‘’. Pembelokan standart input dan standart output dapat dikombinasikan asalkan tidak boleh menggunakan nama file yang sama sebagai standart input dan output

5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
   ![WhatsApp Image 2024-03-19 at 05 07 13_a474b3fd](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/697f2833-4e97-4978-a295-f0692f3b3006)
   Analisa : Menggunakan perintah $ mkdir untuk membuat direktori baru. Ketika membuat direktori nama yang sama, akan muncul pesan error. Pesan error itu kemudian dibelokkan ke file dengan menggunakan ‘2>’

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
  ![WhatsApp Image 2024-03-19 at 05 07 37_4a5e3260](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/c7fa5a4b-0b66-4697-9873-16ef630c1841)
  Analisa : Buat notasi here document yang akan dibelokkan ke sebuah file lalu isi document tersebut. Setelah diisi dan diakhiri, isi dokumen akan tersimpan ke file yang dibelokkan. File tersebut kemudian diurutkan menggunakan perintah $ sort.

  

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
   ![WhatsApp Image 2024-03-19 at 05 08 16_289aa091](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/5e4afe77-18bc-46e1-8d9d-9936519c89d2)
   Analisa : Untuk menghitung jumlah baris, kata, dan karakter (secara berurutan) dari sebuah file, gunakan perintah wc yang dipipakan dengan perintah cat. Kemudian Hhasilnya bisa ditambahkan ke file menggunakan ‘>>’

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
   ![WhatsApp Image 2024-03-19 at 05 08 46_db9c1890](https://github.com/Meiradina/SysOP24-3123521023/assets/160557713/40feda4b-a431-4f4e-9fab-e49b00608a27)
   Analisa : Uniq digunakan untuk menghapus baris-baris berurutan yang mengalami duplikasi, sedangkan Grep digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan. Pola ini disebut regular expression. Salah satu regular expression dari grep adalah -v (invert0match), yang akan menampilkan baris yang TIDAK mengandung pola yang ditentukan.

### Kesimpulan 
 
Pada Linux, terdapat metode File Descriptor, Redirection, Pipelining, dan filter. File descriptor merupakan cara Linux berkomunikasi dengan file. File descriptor direpresentasikan melalui angka yang dimulai dari 0, 1, 2 dan seterusnya. Redirection adalah pembelokan yang dilakukan untuk standar input, output, dan error dan untuk mengalihkan file descriptor dari 0, 1, dan 2. Pipeline adalah suatu mekanisme pipa yang digunakan sebagai alat komunikasi antar proses. Sedangkan filter adalah utilitas Linux yang dapat memproses standard input (dari keyboard) dan menampilkan hasilnya pada standard output (layar). 


## LAPORAN RESMI:

1. Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan    tampilannya.
2. Kerjakan latihan diatas dan analisa hasilnya
3. Berikan kesimpulan dari praktikum ini.
