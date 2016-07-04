---
layout: post
title: "Install Xfburn Slackware"
date: 2015-06-17
tags: Slackware
---
Xfburn adalah aplikasi _burning_ CD/DVD/BD dari XFCE. Versi terbaru saat ini 0.5.4, dengan dependensi:

- Exo-0.10.6
- libxfce4util-4.12.1
- libisoburn-1.4.0

Tapi untuk memudahkan instalasi, kita gunakan saja yang versi 0.5.2 yang ada slackbuildnya, dependensinya
- [libburn]({% post_url 2015-06-16-install-libburn-slackware %})
- [libisofs]({% post_url 2015-06-16-install-libisofs-slackware %})

Untuk menginstall pastikan [tersambung internet]({% post_url 2015-04-01-install-wvdial-slackware %}) untuk mengunduh berkas.

```
$ wget http://slackbuilds.org/slackbuilds/14.1/system/xfburn.tar.gz
```
Ekstrak kemudian pindah direktori ke folder hasil ekstrak
```
$ tar xzf xfburn.tar.gz ; cd xfburn
```
Unduh kode sumber xfburn
```
$ wget http://archive.xfce.org/src/apps/xfburn/0.5/xfburn-0.5.2.tar.bz2
```
Install slackbuildnya
```
# sh xfburn.SlackBUild
```
Install paketnya
```
# installpkg /tmp/xfburn-0.5.2-x86_64-1_SBo.tgz
```
Selesai.





