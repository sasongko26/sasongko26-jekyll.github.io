---
layout: post
title: Akses WhatsApp Web via Seamonkey
date: 2020-10-22
tags: [slackware, firefox]
---
Beberapa waktu ini saya lebih sering _browsing_ dengan **Seamonkey** karena lebih ringan dan cepat (penilaian subjektif). _Overall_ lancar jaya aman terkendali. Namun, ada 1 yang tidak bisa dilakukan : akses **WhatsApp Web**!

![WhatsApp Web tidak bisa diakses dengan Seamonkey](/gambar/seamonkey-gagal-buka-wa-web.png)

Untuk mengatasinya, 
1. <code>about:config</code>
2. Muncul peringatan. Klik **I accept the risk!**
3. Isikan pada _Search:_ <code>general.useragent.compatMode.strict-firefox</code>
4. Ubah valuenya dari false ke true
5. Restart Seamonkey

![WhatsApp Web sudah bisa diakses dengan Seamonkey](/gambar/seamonkey-bisa-buka-wa-web.png)
