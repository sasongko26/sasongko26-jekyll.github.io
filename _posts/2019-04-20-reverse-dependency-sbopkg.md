---
layout: post
date: 2019-04-20
title: "Reverse Dependency sbopkg"
tags: [slackware, sbopkg, slackbuild]
---
Secara _default_ <code>sbopkg</code> tidak menyediakan fitur **reverse dependency**. Adapun untuk butuh _dependency_-nya apa saja bisa menggunakan <code>sqg</code>. Bagaimana tahu _reverse dependency_-nya?

Ini cara sederhana yang saya gunakan

```bash
grep -w REQUIRES /var/lib/sbopkg/SBo/*/*/*/*.info | grep -w nama_paket
```

Dengan cara tersebut bisa diketahui suatu paket/_package_ itu menjadi dependensi dari paket apa. Tapi, salah 1 dari _output_ tersebut tidak lain adalah paket itu sendiri.
