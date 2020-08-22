---
layout: post
date: 2020-08-21
title: Screenshot android dengan adb
tags: [slackware, android]
---
Misalkan akan mengambil screenshot layar hp berbasis android. Screenshot disimpan di _external memory_ (sdcard) dengan nama file screenshot.png
```bash
adb shell screencap -p /sdcard/screenshot.png
```
