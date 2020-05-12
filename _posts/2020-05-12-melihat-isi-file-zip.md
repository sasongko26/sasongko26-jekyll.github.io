---
layout: post
date: 2020-05-12
title: Melihat isi file zip
tags: [slackware, manajemen file]
---
Menggunakan linux terutama **slackware** membuat pekerjaan lebih ringan dan efisien. Suatu ketika diberikan sebuah file terkompresi zip yang misterius. Misterius karena ukurannya besar dan konon kata empunya file tersebut _ngehang_ saat akan dibuka di komputer dengan sistem **bukan slackware** juga **bukan linux**. Dan ketika dibuka di **slackware** ketahuanlah nama "penduduk" zip tersebut.

```bash
zip -sf namafile.zip
# atau
less namafile.zip
```
