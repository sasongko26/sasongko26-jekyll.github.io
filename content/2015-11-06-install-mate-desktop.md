---
layout: post
title: "Install Mate Desktop"
date: 2015-11-06
tags: 
- slackware
- desktop environment
- mate

---
Walaupun _desktop environment_ resmi Slackware adalah KDE dan Xfce, kita tetap bisa menggunakan DE lain, _mate_ contohnya. _Mate_ punya tampilan menarik tapi tetap ringan. Installnya mudah kok, seperti biasa pakai slackbuilds. Pastikan tersambung internet untuk mengunduh berkasnya, oya kita butuh kira-kira 500 MB untuk download _mate_.

Pertama, dengan peramban web buka [github mate slackbuilds](https://github.com/mateslackbuilds/msb). Nah, karena di sini menggunakan 14.1 (bukan _current_) maka pilih _branch_ 14.1-mate-1.10. Setelah itu unduh tarball/zipnya kemudian ekstrak. Atau bisa juga git nya di-_clone_.

Selanjutnya, pindah ke direktori root dari msb itu. Kemudian install (dengan _root privileges_) dependensi yang dibutuhkan (baris 1), install base dari mate itu sendiri (baris 2) dan kalau perlu bisa juga install paket extra (baris 3).

```
sh mate-build-deps.sh
sh mate-build-base.sh
sh mate-build-extra.sh
```

Nah, _mate_ sudah terinstall. Jangan lupa untuk [mengaktifkannya]({% post_url 2015-11-06-ganti-de %}).

Inilah contoh penampakannya.
![](/gambar/mate-desktop.png)

