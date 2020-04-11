---
layout: post
title: Install JASP
tags: [slackware, r]
date: 2020-04-11
---
JASP, singkatan dari Jeffreys's Amazing Statistic Program, merupakan _open source statistics software_. Software ini layak dijadikan pilihan utama karena:

1. _Open source_. Karena _open source_ semua orang boleh memakai, melihat _source code_-nya dan berkontribusi (melaporkan masalah, mengusulkan fitur dan perbaikan). Silahkan menuju ke https://github.com/jasp-stats/jasp-desktop .
2. Pengembangan dinaungi oleh akademisi dari University of Amsterdam, Duke University, University of Southampton, UNiversity of Sussex, University of Missouri, Athens University of Economics dan Business, Missouri State University, University of Groningen, Nyenrode Business University, University of Zurich dan Ludwig-Maximilians-Universität München.
3. Menyediakan berbagai analisis baik analisis frequentist maupun Bayesian. 
4. Tabel hasil dalam format APA yang dengan mudahnya di-copas ke _word processosr_ seperti LibreOffice Writer atau Microsoft Word.
5. Tersedia untuk Linux, MacOS, dan Microsoft Windows.

# Install JASP
Karena saya memakai **Slackware** maka cara yang ditulis di sini tentu saja yang berlaku untuk Slackware dan linux umumnya.
Install menggunakan flatpak. Flatpak tersedia di SBo. Untuk install membutuhkan download dari repo sekitar 1,4GB. 
```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.jaspstats.JASP
```
