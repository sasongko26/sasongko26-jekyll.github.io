---
layout: post
date: 2017-08-08
title: "Mengatur Clang Sebagai C Compiler Utama"
tags: [slackware]
---

Secara _default_, _C Compiler_ yang digunakan adalah <code>gcc</code>. Namun, apabila diinginkan, bisa dialihkan menggunakan <code>clang</code>. Caranya, buat file di <code>/etc/profile.d</code>  misalnya <code>c-compiler.sh</code>, yang isinya

```bash
export CC=/usr/bin/clang
export CXX=/usr/bin/clang++
```

