---
layout: post
date: 2018-05-08
title: "Uninstall Manual Semua Modul Perl"
tags: [slackware, perl]
---
Cara _uninstall_ semua modul perl yang dulunya _install_ dari [CPAN](https://cpan.org) secara manual :

```bash
rm -r /usr/local/{lib{,64},share}/perl5
```
