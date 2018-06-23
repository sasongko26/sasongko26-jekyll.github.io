---
layou: post
date: 2018-06-23
title: "Hapus Trash via Command Line"
tags: [slackware, xfce]
---

Iseng-iseng buka _hidden folder_ ada yang menarik. File yang ada di **Trash** (bisa buka di **Thunar** dengan path <code>trash:///</code> sama dengan yang ada di <code>~/.local/share/Trash/files/</code>. Sehingga kalau ingin mengosongkan **Trash** dan posisi sedang di CLI dan tidak membuka **file manager** ataupun lagi _aras-arasen_, sangat bisa.

```bash
rm -rv ~./local/share/Trash/*
```
