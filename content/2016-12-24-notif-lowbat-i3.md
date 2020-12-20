---
layout: post
date: 2016-12-24
title: "Notifikasi Baterai Lemah i3"
tags: [slackware, battery, i3]
---
Salah satu keistimewaan <code>i3</code> atau <code>i3wm</code> adalah belum adanya notifikasi/pemberitahuan saat baterai lemah perlu di-_charge_. Status baterai sudah ada di bar/panel yang ditampilkan oleh <code>i3status</code>.

Berikut adalah _script_ sederhana untuk menampilkan notifikasi saat baterai sedang lemah dan tidak sedang di-_charge_. Jika baterai telah mencapai batas (di sini saya gunakan 5%) maka setiap 30 detik akan tampil notifikasi untuk segera dilakukan _charging_ <code>Wayahe dicas bro....!</code>. Dan ketika baterai sudah terisi full 100% tetapi masih dalam kondisi dicas akan tampil notifikasi tiap 30 detik bahwa baterai sudah full. 


```bash
#! /bin/bash
status=$(cat /sys/class/power_supply/BAT0/status)
persen=$(cat /sys/class/power_supply/BAT0/capacity)
kritis=5
full=100
while [ "$status" = "Discharging" ]
do
	if [ $persen -le $kritis ]
	then
		notify-send "Wayahe dicas bro....!"
	fi
	sleep 30
done
while [ "$status" = "Charging" ]
do
	if [ $persen -ge $full ]
	then
		notify-send "Wis full bro..."
	fi
	sleep 30
done
```

Simpan file ini (contoh saja) <code>/usr/local/bin/notiflowbatt</code> dan berikan hak eksekusi (<code>chmod +x</code>). Jadikan _startup_ masukkan ke <code>i3config</code> atau ke <code>~/.config/i3/config</code>

```bash
echo "exec_always /usr/local/bin/notiflowbatt" >> ~/.config/i3/config
``` 
