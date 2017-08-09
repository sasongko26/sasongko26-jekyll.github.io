---
layout: post
date: 2017-03-27
title: "Disable Command's History"
tags: [slackware]
---
Secara _default_, perintah/_command_ yang dijalankan via terminal emulator dapat diakses lagi dengan klik tombol panah atas. Bisa juga dilihat dengan _command_ <code>history</code> atau membaca isi <code>~/.bash_history</code>. Ini bisa di-_disable_. Caranya, membuat file di <code>/etc/profile.d/</code>, yang isinya 

```sh
export HISTFILE=/dev/null
export HISTSIZE=0
```
