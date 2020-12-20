---
layout: post
title: "Download ISO BlankOn dengan ZSync"
date: 2014-04-15 07:22:12
tags: blankon
---
Sebagai anggota Quality Assurance (Tim Jaminan Kualitas) BlankOn, kami bertanggung jawab untuk menemukan kutu (bugs) sebanyak-banyaknya. Hampir setiap hari rilis iso baru dan 2 bulan sekali ada rilis kandidat baru, istilahnya sih jahitan.Tiap berkas iso baik itu i386 maupun amd64 berukuran sekitar 1GB. Kalau setiap hari iso tersebut harus diunduh, waaahhhh bakal tekor! :D

Alhamdulillah iso BlankOn bisa diunduh dengan rsync dan zsync sehingga bisa lebih hemat karena tidak perlu mengunduh semua isi iso tapi hanya perubahannya saja. Walau demikian, kami akan sampaikan yang zsync nya saja dulu. Cara menggunakan zsync sangat mudah.
# Install zsync
{% highlight bash %}
$ sudo apt-get install zsync
{% endhighlight %}

# Download dengan Zsync
Sebelumnya sudah ada iso yang kita miliki
{% highlight bash %}
$ ls
tambora-desktop-amd64.iso
tambora-desktop-i386.iso
{% endhighlight %}

Akan diunduh iso yang berarsitektur 64 bit (tambora-desktop-amd64.iso) yang terbaru. Pada direktori di mana tersimpan berkas iso jalankan zsync. 
{% highlight bash %}
$ zsync url_iso
$ zsync http://cdimage.blankonlinux.or.id/blankon/livedvd-harian/current/tambora-desktop-amd64.iso.zsync 
#################### 100.0% 43.9 kBps DONE      

reading seed file tambora-desktop-amd64.iso ***********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************Read tambora-desktop-amd64.iso. Target 67.5% complete.      
downloading from http://cdimage.blankonlinux.or.id/blankon/livedvd-harian/current/tambora-desktop-amd64.iso: 
#############------- 68.4% 3.9 kBps         ETA  
#############------- 69.7% 5.5 kBps         ETA  
{% endhighlight %}
Tampak bahwa iso yang sudah ada berbeda dengan iso yang terbaru. Iso lama berisi 67,5% iso terbaru. Jadi dalam kasus ini mengunduh dengan zsync lebih hemat 67,5% daripada mengunduh keseluruhan iso dari awal.
