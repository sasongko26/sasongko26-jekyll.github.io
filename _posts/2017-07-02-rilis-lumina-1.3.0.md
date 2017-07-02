---
layout: post
date: 2017-07-02
title: "Rilis Lumina 1.3.0"
tags: [slackware, desktop environment, lumina]
---
Di suasana Idul Fitri, 26 Juni 2017, Ken Moore selaku _project leader_ <code>Lumina</code> mengumumkan perihal rilisnya **Lumina Desktop 1.3.0**. Selang 4 hari kemudian dirilis _patch_ yang pertama untuk 1.3.0. Catatan rilis resmi silahkan dibaca [di sini](https://lumina-desktop.org/version-1-3-0-released/).
  
Mungkin saja Moore tidak peduli dengan Idul Fitri, tapi bagi saya rilis kali ini tergolong istimewa. Mulai versi 1.3.0 ini <code>lumina</code> semakin powerfull untuk digunakan di <code>Slackware</code>. Sampai dengan versi 1.2.0_p1 (1.2.0 patchset 1), <code>Restart</code> dan <code>Power Off</code> pada menu sama sekali tidak berfungsi. Namun mulai 1.3.0 <code>reboot</code> dan <code>shutdown</code> sudah bisa dijalankan melalui menu.

Sehubungan dengan rilis tersebut, bagi mereka yang berminat, sudah saya buatkan <code>slackbuild</code> untuk <code>lumina</code>. Insya Allah besok sabtu 8 Juli 2017 <code>lumina</code> versi <code>1.3.0_p1</code> sudah tersedia di [SBo](https://slackbuilds.org).

Oh iya, jika kompilasi menggunakan <code>gcc 7</code> sebagaimana yang digunakan di <code> Slackware current</code> silahkan kompilasi dengan opsi berikut :

```bash
QMAKE_CFLAGS_ISYSTEM= ./lumina.SlackBuild
```

Masukan, kritik, saran, perbaikan dipersilahkan.
