---
layout: post
date: 2017-03-27
title: "Disable Command's History"
tags: [slackware]
---
Secara _default_, perintah/_command_ yang dijalankan via terminal emulator dapat diakses lagi dengan klik tombol panah atas. Ini bisa di-_disable_. Caranya, tambakan baris berikut ke dalam file <code>/etc/profile</code>, di sini saya tambahkan di baris 10 dan 11

```sh
export HISTFILE=/dev/null
export HISTSIZE=0
```
