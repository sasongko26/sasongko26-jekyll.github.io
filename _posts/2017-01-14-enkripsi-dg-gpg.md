---
layout: post
date: 2017-01-14
title: "Enkripsi File dengan gnupg"
tags: [slackware, kriptografi, forensik]
---
Selain dengan [openssl]({% post_url 2017-01-08-enkripsi-dg-openssl.md %}), enkripsi file juga dapat dilakukan dengan <code>gnupg</code> atau yang biasa disebut dengan <code>gpg</code>.

```bash
$ gpg -o file_hasil_enkripsi -c file_yang_akan_dienkripsi
```

Sedangkan untuk dekripsi

```bash
$ gpg -o file_hasil_dekripsi -d file_yang_akan_didekripsi
```
