---
layout: post
date: 2016-12-24
title: "Notifikasi Baterai Lemah i3"
tags: [slackware, battery, i3]
---
Salah satu keistimewaan <code>i3</code> atau <code>i3wm</code> adalah belum adanya notifikasi/pemberitahuan saat baterai lemah perlu di-_charge_. Status baterai sudah ada di bar/panel yang ditampilkan oleh <code>i3status</code>.

Berikut adalah _script_ sederhana untuk menampilkan notifikasi saat baterai sedang lemah. Jika baterai telah mencapai batas (di sini saya gunakan 5%) maka akan tampil notifikasi untuk segera dilakukan _charging_ <code>Wayahe dicas bro....!</code>.


```bash
#! /bin/bash

while true
    do
	    persen=$(cat /sys/class/power_supply/BAT0/capacity)
	    batas=5
	    if [ $persen -le $batas ]
	    then
		    notify-send "Wayahe dicas bro....!"
	    fi
	    sleep 300
    done
```
