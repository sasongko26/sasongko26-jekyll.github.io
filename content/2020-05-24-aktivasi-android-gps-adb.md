---
layout: post
date: 2020-05-24
title: Aktivasi android GPS via adb
tags: [slackware, android]
---

Untuk mengaktifkan lokasi android, dengan mode akurasi tertinggi (GPS dan network/jaringan) menggunakan <code>adb</code>
```bash
adb shell settings put secure location_mode 3
```
Kalau ingin menonaktifkan, ganti angka 3 dengan 0.
