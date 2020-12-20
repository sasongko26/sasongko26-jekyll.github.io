---
layout: post
date: 2017-07-04
title: "Presentasi dengan LCD Projector"
tags: [slackware]
---
_Tools_ yang digunakan adalah <code>xrandr</code>. Sebenarnya bisa menggunakan aplikasi GUI yang disediakan _desktop environment_ masing-masing, tapi saya lebih suka menggunakan <code>xrandr</code> agar universal bisa digunakan di lingkungan desktop apapun, entah itu <code>Fluxbox, FVWM, TWM, Xfce, KDE, Lumina, LXQt, Mate, Cinnamon</code>, dsb.

Pertama, identifikasi monitor/_screen_ primer yang aktif tersambung saat ini, jangan sambungkan proyektor dulu

```bash
$ xrandr
Screen 0: minimum 8 x 8, current 1366 x 768, maximum 32767 x 32767
eDP1 connected primary 1366x768+0+0 (normal left inverted right x axis y axis) 310mm x 170mm
   1366x768      59.97*+
   1024x768      60.00  
   1024x576      60.00  
   960x540       60.00  
   800x600       60.32    56.25  
   864x486       60.00  
   640x480       59.94  
   720x405       60.00  
   680x384       60.00  
   640x360       60.00  
DP1 disconnected (normal left inverted right x axis y axis)
DP2 disconnected (normal left inverted right x axis y axis)
HDMI1 disconnected (normal left inverted right x axis y axis)
HDMI2 disconnected (normal left inverted right x axis y axis)
VIRTUAL1 disconnected (normal left inverted right x axis y axis)
```

Monitor primer saat ini terdeteksi sebagai <code>eDP1</code> dengan resolusi/mode 1366x768.

Kemudian, sambungkan dengan proyektor

```bash
$ xrandr
Screen 0: minimum 8 x 8, current 1366 x 768, maximum 32767 x 32767
eDP1 connected primary 1366x768+0+0 (normal left inverted right x axis y axis) 310mm x 170mm
   1366x768      59.97*+
   1024x768      60.00  
   1024x576      60.00  
   960x540       60.00  
   800x600       60.32    56.25  
   864x486       60.00  
   640x480       59.94  
   720x405       60.00  
   680x384       60.00  
   640x360       60.00  
DP1 disconnected (normal left inverted right x axis y axis)
DP2 disconnected (normal left inverted right x axis y axis)
HDMI1 disconnected (normal left inverted right x axis y axis)
HDMI2 connected (normal left inverted right x axis y axis)
   1024x768      70.07 +  85.00    75.03    60.00  
   1920x1080     60.00    59.94  
   1600x1200     60.00  
   1280x1024     85.02    75.02  
   1440x900      59.89  
   1280x960      85.00  
   1280x800      59.81  
   1152x864      75.00  
   1280x720      60.00    59.94  
   1024x768i     86.96  
   832x624       74.55  
   800x600       85.06    72.19    75.00    60.32    56.25  
   640x480       85.01    75.00    72.81    66.67    60.00    59.94  
   720x400       87.85    70.08  
VIRTUAL1 disconnected (normal left inverted right x axis y axis)
```

Proyektor terdeteksi sebagai <code>HDMI2</code> dengan mode aktif 1024x768.

<code>eDP1</code> dan <code>HDMI2</code> sama-sama mempunyai mode 1024x768. Mode inilah yang akan dipakai.

Karena mode pada <code>eDP1</code> sekarang adalah 1366x768, maka harus disesuaikan menjadi 1024x768.

```bash
$ xrandr -s 1024x768
```

Selanjutnya apa yang tampil di monitor <code>eDP1</code> juga akan ditampilkan di proyektor (<code>HDMI2</code>) sama persis.

```bash
$ xrandr --output HDMI2 --mode 1024x768 --same-as eDP1
```

Kalau ingin menonaktifkan sambungan ke <code>HDMI2</code>

```bash
$ xrandr --output HDMI2 --off
```

 
Nah, setelah presentasi selesai, jangan lupa ubah lagi mode monitor <code>eDP1</code> ke 1366x768

```bash
$ xrandr -s 1366x768
```
