---
layout: post
date: 2018-07-17
title: "Fix sbotools Perl unescaped left brace in regex is deprecated here"
tags: [slackware, perl]
--- 

Siang ini, sudah agak lama tidak _check update_ paket-paket dari [SBo](http://slackbuilds.org). Sudah 3 - 5 mingguan lah kira-kira. Kebetulan juga hari ini tadi agak longgar.

```bash
$ sbocheck # command ini dijalankan oleh root
Unescaped left brace in regex is deprecated here (and will be fatal in Perl 5.32), passed through in regex; marked by <-- HERE in m/\$({ <-- HERE |)[A-Za-z0-9_]+(}|)/ at /usr/share/perl5/SBO/Lib/Build.pm line 244
```

Ada masalah ternyata dan masalahnya di [Perl](http://sasongko.web.id/tags/#perl). Simpel sih solusinya. Buka file <code>/usr/share/perl5/SBO/Lib/Build.pm</code>, pada _line_ 244 karakter <code>{</code> diganti <code>\{</code>

