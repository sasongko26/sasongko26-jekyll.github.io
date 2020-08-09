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

Solusinya
```bash
echo "managed=true" >> /etc/NetworkManager/NetworkManager.conf
```
