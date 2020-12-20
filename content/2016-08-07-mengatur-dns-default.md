---
layout: post
date: 2016-08-07
title: "Mengatur DNS Default"
tags: [slackware, network manager]
---

Secara _default_, DNS atau _Domain Name Server_ yang digunakan adalah DNS dari operator/penyedia layanan internet. Namun sayangnya, operator tertentu kurang baik dalam penapisan/pemblokiran situs-situs negatif sehingga kadang konten-konten pornografi, judi, dan konten lainnya yang tidak sesuai dengan norma kesusilaan dan budaya Indonesia dapat sampai ke hadapan kita. Oleh karena itulah perlu menggunakan DNS lain.

Penggantian DNS ini ada 2 cara, yaitu manual dan otomatis.

Cara manual dengan menyunting berkas <code>/etc/resolv.conf</code>. Mengganti _nameserver_ yang ada dengan _nameserver_ yang diinginkan. Salah satu penyedia DNS penapisan situs negatif adalah [Nawala](http://nawala.id). _Nameserver_ nya adalah:

- 180.131.144.144
- 180.131.145.145

Kelemahan cara ini setelah dinyalakan kembali maka kembali menggunakan dari operator. Untuk membuatnya menetap kita jadikan sebagai DNS _default_ yang secara otomatis akan digunakan setiap kali konek dengan cara memasukkan DNS tersebut ke berkas <code>/etc/dhcpcd.conf</code>

Tambahkan

```bash
static domain_name_servers=180.131.144.144 180.131.145.145
```

di bawah 

```bash
# A list of options to request from the DHCP server.
```

Sebenarnya sih bisa ditambah di baris manapun yang masih kosong, tapi biar tetap rapi dan sesuai kategori yang sudah dikelompokkan _Slackware_ ya taruh saja di situ....hehehe.....

Jangan lupa _save_.
