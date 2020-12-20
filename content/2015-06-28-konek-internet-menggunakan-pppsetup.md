---
layout: post
title: "Konek Internet Slackware"
date: 2015-06-28
tags: slackware
---
Di catatan yang lalu sudah pernah dibahas cara konek internet di Slackware dengan [wvdial]({% post_url 2015-04-01-install-wvdial-slackware %}). Sekarang masih tentang cara konek internet melalui modem di Slackware, hanya saja caranya berbeda. Kali ini menggunakan _pppsetup_ yang secara default sudah dimiliki Slackware.

Perangkat yang kami gunakan:

- laptop [Asus X453MA](http://www.bhinneka.com/Associate/asc_clicks.aspx?BARef=BATL150600398&BATrcID=linfocatatansas225204&Link=http%3a%2f%2fwww.bhinneka.com%2fproducts%2fsku00215793%2fasus_notebook_x453ma-bing-wx320b_-_black.aspx)
- modem USB Huawei E1550
- simcard dengan internet service provider 3.

Cara-cara berikut ini dijalankan oleh root.

```
pppsetup
```

![](/gambar/pppsetup-01.png)

Tekan enter.

![](/gambar/pppsetup-02.png)

Isi phone number dengan
```
ATDT*99***1#
```

Kemudian, lokasi modem silahkan lanjutkan dengan memberikan nilai default/biarkan saja, karena nanti akan kita ubah.

![](/gambar/pppsetup-03.png)

Baud rate ini kami gunakan 9600

![](/gambar/pppsetup-04.png)

Kemudian, penawaran callback, pilih saja NO

![](/gambar/pppsetup-05.png)

Domain ISP kosongkan saja

![](/gambar/pppsetup-06.png)

Untuk nameserver kami gunakan 10.0.28.66, Anda bisa mencobanya dengan 10.0.28.67 atau yang lainnya.

![](/gambar/pppsetup-07.png)

Pengaturan selanjutnya otentikasi, gunakan PAP.

![](/gambar/pppsetup-08.png)

Untuk username karena menggunakan 3 maka username dan passwordnya sama yaitu 3data

![](/gambar/pppsetup-09.png)

![](/gambar/pppsetup-10.png)

Selanjutnya akan tampil hasil pengaturan, silahkan exit.

![](/gambar/pppsetup-11.png)

Saatnya melakukan modifikasi.
```
nano /etc/ppp/options
```
Ganti 
```
/dev/modem
```
dengan
```
/dev/ttyUSB0
```

Untuk menyambungkan ke internet
```
ppp-go
```
![](/gambar/pppsetup-12.png)
Sedangkan untuk diskonek
```
ppp-off
```

