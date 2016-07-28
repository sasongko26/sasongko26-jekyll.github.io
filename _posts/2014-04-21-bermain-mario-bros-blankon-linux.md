---
layout: post
title: "Bermain Super Mario Bros di BlankOn Linux"
date: 2014-04-21 03:12:57
tags: blankon
---
Masih ingat dengan ini?

![](/gambar/supermario-linux-1.png)

Ya! itu adalah permainan Super Mario Brothers atau yang lebih biasa disebut Mario Bros. Waktu kami kecil dulu, akhir dekade 90an, hobi bermain nintendo, di rumahnya Arip sama Icang, ya main Mario ini sampai kadang lupa waktu. Hehehehe.....
Nostalgia, kalau pengguna BlankOn ingin memainkannya silahkan.

{% highlight bash %}
$ sudo apt-get install supermario
{% endhighlight %}

Untuk memainkannya klik menu Aplikasi > Permainan > Super Mario
![](/gambar/supermario-linux-2.png)

Untuk memainkan mario di ubuntu caranya tidak jauh beda.
Pertama, unduh dulu berkasnya [di sini](http://kambing.ui.ac.id/blankon/pool/extras-restricted/s/supermario/supermario_0.2_all.deb)
Kemudian install berkasnya

{% highlight bash %}
sudo dpkg -i supermario_0.2_all.deb
muncul error dpkg: dependency problems prevent configuration of supermario:
 supermario depends on maleo; however:
  Package maleo is not installed.

dpkg: error processing supermario (--install):
 dependency problems - leaving unconfigured
{% endhighlight %}

dan 

{% highlight bash %}
Errors were encountered while processing:
 supermario
{% endhighlight %}
biarkan saja.

Supermario sudah terinstall. Silahkan mainkan dengan browser buka alamat file:///usr/share/supermario/mario.html
![](/gambar/supermario-ubuntu.png)
