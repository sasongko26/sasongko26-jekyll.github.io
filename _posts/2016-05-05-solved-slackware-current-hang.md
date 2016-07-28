---
layout: post
title: "[SOLVED] Slackware Current Susah Booting dan Shutdown"
date: 2016-05-05
tags: [slackware, boot, kernel]
---
Tiga bulan lalu saya _sambat_ **_Slackware current_** [hang]({% post_url 2016-02-08-slackware-current-hang %}) saat _booting_ dan _shutdown_. Sekarang  masalah tersebut teratasi.

Secara _default_ [**laptop**](http://www.bhinneka.com/Associate/asc_clicks.aspx?BARef=BATL150600397&BATrcID=linfocatatansas225204&CatID=02no&Link=http%3a%2f%2fwww.bhinneka.com%2fcategory%2fnotebook___laptop.aspx) [Asus X453MA](http://www.bhinneka.com/Associate/asc_clicks.aspx?BARef=BATL150600398&BATrcID=linfocatatansas225204&Link=http%3a%2f%2fwww.bhinneka.com%2fproducts%2fsku00215793%2fasus_notebook_x453ma-bing-wx320b_-_black.aspx) diperuntukkan bagi pengguna _Microsoft Windows_. Hal ini terlihat dari web resminya yang menyediakan _driver_ hanya untuk _Windows_ khususnya **Windows 8.1** dan **Windows 10**. Juga terlihat dari "paket bundling"-nya yang menyediakan _Windows preinstalled_.

Sedangkan yang saya punya, sebenarnya dulu belinya sudah diinstallkan Windows 8.1 oleh pihak toko. Awalnya saya pilih kosongan aja sesuai aslinya. Tapi berhubung pihak toko menawarkan _Windows 8.1 trial_ 6 bulan dan saya kepengen icip-icip Windows 8.1 jadilah laptopnya ada Windowsnya. Nah, karena Windowsnya cuma trial, saya belum sanggup beli orinya (bajakan sih banyak yang jual) dan lebih suka pakai **Linux**, Jadilah laptopnya ber-**Slackware**.

Sesuai spek, Asus X453MA lebih cocok untuk arsitektur 64 bit (x86_64), komputer kekinian. Maka diinstallah **Slackware64 14.1**.

**Slackware 14.1** joss gandos lancar jaya tanpa masalah berarti. Tapi terlalu jadul karena rilis tahun 2013. Sementara belum ada rilis _stable_ lagi. Setelah terbukti bisa berjalan mulus kemudian saya putuskan _upgrade current_. Tapi malah bermasalah, susah _booting_ dan _shutdown_.

Alhamdulillah masih punya kernel lama (3.10.17), upgrade pakai **slackpkg** dan tidak lupa mem-_blacklist_ kernel sehingga masih bisa produktif dengan memakai kernel lama. Kernel versi current saya install manual dari berkas txz yang disediakan repo UKDW.

Oke, basa-basinya cukup, sekarang solusinya.

Atur agar kernel yang digunakan adalah kernel curent (sekarang 4.4.8, insya Allah sebentar lagi 4.4.9).

_Reboot_. Saat akan _booting_ kembali tekan <code>F2</code> untuk memunculkan pengaturan **BIOS**. Silahkan tekan tombol panah kanan untuk berpindah ke tab **Advanced**. Pada bagian **OS Selection** pilih **Windows 7** jangan **Windows 8.1**.

Tekan <code>F10</code>, muncul dialog, pilih _Yes_ untuk menyimpan dan keluar dari BIOS.  

Tidak ada _stuck_ lagi saat _booting_ maupun _shutdown_ dengan kernel current (saat ini yang saya gunakan 4.4.8).
