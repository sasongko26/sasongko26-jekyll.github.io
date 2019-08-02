---
layout: post
date: 2019-08-03
title: "Restart android via adb"
tags: [slackware, android]
---
Catatan kali ini masih seputar _troubleshoot_ HP android dengan komputer terutama **Slackware**.

Tadi malam, HP yang OS android _touchscreen_-nya tidak ada respon. Di semua bagian layar. Tapi tombol power dan volume masih berfungsi. Begitu juga dengan konektivitas internet maupun telepon. Mau mencoba di-_restart_, tombol power normal tapi untuk memilih _shutdown_ atau _reboot_ tidak bisa karena _tochscreen_-nya tidak ada respon. Lepas baterai? Tidak bisa karena baterainya tanam.

Solusinya? _restart_ via komputer. Pastikan sudah terinstall _andorid tools_ (tersedia di SBo).

Cek dulu apakah HP nya terdeteksi
```bash
$ adb devices
List of devices attached
* daemon not running; starting now at tcp:5037
* daemon started successfully
9H75BEO7W4UORSKF	device
```

Ok. Lanjut _restart_
```bash
$ adb reboot
```
 
