# ps, kill, dan top

Perintah `ps`, `kill`, dan `top` digunakan untuk memantau, mengelola, dan menghentikan proses (program) yang sedang berjalan di sistem Linux.

## Contoh 1: Melihat daftar proses yang berjalan (`ps`)
Menampilkan daftar seluruh proses yang aktif di sistem beserta nomor identitas prosesnya (PID).

```bash
[tempelkan baris perintah Anda di sini, contoh: p07@laptop:~$ ps aux | head -n 5]
[tempelkan 3-5 baris output asli dari terminal Anda di sini]
```

## Contoh 2: Memantau penggunaan sumber daya secara real-time (`top`)
Menampilkan pemantauan langsung penggunaan CPU, memori (RAM), dan daftar proses yang paling berat. Menggunakan opsi `-n 1` agar perintah langsung berhenti setelah satu kali pemindaian.

```bash
[tempelkan baris perintah Anda di sini, contoh: p07@laptop:~$ top -b -n 1 | head -n 5]
[tempelkan 3-5 baris output asli dari terminal Anda di sini]
```

## Contoh 3: Menghentikan proses tertentu (`kill`)
Menghentikan program yang macet (*hang*) atau berjalan di latar belakang menggunakan nomor PID-nya.

```bash
[tempelkan baris perintah Anda di sini, contoh: p07@laptop:~$ sleep 100 & kill -9 $!]
[tempelkan output asli dari terminal Anda di sini]
```

## Kesalahan umum

* **Salah memasukkan nomor PID saat menggunakan `kill`:** Mematikan nomor PID yang keliru dapat menghentikan layanan penting sistem secara paksa. Selalu pastikan PID target melalui perintah `ps` terlebih dahulu.
* **Terlalu sering memakai `kill -9` (SIGKILL):** Sinyal `-9` memaksa program mati seketika tanpa sempat menyimpan data sementara. Gunakan `kill <PID>` (sinyal default SIGTERM) terlebih dahulu agar program bisa menutup prosesnya dengan aman.
* **Lupa cara keluar dari tampilan `top`:** Karena `top` berjalan terus-menerus secara interaktif, pengguna pemula sering bingung cara menutupnya. Tekan tombol huruf **`q`** pada keyboard untuk keluar dari tampilan `top`.
* **Salah penulisan huruf besar/kecil pada opsi `ps`:** Opsi pada perintah `ps` bersifat *case-sensitive* (sensitif huruf kapital), misalnya `ps -e` memiliki fungsi yang berbeda dengan `ps -E`.