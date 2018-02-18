---
layout: post
date: 2018-02-18
title: "Rename Network Interface"
tags: [slackware, networking]
---

Entah mengapa tadi kepikiran untuk jalankan <code>ifconfig -a</code>. Ternyata kemudian ada _output_ yang menarik

```bash
eth0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        ether c8:5b:76:66:51:6a  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

wlan1: flags=4098<BROADCAST,MULTICAST>  mtu 1500
        ether ca:b0:da:b5:3d:75  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

Menariknya adalah angka index _interface_-nya. Semua 0 kecuali <code>wlan</code> yang 1 sendiri. Sebenarnya _no problem_ sih, cuma ga sedap dipandang aja. Kalau indexnya kompak 0 kan cakep. Hahahaha.....

Penelusuran mengapa _interface_-nya <code>wlan1</code> bukan <code>wlan0</code>

```bash
$ cat /etc/udev/rules.d/70-persistent-net.rules
# PCI device 0x10ec:/sys/devices/pci0000:00/0000:00:1c.3/0000:03:00.0 (r8169)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="c8:5b:76:66:51:6a", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="eth*", NAME="eth0"

# PCI device 0x168c:/sys/devices/pci0000:00/0000:00:1c.2/0000:02:00.0 (ath10k_pci)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="ca:b0:da:b5:3d:75", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="wlan*", NAME="wlan0"

# PCI device 0x168c:/sys/devices/pci0000:00/0000:00:1c.2/0000:02:00.0 (ath10k_pci)
#SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="ca:b0:da:b5:3d:75", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="wlan*", NAME="wlan1"

# USB device 0x0cf3:0x9271 (usb)
SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="84:16:f9:18:92:40", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="wlan*", NAME="wlan2"
```

Ternyata 1 _device_ dengan _address_ (<code>ca:b0:da:b5:3d:75</code>) diberi 2 nama yaitu <code>wlan0</code> dan <code>wlan1</code>. Ya sudah yang <code>wlan1</code> dikomen aja. Beres.
