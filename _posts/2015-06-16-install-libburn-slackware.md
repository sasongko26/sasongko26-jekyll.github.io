---
layout: post
title: "Install libburn Slackware"
date: 2015-06-16
tags: Slackware
---
Libburn adalah pustaka (_library_) untuk menulis ke CD, DVD, dan _blueray_.

Berikut langkah-langkah installnya di slackware melalui slackbuild. Adapun versi libburn yang diinstall adalah 1.4.0.

Pertama, pastikan [tersambung internet]({% post_url 2015-04-01-install-wvdial-slackware %}) untuk mengunduh paket. Kemudian unduh slackbuild libburn.
```
$ wget http://slackbuilds.org/slackbuilds/14.1/libraries/libburn.tar.gz
```
Ekstrak
```
$ tar xzf libburn.tar.gz
```
Akan terbentuk folder libburn. Pindah direktori ke folder itu.
```
$ cd libburn
```
Kemudian unduh kode sumber libburn.
```
$ wget http://files.libburnia-project.org/releases/libburn-1.4.0.tar.gz
```
Install slackbuildnya
```
sh libburn.SlackBuild
```
Install paketnya
```
# installpkg /tmp/libburn-1.4.0-x86_64-1_SBo.tgz
```
