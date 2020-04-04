---
layout: post
date: 2020-04-04
title: Dispersi Data dengan R
tags: [slackware, r]
---
Dispersi atau ukuran penyebaran data menunjukkan seberapa bervariasi suatu data.
Kali ini data yang digunakan diambil dari dataset **ldeaths** yang merupakan bagian dari **UKLungDeaths**. Dataset **UKLungDeaths** berisi data jumlah kematian akibat penyakit bronchitis, emphysema dan asma di Inggris dalam kurun waktu 1974-1979. Data ini disajikan berdasarkan bulan dan jenis kelamin. Secara total untuk kedua jenis kelamin ada di **ldeaths**, laki-laki **mdeaths** dan perempuan **fdeaths**.

# Nilai minimal
```R
min(ldeaths)
[1] 1300
```
# Nilai maksimal
```R
max(ldeaths)
[1] 3891
```
# Range
```R
range(ldeaths)
[1] 1300 3891
```
# Varians
```R
var(ldeaths)
[1] 371911.8
```
# Standar deviasi
```R
sd(ldeaths)
[1] 609.8457
```
