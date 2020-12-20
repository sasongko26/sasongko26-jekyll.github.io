---
layout: post
title: "Mount ISO Image"
date: 2015-12-26
tags: 
- slackware
- blankon

---
Mempunyai berkas citra ISO/ISO image ada manfaatnya. Pertama, sebagai cadangan kalau FD/DVD installernya tidak dapat digunakan. Kedua, untuk melakukan remaster. 
Bagaimana caranya mengetahui isi dari ISO tersebut? Paket apa saja yang ada di dalamnya? Untuk distro tertentu seperti slackware misalnya, paket yang disertakan bisa dilihat dengan mudah dari ISO tanpa harus membakarnya. Kita mount saja ISOnya.

Misalkan berkas ISO yang akan di mount adalah slackware64-14.1-install-dvd.iso, dan akan di-mount di /mnt/iso
```
mount -o loop slackware64-14.1-install-dvd.iso /mnt/iso
```
ISO sudah dimount. Untuk selanjutnya mau diapakan nggih monggo. 
  
