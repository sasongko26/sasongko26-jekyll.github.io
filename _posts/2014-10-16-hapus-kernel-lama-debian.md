---
layout: post
title: "Hapus Kernel Lama Debian"
date: 2014-10-16 17:10
tags: [blankon, kernel]
---
Setelah upgrade kernel, ada yang kurang sreg. Ternyata kernelnya malah jadi ada 2. ini terlihat di grub

![](/gambar/hapus-kernel-1.png)

OK, kernel yang lama (2.6.32-5-686) dihapus saja.

```
# apt-get remove linux-image-2.6.32-5-686
```

kemudian restart.

![](/gambar/hapus-kernel-2.png)
