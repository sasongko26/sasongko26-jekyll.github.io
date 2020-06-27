---
layout: post
date: 2020-06-20
title: Edit video ffmpeg tanpa menurunkan kualitas
tags: [slackware, multimedia]
---
Ketika mengedit video menggunakan <code>ffmpeg</code>, filter video ataupun filter yang lebih kompleks seperti menambahkan watermark, tanpa pengaturan tambahan kadang hasilnya mengecewakan. Gambar pada video menjadi pecah. Untuk meminimalisirnya, bisa ditambahkan opsi <code>-q:v 0</code>.
