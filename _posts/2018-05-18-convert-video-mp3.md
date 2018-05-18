---
layout: post
date: 2018-05-18
title: "Convert Video Menjadi MP3"
tags: [slackware, terminal]
---

Ternyata tidak sulit mengkonversi/_convert_ video menjadi audio, dalam hal ini mp3. Misalkan, akan dikonversi file video Gambang_Semarang.mkv menjadi file Gambang_Semarang.mp3

```bash
ffmpeg -i Gambang_Semarang.mkv -b:a 128K -vn Gambang_Semarang.mp3
```

(_output_) dari _command_ tersebut di atas sengaja tidak ditampilkan di sini karena agak panjang. 

Cara ini juga berlaku untuk mengubah file mp4 ke mp3 atau dengan kata lain, sebenarnya mengekstrak audio yang ada di dalam video.
