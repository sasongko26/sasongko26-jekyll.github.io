---
layout: post
date: 2016-05-03
title: "Install sbopkg"
tags: [slackware, sbopkg, slackbuild]
---
Adakalanya pengguna **Slackware** membutuhkan paket/aplikasi di luar yang dirilis secara resmi oleh **Slackware** tapi tidak mau repot _install_ dari kode sumber (_source code_). [**SlackBuilds.org (SBo)**](http://slackbuilds.org) inilah yang mewujudkannya. Di SBo tersedia ribuan paket yang dapat dijalankan dengan baik di **Slackware**.

Kecuali dalam bentuk _web interface_ SBo juga bisa dinikmati dalam bentuk _command line interface_ yang dinamakan **sbopkg**. Sbopkg secara _default_ tidak ter-_install_ karena paket ini memang paket _third party_.

Untuk _install_-nya mudah. Tersedia kode sumber maupun paket binernya. Biar lebih praktis _install_ dari binernya saja. Pastikan tersambung internet untuk mengunduh.

```
wget https://github.com/sbopkg/sbopkg/releases/download/0.37.1/sbopkg-0.37.1-noarch-1_wsr.tgz
installpkg sbopkg-0.37.1-noarch-1_wsr.tgz
```

Sbopkg sudah ter-_install_. UNtuk menjalankannya harus dengan _root privileges_

```
sbopkg
```
