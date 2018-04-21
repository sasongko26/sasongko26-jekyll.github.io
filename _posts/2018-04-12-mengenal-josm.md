---
layout: post
title: "Mengenal JOSM dan OpenStreetMap"
date: 2018-04-12
tags: [slackware, gis]
---

Sebenarnya sudah lama ingin menulis dengan topik _Geographical Information System (GIS)_ tapi baru sempat sekarang.

# OSM

![](/gambar/osm-home.png)

Apakah OSM itu? **OpenStreetMap (OSM)** adalah salah satu layanan peta digital seperti _Google Maps_ dan _Here Maps_ yang dapat diakses melalui https://openstreetmap.org/ . OSM bersifat _free & open source_ sehingga mempersilakan kita untuk berkontribusi secara luas, baik itu menambah/edit data maupun koreksi peta. Mengapa saya lebih suka OSM daripada layanan peta digital lainnya?

1. _Open source_. Inilah alasan utama. Karena _open source_ memungkinkan kita untuk berkontribusi.
2. Masih berhubungan dengan alasan pertama, OSM memberikan kepercayaan (_trust_) kepada penggunanya dan ini membuat saya nyaman. Ada pengalaman tidak mengenakkan ketika saya mencoba memperbaiki peta digital lainnya. Saya usulkan perubahan/perbaikan agar peta tersebut sesuai kenyataan di lapangan. Sebagian kecil diterima, sedangkan sebagian lainnya bernasib antah-berantah yang meminjam kosa kata dalam lagu _Gereja Tua_-nya _Panbers_ : tak tahu di mana rimbanya. Yang menyakitkan adalah perbaikan yang saya usulkan yang bernasib ga jelas itu lokasinya sangat dekat dengan rumah saya sendiri! Saya merasa dia kurang ajar dan sok tahu. Dia datang ke sana paling cuma 1x saja di tahun 2015 saat pemotretan dan _tracking GPS_ (pembuatan peta). Lha saya bertahun-tahun lewat sana!

Saya rasa cukup curcolnya. Mari lanjutkan!

# JOSM

**Java OpenStreetMap Editor (JOSM)** adalah aplikasi desktop berbasis java untuk menyunting/edit OSM. Sebenarnya untuk edit OSM bisa melalui website juga. Tapi saya lebih suka menggunakan aplikasi. Kalau melalui website dikhawatirkan bisa memecah konsentrasi, jadi gagal fokus, malah nyambi _browsing_. Hehehehe....

![](/gambar/josm-start.png)

Agar dapat menggunakan josm harus memiliki akun OSM dan tentu saja install aplikasinya. Informasi lebih jauh tentang JOSM silahkan kunjungi https://josm.openstreetmap.de/

Alhamdulillah <code>josm</code> tersedia di [SBo](http://slackbuilds.org/repository/14.2/gis/josm/) walaupun versi lawas. Kalau ingin versi terbaru tinggal edit _slackbuild_-nya.

