---
layout: post
date: 2016-07-03
title: "Upgrade ke Slackware 14.2"
---
Sehubungan dengan telah rilisnya **Slackware 14.2** maka silahkan melakukan _upgrade_ untuk mendapatkan keamanan yang lebih bagus dan fitur-fitur baru. Saya selama ini melakukan **_upgrade_ bertahap demi penghematan kuota internet**. Dimulai dengan upgrade ke _current_ karena saat itu versi _stable_ yang baru (14.2) masih dalam proses pengembangan. _Upgrade_ ini menggunakan <code>slackpkg</code>. Dan tentu saja membutuhkan sambungan internet.

1. Pilih cermin atau _mirror_. Dengan menyunting <code>/etc/slackpkg/mirrors</code>, menghilangkan tanda komentar/tanda pagar pada repo yang diinginkan. Tersedia banyak repo yang bisa dijadikan rujukan, tetapi sayangnya baru 2 repo lokal yang resmi terdaftar, yaitu _UI_ dan _UKDW_. Saya gunakan milik UKDW karena lebih dekat (UKDW di Yogyakarta sedangkan saya di Semarang) sehingga harapannya lebih cepat. Bisa juga memilih repo _Slackware.com_ yang secara otomatis akan memilihkan repo terdekat. Pastikan hanya 1 repo yang dipilih.
2. _Update_ daftar paket dengan melakukan <code>slackpkg update</code>
3. _Upgrade_ <code>slackpkg</code> untuk mendapatkan alamat repo 14.2. _Upgrade_ juga <code>glibc-solibs</code>. Keduanya dapat dilakukan secara simultan : <code>slackpkg upgrade slackpkg glibc-solibs</code> 
4. Kalau muncul pertanyaan tentang konfigurasi baru, pilih saja <code>O</code> alias <code>overwrite</code>. Kalau tidak muncul lakukan <code>slackpkg new-config</code>
5. Setelah _upgrade_ <code>slackpkg</code> pilih repo lagi karena ada perubahan alamat/URL repo kemudian _update_ lagi.
6. Lanjut install paket-paket baru yang sebelumnya tidak ada : <code>slackpkg install-new</code>
7. _Upgrade_ sistem : <code>slackpkg upgrade-all</code>. Akan ditampilkan paket yang bisa di-_upgrade_. Hilangkan tanda bintangnya dengan menekan tombol <code>spasi</code> bila tidak ingin paket tersebut di-_upgrade_ kemudian <code>OK</code>. 
8. Hapus paket yang tidak berguna. Paket yang perlu dihapus dan berbagai perubahan dari Slackware 14.1 ke 14.2 bisa dilihat [di sini](http://repo.ukdw.ac.id/slackware/slackware64-14.2/CHANGES_AND_HINTS.TXT) : <code>slackpkg remove    </code>
9. Karena ada pergantian kernel, jangan lupa konfigurasi ulang _boot loader_ itu <code>lilo</code> atau <code>elilo</code>. Kalau menggunakan <code>lilo</code> : <code>liloconfig</code>. Kalau menggunakan <code>elilo</code> : <code>eliloconfig</code>
