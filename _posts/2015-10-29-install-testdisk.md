---
layout: post
title: "Install Testdisk"
date: 2015-10-29
tags:
- slackware
- blankon
- forensik

---
Testdisk adalah salah satu aplikasi _digital_ forensik multiplatform. Bisa dijalankan di Windows (NT4, 2000, 2003, XP, Vista dan 7), Linux, FreeBSD, OpenBSD, NetBSD, SunOS, dan MacOS. Adapun kegunaannya untuk mengembalikan partisi yang terhapus beserta file-file yang ada di dalamnya. Informasi lebih lengkap tentang testdisk bisa didapatkan di [sini](http://www.cgsecurity.org/).

Sebenarnya untuk Slackware sudah ada _slackbuild_-nya, tapi tidak ada salahnya kalau install dari kode sumber. Penginstallan dijalankan dengan level root.
```
wget http://www.cgsecurity.org/testdisk-7.0.tar.bz2
tar xjvf testdisk-7.0.tar.bz2
cd testdisk-7.0 
./configure
make
make install
```
Oke, testdisk sudah diinstall. Untuk mulai menjalankannya (harus level root)
```
testdisk
```
![](/gambar/testdisk01.png)
