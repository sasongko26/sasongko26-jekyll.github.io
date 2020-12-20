---
layout: post
title: "Install wxPython"
date: 2015-07-18
tags: 
- slackware
- python

---
wxPython adalah salah satu toolkit untuk membuat aplikasi grafis dengan python. Untuk menginstallnya mudah, kita install saja slackbuildnya. Pastikan tersambung internet.
```
wget http://slackbuilds.org/slackbuilds/14.1/libraries/wxPython.tar.gz
tar xzf wxPython.tar.gz
cd wxPython
wget http://downloads.sourceforge.net/wxpython/wxPython-src-2.8.12.1.tar.bz2
sh wxPython.SlackBuild
installpkg /tmp/wxPython-2.8.12.1-x86_64-2_SBo.tgz
```
