---
layout: post
title: "Setting Internet XL Slackware"
date: 2015-08-17
tags: slackware
---
Di [catatan yang lalu]({% post_url 2015-06-28-konek-internet-menggunakan-pppsetup %}) telah kami sampaikan cara konek internet di Slackware dengan modem, ppp, dan internet provider atau operator Tri. Kali ini akan kami ganti dengan operator XL.

Sunting berkas /etc/ppp/options
```
# General configuration options for PPPD:
lock
defaultroute
noipdefault
modem
/dev/ttyUSB0
460800
crtscts
# Uncomment the line below for more verbose error reporting:
#debug
# If you have a default route already, pppd may require the other side
# to authenticate itself, which most ISPs will not do.  To work around this,
# uncomment the line below.  Note that this may have negative side effects
# on system security if you allow PPP dialins.  See the docs in /usr/doc/ppp*
# for more information.
#noauth
passive
asyncmap 0
name "3data"
```

Baris 19, ganti "3data" dengan "internet".

Kemudian sunting /etc/ppp/pap-secrets
```
# PAP authentication file: /etc/ppp/pap-secrets
# This file should have a permission of 600.
# ~# chmod 600 /etc/ppp/pap-secrets
# Username      Server      Password      IP addresses
"3data"   *   "3data"
```
Baris 5, ganti

> "3data"   *   "3data"

dengan

> *    *    *

Selesai. Silahkan sambungkan internet dengan hak akses root
```
ppp-go
```


