---
layout: post
date: 2018-06-19
title: "Mengganti Kata Secara Massal"
tags: [slackware]
---

Dulu, saat masih menggunakan BlankOn, ternyata pada beberapa postingan di blog ini ada ketidakseragaman, yaitu tag **blankOn** dan **blankon** yang sebenarnya secara esensial sama saja. 

Sekarang sudah diperbaiki. Kata "blankOn" yang ada di tiap file diganti "blankon". Penggantian ini secara massal saja biar lebih praktis. Filenya di direktori \_posts.

```bash
sed -i 's/blankOn/blankon/g' _posts/*.md
```
