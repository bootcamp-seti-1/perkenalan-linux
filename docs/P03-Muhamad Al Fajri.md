Nama: Muhamad Al Fajri
Tempat, Tanggal, Lahir: Cirebon, 29 November 2002
alamat: Pondok Al Kahfi
hobi: olahraga (Semua olahraga sport)

| P03 | cat, head, tail, less | docs/P03-cat-head-tail.md |

1. cat (Concatenate)
Menampilkan seluruh isi file sekaligus dari baris pertama sampai terakhir di layar terminal.
- Kapan dipakai: Untuk file teks yang pendek (misal: file .txt singkat, script sederhana, atau config file kecil).
- Kelemahan: Jika filenya sangat panjang (ribuan baris), terminal akan tergulung (scroll) dengan cepat sampai ke baris paling bawah.
Contoh: cat script.py

2. head
Menampilkan beberapa baris pertama (paling atas) dari sebuah file. Secara default, head akan menampilkan 10 baris pertama.
- Kapan dipakai: Saat ingin mengintip bagian awal file (misalnya melihat header baris judul pada file CSV atau komentar di awal script).
- Opsi opsional: Gunakan -n untuk menentukan jumlah baris.
Contoh: head file.txt        # Menampilkan 10 baris pertama
        head -n 5 file.txt   # Menampilkan 5 baris pertama

3. tail
Menampilkan beberapa baris terakhir (paling bawah) dari sebuah file. Secara default, tail menampilkan 10 baris terakhir.
- Kapan dipakai: Sangat sering digunakan oleh DevOps / Developer untuk melihat log error aplikasi atau aktivitas sistem terbaru.
- Fitur Penting (-f): Kamu bisa memantau perubahan file log secara real-time (live) saat ada data baru yang masuk.
Contoh: tail -n 20 error.log   # Menampilkan 20 baris terakhir
        tail -f server.log     # Memantau isi file log secara terus-menerus (live)

4. less
Membuka file dalam mode baca interaktif halaman per halaman (paginator). Isi file tidak langsung membanjiri terminal, melainkan dibuka di tampilan penuh yang bisa kamu navigasi.
- Kapan dipakai: Sangat cocok untuk membaca file yang sangat besar/panjang.
Cara Navigasi di dalam less:
Panah Atas / Bawah atau Space: Untuk scroll naik/turun.
- /kata_kunci: Untuk mencari teks di dalam file (tekan n untuk lanjut ke kata berikutnya).
- q: Untuk keluar (quit) kembali ke terminal.
Contoh: less data_besar.txt