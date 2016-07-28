---
layout: post
title: "Memformat Partisi"
date: 2015-07-12
tags: slackware
---
Melanjutkan catatan [kemarin]({% post_url 2015-07-11-membuat-partisi-dengan-cgdisk %}) sekarang partisinya diformat menjadi ext4, format filesystem yang umum digunakan untuk linux dengan kestabilan yang tidak diragukan lagi.

Partisi yang akan diformat ext4 adalah /dev/sda9 dan akan diberi label sebagai src. Pemformatan ini juga harus dilakukan root.
```
# mkfs -t ext4 -L 'src' /dev/sda9
mke2fs 1.42.8 (20-Jun-2013)
Filesystem label=src
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
871408 inodes, 3482075 blocks
174103 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=3569352704
107 block groups
32768 blocks per group, 32768 fragments per group
8144 inodes per group
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done   

```
