---
layout: post
title:  "Blokir Situs Porno di BlankOn Linux"
date:   2014-04-26 11:30:51
tags: BlankOn
---

[BlankOn](http://www.blankonlinux.or.id) adalah salah satu distro linux karya Indonesia yang dibuat tidak dengan main-main. Ya, hanya salah satu satu distro karena ada distro lain seperti [IGN](http://www.igos-nusantara.or.id). [Pengembang BlankOn](http://dev.blankonlinur.or.id) serius menjalankan misi dan filosofi _BlankOn_. _BlankOn_ diambil dari kata _Blank_ dan _On_, mengandung filosofi bahwa pengguna _BlankOn_ diharapkan berubah dari _Blank_ (kosong, belum tahu, belum sadar) menjadi _On_ (tahu dan sadar sepenuhnya). Maksudnya? Pengguna diharapkan sadar akan ke-Indonesia-annya. Bangsa Indonesia sejak dulu kala dikenal sebagai bangsa yang bermartabat, bangsa yang menjunjung tinggi moral. Salah satu moral yang diperhatikan BlankOn adalah berinternet secara sehat. Salah satu contoh internet sehat adalah penapisan atau pemblokiran situs-situs porno. Apa buktinya? BlankOn menyediakan [DNS Nawala](http://www.nawala.id) yang sudah terkenal ampuh memblokir situs-situs amoral. 
Pengguna BlankOn tidak perlu repot-repot mengatur DNS nya sendiri karena sudah diatur otomatis oleh _nawala_. Cara memasangnya
```
$ sudo apt-get install nawala
```
Kemudian kita tes buka laman [test.nawala.org](http://test.nawala.org). Kalau tampil seperti ini berarti sukses.

![](/gambar/nawala-tes.png)
Nah, kalau misalnya membuka situs yang disaring/diblokir nawala akan tampil

![](/gambar/nawala.png)