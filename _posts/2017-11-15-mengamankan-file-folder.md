---
layout: post
date: 2017-11-15
title: Mengamankan File Folder
tags: [slackware,security]
---
Salah satu hal yang membuat saya menggunakan linux khususnya _Slackware_ adalah perlindungan terhadap privasi. Data-data sensitif dan rahasia terlindungi dengan aman. Perlindungan ini ada beberapa bentuk/teknik antara lain penyembunyian, hak akses dan enkripsi. Penyembunyian sederhana dengan menambahkan <code>.</code> pada nama file/folder sangat tidak dianjurkan karena akan mudah dibobol. Teknik penyembunyian yang kami sarankan adalah dengan _steganografi_ tetapi itu akan kami sampaikan besok-besok, insyaallah. Yang sekarang adalah menggunakan hak akses. Adapun dengan enkripsi bisa menggunakan [<code>gpg</code>]({% post_url 2017-01-14-enkripsi-dg-gpg %})  atau [<code>openssl</code>]({% 2017-01-08-enkripsi-dg-openssl %}).

Misalkan terdapat folder <code>privat</code>. Folder ini diatur sedemikian rupa agar tidak sembarang orang/pengguna/user bisa mengaksesnya. Hanya root dan user dari group tertentu saja yang bisa. User tersebut adalah bernama <code>rahasia1</code> dari group <code>rahasia</code>.

Silahkan buat grup dan usernya dulu kalau memang belum dibuat

```bash
groupadd rahasia
useradd rahasia1 -g rahasia
```

Sekarang, atur hak milik (_ownership_) folder tersebut

```bash
chown rahasia1:rahasia -R privat
```

Kemudian berikan hak akses penuh (_read,write,execute_) untuk _owner_ dan grupnya, sedangkan untuk selain mereka tidak akan mendapatkan akses.

```bash
chmod ug+rwx,o-rwx -R privat
```

Nah, sekarang foldernya sudah aman. Untuk mengembalikan lagi agar semua bisa mengakses secara penuh

```bash
chmod a+rwx -R privat
```
