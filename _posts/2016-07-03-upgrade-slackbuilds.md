---
layout: post
date: 2016-07-03
title: "Upgrade Slackbuilds Slackware 14.2"
tags: Slackware
---
Setelah melakukan [ _upgrade_ sistem ke _Slackware 14.2_]({% post_url 2016-07-03-upgrade-slackware-142 %}) ada baiknya _upgrade_ juga paket yang diinstal dari slackbuilds.org.

1. _Upgrade_ <code>sbopkg</code> : <code>sbopkg -u</code>
2. Versi <code>sbopkg</code> terbaru adalah 0.38.0 sedangkan yang terinstall 0.37.1. Untuk mengunduh versi terbaru ketik <code>D</code>
3. Hasil unduhan : <code>/tmp/sbopkg-0.38.0-noarch-1_wsr.tgz</code>
4. Setelah diunduh, _upgrade_ : <code>upgradepkg /tmp/sbopkg-0.38.0-noarch-1_wsr.tgz</code>
5. Karena menghasilkan konfigurasi baru, lakukan <code>slackpkg new-config</code> dan pilih overwrite saja.
6. Kemudian _update_ ke repo 14.2 : <code>sbopkg</code> pilih <code>Utilities</code> lalu <code>Repository</code>. Kemudian pilih <code>SBo (14.2)</code>
7. Muncul konfirmasi, apakah akan membuat baru, pilih <code>C</code> untuk <code>Create</code>.
8. Kemudian <code>Back</code> ke awal <code>sbopkg</code>, pilih <code>Sync</code> untuk _update_ repo.
9. Setelah _sync_-nya selesai, pilih <code>EXIT</code> kembali ke awal <code>sbopk</code>
10. Kemudian pilih <code>Updates</code> untuk mengecek paket apa saja yang bisa di-_upgrade_.
11. <code>EXIT</code> keluar konfirmasi apakah paket-paket tersebut akan dimasukkan ke dalam <code>queue</code> untuk bisa diinstall kemudian.<code>YES</code> untuk memasukkannya.
12. Kembali di awal <code>sbopkg</code>. Pilih <code>Queue</code>
13. PIlih <code>Process</code> akan muncul daftar paket langkah no.11
14. Silahkan pilih paketnya kemudian <code>OK</code> Kemudian <code>Install</code> dan <code>OK</code>
15. Tunggu sampai selesai.
16. Keluar dialog apakah akan menghapus yang ada di <code>queue</code>. Pilih <code>Clear</code> untuk menghapus. Kemudian keluar info bahwa queue sudah dihapus, keudian <code>OK</code>
17. Kembali ke <code>Queue Menu</code> pilih <code>Back</code>
18. Kembali ke awal <code>sbopkg</code>, karena sudah selesai, silahkan <code>Exit</code> 
