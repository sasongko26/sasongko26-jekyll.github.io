---
layout: post
title: "Slackpkg packages database error"
date: 2018-04-03
tags: [slackware,slackpkg]
---

Siang ini, _upgrade_ beberapa paket <code>SBo</code>, salah satunya adalah <code>nodejs</code>. Tetapi terjadi insiden di sela-sela prosesnya : _lowbatt_ sehingga laptop mati. Kejadian ini awalnya tidak saya ketahui, karena banyak paket yang di-_upgrade_ sehingga lama kemudian saya tinggal mengerjakan pekerjaan yang lain.

Singkat cerita, saya ingin _upgrade_ paket-paket _official_ melalui <code>slackpkg</code>

```bash
slackpkg upgrade-all

FATAL! There is some problem in packages database
       or maybe an installation or upgrade in progress:

   nodejs-6.11.2-x86_64-1_SBo-upgraded-2018-04-03,11:12:24

       If you continue you may corrupt packages database.
       Check or retry later
```

Ternyata tadi _upgrade_ paket dari <code>SBo</code> belum selesai. Masih memproses <code>nodejs</code>. Ini terlihat dari _output_ <code>slackpkg upgrade-all</code> di atas.

Yah memang, paket <code>nodejs</code> belum sempurna ter-_upgrade_. Padahal _compile_-nya lama. Apa boleh buat, harus mengikhlaskan untuk menghapus dan _reinstall_ <code>nodejs</code>-nya.

```bash
removepkg nodejs-6.11.2-x86_64-1_SBo-upgraded-2018-04-03,11:12:24
```

Nah, kalau paket yang bermasalah _removed_, lanjutkan lagi _upgrade_-nya.



