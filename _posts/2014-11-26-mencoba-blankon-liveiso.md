---
layout: post
title:  "Booting BlankOn LiveISO"
date:   2014-11-26 11:30:51
tags: blankon
---
Bagi yang ingin menggunakan BlankOn, ada baiknya mencoba BlankOn dulu tanpa memasangnya. Percobaan ini biasanya disebut dengan istilah live. Umumnya percobaan ini menggunaan sarana atau media berupa DVD sehingga muncullah istilah livedvd, atau flashdisk yang kemudian memunculkan liveusb. Bisakah kita live tanpa dvd maupun usb? Bisa saja, asal kita punya ISO-nya. Kita akan me-live langsung dari komputer atau laptop yang sudah terpasang BlankOn atau distro linux lainnya. Dengan ini kita ga perlu repot membakar ISOnya ke DVD atau membuat liveusb segala. Cukup boot ISOnya.

Misalnya, kita punya berkas ISO BlankOn yang sudah diunduh dengan nama berkasnya suroboyo-desktop-i386.iso disimpan di /home/sasongko/Unduhan.
Agar bisa booting dari berkas ISO tersebut, kita harus ubah dulu konfigurasi grub. Sebelum mengubah jangan lupa berkas konfigurasi yang asli disalin dulu.
```
$ sudo cp /boot/grub/grub.cfg /boot/grub/grub.cfg.asli
```
Nama berkas baru hasil salinan beserta lokasi tujuannya terserah. Dalam contoh ini nama barunya adalah grub.cfg.asli di /boot/grub/grub.
Langkah berikutnya, sunting berkas grub.cfg. Silahkan gunakan teks editor kesayangan masing-masing, bisa nano, pico, gedit, leafpad, kwrite, dll. Yang digunakan di sini adalah sublime text. Tidak ada alasan khusus mengapa sublime text, cuma lagi pengen aja.
```
$ sudo sublime /boot/grub/grub.cfg
```
Kemudian, cari ```### END /etc/grub.d/10_linux ###```
Di atas baris tersebut tulis seperti ini:
```
menuentry 'BlankOn Live' { 
  set isofile='/home/sasongko/Unduhan/suroboyo-desktop-i386.iso' 
  loopback loop $isofile 
  linux (loop)/boot/vmlinuz boot=live findiso=${isofile} config quiet splash 
  initrd (loop)/boot/initrd.img 
}
```

Simpan dan perbarui grubnya.
```
$ sudo update-grub
```
Untuk mencobanya, silahkan restart dan ketika muncul grubnya pilih **BlankOn Live**.
Selamat Mencoba!
