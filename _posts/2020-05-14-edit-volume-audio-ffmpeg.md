---
layout: post
date: 2020-05-14
title: Edit volume suara
tags: [slackware, multimedia]
---
_Editing_ kali ini adalah bagaimana mengubah volume default audio/suara menggunakan **ffmpeg**. Misal, file yang akan diinput/diedit adalah video.mp4. Karena suaranya terlalu pelan, akan dinaikkan menjadi 5x semula melalui filter audio. File hasil editan diberi nama video-louder.webm.
```bash
ffmpeg -i video.mp4 -filter:a "volume=5" video-louder.webm
```
Apabila suara terlalu nyaring bisa dipelankan. Berikut akan dipelankan menjadi setengahnya dari volume semula dan file baru diberi nama new.webm
```bash
ffmpeg -i video.mp4 -filter:a "volume=0.5" new.webm
```
Atau, dengan menuliskan volume suaranya secara langsung. Default aslinya 256. Misalkan akan dinaikkan menjadi 300 kemudian disimpan sebagai anyar.mkv
```bash
ffmpeg -i video.mp4 -vol 300 anyar.mkv
```
