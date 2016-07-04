---
layout: post
title:  "Disable Automount BlankOn 9 Suroboyo"
date:   2014-03-01 11:30:51
tags: BlankOn
---
Walaupun diturunkan dari [debian](http://www.debian.org), **BlankOn Suroboyo** berbeda dengan debian karena pada Suroboyo secara default akan secara otomatis membuka media simpan (_flashdisk_ misalnya) setelah media disambungkan ke komputer/laptop. Fitur ini dinamakan _automount-open media_ yang agak mirip dengan _autorun_ pada _windows_. Beberapa orang mungkin merasa terganggu dan ingin mematikan. Atau sebaliknya, pengguna debian justru ingin mengaktifkan fitur ini. Bagaimana cara mengaturnya?

```bash
$ gsettings set org.gnome.desktop.media-handling automount false
$ gsettings set org.gnome.desktop.media-handling automount-open false
```
 
Atau untuk tampilan grafisnya gunakan **dconf-editor / penyunting dconf** yang mana harus install dulu, sedangkan debian tidak usah karena **dconf-editor** sudah terpasang.
```bash
$ sudo apt-get  install dconf-editor
```

Kemudian jalankan **dconf-editor** melalui menu _Aplikasi > Rupa-rupa > Penyunting dconf_. Pilih 
```bash
org.gnome.desktop.media-handling
```

Opsi **Automount** memberikan pilihan apakah akan mengaitkan/_mount_ media secara otomatis. Jika diaktifkan (diberi tanda centang), maka _Nautilus_ akan mengait otomatis media seperti _flashdisk_ begitu ditancapkan. Sedangkan _Automount-open_ memberikan pilihan apakah akan mengaitkan sekaligus membuka media begitu ditancapkan.
![](/gambar/disableautomount.png)
