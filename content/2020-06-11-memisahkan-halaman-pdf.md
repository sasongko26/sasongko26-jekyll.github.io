---
layout: post
title: Memisahkan halaman PDF
date: 2020-06-11
tags: [slackware, manajemen file]
---
Kadang kita perlu mengambil beberapa halaman dari *e-book* atau sejenisnya yang bertipe pdf. Kita bisa gunakan <code>pdfjam</code>. Misalkan akan mengambil halaman 10-21 dari file buku.pdf.
```bash
pdfjam buku.pdf '10-21'
```

