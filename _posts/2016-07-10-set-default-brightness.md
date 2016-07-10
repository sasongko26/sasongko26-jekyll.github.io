---
layout: post
date: 2016-07-10
title: "Set Default Brightness"
tags:
- Slackware
- Xfce
- display
---
Kecerahan monitor / _brightness_ 100% membuat mata cepat lelah. Apalagi kalau secara _default_ begitu masuk X _brigtness_-nya 100% dan mata terpajan dalam waktu lama. Hal ini tentunya tidak bagi kesehatan mata karena bisa menimbulkan _Computer Vision Syndrome_.

Berapa persen _brigtness_ yang pas? Silahkan Anda sesuaikan, senyaman Anda. Untuk mengatur _brigtness_ bisa gunakan <code>xbacklight</code>.

Untuk mengetahui berapa persen _brightness_ yang digunakan saat ini <code>xbacklight</code>. Sedangkan untuk mengubahnya <code>xbacklight -set persen</code>. Contoh akan diatur _brightness_-nya 15%:

```bash
xbacklight -set 15
```

Pengaturan ini hanyalah bersifat _current_/temporer. Setelah dihidupkan ulang _brightness_ kembali ke 100%.

Untuk membuatnya permanen, dalam arti membuat _brightness_ sesuai keinginan (tidak 100%) walau di-_restart_, jadikan saja sebagai _autostart_. Caranya, klik menu <code>Applications</code> --> <code>Settings</code> --> <code>Session and Startup</code>

![](/gambar/session-startup.png)

Klik tab <code>Application Autostart</code> kemudian klik tombol <code>+ Add</code>

![](/gambar/application-autostart.png)

Lalu isikan

![](/gambar/add-autostart.png)

Yang paling penting adalah bagian <code>Command</code>. Silahkan isikan <code>xbacklight</code>-nya. Di sini saya gunakan 15%.

