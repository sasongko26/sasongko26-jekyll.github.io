---
layout: post
date: 2017-07-29
title: "Menghapus dengan Pengecualian"
tags: [slackware, terminal]
---

Sebagai pengguna _SBo_ dan <code>sbopkg</code>, file yang dihasilkan proses _build_ ditaruh di <code>/tmp</code>. Folder ini lama-lama semakin banyak isinya. Padahal filenya bisa dikatakan tidak terpakai. _Script_ masih aman tersimpan rapi di <code>/var/lib/sbopkg</code>. Sedangkan _source_-nya di <code>/var/cache/sbopkg</code>.

Semua yang ada di folder <code>/tmp</code> akan saya hapus kecuali file yang berekstensi <code>txt</code>. Saya memang kadang iseng nulis-nulis sesuatu kemudian saya simpan dengan ekstensi <code>txt</code> dan ditaruh di <code>/tmp</code>. File-file ini tidak mau saya hapus, buat dibaca jadi hiburan sendiri kelak bahwa dulu pernah iseng nulis seperti itu... Hahahaha.....

```bash
cd /tmp
shopt -s extglob
rm -rv !(*.txt)
```

