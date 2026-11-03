# Buku Panduan Onboarding PT Sakura Soft

Selamat datang di tim! Buku ini ditulis bersama oleh karyawan baru. Tiap orang menulis satu bab tentang satu perintah Linux, lalu menggabungkannya ke buku ini.

## Cara berkontribusi

1. Clone repo ini pakai SSH.
2. Buat branch atas ID kamu: `git switch -c P07`
3. Tulis bab kamu di `docs/` sesuai tabel di bawah.
4. Commit minimal 3 kali, contoh pesan: `docs: add contoh ps aux`
5. Tambahkan link bab kamu di bawah judul **Daftar Isi**.
6. Merge ke `main`: `git switch main` → `git pull` → `git merge P07` → `git push`
7. Push ditolak? `git pull`, bereskan conflict, lalu push lagi. Dilarang `git push --force`.

## Pembagian topik

| ID | Topik | Nama file |
| --- | --- | --- |
| P01 | pwd, ls, cd | docs/P01-pwd-ls-cd.md |
| P02 | mkdir, cp, mv, rm | docs/P02-mkdir-cp-mv-rm.md |
| P03 | cat, head, tail, less | docs/P03-cat-head-tail.md |
| P04 | grep | docs/P04-grep.md |
| P05 | find | docs/P05-find.md |
| P06 | chmod, ls -l | docs/P06-chmod.md |
| P07 | ps, kill, top | docs/P07-ps-kill.md |
| P08 | curl | docs/P08-curl.md |
| P09 | tar, zip | docs/P09-tar-zip.md |
| P10 | export, .env | docs/P10-export-env.md |

## Isi tiap bab

- Judul dan satu kalimat kegunaan perintah
- 3 contoh perintah + output dari laptop kamu sendiri
- 1 kesalahan umum dan cara menghindarinya

## Daftar Isi
