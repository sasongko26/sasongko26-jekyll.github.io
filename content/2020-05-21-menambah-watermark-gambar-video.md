---
layput: post
date: 2020-05-24
title: Menambah watermark gambar ke video dengan ffmpeg
tags: [slackware, multimedia]
---

Misalkan kita akan memberikan _watermark_ berupa gambar logo.png ke video ramadhan.mkv. _Watermark_ ditempatkan di pojok kiri bawah. Video dengan _watermark_ diberi nama ramadhan-fix.mkv

```bash
ffmpeg -i ramadhan.mkv -i logo.png -filter_complex "overlay=x=0:y=(main_h-overlay-h)" ramadhan-fix.mkv
```
Keterangan opsi dan parameternya
```bash
-filter_complex : menggunakan filter yang kompleks
overlay : menambahkan watermark
x : posisi pada sumbu x, dihitung dari ujung kiri
y : posisi pada sumbu y, dihitung dari ujung atas
main_h : tinggi video
main_w : lebar video
overlay_h : tinggi gambar yang akan dijadikan watermark
overlay_w : lebar gambar yang akan dijadikan watermark
```
