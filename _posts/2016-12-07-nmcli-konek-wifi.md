---
layout: post
date: 2016-12-07
title: "nmcli untuk konek wifi"
tags: [slackware, network manager, terminal]
---
Untuk konek internet baik itu melalui modem, LAN, maupun wifi, pengguna GNU/Linux lebih sering menggunakan <code>network manager</code> yang _applet_-nya biasanya ada di panel sebelah kanan walau sebenarnya ada cara lain seperti <code>ifconfig</code> dan <code>dhcpcd</code>. Kalau dalam mode grafis sih saya rasa tidak masalah, tapi bagaimana kalau sedang berada dalam mode teks yang jelas tidak terpampang _applet network manager_-nya? <code>nmcli</code> adalah solusinya.

Lah, buat apa sih repot-repot mode teks? Jadul, ga modern! Benar. Kalau keperluannya hanya _download file_ berukuran besar, dan dalam waktu bersamaan ada kegiatan lain yang tidak bisa ditinggalka, beralih ke mode teks bisa dijadikan pilihan, mengingat dalam mode teks aplikasi yang dijalankan tidak sebanyak dalam mode grafis sehingga menghemat _memory_ dan daya. 

Anggaplah di tempat saya saat ini, belum diketahui apakah tersedia wifi atau tidak. Mari kita cek

![](/gambar/nmcli-d-wifi-list.png)

Dan ternyata ada.

Saya ingin konek ke <code>a1</code>. <code>a1</code> ini ternyata di-_password_. Terlihat dari kolom <code>SECURITY</code> tertulis <code>WPA2</code>. Tapi saya sudah tahu _password_ tersebut.

![](/gambar/nmcli-ask-success.png)

Nah sudah konek.

Lalu bagaimana kalau tidak ada _password_-nya ? Hilangkan opsi <code>--ask</code>.
