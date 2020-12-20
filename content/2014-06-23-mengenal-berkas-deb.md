---
layout: post
title: "Mengenal Berkas .deb"
date: 2014-06-23 23:02:12
tags: blankon
---
File atau berkas berekstensi deb adalah file paket installer debian dan turunannya. File deb adalah sejenis dengan file rpm pada keluarga redhat. 
Tatanama file deb

Contoh, penulis punya file **skype-debian_4.2.0.13-1_i386.deb**. Tatanama ini ada 3 informasi penting yang masing-masing dipisahkan tanda underscore.

**skype-debian_4.2.0.13-1_i386.deb**

```
Nama paketnya skype-debian.
Versinya 4.2.0.13-1.
Arsitekturnya, i386 untuk 32 bit atau amd64 untuk 64 bit.
```
 
# Menampilkan informasi file deb
Untuk mengetahui seluk beluk file deb gunakan dpkg -I

contoh

```
$ dpkg -I skype-debian_4.2.0.13-1_i386.deb
new debian package, version 2.0. 
 size 16308334 bytes: control archive=4855 bytes. 
      32 bytes,     1 lines      conffiles            
    1099 bytes,    20 lines      control              
   10411 bytes,   144 lines      md5sums              
 Package: skype 
 Version: 4.2.0.13-1 
 Section: non-free/net 
 Priority: extra 
 Architecture: i386 
 Depends: libasound2 (>= 1.0.16), libc6 (>= 2.3.6-6~), libc6 (>= 2.7), libgcc1 (>= 1:4.1.1), libqt4-dbus (>= 4:4.5.3), libqt4-network (>= 4:4.8.0), libqt4-xml (>= 4:4.5.3), libqtcore4 (>= 4:4.7.0~beta1), libqtgui4 (>= 4:4.8.0), libqtwebkit4 (>= 2.1.0~2011week13), libstdc++6 (>= 4.6), libx11-6, libxext6, libxss1, libxv1, libssl1.0.0, libasound2-plugins 
 Conflicts: skype-mid, skype-common, skype-bin 
 Replaces: skype-mid, skype-common, skype-bin 
 Installed-Size: 36483 
 Maintainer: Skype Technologies <info@skype.net> 
 Description: Wherever you are, wherever they are 
  Skype keeps you together. Call, see, message and share with others. 
   * It's free to download and join. 
   * Call, instant message and send photos and documents to anyone else on Skype. 
   * And with a webcam you can catch up face-to-face with a video call. 
   * Call mobiles and landlines worldwide at low rates. 
   * Easily text message anywhere in the world. 
   * Get your friends together on a conference call. 
  . 
  And that's just the start... 

```

# Memasang file deb
Sebelum memasang atau install, pastikan semua dependensi telah terinstall. Pemasangan gunakan sudo dpkg -i paket. Contoh

```
$ sudo dpkg -i skype-debian_4.2.0.13-1_i386.deb
```
Atau, kalau ingin memasang dengan mode grafis silahkan pakai aplikasi _gdebi_.
