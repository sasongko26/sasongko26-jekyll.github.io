---
layout: post
date: 2016-09-10
title: "Nonaktifkan Penghapusan Unduhan Slackpkg"
tags: [slackware, slackpkg]
---
Secara _default_, <code>slackpkg</code> akan menghapus semua file yang di- _download_ / unduh untuk melakukan install/upgrade paket segera setelah paket tersebut terinstall/upgrade. Ini terlihat dari file konfigurasinya yang terletak di <code>/etc/slackpkg/slackpkg.conf</code> pada baris 77

```bash
DELALL=on
```

Keuntungan dari konfigurasi ini menghemat _ruang harddisk_. Tapi saya lebih suka menonaktifkan fitur penghapusan ini. Jadi, pada bagian tersebut saya ubah <code>on</code> menjadi <code>off</code>.
