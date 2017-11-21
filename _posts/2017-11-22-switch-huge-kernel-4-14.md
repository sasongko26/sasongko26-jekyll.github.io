---
layout: post
date: 2017-11-22
title: "Menggunakan Kernel Huge 4.14.0"
tags: [slackware, kernel, elilo]
---
Melanjutkan [catatan yang lalu]({% post_url 2017-11-18-switch-generic-kernel-4-14 %}) tentang _bootloop_ apabila menggunakan kernel huge 4.14.0 sehingga harus beralih ke kernel generic. _Update_ terbaru kemarin, 21 November 2017 jam 05.05.41 UTC atau jam 12.05.41 WIB menyelesaikan masalah ini melalui _rebuilt_ <code>elilo</code>.

Setelah _upgrade_ terutama untuk <code>elilo</code> jangan lupa menjalankan

```bash
eliloconfig
```

yang secara otomatis juga akan meng-_generate_ <code>elilo.conf</code> yang berisi pengaturan _boot_ dengan kernel huge.

Namun, saya kurang suka dengan cara otomatis ini. Dan saya memilih melakukannya secara manual saja agar lebih fleksibel dalam konfigurasinya.

```bash
cp -v /boot/elilo-x86_64.efi /boot/efi/EFI/Slackware/elilo.efi
```
