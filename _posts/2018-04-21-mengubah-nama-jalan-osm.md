---
layout: post
date: 2018-04-21
title: "Mengubah Nama Jalan OSM"
tags: [slackware, gis]
---

Ketika [menggunakan OpenStreetMap (OSM)]({% post_url 2018-04-13-cari-lokasi-osm %}) dan menjumpai ada data/informasi yang kita tahu tidak benar, **kita diijinkan untuk memperbaikinya**. Inilah kelebihan OSM yang bersifat _open source_. 

Kali ini memperbaiki kesalahan nama jalan. Jalan yang keliru penamaannya adalah **Jalan Wonosari IV** yang seharusnya **Jalan Widosari IV**. Jalan ini terletak di sebelah barat laut SMP Negeri 3 Semarang.

![](/gambar/osm-search-spega.png)

Kesalahan tersebut sudah saya perbaiki, sehingga kalau Pembaca membukanya di OSM peta di atas sudah tidak berlaku.

Untuk memperbaikinya, dan memodifikasi peta OSM, diperlukan :

1. OSM editor. Bisa melalui web ataupun aplikasi desktop. Saya gunakan <code>JOSM</code>
2. Akun OSM
3. JOSM yang diotentikasi akun OSM
4. Koneksi internet, sangat disarankan berkecepatan tinggi (untuk download dan upload)

Marilah kita anggap 4 hal di atas sudah siap. Pembuatan akun OSM, install JOSM dan otentikasinya mohon maaf belum bisa saya tuliskan karena dulu tidak sempat mendokumentasikannya.

Oiya, hal yang **wajib diperhatikan dalam memodifikasi OSM** adalah

1. Dilarang menyalin dari peta lain
2. Dilakukan dengan gembira

Pada _home screen_ **josm**, klik ikon **Download map data** (saya lingkari merah)

![](/gambar/josm-icon-download.png)

Muncul _window_ **Download**

![](/gambar/josm-download-peta.png)

Opsi <code>Data Sources and Types</code> yang sebaiknya dicentang adalah <code>OpenStreetMap data</code> dan <code>Notes</code>. 

Secara _default_, pemilihan area peta yang akan di-_donwload_ menggunakan cara <code>Slippy map</code>.

![](/gambar/josm-download-peta.png)

- untuk memilih area yang ada di peta silahkan _drag mouse_ ataupun _touchpad_ (kalau menggunakan laptop). Di sini saya pilih secuil dikit saja, toch saya hanya akan mengubah nama 1 jalan itu.
- gunakan tombol panah pada _keyboard_ untuk menggeser peta
- gunakan tombol + atau - untuk _zoom_ peta

Setelah area terpilih, tekan tombol <code>Download</code> dan tunggu sampai selesai. Lamanya _download_ sebanding dengan luas area yang dipilih dan berbanding terbalik dengan kecepatan internet.

Peta yang di-_download_ tampil.

![](/gambar/josm-ganti-nama-jalan-1.png)

 Klik _nodes_ yang akan diedit, dalam hal ini adalah _Jalan Wonosari IV_.

![](/gambar/josm-ganti-nama-jalan-2.png)

Di sisi kanan, bagian <code>tags</code>, di tabel tags tersebut, dobel klik baris <code>nama</code> (saya tandai elips hitam), atau klik tombol <code>Edit</code>

![](/gambar/josm-ganti-nama-jalan-3.png)

ganti <code>Value</code>-nya dari <code> Jalan Wonosari IV</code> menjadi <code>Jalan Widosari IV</code> kemudian klik <code>OK</code>.

Nama jalan sudah kita perbaiki.

![](/gambar/josm-ganti-nama-jalan-5.png)

Saatnya _upload_ ke _server_ OSM agar perubahan bisa dinikmati banyak orang. Klik ikon _Upload_

![](/gambar/josm-icon-upload.png)

Selanjutnya isi keterangan perubahan. Sangat tidak disarankan membiarkannya kosong tanpa diisi. Kalau sudah beres klik <code>Upload Changes</code> dan tunggu beberapa saat sampai perbaikan berhasil.

![](/gambar/josm-upload-data-1.png)
