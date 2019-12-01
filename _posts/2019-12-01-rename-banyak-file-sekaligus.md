---
layout: post
date: 2019-12-01
tilte: "Rename Banyak File Sekaligus"
tags: [slackware, manajemen file]
---

Tak terasa ternyata sudah lebih dari 3 bulan tidak _posting_. Mengapa? Sibuk? Kesibukan sebenarnya seperti biasa. Tidak ada peningkatan kesibukan secara signifikan. Lalu mengapa? Alasannya simpel. Karena semua kegiatan berkomputer baik-baik saja. Tidak ada masalah. Biasanya saya menulis di sini ketika saya menghadapi masalah terkait penggunaan komputer. Nah, kali ini masalahnya adalah saya menemukan banyak file yang namanya tidak sesuai dengan standar saya. 

Contoh, adik-adik asisten anatomi mengirimkan _softcopy_ materi asistensi. Penamaan file yang diberikan adik-adik adalah berawalan dengan **MC** untuk materi _systema musculoskeletale_. Saya ingin melakukan _rename_ semua file tersebut yang semula berawalan **MC** menjadi berawalan **Asistensi Anatomi Syst Musculoskeletale**. Perubahan nama banyak file dengan nama yang cukup panjang tentu saja menyita waktu. Sebenarnya ini masih sangat mendingan, hanya 6 file. _Rename_ satu-persatu sebenarnya tidak masalah juga. Tapi **bagaimana kalau kasus serupa jumlah filenya puluhan, ratusan bahkan ribuan?** Era industri 4.0 semakin menuntut efisiensi waktu. Efisiensi waktu ini berdampak pada efisiensi tenaga, baik itu tenaga _brainware_ maupun komputernya yang kemudian mengakibatkan efisiensi biaya. 

Alhamdulillah, GNU/Linux terutama **Slackware** secara _default_ bisa melakukan hal itu dengan mudah.

```bash
$ for file in MC*; do mv "$file" "${file/MC/Asistensi\ Anatomi\ Syst\ Musculoskeletale}"; done
```
