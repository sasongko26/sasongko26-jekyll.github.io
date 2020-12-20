---
layout: post
date: 2020-05-24
title: Mengubah resolusi video ffmpeg
tags: [slackware, multimedia]
---

Misalkan terdapat video VID20200509135621.mp4, dengan resolusi 3840x2160 SAR 1:1 DAR 16:9. Akan diubah resolusinya menjadi 1920x1080 dengan tetap memperhatikan SAR dan DAR. Video hasil _scaling_ ini diberi nama VID20200509135621-1080p.mkv. Perubahan ini sekaligus konversi ke mkv agar menghemat _space_.

```bash
ffmpeg -i VID20200509135621.mp4 -vf "scale=1920:1080, setdar=16:9, setsar=1:1" VID20200509135621-1080p.mkv
```
