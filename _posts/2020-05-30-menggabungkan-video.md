---
layout: post
date: 2020-05-30
title: Menggabungkan video ffmpeg
tags: [slackware, multimedia]
---

Sebelum menggabungkan video, agar optimal, video-video yang akan digabungkan harus mempunyai frame size, frame rate, rata-rata volume dan container/format yang sama. Misalkan akan digabungkan 4 file video, yaitu
1. piknik-1.mkv
2. piknik-2.mkv
3. piknik-3.mkv
4. piknik-4.mkv

Keempat file tersebut berada dalam folder yang sama. 
Kemudian mereka akan digabungkan menjadi piknik.mkv.
Sebelum digabungkan, membuat list dulu bernama list-piknik yang juga berada sefolder dengan mereka berempat. List berisi video yang akan digabung.
```bash
$ vim list-piknik
file 'piknik-1.mkv'
file 'piknik-2.mkv'
file 'piknik-3.mkv'
file 'piknik-4.mkv'
```
Untuk menggabungnya
```bash
ffmpeg f concat -i list-piknik piknik.mkv
```
