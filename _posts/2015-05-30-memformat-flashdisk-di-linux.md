---
layout: post
title: "Memformat Flashdisk di LInux"
date: 2015-05-30
tags: 
- Slackware
- BlankOn
- Terminal

---
Memformat flashdisk di linux adalah hal yang mudah. 

Pertama, pastikan flashdisknya terdeteksi oleh sistem. Pada kesempatan ini merk flashdisknya adalah Toshiba.

```
$ lsusb
Bus 001 Device 003: ID 0930:1400 Toshiba Corp. Memory Stick 2GB
Bus 001 Device 002: ID 04f2:b483 Chicony Electronics Co., Ltd 
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
```
Perhatikan baris 2, flashdisk terdeteksi. Untuk lebih meyakinkan lagi, sekaligus mengetahui flashdisk ini diperlakukan sebagai apa oleh sistem, segera setelah flashdisk ditancapkan, 
```
$ su
Password:
# dmesg | tail -20
[  842.096153] usb 1-2: new high-speed USB device number 4 using xhci_hcd
[  842.113907] usb 1-2: New USB device found, idVendor=0930, idProduct=1400
[  842.113930] usb 1-2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[  842.113946] usb 1-2: Product: TOSHIBA USB DRV
[  842.113959] usb 1-2: Manufacturer: TOSHIBA
[  842.113973] usb 1-2: SerialNumber: 07B60907914CACE7
[  842.114961] usb-storage 1-2:1.0: USB Mass Storage device detected
[  842.116210] scsi5 : usb-storage 1-2:1.0
[  843.154056] scsi 5:0:0:0: Direct-Access     TOSHIBA  TOSHIBA USB DRV  PMAP PQ: 0 ANSI: 0 CCS
[  843.908583] sd 5:0:0:0: [sdb] 7823360 512-byte logical blocks: (4.00 GB/3.73 GiB)
[  843.909766] sd 5:0:0:0: [sdb] Write Protect is off
[  843.909786] sd 5:0:0:0: [sdb] Mode Sense: 23 00 00 00
[  843.910861] sd 5:0:0:0: [sdb] No Caching mode page found
[  843.910877] sd 5:0:0:0: [sdb] Assuming drive cache: write through
[  843.915571] sd 5:0:0:0: [sdb] No Caching mode page found
[  843.915587] sd 5:0:0:0: [sdb] Assuming drive cache: write through
[  843.948245]  sdb: sdb1
[  843.951693] sd 5:0:0:0: [sdb] No Caching mode page found
[  843.951714] sd 5:0:0:0: [sdb] Assuming drive cache: write through
[  843.951737] sd 5:0:0:0: [sdb] Attached SCSI removable disk
```

Tampak bahwa flashdisk Toshiba itu dianggap oleh sistem sebagai /dev/sdb1.

Nah, karena flashdisk ini biasanya dibawa kemana-mana, digunakan untuk pertukaran file antar komputer yang mana mayoritas komputer di Indonesia umumnya bersistem Windows, maka flashdisknya diformat FAT32 saja agar tetap terbaca di Windows.

```
# mkfs.vfat -F 32 -n "ini punyaku" /dev/sdb1
mkfs.fat 3.0.22 (2013-07-19)
```

- mkfs.vfat digunakan untuk membuat file sistem dengan format FAT.
- opsi -F 32 untuk memformat menjadi FAT32, seperti yang digunakan flashdisk pada umumnya.
- opsi -n digunakan untuk memberikan label atau nama dari flashdisknya. Silahkan ganti "ini punyaku" dengan label pilihan Anda.
- /dev/sdb1 adalah device flashdisknya. Bisa saja di komputer Anda berbeda. Silahkan disesuaikan.
