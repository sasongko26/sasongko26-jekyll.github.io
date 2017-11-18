---
layout: post
date: 2017-11-18
title: "Kernel 4.14.0 Masuk -Current, Beralih ke Kernel Generic"
tags: [slackware, kernel, elilo]
---

Setelah 2 minggu, -Current kembali mendapatkan _update_ Jum'at kemarin tanggal 17 November 2017. Banyak _update_, ada yang _upgraded, rebuilt, added,_ dan _removed_. Salah satunya adalah masuknya kernel 4.14.0 yang merupakan kernel terbaru yang dirilis tanggal 12 November 2017 yang lalu.

Setelah _upgrade_ dan <code>eliloconfig</code> kemudian _restart_, ternyata muncul masalah! _Bootloop_!  <code>Loading vmlinuz... </code> langsung _reboot_. Begitu seterusnya.

Alhamdulillah punya DVD Slackware64 14.1 yang masih bisa dipakai, jadi untuk _recovery_-nya lebih mudah. _Boot_ dari DVD kemudian waktu muncul <code>grub</code> pilih opsi yang intinya _detect another operating system_ (persisnya saya lupa). Ada beberapa pilihan, antara lain

```bash
Linux /boot/vmlinuz-generic-4.14.0
Linux /boot/vmlinuz-huge-4.14.0  
```

Pilih kernel huge bisa lancar tidak ada masalah. Saya biasanya pakai kernel huge karena tidak mau ribet, sesuai _default_ hasil <code>eliloconfig</code>. Memastikan <code>elilo.conf</code> terisi dengan benar. Tak lupa membuat <code>initrd</code> untuk kernel generic, jaga-jaga, siapa tahu dibutuhkan.

Pengaturan beres! _Restart_.... eh..... masih _bootloop_. Ya sudah, _switch_ ke kernel generic dan hasilnya _booting_ sukses. Alhamdulillah....
