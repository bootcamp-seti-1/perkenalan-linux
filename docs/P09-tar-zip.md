Kegunaan TAR dan ZIP

Perintah tar berfungsi menggabungkan banyak berkas menjadi satu arsip sambil menjaga izin akses sistem Linux, sedangkan perintah zip menggabungkan sekaligus mengompres berkas agar ukurannya lebih kecil untuk berbagai sistem operasi.

Perintah zip langsung menggabungkan sekaligus mengompres berkas untuk mengecilkan ukurannya secara otomatis, sehingga sangat praktis dan universal untuk dibagikan lintas sistem operasi seperti Windows, macOS, dan Linux.

C:\Users\Lenovo\latihan_arsip>tar -czvf hasil_linux.tar.gz catatan.txt laporan.txt
a catatan.txt
a laporan.txt

C:\Users\Lenovo\latihan_arsip>tar -acvf hasil_windows.zip catatan.txt laporan.txt
a catatan.txt
a laporan.txt

C:\Users\Lenovo\latihan_arsip>mkdir folder_ekstrak

C:\Users\Lenovo\latihan_arsip>tar -xzvf hasil_windows.zip -C folder_ekstrak
x catatan.txt
x laporan.txt

C:\Users\Lenovo\latihan_arsip>dir folder_ekstrak
 Volume in drive C is Windows-SSD
 Volume Serial Number is CA4F-E64D

 Directory of C:\Users\Lenovo\latihan_arsip\folder_ekstrak

09/11/2026  18:42    <DIR>          .
09/11/2026  18:42    <DIR>          ..
09/11/2026  18:41                14 catatan.txt
09/11/2026  18:41                14 laporan.txt
               2 File(s)             28 bytes
               2 Dir(s)  69.829.197.824 bytes free

Lupa menambahkan flag -r pada zip atau terbalik urutan flag -f pada tar. Jika Anda menjalankan zip proyek.zip dokumen/ tanpa -r, terminal hanya membuat wadah folder kosong tanpa menyertakan berkas di dalamnya, dan selalu pastikan nama berkas hasil langsung mengikuti huruf f (seperti -czvf nama.tar.gz) agar perintah tidak gagal.

