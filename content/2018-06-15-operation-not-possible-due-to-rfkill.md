---
layout: post
date: 2018-06-16
title: "Operation not possible due to RF-kill"
tags: [slackware, terminal, networking, desktop environment]
---

Pagi ini, _refreshing_ dengan berganti _desktop environment (DE)_ memakai **Window Maker (WM)**. DE yang jarang digunakan karena biasanya memakai **XFCE**. Tampilannya sederhana, sampai-sampai panel pun tak ada. Sementara HP sudah siap untuk _tethering_. Tinggal konekkan! Eh tapi, bagaimana ini konek internetnya kalau panel tempat nongkrong **Network Manager** atau **Wicd** aja tak ada? Ya mau ga mau pakai CLI. Ok lah. Oh iya, untuk konek internet via CLI yang punya hak adalah _root_. Di sini <code>$</code> maksudnya adalah tetap dilakukan oleh _root_. Untuk memudahkan _syntax highlighting_ karena kalau _command_-nya ditulis dengan <code>#</code> akan terbaca sebagai komentar sehingga tidak begitu jelas terbacanya.

Pertama, cek wifi adapter dan interfacenya. Sebenarnya saya sudah hafal interfacenya wlan0, tapi karena jarang pakai WM ya lakukan "prosedur standar" untuk memudahkan _troubleshoot_ siapa tahu beda atau ada masalah. Firasat ini ternyata benar.

```bash
$ iw dev
phy#0
	Interface wlan0
		ifindex 3
		wdev 0x1
		addr cc:b0:da:b5:yy:xx
		type managed
		txpower 0.00 dBm
```

Ok, masih tetap sama wlan0 dengan _device adapter_ terdaftar sebagai phy#0.

_Next_, cek _wifi_ statusnya apakah kondisi _up_ atau _down_

```bash
$ ip link show wlan0
3: wlan0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether cc:b0:da:b5:yy:xx brd ff:ff:ff:ff:bb:aa
```

Masih _down_. Ok, kita _up_-kan.

```bash
$ ip link set wlan0 up
RTNETLINK answers: Operation not possible due to RF-kill
```

O'o....

Ini mengagetkan! Sudah 5 tahun lebih tidak _ngutak-atik_ RF-kill dan selama pakai **Slackware** _fine fine_ aja. FYI, terakhir mengetikkan _command_ <code>rfkill</code> ya sekitar 5 tahunan yang lalu, saat "membelot" sejenak memakai **Kali Linux**. Ya, sejenak. Hanya sejenak, tapi persisnya berapa lama mbuh..... Yang penting terus tetap **Slackware**.

Karena kaget, seakan tak percaya, kontan mencari _2nd opinion_ memakai <code>ifconfig</code>. 

```bash
$ ifconfig wlan0 up
SIOCSIFFLAGS: Operation not possible due to RF-kill
```

Ternyata sama saja. 

```bash
$ rfkill list
0: ideapad_wlan: Wireless LAN
	Soft blocked: yes
	Hard blocked: no
1: ideapad_bluetooth: Bluetooth
	Soft blocked: yes
	Hard blocked: no
2: phy0: Wireless LAN
	Soft blocked: yes
	Hard blocked: no
3: hci0: Bluetooth
	Soft blocked: yes
	Hard blocked: no
```

Ternyata terblokir. Entah mengapa dan bagaimana prosesnya bisa terblokir.
Yo wislah, di-_unblock_ saja.

```bash
$ rfkill unblock 2
```

Cek lagi apakah masih terblokir.

```bash
$ rfkill list 2
2: phy0: Wireless LAN
	Soft blocked: no
	Hard blocked: no
```

Selanjutnya, coba _up_-kan lagi.

```bash
$ ip link set wlan0 up
$ ip link show wlan0
3: wlan0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc mq state DOWN mode DEFAULT group default qlen 1000
    link/ether cc:b0:da:b5:xx:yy brd ff:ff:ff:ff:bb:aa
```

Alhamdulillah sudah ada tanda kehidupan. Sudah _up_ walaupun belum tersambung ke mana pun. tahu darimana?

```bash
$ iw wlan0 link
Not connected
```

_Next_, scan apa ada wifi

```bash
$ iw wlan0 scan | egrep '(SSID|Authentication)'
	SSID: EN 262 XY
		 * Authentication suites: PSK
```

Sebenarnya _output_-nya panjang, tapi berhubung hanya butuh SSID sama autentikasinya ya sudah di egrep aja. 

Dan karena ada passwordnya, perlu diatur terlebih dulu

```bash
$ vi /etc/wpa_supplicant.conf
network={
    ssid="EN 262 XY"
    psk="indcncniub"
}
```

Coba konekkan

```bash
$ wpa_supplicant -B -D wext -i wlan0 -c /etc/wpa_supplicant.conf
Successfully initialized wpa_supplicant
```

Konfirmasi,

```bash
$ iw wlan0 link
Connected to 20:5e:f7:cb:jj:hh (on wlan0)
	SSID: EN 262 XY
	freq: 2437
	RX: 11111 bytes (126 packets)
	TX: 1438 bytes (14 packets)
	signal: -29 dBm
	tx bitrate: 1.0 MBit/s

	bss flags:	short-preamble short-slot-time
	dtim period:	3
	beacon int:	100
```

Sipp. Konek. Saatnya minta ip.

```bash
$ dhclient wlan0
```

Test koneksi

```bash
$ ping -c 5 google.com
PING google.com (172.217.194.100) 56(84) bytes of data.
64 bytes from 172.217.194.100: icmp_seq=1 ttl=41 time=52.5 ms
64 bytes from 172.217.194.100: icmp_seq=2 ttl=41 time=377 ms
64 bytes from 172.217.194.100: icmp_seq=3 ttl=41 time=54.0 ms
64 bytes from 172.217.194.100: icmp_seq=4 ttl=41 time=217 ms
64 bytes from 172.217.194.100: icmp_seq=5 ttl=41 time=445 ms

--- google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 13070ms
rtt min/avg/max/mdev = 52.536/229.255/445.066/161.638 ms
```

Ok. Beres!
