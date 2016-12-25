---
layout: post
date: 2016-12-24
title: "Notifikasi Baterai Lemah i3"
tags: [slackware, battery, i3]
---
Salah satu keistimewaan <code>i3</code> atau <code>i3wm</code> adalah belum adanya notifikasi/pemberitahuan saat baterai lemah perlu di-_charge_. Status baterai sudah ada di bar/panel yang ditampilkan oleh <code>i3status</code>.

Berikut adalah _script_ sederhana untuk menampilkan notifikasi saat baterai sedang lemah dan tidak sedang di-_charge_. Jika baterai telah mencapai batas (di sini saya gunakan 5%) maka setiap 30 detik akan tampil notifikasi untuk segera dilakukan _charging_ <code>Wayahe dicas bro....!</code>.


```bash
#! /bin/bash
status=$(cat /sys/class/power_supply/BAT0/status)
while [ "$status" = "Discharging" ]
    do
	    persen=$(cat /sys/class/power_supply/BAT0/capacity)
	    batas=5
	    if [ $persen -le $batas ]
	    then
		    notify-send "Wayahe dicas bro....!"
	    fi
            if [ $persen -ge 100 ]
            then
                    notify_send "Wis full bro....."
            fi
	    sleep 30
    done
```
