## THREADS

### Practice Exercises

**4.1 Provide three programming examples in which multithreading provides better performance than a single-threaded solution.**

Answer:<br>
a. A Web server that services each request in a separate thread.<br>
b. A parallelized application such as matrix multiplication where different parts of the matrix may be worked on in parallel.<br>
c. An interactive GUI program such as a debugger where a thread is used to monitor user input, another thread represents the running application, and a third thread monitors performance.

**4.2 What are two differences between user-level threads and kernel-level threads? Under what circumstances is one type better than the other?**

Answer:<br>
a. User-level threads are unknown by the kernel, whereas the kernel is aware of kernel threads.<br>
b. On systems using either M:1 or M:N mapping, user threads are scheduled by the thread library and the kernel schedules kernel threads.<br>
c. Kernel threads need not be associated with a process whereas every user thread belongs to a process. Kernel threads are generally more expensive to maintain than user threads as they must be represented with a kernel data structure.

**4.3 Describe the actions taken by a kernel to context-switch between kernel-level threads.**

Answer:<br>
Context switching between kernel threads typically requires saving the value of the CPU registers from the thread being switched out and restoring the CPU registers of the new thread being scheduled.

**4.4 What resources are used when a thread is created? How do they differ from those used when a process is created?**

Answer:<br>
Because a thread is smaller than a process, thread creation typically uses fewer resources than process creation. Creating a process requires allocating a process control block (PCB), a rather large data structure. The PCB includes a memory map, list of open files, and environment variables. Allocating and managing the memory map is typically the most time-consuming activity. Creating either a user or kernel thread involves allocating a small data structure to hold a register set, stack, and priority.

**4.5 Assume that an operating system maps user-level threads to the kernel using the many-to-many model and that the mapping is done through LWPs. Furthermore, the system allows developers to create real-time threads for use in real-time systems. Is it necessary to bind a real-time thread to an LWP? Explain.**

Answer:<br>
Yes. Timing is crucial to real-time applications. If a thread is marked as real-time but is not bound to an LWP, the thread may have to wait to be attached to an LWP before running. Consider if a real-time thread is running (is attached to an LWP) and then proceeds to block (i.e. must perform I/O, has been preempted by a higher-priority real-time thread, is waiting for a mutual exclusion lock, etc.) While the real-time thread is blocked, the LWP it was attached to has been assigned to another thread. When the real-time thread has been scheduled to run again, it must first wait to be attached to an LWP. By binding an LWP to a real-time thread you are ensuring the thread will be able to run with minimal delay once it is scheduled.


### Terjemahan 

### Latihan 

**4.1 Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi single-threaded.**

Jawaban : <br>
a. Server web yang melayani setiap permintaan dalam utas terpisah.<br>
b. Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian-bagian yang berbeda dari matriks dapat dikerjakan secara paralel.<br>
c. Program GUI interaktif seperti debugger di mana satu utas digunakan untuk memantau input pengguna, utas lain mewakili aplikasi yang berjalan, dan utas ketiga memantau kinerja.

**4.2 Apa dua perbedaan antara utas tingkat pengguna (user-level threads) dan utas tingkat kernel (kernel-level threads)? Dalam kondisi apa salah satu jenis lebih baik daripada yang lain?** 

Jawaban :<br> 
a. User-level threads tidak diketahui oleh kernel, sedangkan kernel mengetahui Kernel threads.<br>
b. Pada sistem yang menggunakan mapping M:1 atau M:N, user threads dijadwalkan oleh threads library dan kernel menjadwalkan kernel threads. <br>
c. Kernel threads tidak perlu terkait dengan suatu proses sedangkan setiap utas pengguna termasuk dalam suatu proses. Kernel threads umumnya lebih mahal untuk dipelihara daripada user threads karena harus diwakili dengan struktur data kernel.

**4.3 Jelaskan tindakan yang diambil oleh kernel untuk beralih konteks (context-switch) antara utas tingkat kernel.**

Jawaban :<br>

Pengalihan konteks antara kernel threads biasanya memerlukan penyimpanan nilai dari register CPU dari threads yang sedang dialihkan keluar dan memulihkan register CPU dari threads baru yang dijadwalkan.

**4.4 Sumber daya apa yang digunakan saat sebuah utas dibuat? Bagaimana perbedaannya dengan sumber daya yang digunakan saat sebuah proses dibuat?**

Jawaban :<br>

Karena threads lebih kecil daripada proses, pembuatan threads biasanya menggunakan lebih sedikit sumber daya dibandingkan dengan pembuatan proses. Membuat sebuah proses memerlukan pengalokasian process control block (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori(memory map), daftar file yang terbuka, dan variabel lingkungan. Pengalokasian dan pengelolaan peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat utas pengguna atau kernel melibatkan pengalokasian struktur data kecil untuk menyimpan set register, tumpukan (stack), dan prioritas.

**4.5 Asumsikan bahwa sebuah sistem operasi memetakan utas tingkat pengguna (user-level threads) ke kernel menggunakan model many-to-many dan pemetaan dilakukan melalui LWP (Lightweight Processes). Selain itu, sistem mengizinkan pengembang untuk membuat utas real-time untuk digunakan dalam sistem real-time. Apakah perlu untuk mengikat (bind) utas real-time ke LWP? Jelaskan.**

Jawaban :<br>

Ya. Waktu sangat krusial bagi aplikasi real-time. Jika sebuah utas ditandai sebagai real-time tetapi tidak diikat ke LWP, threads tersebut mungkin harus menunggu untuk terhubung ke LWP sebelum berjalan. Pertimbangkan jika sebuah real-time threads sedang berjalan (terhubung ke LWP) dan kemudian mengalami pemblokiran (misalnya, harus melakukan I/O, telah digeser oleh utas real-time dengan prioritas lebih tinggi, sedang menunggu kunci eksklusi mutual, dll.). Saat real-time threads diblokir, LWP yang terhubung ke thread tersebut telah ditugaskan ke thread lain. Ketika real-time threads dijadwalkan untuk berjalan lagi, ia harus terlebih dahulu menunggu untuk terhubung ke LWP. Dengan mengikat LWP ke real-time threads, Anda memastikan bahwa thread akan dapat berjalan dengan penundaan minimal setelah dijadwalkan.
