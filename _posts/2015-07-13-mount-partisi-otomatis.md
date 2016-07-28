---
layout: post
title: "Mount Partisi Otomatis"
date: 2015-07-13
tags: 
- slackware
- blankOn

---
Masih melanjutkan catatan yang kemarin tentang pemartisian. Setelah [membuat partisi]({% post_url 2015-07-11-membuat-partisi-dengan-cgdisk %}) kemudian [diformat]({% post_url 2015-07-12-memformat-partisi %}), langkah selanjutnya adalah memutuskan apakah partisi itu akan di-_mount_ secara otomatis saat _boot_ atau tidak.

Nah, karena partisi /dev/sda9 yang bersistem ext4 kemarin akan saya jadikan sebagai tempat _source code_ paket/aplikasi, seperti untuk menyimpan berkas _slackbuild_, saya putuskan untuk mengaitkannya secara otomatis di /usr/local/src. Caranya adalah dengan menambahkan baris berikut ke /etc/fstab
```
/dev/sda9	 /usr/local/src	  ext4        defaults         1   2
```
