---
layout: post
title: "Install Libre Office di Slackware"
date: 2015-06-09
tags:
- slackware
- office

---
Secara _default_ aplikasi perkantoran yang disediakan _Slackware_ bukan _Libre Office_. Kalau pada saat instalasi _Slackware_ (yang penulis gunakan arsitektur 64 bit) memilih _full install_ maka aplikasi perkantoran yang terpasang adalah _Calligra_. Dibandingkan dengan _Calligra_, saya merasa lebih sreg menggunakan _LibreOffice_ karena kompatibilitasnya yang lebih baik terhadap dokumen yang dibuat dengan _Ms Office_ (harap maklum, masih banyak saudara-saudara kita yang belum bisa _move on_ ke _open source_ dan tidak semua menggunakan _Ms Office_ bajakan).

Berikut adalah langkah-langkah install _Libre Office_ melalui _SlackBuild_.

Pastikan sudah terinstall _Java Development Kit_ (JDK) dan _CPAN Archive Zip_. Untuk install JDK bisa dilihat [di sini]({% post_url 2015-06-07-install-jdk-slackware %}). Kemudian untuk modul perl CPAN Archive Zip.
 
```
# cpan -i Archive::Zip
```

Setelah dependensinya terinstall, kita install _Libre Office_-nya melalui _SlackBuild_ aja yang gampang. Oiya di sini pastikan kita memegang _root privileges_.

```
cd /usr/local/src
wget http://slackbuilds.org/slackbuilds/14.1/office/libreoffice.tar.gz
tar xzf libreoffice.tar.gz
cd libreoffice
wget http://download.documentfoundation.org/libreoffice/stable/4.4.3/rpm/x86_64/LibreOffice_4.4.3_Linux_x86-64_rpm.tar.gz
sh libreoffice.SlackBuild
installpkg /tmp/libreoffice-4.4.3-x86_64-1_SBo.tgz
```

Oke, _Libre Office_ sudah terinstall. Alhamdulillah....
