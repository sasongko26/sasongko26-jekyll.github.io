---
layout: post
title: "Mouse Stuck"
date: 2016-02-26
tags: [slackware, mouse, kernel, boot]
---
Setelah _upgrade current_ ternyata ada masalah dengan mouse. Mouse mengalami _stuck_, ga ada respons saat _drag, drop_, bahkan ga bisa klik baik klik kiri maupun kanan.
Dari grup di _telegram_ dapat informasi dari Pak Willy hal serupa juga dialami oleh beberapa _slacker_ yang lainnya. Alhamdulillah masalah ini bisa _solved_ dengan mudahnya di Slackware64 saya.

Dengan akses root copas <code>/lib/modprobe.d/psmouse.conf</code> ke <code>/etc/modprobe.d</code>. Kemudian _uncomment_ baris terakhir.

```
##############################################################################
# Do not edit this file; instead, copy it to /etc/modprobe.d/ and edit that
##############################################################################

# PS/2 mouse support:
# The default options when the psmouse module can cause problems with KVM
# switches.  If you experience this, you may want to uncomment the line
# below to use a more basic mouse protocol with the psmouse module:
#options psmouse proto=imps
```

Setelah disimpan, silahkan _reboot_.
