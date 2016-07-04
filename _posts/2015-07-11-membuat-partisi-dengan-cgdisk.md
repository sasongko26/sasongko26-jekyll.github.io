---
layout: post
title: "Membuat Partisi dengan cgdisk"
date: 2015-07-11
tags: Slackware
---
_Partitioning_ atau pemartisian atau pembuatan partisi adalah pengetahuan yang harus dimiliki sebelum menginstall linux. Jika harddisk dianalogikan dengan rumah, maka partisi adalah kamar atau ruangan yang ada di dalam rumah itu. Kita bisa mengatur berapa jumlah kamar beserta ukuran dan fungsinya.

Skema partisi yang digunakan adalah GPT, bukan MBR, jadi pemartisian menggunakan cgdisk saja biar lebih mudah. Selain cgdisk bisa menggunakan gdisk. Sedangkan untuk MBR menggunakan cfdisk atau fdisk. Keempatnya berantarmuka text dan dijalankan oleh root. Oya, untuk antarmuka grafis (GUI) bisa menggunakan gparted.

```
cgdisk /dev/sda
```

Perintah cgdisk diikuti dengan disk yang akan dipartisi. Karena ini merupakan hardisk utama maka /dev/sda. Kalau harddisk external atau flashdisk tidak akan dikenal sebagai /dev/sda tetapi bisa jadi /dev/sdb.

Di hardisk yang saya gunakan ini, sudah ada beberapa partisi untuk berbagai keperluan (di sini dualboot Windows 8.1 dan Slackware 14.1). Mau buat 1 lagi.
![](/gambar/cgdisk-01.png)
Masih ada 4 partisi kosong. Yang akan dibuat partisi baru adalah yang ukuran 13.3GiB. Seluruh ukuran 13.3GiB ini akan kita gunakan untuk 1 partisi. Arahkan kursor padanya pilih [ New ]. Gunakan panah atas bawah untuk memilih partisi. Gunakan panah kanan kiri untuk menentukan opsi.

Isikan First sector, kalau ga mau ambil pusing biarlah default saja. Enter.
![](/gambar/cgdisk-02.png)
Isikan ukurannya atau Size in Sectors. Bisa dengan menuliskan dalam KB (K), MB (M), GB (G) atau TB (T). Bisa juga menulis sektornya. Di sini saya pakai default saja.
![](gambar/cgdisk-03.png)
Selanjutnya mengisikan filesystem. Karena mau saya pakai untuk slackware ya biarlah default Linux filesystem.
![](/gambar/cgdisk-04.png)
Selanjutnya, nama atau label partisinya. Silahkan isi sesuka hati atau biarkan kosong juga ga apa-apa.
![](/gambar/cgdisk-05.png)
Langkah selanjutnya adalah membuat partisi tadi secara resmi. Pilih [ Write ]. Awas, Write ini akan menghapus semua data yang ada di partisi itu. Kalau memang partisinya kosong ya ga masalah.
![](/gambar/cgdisk-06.png)
Karena pemartisian berisiko kehilangan data, kita akan dikonfirmasi lagi, yakin atau tidak? Ketik yes kalau akan melanjutkan proses, atau no untuk membatalkannya.
![](/gambar/cgdisk-07.png)
Partisi sudah jadi. Mungkin perlu restart untuk meresmikan partisi barunya. Tekan sembarang tombol untuk keluar dari cgdisk.
![](/gambar/cgdisk-08.png)

 
