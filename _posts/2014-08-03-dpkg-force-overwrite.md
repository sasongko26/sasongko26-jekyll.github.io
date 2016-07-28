---
layout: post
title: "DPKG Force Overwrite"
date: 2014-08-03 12:40:22
tags: blankon
---
Alhamdulillah bertambah lagi 1 pengguna BlankOn, sahabat yang sudah saya anggap seperti saudara sendiri, memberikan kepercayaan kepada BlankOn untuk menjadi sistem operasi utama di laptop pertamanya. Dari 2 distro linux yang saya tawarkan dan telah dicobanya secara live, dia lebih memilih BlankOn 9 daripada Ubuntu 13.04.
Pemasangan BlankOn lancar jaya. Karena ISO yang saya punya adalah ISO sesaat setelah rilis (saya unduh tanggal 18 Februari 2014), maka saya merasa wajib untuk memperbaruinya. _Upgrade_ tidak masalah, walau sebenarnya ada kendala koneksi yang kebetulan meng-keong. 
Pemasangan virtualbox inilah masalahnya. Pemasangan menemui _unmet dependency_.

{% highlight bash %}
You might want to run 'apt-get -f install' to correct these.
The following packages have unmet dependencies:
linux-image-3.0.7-1-generic : Depends: wireless-crda but it is not installed
linux-image-generic : Depends: linux-firmware but it is not installed
E: Unmet dependencies. Try using -f
{% endhighlight %} 

Sesuai permintaan, tambahkan opsi -f, tapi.........masih error saudara-saudara!

{% highlight bash %}
$ sudo apt-get install virtualbox -f
Reading package lists... Done
Building dependency tree
Reading state information... Done
Correcting dependencies... Done
The following extra packages will be installed:
linux-firmware wireless-crda
The following NEW packages will be installed:
linux-firmware wireless-crda
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
12 not fully installed or removed.
Need to get 18.5 MB of archives.
After this operation, 33.8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://arsip.blankonlinux.or.id/blankon/ suroboyo/main wireless-crda i386 1.14 [16.0 kB]
Get:2 http://arsip.blankonlinux.or.id/blankon/ suroboyo/main linux-firmware all 2.1 [18.5 MB]
Fetched 18.5 MB in 2min 5s (148 kB/s) 
(Reading database ... 142396 files and directories currently installed.)
Preparing to unpack .../wireless-crda_1.14_i386.deb ...
Unpacking wireless-crda (1.14) ...
dpkg: error processing archive /var/cache/apt/archives/wireless-crda_1.14_i386.deb (--unpack):
trying to overwrite '/sbin/crda', which is also in package crda 1.1.2-1
Preparing to unpack .../linux-firmware_2.1_all.deb ...
Unpacking linux-firmware (2.1) ...
dpkg: error processing archive /var/cache/apt/archives/linux-firmware_2.1_all.deb (--unpack):
trying to overwrite '/lib/firmware/radeon/CAYMAN_mc.bin', which is also in package firmware-linux-nonfree 0.40
dpkg-deb: error: subprocess paste was killed by signal (Broken pipe)
Errors were encountered while processing:
/var/cache/apt/archives/wireless-crda_1.14_i386.deb
/var/cache/apt/archives/linux-firmware_2.1_all.deb
E: Sub-process /usr/bin/dpkg returned an error code (1)
{% endhighlight %}

Hm....gimana ya caranya?
Yang saya suka dari linux adalah ketika error linux menawarkan solusi dan menampilkan pesan error / errornya itu kenapa. Menawarkan solusi ya itu tadi dengan menambahkan opsi -f. Solusi ini sudah dicoba tapi kok masih gagal? Mari kita lihat errornya itu di mana. Perhatikan proses installnya, output apa yang dihasilkan? Kalau dicermati, kegagalan installasi adalah karena gagal meng-_overwrite_ **/var/cache/apt/archives/wireless-crda_1.14_i386.deb dan /var/cache/apt/archives/linux-firmware_2.1_all.deb**, perhatikan ada “**trying to overwrite**”. 

![](/gambar/dpkg-force-overwrite.jpg)

Sebab kegagalan sudah ketemu, langsung kita coba atasi. Kita akan melakukan overwrite secara paksa.

{% highlight bash %}
$ sudo dpkg -i --force-overwrite /var/cache/apt/archives/wireless-crda_1.14_i386.deb ; sudo dpkg -i --force-overwrite /var/cache/apt/archives/linux-firmware_2.1_all.deb
{% endhighlight %}

Alhamdulillah berhasil.
