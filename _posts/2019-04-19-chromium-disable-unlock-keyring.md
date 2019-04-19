---
layout: post
date: 2019-04-19
title: "Chromium Disable Unlock Keyring"
tags: [slackware, security]
---
Mungkin ada yang merasa bosan setiap membuka **Chromium** muncul kotak dialog _Unlock Keyring_.

![](/gambar/chromium-unlock-keyring.png)

Itu bisa diatasi, agar tidak muncul lagi. Aktifkan <code>CHROMIUM_FLAGS</code> pada <code>/etc/chromium/00-default.conf</code>. 

```bash
CHROMIUM_FLAGS="--password-store=basic"
```
