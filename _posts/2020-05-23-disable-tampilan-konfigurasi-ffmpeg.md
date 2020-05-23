---
layout: post
date: 2020-05-23
title: Disable tampilan konfigurasi ffmpeg
tags: [slackware, multimedia]
---
Secara _default_, _output_ <code>ffmpeg</code> akan menampilkan _built configuration_ yang digunakan.
```bash
$ ffmpeg
ffmpeg version 4.2.2 Copyright (c) 2000-2019 the FFmpeg developers
  built with gcc 9.2.0 (GCC)
  configuration: --prefix=/usr --libdir=/usr/lib64 --shlibdir=/usr/lib64 --docdir=/usr/doc/ffmpeg-4.2.2/html --mandir=/usr/man --disable-debug --enable-shared --disable-static --enable-gpl --enable-version3 --enable-avresample --arch=x86_64 --disable-encoder=aac --enable-libfontconfig --enable-libfreetype --enable-libfribidi --enable-gnutls --enable-libbluray --enable-libcaca --enable-libcdio --enable-libopus --enable-libspeex --enable-libssh --enable-libtheora --enable-libv4l2 --enable-libvorbis --enable-libvpx --enable-libwebp --enable-libmp3lame --enable-opencl --enable-opengl --enable-libopenjpeg --enable-libpulse --enable-libsmbclient --enable-libwavpack
  libavutil      56. 31.100 / 56. 31.100
  libavcodec     58. 54.100 / 58. 54.100
  libavformat    58. 29.100 / 58. 29.100
  libavdevice    58.  8.100 / 58.  8.100
  libavfilter     7. 57.100 /  7. 57.100
  libavresample   4.  0.  0 /  4.  0.  0
  libswscale      5.  5.100 /  5.  5.100
  libswresample   3.  5.100 /  3.  5.100
  libpostproc    55.  5.100 / 55.  5.100
Hyper fast Audio and Video encoder
usage: ffmpeg [options] [[infile options] -i infile]... {[outfile options] outfile}...

Use -h to get full help or, even better, run 'man ffmpeg'
```
Menurut saya ini tidak perlu ditampilkan. Berdasarkan pengalaman selama ini menggunakan <code>ffmpeg</code> baik-baik saja. Informasi tersebut bisa dikatakan mubadzir. Lebih baik tidak ditampilkan. Caranya beri opsi
```bash
-hide_banner
$ ffmpeg -hide_banner
```
