---
layout: post
date: 2017-03-25
title: "Konek Internet USB Tethering"
tags: slackware
---
Salah satu keunggulan _GNU/Linux_ terutama **Slackware** adalah berlakunya **banyak jalan menuju Roma**. Contohnya untuk konek/menyambung ke internet, ada beberapa cara antara lain :

1. <code>nmcli</code>, contohnya [di sini]({% post_url 2016-06-26-konek-inet-nmcli %}) dan [di sini]({% post_url 2016-12-07-nmcli-konek-wifi %}).
2. <code>pppsetup</code>, caranya [seperti ini]({% post_url 2015-06-08-konek-internet-menggunakan-pppsetup %}) dan [ini]({% post_url 2015-08-17-setting-internet-xl-slackware %}) 
3. [<code>wvdial</code>]({% post_url 2015-04-01-install-wvdial-slackware %})
4. <code>wpa_supplicant</code>
5. <code>wicd</code>

Cara lainnya yang saya pakai adalah dengan <code>dhcpcd</code>.

Misalkan akan menyambungkan internet melalui _USB tethering_ - cara melakukan _USB tethering_ tidak saya bahas,

Cek _network interface_, ternyata di sini _interface_-nya dikenali sebagai <code>usb0</code>

```bash
bash-4.4# ifconfig -a
```

Contoh _output_

```bash
usb0: flags=4098<BROADCAST,MULTICAST>  mtu 1500
        ether 92:60:82:2c:9d:2c  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

Aktifkan

```bash
bash-4.4# ifconfig usb0 up
bash-4.4# dhcpcd usb0
DUID 00:01:00:01:1f:c6:eb:38:32:6a:34:71:ab:80
usb0: IAID 82:2c:9d:2c
usb0: soliciting an IPv6 router
usb0: soliciting a DHCP lease
usb0: offered 192.168.42.180 from 192.168.42.129
usb0: leased 192.168.42.180 for 3600 seconds
usb0: adding route to 192.168.42.0/24
usb0: adding default route via 192.168.42.129
forked to background, child pid 5980
```

Done.
