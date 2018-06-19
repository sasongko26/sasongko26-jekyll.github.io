---
layout: post
date: 2018-06-19
title: Mencoba Manokwari
tags: [slackware, desktop environment]
---

Beberapa waktu yang lalu mencoba install [**manokwari**](http://manokwari.blankonlinux.or.id) dan berhasil dengan beberapa kekurangan.

Proses install berjalan lancar walau sempat terhambat sebentar. Apalagi kalau bukan karena dependensi. Untuk _compile_ menggunakan <code>meson</code> yang disediakan Pengembang dan prosesnya lebih cepat. Oiya, ini saya hanya lakukan di slackware64-current. 

Tentang dependensi, saya bagi menjadi 3 bagian.

1. Sudah terinstall secara default atau tersedia di _official repo_ Slackware
   - meson
   - glib2
   - gtk+3
   - atk
   - cairo
   - x11
   - libnotify

2. Tersedia di SBo
   - vala
   - libgee1
   - gnome-common
   - gnome-menus
   - libwnck3
   - libunique3
   - geoclue2
   - webkitgtk3

3. _build_ sendiri
   - libwebp5
   - icu4c56

libwebp dan icu4c sebenarnya sudah tersedia untuk current tetapi dengan versi yang lebih tinggi dari yang disyaratkan. Sementara itu webkitgtk3 yang tersedia masih versi 2.4.11 yang berhubungan dengan <code>.so</code> lawas dari libwebp dan icu4c. Mau _build_ sendiri webkitgtk3 terbaru diperkirakan akan butuh waktu yang lama. Jadi libwebp dan icu4c akhirnya _build_ sendiri. libwebp pakai versi 0.4.3 tetapi nama paket menjadi libwebp5 agar tidak bentrok dengan libwebp versi _official_. Begitu juga icu4c pakai versi 56_1 nama paket jadi icu4c56.

Setelah install timbul masalah. Kemungkinan timbul karena tidak menginstall gnome-session, gnome-settings-daemon, gnome-desktop.

1. Logout, shutdown, reboot melalui menu tidak berfungsi
2. Tidak ada tombol minimize, maximize dan close pada window aplikasi
3. Settings tidak berfungsi
4. Lockscreen tidak berfungsi
5. Kursor/pointer tidak muncul
6. Tidak bisa pindah workspace

Sementara itu dulu, mungkin masih banyak masalah lain. Insyaallah kapan-kapan kalau sempat dioprek lagi.

![](https://raw.githubusercontent.com/sasongko26/manokwari-slackbuild/master/screenshot/Screenshot_2018-06-17_07-21-19.png)

![](https://raw.githubusercontent.com/sasongko26/manokwari-slackbuild/master/screenshot/Screenshot_2018-06-17_07-22-13.png) 
