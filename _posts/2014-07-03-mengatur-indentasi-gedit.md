---
layout: post
title: "Mengatur Indentasi gEdit"
date: 2014-07-03 08:00:00
tags: 
- BlankOn
- Text Editor

---
Untuk keperluan coding, bagi pengguna gedit sebagai text editor-nya, pengaturan indentasi sangatlah penting.

**Indentasi Otomatis**
```
$ gsettings set org.gnome.gedit.preferences.editor auto-indent true
``` 

**Jaraknya?**
Default-nya 8 spasi, tapi umumnya hanya 4 spasi.
```
$ gsettings set org.gnome.gedit.preferences.editor tabs-size 4
```
