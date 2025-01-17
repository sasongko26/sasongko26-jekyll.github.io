---
layout: post
date: 2016-06-26
title: "Konek Internet dengan nmcli"
tags:
- slackware
- network manager

---
Menyambung catatan tentang [hilangnya ikon atau NetworkManager]({% post_url 2015-12-26-ikon-networkmanager-hilang %}). Jika <code>nm-applet</code> tidak mempan untuk menampilkan _applet NetworkManager_, maka kita bisa gunakan <code>nmcli</code>.

<code>nmcli</code> adalah _NetworkManager_ dengan antarmuka teks (_command line interface_).

```
nmcli
Usage: nmcli [OPTIONS] OBJECT { COMMAND | help }

OPTIONS
  -t[erse]                                   terse output
  -p[retty]                                  pretty output
  -m[ode] tabular|multiline                  output mode
  -c[olors] auto|yes|no                      whether to use colors in output
  -f[ields] <field1,field2,...>|all|common   specify fields to output
  -e[scape] yes|no                           escape columns separators in values
  -a[sk]                                     ask for missing parameters
  -s[how-secrets]                            allow displaying passwords
  -w[ait] <seconds>                          set timeout waiting for finishing operations
  -v[ersion]                                 show program version
  -h[elp]                                    print this help

OBJECT
  g[eneral]       NetworkManager's general status and operations
  n[etworking]    overall networking control
  r[adio]         NetworkManager radio switches
  c[onnection]    NetworkManager's connections
  d[evice]        devices managed by NetworkManager
  a[gent]         NetworkManager secret agent or polkit agent
  m[onitor]       monitor NetworkManager changes

```

Untuk melihat sambungan/koneksi yang telah dibuat dengan _NetworkManager_ gunakan <code>nmcli c</code>. Berikut adalah contoh _output_-nya
```
NAME                        UUID                                  TYPE             DEVICE 
3 Monthly Internet Service  72c411c9-a79b-40c3-a5e7-00411fde9b74  gsm              --     
AndroidAP                   9858bf43-529c-4089-8844-57ed40637de2  802-11-wireless  --     
Mbah Min                    06d393a3-9494-4434-bf07-62967d43dbe3  802-11-wireless  --     
Perpus FK                   3b7599a5-7c6c-4797-8809-a866578d0fa6  802-11-wireless  --     
Star Hotel Semarang         26db7a92-b1d2-4eb3-9b52-f28cda1e6991  802-11-wireless  --     
```

Dari hasil tersebut tampak ada 6 sambungan. Tapi perlu diketahui, sambungan tersebut tidaklah _realtime_. Itu adalah daftar semua sambungan yang pernah saya gunakan. 1 melalui [modem](http://www.bhinneka.com/Associate/asc_clicks.aspx?BARef=BATL160601616&BATrcID=linfocatatansas225204&CatID=01j8&Link=http%3a%2f%2fwww.bhinneka.com%2fcategory%2fmodem.aspx&SubID=) dan 4 wifi/hotspot.

Untuk menyambungkan ke internet <code>nmcli c up UUID</code>. Contoh akan konek internet dengan modem
```
nmcli c up 72c411c9-a79b-40c3-a5e7-00411fde9b74
```

Sedangkan untuk diskonek <code>nmcli c down UUID</code>.
