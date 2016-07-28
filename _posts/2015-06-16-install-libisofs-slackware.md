---
layout: post
title: "Install libisofs Slackware"
date: 2015-06-16
tags: slackware
---
Libisofs adalah pustaka untuk membuat filesystem ISO-9660. 

Berikut cara install libisofs-1.4.0 di slackware melalui slackbuild. Pastikan [tersambung internet]({% post_url 2015-04-01-install-wvdial-slackware %}) untuk mengunduh berkas yang diperlukan.

Unduh slackbuild libisofs
```
$ wget http://slackbuilds.org/slackbuilds/14.1/libraries/libisofs.tar.gz
```
Ekstrak
```
$ tar xzf libisofs.tar.gz
```
Terbentuk folder libisofs, pindah direktori ke folder itu kemudain unduh kode sumbernya.
```
$ cd libisofs
$ wget http://files.libburnia-project.org/releases/libisofs-1.4.0.tar.gz
```
Install slackbuildnya
```
# sh libisofs.SlackBuild
```
Install paketnya
```
# installpkg /tmp/libisofs-1.4.0-x86_64-1_SBo.tgz
```
Selesai.


