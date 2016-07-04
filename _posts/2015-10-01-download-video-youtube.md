---
layout: post
title: "Download Video Youtube"
date: 2015-10-01
tags: 
- Slackware
- Multimedia

---
Download video dari _Youtube_ adalah hal yang mudah bagi pengguna _Slackware_. Paling tidak ada 2 cara. Cara pertama menggunakan peramban web, dan cara kedua menggunakan _youtube-dl_ yang berantar muka teks. Di sini menggunakan cara kedua. Untuk menginstall _youtube-dl_ silahkan [klik di sini]({% post_url 2015-10-01-install-youtubedl %}).

Cara menggunakannya
```
youtube-dl url_video_youtube
```
Contoh, akan URL video yang akan di download adalah https://www.youtube.com/watch?v=lGRQIBJ5FBE&index=1&list=PLB9F411241A111B54.
```
youtube-dl https://www.youtube.com/watch?v=lGRQIBJ5FBE&index=1&list=PLB9F411241A111B54
```
Kalau ada beberapa video yang ingin didownload, masukkan saja URLnya ke satu file, tiap baris 1 URL, kemudian cara downloadnya tambahkan opsi -a
```
youtube-dl -a file
```
Untuk keterangan lainnya tentang _youtube-dl_ silahkan
```
youtube-dl --help 
```
