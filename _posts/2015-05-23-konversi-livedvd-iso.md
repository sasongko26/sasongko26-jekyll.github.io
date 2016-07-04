---
layout: post
title: "Mengubah LiveDVD Menjadi ISO"
date: 2015-05-23
tags: 
- Slackware
- BlankOn
- Forensik

---
Beberapa waktu lalu lihat DVD BlankOn 8 Rote nganggur di seonggok kumpulan CD/DVD. Enaknya diapain ya itu DVD? Kalau dibiarkan khawatirnya kotor malah ngga bisa digunakan lagi. Ya udah mending dibuat file ISO aja. Kalau dibuat file ISO insya Allah manfaatnya lebih banyak karena tersimpan di hardisk bisa lebih tahan lama daripada dalam bentuk DVD, dan suatu saat nanti kalau dibutuhkan tapi DVDnya ngga bisa dipakai tinggal dibakar aja ISOnya entah itu jadi DVD atau ke flashdisk. Jadi misalnya besok mau install BlankOn Rote ke netbook ga usah download lagi ISOnya cukup jadikan liveUSB aja.

Caranya?

```
$ dd if=/dev/cdrom of=~/rote-i386.iso
```

if adalah input file, di sini /dev/cdrom adalah DVDnya, harap disesuaikan, bisa jadi di komputer Anda berbeda, misalnya /dev/sr0 atau /dev/sr1 atau yang lainnya.

of adalah file iso yang akan dibuat. Terserah mau diletakkan di mana.

*Atau*, bagi pengguna KDE bisa menggunakan K3B. Buka K3B melalui menu, pastikan DVD sudah terdeteksi (lihat di sisi kiri, di sini DVDnya berlabel _blankon_). Klik medium atau DVDnya kemudian klik _Copy Medium..._ 

![](/gambar/k3b-copy-medium.png)

Muncul kotak dialog. Perhatikan tab *Options* centang _Only create image_ karena hanya akan membuat image/ISOnya saja.

![](/gambar/k3b-only-create-image.png)

Kemudian klik tab *Image*. Silahkan tulis lokasi penyimpanan ISOnya. kemudian klik *Start*.

![](/gambar/k3b-lokasi-image.png)

Tunggu beberapa saat.

![](/gambar/k3b-create-iso-sukses.png)

DVD sudah berhasil dijadikan file ISO. Alhamdulillah.
