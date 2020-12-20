---
layout: post
date: 2019-06-09
title: Back Up Data HP Android
tags: [slackware, android]
---
Sebelum berganti ponsel atau HP sangat disarankan untuk mem-_back up_ data-data penting, seperti dokumen, foto, video, maupun chat _WhatsApp_. Berikut cara menyalin file dari HP android ke laptop yang tentu saja laptopnya bersistem operasi **Slackware**.

# Persiapan **Slackware**
Pastikan bisa menjalankan <code>adb</code> yang merupakan bagian dari <code>android tools</code>. Kalau belum bisa install dari SBo
# Mengapa adb?
Mengapa <code>adb</code>? Mengapa tidak pakai _file manager_ saja? Karena transfer pakai <code>adb</code> bisa lebih cepat
# Persiapan **Android**
Aktifkan mode **USB debugging** yang ada di _Settings_ --> _Developer options_. Apabila tidak ada bagian _Developer options_ aktifkan dulu dengan cara _Settings_ --> _About phone_. Tekan beberapa kali _Build number_ sampai muncul keterangan yang kurang lebih seperti ini "You are now a developer". Jangan lupa konfirmasi izin akses perangkat.
Pada HP tertentu mungkin akan diminta memasukkan IMEI terlebih dahulu sebagai _password_ untuk mengakses _Developer options_.
Dan, ingat-ingat lokasi penyimpanan file datanya. Dalam catatan kali ini ada di penyimpanan/memory internal (bukan memory external) di folder <code>pindah</code>.
# Next
Sambungkan kedua perangkat. Dari laptop kita gunakan <code>adb</code>

Pastikan perangkat telah siap digunakan. Cek apakah androidnya sudah siap
```bash
$ adb devices
List of devices attached
9H75BEO7W4UORSKF	device
```

Ok. Siap.

Kita pindahkan datanya ke _current working directory_
```bash
$ adb pull /storage/emulated/0/pindah/ .
```
Tunggu sampai selesai
