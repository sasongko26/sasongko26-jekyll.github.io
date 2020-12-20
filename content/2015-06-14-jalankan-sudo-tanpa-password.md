---
layout: post
title: "Jalankan Sudo Tanpa Password"
date: 2015-06-14
tags: 
- slackware
- blankon

---
Idealnya perintah sudo memang memerlukan password/kata sandi karena hakikat sudo itu pengguna "meminjam" hak _super user / root_. Tapi, password itu bisa saja kita hilangkan. Maksudnya, tidak perlu menuliskan password, contoh

```
$ wvdial 3
bash: wvdial: command not found
```

Baris 2, _command not found_ menunjukkan 2 kemungkinan. Kemungkinan pertama, perintah yang diketikkan memang tidak ada. Kemungkinan kedua, perintah itu memerlukan hak _root_. Nah perintah [wvdial]({% post_url 2015-04-01-install-wvdial-slackware %}) ini yang bisa menjalankan adalah _root_ atau _sudoers_ (pengguna yang bisa menjalankan perintah hak _root_ tapi dengan syarat memasukkan passwordnya root.

Wvdial ini kan perintah untuk konek internet via modem, rasanya tidak akan berbahaya kalau tidak dipassword. Caranya, edit /etc/sudoers. Untuk mengeditnya butuh hak root atau sudoers. Tambahkan baris dengan format berikut ke file tersebut.

```
pengguna hostname = NOPASSWD: perintah
```

- pengguna : nama pengguna yang termasuk dalam sudoers
- hostname : nama host 
- perintah : ya perintah yang aslinya butuh password saat melakukan sudo yang ingin kita tidak pakai passwordnya

Contoh
```
sasongko laptopku = NOPASSWD: /usr/bin/wvdial
```

Nah, untuk selanjutnya, kalau login sebagai sasongko yang termasuk sudoers menjalankan perintah 
```
$ sudo wvdial 
```
maka sasongko tidak akan diminta password dulu langsung jalan aja si wvdial.
 
