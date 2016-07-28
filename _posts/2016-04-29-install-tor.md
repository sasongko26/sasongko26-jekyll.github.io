---
layout: post
date: 2016-04-29
title: "Install Tor Browser"
tags: 
- slackware
- blankOn
- tor
- firefox

---
[Tor Browser](http://torproject.org) adalah peramban web yang sangat memerhatikan privasi. Kita bisa mengakses web secara anonim/ _anonymous_ karena melewati jaringan Tor yang beraneka jalur.

Sebenarnya di [SBo](http://slackbuilds.org) sudah tersedia browser satu ini. Tapi sayang untuk versi **Slackware 14.1** _download link_-nya _expired_. _Tor Stable_ terbaru adalah versi 5.5.5 dan ini belum tersedia SBo resminya untuk Slackware. Jadi kita akan install mandiri. Tentu saja kita butuh koneksi internet untuk mengunduh berkasnya. Tor tersedia untuk Linux, Windows maupun Mac Os X, baik arsitektur 32 bit maupun 64 bit. Ini tidak hanya berlaku untuk Slackware tapi juga BlankOn. Di sini digunakan 64 bit. **Proses instalasi dengan bukan root**.

```
wget https://www.torproject.org/dist/torbrowser/5.5.5/tor-browser-linux64-5.5.5_en-US.tar.xz
tar xvJf tor-browser-linux64-5.5.5_en-US.tar.xz
./start-tor-browser.desktop
```


Kemudian muncul jendela pengaturan _network_ / jaringan. Gunakan saja pengaturan _default_ dari Tor, klik <code>Connect</code>

![](/gambar/tor-install.png)

Tunggu sebentar, koneksi ke jaringan Tor sedang disambungkan.

![](/gambar/tor-install-2.png)

Setelah tersambung, Tor siap digunakan. Harap perhatikan, jangan _maximize_ jendela Tor, karena kalau jendelanya di-_maximize_ bisa mengakibatkan kita kehilangan privasi karena posisi kita _browsing_ bisa terdeteksi.

![](/gambar/tor-siap.png)

Untuk menjalankan Tor, eksekusi file <code>start-tor-browser.desktop</code>. 

Dan perlu diperhatikan juga, **ada website yang memblokir diakses dari IP tertentu ataupun juga memblokir akses dari Tor**.
