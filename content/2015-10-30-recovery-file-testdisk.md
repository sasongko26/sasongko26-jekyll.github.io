---
layout: post
title: "Mengembalikan File yang Terhapus dengan Testdisk"
date: 2015-10-30
tags: 
- slackware
- forensik
- blankon
---
Melanjutkan [catatan kemarin]({% post_url 2015-10-29-install-testdisk %}), kali ini adalah cara menggunakan testdisk untuk mengembalikan/memulihkan/_recovery_ file yang terhapus. Misalkan dipunyai Flashdisk Toshiba berkapasitas 15 GB yang secara tak sengaja terhapus semua file yang di dalamnya.

Sebagai root jalankan
```
testdisk
```
kemudian akan muncul deskripsi tentang testdisk dan tawaran apakah akan membuat file log atau tidak. Di sini saya pilih _No Log_ karena merasa log ini tidak terlalu penting.
![](/gambar/testdisk01.png)

Selanjutnya akan terdeteksi media simpan yang terpasang di komputer. Di sini flashdisknya terdeteksi sebagai /dev/sdc.
![](/gambar/testdisk02.png)
pilih Disk /dev/sdc kemudian _Proceed_ untuk melanjutkan.

Kemudian akan terdeteksi jenis partisinya. Di sini partisinya adalah Intel/PC Partition.
![](/gambar/testdisk03.png)

Kemudian muncul berbagai opsi, pilih _Advanced_
![](/gambar/testdisk04.png)

Selanjutnya, terlihat bahwa flashdisk ini hanya mempunyai 1 partisi dengan tipe FAT32
![](/gambar/testdisk05.png)
Pilih _Undelete_. Gunakan panah kanan kiri untuk berpindah opsi.

Akan muncul file dan foldernya.
![](/gambar/testdisk06.png)
Gunakan panah kanan untuk membuka folder, q untuk keluar, : untuk menandai file yang dipilih, a untuk memilih semua file, C untuk menyalin semua file terpilih, c untuk menyalin file yang terpilih saat itu saja.
Karena akan mengembalikan semua file, maka pilih a, kemudian C.

Akan muncul tawaran di mana file akan disalin ke mana.
![](/gambar/testdisk07.png)

Silahkan gunakan tanda panah untuk berpindah direktori, setelah ketemu atau mantap lokasinya tekan C untuk mulai menyalin.
![](/gambar/testdisk08.png)

Penyalinan sukses, tak ada 1 file pun yang gagal disalin/dipulihkan.
![](/gambar/testdisk09.png)

Setelah selesai, tekan q, kemudian _Quit_
![](/gambar/testdisk10.png)
![](/gambar/testdisk11.png)
![](/gambar/testdisk12.png)
  
