---
layout: post
title: "Cek Paket Terinstall di Slackware"
date: 2015-06-15
tasg: Slackware
---
Untuk mengetahui apakah suatu paket atau aplikasi telah terpasang di Slackware kita atau belum caranya mudah.

```
$ ls /var/log/packages | grep nama_paket
```

Contoh, mencari paket yang di nama paketnya ada kata _xfce_
```
$ ls /var/log/packages | grep xfce
gtk-xfce-engine-3.0.1-x86_64-1
libxfce4ui-4.10.0-x86_64-2
libxfce4util-4.10.1-x86_64-1
libxfcegui4-4.10.0-x86_64-2
xfce4-clipman-plugin-1.2.3-x86_64-2
xfce4-dev-tools-4.10.0-x86_64-1
xfce4-mixer-4.8.0-x86_64-1
xfce4-notifyd-0.2.4-x86_64-1
xfce4-panel-4.10.1-x86_64-2
xfce4-power-manager-1.2.0-x86_64-2
xfce4-screenshooter-1.8.1-x86_64-2
xfce4-session-4.10.1-x86_64-3
xfce4-settings-4.10.1-x86_64-1
xfce4-systemload-plugin-1.1.1-x86_64-2
xfce4-taskmanager-1.0.0-x86_64-2
xfce4-terminal-0.6.2-x86_64-1
xfce4-volumed-0.1.13-x86_64-1
xfce4-weather-plugin-0.8.3-x86_64-2
``` 

Jika tidak ada keluaran berarti paket tersebut belum diinstall.
