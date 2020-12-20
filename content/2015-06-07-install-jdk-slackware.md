---
layout: post
title: "Install JDK Slackware"
date: 2015-06-07
tags: slackware
---
_Java Development Kit_ atau yang biasa disingkat JDK ini berguna untuk membuat/mengembangkan aplikasi berbasis Java. Selain itu, untuk menginstall dan/atau menjalankan aplikasi tertentu disyaratkan JDK, seperti _LibreOffice_, _Netbeans_ dan _Aptana_. Sebelum install kita unduh dulu dari http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html .

Karena _Slackware_ yang digunakan adalah 64 bit maka pilih untuk yang LInux x64 format rpm.

![](/gambar/install-jdk-1.png)

Untuk bisa mengunduh harus menyetujui perjanjian lisensi dulu (_Accept License Agreement_).

Kemudian pindahkan hasil unduhan ke /usr/local/src dilanjutkan dengan pindah ke direktori /usr/local/src
```
# rpm2tgz jdk-8u45-linux-x64.rpm
# installpkg /usr/local/src/jdk-8u45-linux-x64.tgz
```

JDK sukses terinstall.

