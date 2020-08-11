---
layout: post
date: 2020-08-07
title: NetworkManager device not ready
tags: [slackware, networking, network manager]
---
Baru beberapa hari memakai (lagi) **NetworkManager**, sudah bermasalah (lagi).
```bash
device not ready
```
![](/gambar/networkmanager-device-not-ready.png)

begitulah....

Padahal _network interface_-nya terdeteksi semua dengan benar seperti biasanya jaman tidak pakai **NetworkManager**.
Solusinya dari berbagai referensi (lupa mencatat linknya)
```bash
echo "managed=true" >> /etc/NetworkManager/NetworkManager.conf
```

Tapi, ternyata ini kemudian munculkan _warning_ di **syslog**
```bash
Aug  9 12:04:53 localhost NetworkManager[1047]: <warn>  [1596949493.8398] config: unknown key 'managed' in section [main] of file '/etc/NetworkManager/NetworkManager.conf
```
Ya sudah, kembalikan saja ke aslinya, dan restart (entah berapa kali restart sampai normal). Sampai sekarang belum terjadi lagi (dan semoga tidak akan terjadi lagi. Saya lelah dengan kerewelan **NetworkManager**).
