---
layout: post
date: 2016-10-01
title: "Upgrade Plasma 5"
tags: [slackware, kde, desktop environment]
---
Secara resmi, _Slackware_ masih menggunakan KDE 4 yang "ketinggalan jaman" padahal pengembang KDE telah merilis KDE (sekarang biasa disebut **Plasma**) 5. Plasma 5 ini masih tetap seperti "kakaknya" (KDE 4) yang boros _memory_ dibandingkan _Xfce_. Tapi, masya Allah tampilan lebih keren!

Untuk menikmatinya, Eric Hameleer atau yang terkenal dengan nama Alien telah membuat _slackbuild_ dan _binary package_-nya yang bisa kita gunakan. Versi terakhir versi Eric saat ini adalah **Plasma 5.7.4** sedangkan insya Allah tanggal 4 Oktober 2016 KDE merilis Plasma 5.8.0.

Karena keterbatasan kuota internet (maklum tarif internet di Indonesia masih mahal), saya lebih suka langsung _download binary_ daripada _slackbuild_. Di sini saya gunakan 14.2  64 bit dan sejak awal tidak meng-_install_ paket dari kelompok **kdei**.

```bash
rsync -rvz --partial --progress --exclude=kdei rsync://slackware.uk/people/alien-kde/14.2/5/x86_64/ plasma5/
```

Selama proses _install_ oleh Eric dilarang menjalankan KDE maupun X, dalam artian _install_ dengan **runlevel 3**.

```bash
init 3
```

_Uninstall_ KDE 4 terlebih dahulu.

```bash
removepkg /var/log/packages/*-4.14.3-* libkscreen kscreen kactivities kde-workspace libmm-qt libnm-qt plasma-nm polkit-kde-agent-1 polkit-kde-kcmodules-1 kdeconnect-kde kdepimlibs
```

_Install_ dependensinya

```bash
cd plasma5
upgradepkg --reinstall --install-new deps/*.t?z
```

_Install_ Plasma 5 beserta aplikasinya

```bash
upgradepkg --reinstall --install-new kde/*/*.t?z
```

Nah, peng-_install_-an **Plasma 5** ini akan membuat beberapa konfigurasi baru. Silahkan pilih akan di-_overwrite, remove_, atau _ignore_.

```bash
slackpkg new-config
```

Setelah semua beres, jangan lupa untuk mengubah DE _default_

```bash
xwmconfig
```

Pilih <code>xinitrc.plasma</code>
