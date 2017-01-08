---
layout: post
date: 2017-01-08
title: "Enkripsi File dengan OpenSSL"
tags: [slackware]
---
Salah satu yang membuat saya kepincut menggunakan GNU/Linux yaitu mudahnya mengamankan file. Salah satu caranya adalah dengan enkripsi. Di sini saya gunakan <code>openssl</code>.

Contoh, saya punya file yang perlu diamankan. Katakanlah filenya <code>indonesia-raya.odt</code>. Saya enkripsi menggunakan <code>openssl</code> dengan _cipher rc4_. File hasil enkripsi saya namai <code>rahasia.odt</code> yang saya taruh di fd dan fd saya <code>mount</code> di <code>/media/hd0</code>. Kemudian akan ditanya _password_ enkripsinya.

```bash
$ openssl rc4 -in indonesia-raya.odt -out /media/hd0/rahasia.odt
enter rc4 encryption password:
Verifying - enter rc4 encryption password:
```

![konten indonesia-raya.odt yang asli belum dienkripsi](/gambar/openssl-enkrip-1.png)

![konten file rahasia.odt hasil enkripsi](/gambar/openssl-enkrip-2.png)

Untuk mendekrip, tambahkan opsi -d kemudian masukkan _password_-nya.

```bash
$ openssl rc4 -d -in /media/hd0/rahasia.odt -out indonesia-raya.odt
```