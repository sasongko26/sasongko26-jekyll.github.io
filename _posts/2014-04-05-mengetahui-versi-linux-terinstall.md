---
layout: post
title: "Mengetahui Versi Linux Terinstall"
date: 2014-04-05 05:22:12
tags: blankon
---
Untuk mengetahui linux apa yang terinstall atau terpasang dapat menggunakan perintah
```
$ cat /etc/lsb-release 
DISTRIB_ID=Blankon 
DISTRIB_RELEASE=9.0 
DISTRIB_CODENAME=suroboyo 
DISTRIB_DESCRIPTION="BlankOn Suroboyo" 
```
atau
```
$ lsb_release -a 
No LSB modules are available. 
Distributor ID:Blankon 
Description:	BlankOn Suroboyo 
Release:	9.0 
Codename:	suroboyo
```
Dari hasil kedua perintah tersebut tampak distro yang terpasang adalah BlankOn rilis ke-9 dengan nama kode **suroboyo**.
