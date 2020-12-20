---
layout: post
date: 2016-08-17
title: "Cek Harddisk Korup"
tags: [slackware, hardware]
---

Sewaktu _booting_, sekilas membaca <code>some data may be corrupt</code>. Untuk pesan _error_ komplitnya belum sempat baca. Ya sudahlah setelah login langsung aja baca lognya 

```bash
dmesg | grep -i corrupt
[   19.076118] FAT-fs (sda1): Volume was not properly unmounted. Some data may be corrupt. Please run fsck.
```

Nah kan, ternyata ada kemungkinan partisi yang korup, yaitu <code>/dev/sda1</code>. Dan direkomendasikan untuk menjalankan <code>fsck</code>.

```bash
fsck /dev/sda1

fsck from util-linux 2.27.1
fsck.fat 3.0.28 (2015-05-16)
0x41: Dirty bit is set. Fs was not properly unmounted and some data may be corrupt.
1) Remove dirty bit
2) No action
?
```

pilih <code>1</code> kemudian konfirmasi <code>y</code>

```bash
Perform changes ? (y/n) y
/dev/sda1: 14 files, 21473/101590 clusters
```

Ok. Selesai.
