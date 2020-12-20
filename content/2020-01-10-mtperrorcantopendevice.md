---
layout: post
date: 2020-01-10
title: MtpErrorCantOpenDevice
tags: [slackware, android]
---
Ketika akan memindahkan data dari HP android ke laptop melalui <code>thunar</code>, menunggu lama dan berujung gagal. Setelah dicek dengan mencoba melalui <code>jmtpfs</code>

```bash
$ jmtpfs
Device 0 (VID=0e8d and PID=201d) is a MediaTek Inc Elephone P8000.
error returned by libusb_claim_interface() = -6LIBMTP PANIC: Unable to initialize device
terminate called after throwing an instance of 'MtpErrorCantOpenDevice'
  what():  Can't open device
Aborted
```

Ada masalah di <code>libusb</code>. Coba reinstall <code>libusb</code>

```
# slackpkg reinstall libusb
```

Alhamdulillah sukses. 

