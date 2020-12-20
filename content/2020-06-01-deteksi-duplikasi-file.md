---
layout: post
date: 2020-06-01
title: Deteksi duplikasi file
tags: [slackware, forensik, manajemen file]
---

Walau sudah ada _tools_ yang secara langsung mengetahui duplikasi file di linux, saya lebih suka menggunakan _tools_ bawaan **Slackware**. _Tools_ yang umum digunakan antara lain <code>fslint</code>, <code>fdupes</code> atau <code>jdupes</code>. Adapun _tools_ yang biasa saya gunakan 
1. <code>sha512sum</code>
2. <code>awk</code>
3. <code>uniq</code>
4. <code>grep</code>

Misalkan, akan mencari adakah duplikasi file di folder <code>Downloads</code>. Pertama, catat dulu _hash_-nya. Di sini saya gunakan _sha512_. Kumpulan _sha512_ tersebut disatukan dalam file <code>downloads.sha512</code>. File ini terdiri dari 2 kolom. Kolom pertama berisi _hash_, sedangkan kolom kedua nama filenya.
```bash
sha512sum Downloads/* > downloads.sha512
```
Selanjutnya difilter berdasarkan _hash_ atau kolom pertama yang kemudian dicek keunikannya. Kalau ada _hash_ yang sama akan tampil karena menunjukkan file yang sama.
```bash
awk '{ print $1 }' downloads.sha512|uniq -d
```
Kemudian, untuk mengetahui file mana saja yang sama
```bash
grep "[tulis hash nya di sini]" downloads.sha512 
```

