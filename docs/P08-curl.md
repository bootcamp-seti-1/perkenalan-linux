# CURL (Client URL) pada Command Line Interface (CLI)

Kegunaan: curl adalah perintah CLI yang digunakan untuk mengirim dan menerima data dari server melalui URL menggunakan protokol seperti HTTP, HTTPS, FTP, dan lainnya.

## 1. Contoh Perintah CURL dan Output
Berikut 3 contoh perintah yang bisa dijalankan di laptop saya.

### Contoh 1 — Melihat HTTP Response Header
Perintah:
curl -I https://example.com

Input:
agama@Pili MINGW64 /d/bootcamp-seti/software/perkenalan-linux (P08)
$ curl -I https://example.com

Output:
HTTP/2 200 
date: Mon, 09 Nov 2026 23:46:49 GMT
content-type: text/html; charset=utf-8
server: cloudflare
last-modified: Thu, 05 Nov 2026 21:17:41 GMT
allow: GET, HEAD
accept-ranges: bytes
age: 11
cf-cache-status: HIT
cf-ray: a580b2f2eb0dd042-SIN
alt-svc: h3=":443"; ma=86400

Penjelasan:
| Output | Penjelasan |
| --- | --- |
| HTTP/2 200 | Server berhasil menerima dan memproses request. Kode 200 berarti OK atau berhasil |
| date: Mon, 09 Nov 2026 23:46:49 GMT | Waktu ketika server memberikan respons. GMT adalah zona waktu yang digunakan |
| content-type: text/html; charset=utf-8 | Jenis konten yang dikirim adalah HTML dengan encoding UTF-8 |
| server: cloudflare | Server menggunakan layanan Cloudflare sebagai perantara atau pelindung website |
| last-modified: Thu, 05 Nov 2026 21:17:41 GMT | Terakhir kali konten website dimodifikasi menurut informasi server |
| allow: GET, HEAD | Server menginformasikan bahwa metode HTTP yang diizinkan adalah GET dan HEAD |
| accept-ranges: bytes | Server mendukung permintaan sebagian file berdasarkan rentang byte |
| age: 11 | Konten yang diberikan oleh cache Cloudflare sudah tersimpan selama 11 detik |
| cf-cache-status: HIT | Cloudflare berhasil mengambil konten dari cache, sehingga tidak perlu mengambilnya kembali dari server asal |
| cf-ray: a580b2f2eb0dd042-SIN | ID unik untuk membantu pelacakan request di Cloudflare. SIN menunjukkan lokasi pusat data Singapura |
| alt-svc: h3=":443"; ma=86400 | Server mengiklankan dukungan HTTP/3 melalui port 443 selama 86.400 detik (24 jam) |

Penjelasan tambahan:
- -I berarti hanya mengambil HTTP response header.
- 200 berarti request berhasil.
- content-type menunjukkan jenis konten yang dikirim server.
- Berguna untuk mengecek status dan informasi server.

### Contoh 2 — Mengambil Data dari API
Perintah:
curl https://jsonplaceholder.typicode.com/posts/1

Input:
agama@Pili MINGW64 /d/bootcamp-seti/software/perkenalan-linux (P08)
$ curl https://jsonplaceholder.typicode.com/posts/1

Output:
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}

Penjelasan:
| Field | Penjelasan |
| --- | --- |
| userId: 1 | ID pengguna yang membuat postingan |
| id: 1 | ID unik dari postingan tersebut |
| title | Judul postingan |
| body | Isi atau konten postingan |

Penjelasan tambahan:
- Perintah tersebut mengirim HTTP GET request ke API.
- Server mengembalikan data dalam format JSON.
- Berguna untuk menguji API dan mengambil informasi dari server.

### Contoh 3 — Mengunduh File dari Internet
Perintah:
curl -o example.html https://example.com

Input:
agama@Pili MINGW64 /d/bootcamp-seti/software/perkenalan-linux (P08)
$ curl -o example.html https://example.com

Output:
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   577    0   577    0     0   2353      0 --:--:-- --:--:-- --:--:--  2384

Penjelasan:
| Bagian | Arti | Penjelasan |
| --- | --- | --- |
| % Total | Persentase total | Persentase keseluruhan data yang berhasil diproses |
| % Received | Persentase diterima | Persentase data yang berhasil diterima dari server |
| % Xferd | Persentase transfer | Persentase data yang berhasil ditransfer |
| Average Speed Dload | Rata-rata kecepatan download | Kecepatan rata-rata saat mengunduh data |
| Average Speed Upload | Rata-rata kecepatan upload | Kecepatan rata-rata saat mengunggah data |
| Time Total | Total waktu | Perkiraan waktu keseluruhan transfer |
| Time Spent | Waktu terpakai | Waktu yang sudah digunakan |
| Time Left | Sisa waktu | Perkiraan waktu yang dibutuhkan hingga selesai |
| Current Speed	| Kecepatan saat ini | Kecepatan transfer pada saat tersebut |

Penjelasan tambahan:
- -o digunakan untuk menentukan nama file hasil unduhan.
- example.html merupakan nama file yang akan disimpan.
- File akan disimpan di direktori tempat perintah dijalankan.

## 2. Kesalahan Umum dan Cara Menghindarinya

### Kesalahan umum
Tidak menggunakan tanda kutip pada URL dengan parameter tertentu

Contoh yang salah:
curl https://example.com/search?q=linux&sort=dat

### Mengapa salah?

Pada Linux CLI, karakter & memiliki fungsi khusus untuk menjalankan proses di background sehingga URL bisa terbaca secara tidak tepat.

### Cara menghindarinya:
curl "https://example.com/search?q=linux&sort=date"

Gunakan tanda kutip agar seluruh URL diperlakukan sebagai satu argumen.

## 3. Ringkasan Perintah CURL
Perintah	Kegunaan
curl -I URL	Melihat HTTP header
curl URL	Mengambil data dari server
curl -o file URL	Mengunduh dan menyimpan file
curl -X POST URL	Mengirim POST request
curl -L URL	Mengikuti redirect URL
curl -v URL	Melihat detail komunikasi request