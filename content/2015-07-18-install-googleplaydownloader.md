---
layout: post
title: "Install Google Play Downloader"
date: 2015-07-18
tags: 
- slackware
- python
- android

---
GooglePlayDownloader adalah aplikasi berantar muka grafis (GUI) untuk mengunduh berkas APK dari Google Play Store. Dependensi:
- python-protobuf (>=2.4)
- python-requests (>=0.12)
- python-ndg-httpsclient
- python-pyasn1
- python-wxgtk2.8 (>=2.8)
- python 2.5+
- java (opsional)

Itu yang tertulis di README.txt nya GooglePlayDownloader, tapi ternyata, khusus python-wxgtk2.8 diganti saja dengan wxpython. Oke kita install dependensinya dulu (pastikan tersambung internet).
```
easy_install protobuf requests ndg-httpsclient
```
Nah, karena wxpython diinstall dengan easy_install ga berhasil, maka install saja pakai [slackbuildnya]({% post_url 2015-07-18-install-wxpython %}).
Kemudian, unduh Google Play Downloadernya. Sebenarnya sih mau unduh dulu atau install dependensi dulu terserah. Sebenarnya ada .deb nya, tapi berhubung di sini pakai Slackware maka unduh aja [kode sumbernya](http://codingteam.net/project/googleplaydownloader/download/file/googleplaydownloader_1.7.orig.tar.gz) biar lebih asyik.

Selanjutnya, ekstrak
```
tar xzf googleplaydownloader_1.7.orig.tar.gz
```
Nah, sekarang tinggal eksekusi aja.
```
python googleplaydownloader/googleplaydownloader/googleplaydownloader.py
```
![](/gambar/googleplaydownloader.png)

