---
layout: post
title: "Unduh ISO Slackware Current"
date: 2015-08-01
tags: slackware
---
Slackware adalah distro yang istimewa. Tak seperti distro lainnya yang menyediakan ISO versi terbaru atau _current_ yang masih dalam pengembangan, slackware tidak merilis _current ISO_ secara resmi. Walaupun demikian, ada yang menyediakannya bagi yang berminat, salah satunya bisa didapatkan di repo ftp://ftp.slackware.no.

Kali ini coba mengunduh _slackware current ISO_. Pakai _rsync_ saja yang gampang dan bisa dilanjut kalau internetnya putus.

Sebelumnya cek dulu ISO terbaru
```
$ rsync ftp.slackware.no::slackware/slackware-iso/slackware-current-iso/
 
drwxr-xr-x          4,096 2015/07/28 10:00:29 .
-rw-r--r--            146 2015/07/28 10:00:29 CHECKSUMS.md5
-rw-r--r--        146,519 2015/07/18 02:38:53 ChangeLog-current.txt
-rw-r--r--        146,370 2015/07/18 02:38:53 ChangeLog64-current.txt
-rw-r--r--            371 2015/07/28 10:00:29 README.TXT
-rw-r--r--  2,703,075,328 2015/07/28 10:00:11 slackware-current-28_Jul_2015-DVD.iso
-rw-r--r--  2,633,039,872 2015/07/28 10:00:15 slackware64-current-28_Jul_2015-DVD.iso
```
ISO terbaru tertanggal 28 Juli 2015.

Selanjutnya lakukan rsync (pastikan berada di direktori di mana file ISOnya disimpan).
```
$ rsync -avz --progress --partial ftp.slackware.no::slackware/slackware-iso/slackware-current-iso/slackware64-current-28_Jul_2015-DVD.iso .
```
Silahkan tunggu sampai selesai.
