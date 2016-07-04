---
layout: post
title: "Install Unrar"
date: 2015-06-25
tags: Slackware
---
Di antara file kompresi/arsip yang ada, kompresi yang tidak saya utamakan adalah rar. Simpel sih alasannya, karena secara default baik BlankOn maupun Slackware tidak meng-_embed_ ekstraktornya :D. Harus install dulu. Pastikan tersambung internet untuk mengunduh berkas.

Untuk BlankOn bisa install dari repo.
```
$ sudo apt-get install unrar
```

Sedangkan untuk Slackware install slackbuildnya saja.
```
# cd /usr/local/src
# wget http://slackbuilds.org/slackbuilds/14.1/system/unrar.tar.gz
# tar xzf unrar.tgr.gz
# cd unrar
# wget http://www.rarlab.com/rar/unrarsrc-5.2.6.tar.gz
# sh unrar.SlackBuild
# installpkg /tmp/unrar-5.2.6-x86_64-1_SBo.tgz
```
Install unrar selesai.
 

