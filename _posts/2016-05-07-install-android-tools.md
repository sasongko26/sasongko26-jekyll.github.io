---
layout: post
date: 2016-05-07
title: "Install Android Tools"
tags: 
- Slackware
- Android

---
Di catatan kemarin sudah saya sampaikan [cara install **sbopkg**]({% post_url 2016-05-03-install-sbopkg %}), nah sekarang adalah contoh cara menggunakan **sbopkg**, untuk install **Android Tools**.

Jalankan sebagai **root**
```
sbopkg
```
![](/gambar/sbopkg-android-tools-1.png)
Tersedia pilihan **Sync, Changelog, Packages, Updates, Browse, Search, Queue, Utilities, Help**.

Pilih <code>Search</code>

Masukkan kata kuncinya, misalnya <code>android</code>

![](/gambar/sbopkg-android-tools-2.png)

Kemudian akan muncul paket yang sesuai dengan kata kunci. Kemudian pilih paket yang diinginkan dengan <code>OK</code>.

![](/gambar/sbopkg-android-tools-3.png)

Keluar beraneka opsi. Alangkah baiknya baca-baca <code>README</code> atau <code>Info</code> dulu terutama untuk cek dependensi pada bagian <code>REQUIRE</code>

![](/gambar/sbopkg-android-tools-4.png)

![](/gambar/sbopkg-android-tools-5.png)

Setelah semua dependensi terpenuhi, silahkan lanjut, pilih <code>Process</code> kemudian <code>Install</code> lalu <code>Start</code>

![](/gambar/sbopkg-android-tools-6.png)

![](/gambar/sbopkg-android-tools-7.png)

Proses, download, build dan install dimulai. Silahkan tunggu. 

