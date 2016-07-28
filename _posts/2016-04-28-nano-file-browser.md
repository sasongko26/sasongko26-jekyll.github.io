---
layout: post
date: 2016-04-28
title: "Kekuatan Tersembunyi Nano : Menampilkan File Tersembunyi"
tags:
- slackware
- blankOn
- text editor

---
Bertahun-tahun pakai linux, baru sadar ternyata **nano** punya kekuatan tersembunyi. Bisa menampilkan file maupun folder yang _hidden_ secara otomatis.

Selama ini, untuk mengetahui apa saja yang _hidden_ dengan mengetikkan di **terminal**
```
ls -a
```

Atau dengan menekan <code>^H</code> atau <code>Ctrl H</code> di **thunar**, atau <code> Alt . </code> di **dolphin**.

Nah, **nano** secara _default_ akan menampilkan _hidden file_ saat digunakan untuk mencari _file_ yang akan dibuka/disisipkan.

Perhatikan bagian bawahnya, ada beberapa opsi yang bisa dilakukan.

![](/gambar/nano.png)

Pilih **^R Read File** dengan menekan <code>^R</code>.

Kemudian keluar isian
```
File to insert [from ./] : 
```

![](/gambar/nano-ctrl-r.png)

Tekan <code>^T</code> karena akan mencari filenya.

Nah, keluar file dan folder yang ada di direktori aktif kita.

![](/gambar/nano-browse-dir.png)


