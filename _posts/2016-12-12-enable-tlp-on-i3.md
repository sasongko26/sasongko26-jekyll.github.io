---
layout: post
date: 2016-12-12
title: "Enable TLP on i3wm"
tags: [power manager, hardware, battery, i3]
---
Beberapa hari yang lalu install <code>i3 (i3wm)</code> menggunakan <code>sbopkg</code>. Biasanya, dengan _desktop environment_ lain seperti _Mate_, baterai bisa bertahan 4 - 6 jam. Namun, dengan _i3_ belum 3 jam sudah minta dicas, padahal penggunaannya seperti biasa tidak ada perbedaan signifikan.

Cek <code>powertop</code> ternyata banyak yang **Bad** seperti _default_-nya tanpa TLP. Padahal _service_ TLP saat _booting_ jalan, _Tunable_ di <code>powertop</code> hanya 1 yang **Bad** lainnya **Good** semua.

I3 memiliki berkas konfigurasi <code>/etc/i3/config</code>. Konfigurasi itu yang saya gunakan. Berkas tersebut juga bisa diisi _script_ atau aplikasi yang jalan saat i3 di-_start_. Di berkas ini saya masukkan _service_ TLP untuk di-_restart_ ketika masuk i3. Yang perlu diperhatikan, pengguna _login_ sebagai _user_ biasa bukan _root_, sedangkan untuk me-_restart_ TLP butuh hak akses root.

Nah, di sinilah saya menggunakan sesuatu yang sebenarnya tidak terlalu saya sukai, yaitu <code>sudo</code>. Mengapa saya tidak terlalu menyukai <code>sudo</code>?. Karena **Slackware** sudah diketahui _password_ rootnya yang dibuat saat install. Berbeda dengan _Ubuntu, Linux Mint_ dan anak cucunya yang memang butuh <code>sudo</code> karena _password_ rootnya secara _default_ sangat misterius antah berantah.

```bash
echo "exec sudo /etc/rc.d/rc.tlp restart" >> /etc/i3/config
echo "sasongko ALL=(ALL) NOPASSWD: /etc/rc.d/rc.tlp restart" >> /etc/sudoers
# silahkan ganti 'sasongko' dengan user Anda
```

Untuk _booting_ selanjutnya TLP akan tetap jalan walau di i3 sekalipun.
