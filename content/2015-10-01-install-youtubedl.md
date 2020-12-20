---
layout: post
title: "Install Youtube Downloader"
date: 2015-10-01
tags: 
- slackware
- multimedia

---
Siapa bilang pakai _Slackware_ ga bisa download video dari _Youtube_? Bisa kok pakai _youtube-dl_.Cara installnya gampang. Pastikan terhubung ke internet untuk mengunduh berkasnya. Dan untuk install butuh hak akses root. Di sini kita pakai cara yang mudah saja, install dari slackbuilds.org.
```
cd /usr/local/src
wget http://slackbuilds.org/slackbuilds/14.1/network/youtube-dl.tar.gz
tar xzf youtube-dl.tar.gz
cd youtube-dl
wget https://github.com/rg3/youtube-dl/archive/2015.09.22.tar.gz
sh youtube-dl.SlackBuild
installpkg /tmp/youtube-dl-2015.09.22-x86_64-1_SBo.tgz
```   
