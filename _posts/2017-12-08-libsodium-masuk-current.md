---
layout: post
date: 2017-12-08
title: "Libsodium Masuk -Current"
tags: [slackware, security]
---
Pada hari Rabu 6 Desember 2017 jam 14.13.48 UTC, Patrick Volkerding selaku BDFL **Slackware**, memberikan _update_ di kanal <code>-current</code>. Salah satunya adalah menambahkan <code>libsodium-1.0.15</code>. Libsodium merupakan _library_ atau pustaka untuk enkripsi, dekripsi, _signature_ (tanda tangan digital), dlsb.

Bagi saya, masuknya <code>libsodium</code> membawa konsekwensi untuk _rebuild_ <code>dnscrypt-proxy</code> yang menggunakan <code>libsodium</code>. <code>libsodium</code> yang sebelumnya adalah versi 1.0.13 dari [SBo](http://slackbuilds.org/repository/14.2/libraries/libsodium/) sedangkan versi baru dari _official_ **Slackware** 1.0.15. Hal ini diketahui dari gagalnya men-_start service_ <code>dnscrypt-proxy </code>.

```bash
/etc/rc.d/rc.dnscrypt-proxy start
/usr/sbin/dnscrypt-proxy: error while loading shared libraries: libsodium.so.18: cannot open shared object file: No such file or directory
```
