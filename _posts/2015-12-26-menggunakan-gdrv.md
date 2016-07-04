---
layout: post
title: "Cara Menggunakan gdrv"
date: 2015-12-26
tags: 
- Slackware
- BlankOn

---
gdrv adalah salah satu _command line interface tool_ berbasis python untuk **Google Drive**. Cara menginstallnya silahkan buka [catatan ini]({% post_url 2015-07-26-install-gdrv %}). Adapun cara penggunaannya adalah sebagai berikut:

```
$ gdrv -h
usage: gdrv [-h] [-v] [-w] [-V]
            {ftp,pull,search,url,push,mkdir,share,trash,list,init} ...

YMK google drive command line tool

positional arguments:
  {ftp,pull,search,url,push,mkdir,share,trash,list,init}
                        drive sub command
    ftp                 interactive mode like sftp, lftp
    pull                command pull help
    search              command search help
    url                 command url help
    push                command push help
    mkdir               command mkdir help
    share               command share help
    trash               command trash help
    list                command list help
    init                command init help

optional arguments:
  -h, --help            show this help message and exit
  -v, --verbose         increse verbosity/logging level
  -w, --write-config    write a default config
  -V, --version         show version infomation
```



Pertama, inisiasi dulu, 
```
$ gdrv init
Enter verrification code in url https://www.google.com/device: ZPNG-WBVQ
Then press any key to continue...
```

Kemudian akan terbuka peramban web untuk masuk/login ke akun google jika belum masuk. Setelah itu akan muncul laman untuk memasukkan kode verifikasi. Masukkan kode verifikasi tersebut.

![](/gambar/gdrv-code.png)

Setelah diklik _Next_ akan muncul permintaan ijin/_permissions_. Kalau setuju klik _Allow_.

![](/gambar/gdrv-permission.png)

Selanjutnya akan muncul konfirmasi dari Google untuk melanjutkan.

![](/gambar/gdrv-return.png)

Berikutnya, kembali ke terminal, proses initnya masih menggantung. Untuk melanjutkan atau menyelesaikan inisiasi tekan sembarang tombol. Kemudian muncul output yang menginformasikan username, ID root folder, kapasitas total dan pemakaian, seperti ini.
```
Current user name: Sasongko 
Root folder ID: 0ALo7yI_gNQVRUk2ABS
Total quota (bytes): 16106127360
Used quota (bytes): 68240901
```

Untuk menampilkan file apa saja yang ada di akun google drive kita
```
$ gdrv list /
```

Untuk membuat direktori atau folder baru 
```
$ gdrv mkdir /nama_direktori
```

Upload/unggah file ke direktori root dari google drive.
```
$ gdrv push nama_file_di_komputer_yang_akan_diupload /
```

Download/unduh 
```
$ gdrv pull /direktori_file/nama_file_yang_akan_didownload
```

Hapus
```
$ gdrv trash /file_atau_direktori_yang_akan_dihapus
``` 

Argumen ftp yang interaktif.
```
$ gdrv ftp
gdrv> 
```

Untuk mengetahui _command_ apa saja yang bisa digunakan melalui mode ftp ini, ketik help
```
gdrv> help

Documented commands (type help <topic>):
========================================
help

Undocumented commands:
======================
EOF  exit  lcd  lpwd  mkdir  push  share  url
cd   init  lls  ls    pull   pwd   trash

```

EOF dan exit digunakan untuk mengakhiri/menutup gdrv.

lcd diikuti dengan nama_direktori digunakan untuk berpindah ke direktori yang dituju. Direktori di sini adalah direktori yang ada di komputer.

lpwd untuk mengetahui saat ini berada di direktori apa (komputer).

mkdir untuk membuat direktori baru di server/akun google drive.

push untuk upload.

share untuk berbagi file.

url untuk mendapatkan alamat url file.

cd berpindah direktori di google drive.

init untuk inisiasi.

lls untuk menampilkan isi direktori komputer.

ls untuk menampilkan isi direktori google drive.

pull untuk unduh file.

pwd untuk mengetahui direktori google drive saat ini.

trash untuk menghapus file.


