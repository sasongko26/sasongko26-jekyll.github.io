---
layout: post
date: 2020-05-22
title: Mengenal objek R factor
tags: [slackware, r]
---
Factor adalah representasi data kategorik. Factor bisa dibuat dengan fungsi <code>factor()</code> atau <code>cut()</code>. Saya lebih sering menggunakan <code>cut()</code> karena lebih aplikatif saat akan mengubah skala data dari rasio atau interval ke ordinal.

Contoh, bmi adalah data _body mass index_ (BMI) atau indeks massa tubuh (IMT). Klasifikasi IMT ada 4 macam, yaitu
- < 18,5 : underweight
- 18,5 - 24,99 : normal
- 25 - 29,99 : overweight
- \> 30 : obese/obesitas
Untuk obesitas, masih bisa diklasifikasikan menjadi 3
- 30 - 34,99 : obese class 1
- 35 - 39,99 : obese class 2
- \> 40 : extreme obesity

```R
> bmi <- c(20, 21.5, 18, 24, 26, 28, 25.5, 20.5)
> kategori <- cut(bmi, breaks=c(0, 18.5, 25, 30, 35, 40, Inf), labels=c('Underweight', 'Normal', 'Overweight', 'Obese Class 1', 'Obese Class 2', 'Extreme Obesity')
> View(kategori)
1 Normal
2 Normal
3 Underweight
4 Normal
5 Overweight
6 Overweight
7 Overweight
8 Normal
```
kategori pada data di atas, adalah factor yang saya buat dengan 6 level, yaitu Underweight, Normal, Overweight, Obese Class 1, Obese Class 2, Extreme Obesity. Berhubung sumber data kategori berasal dari bmi, maka ketika di-View, yang terlihat hanya kategori Normal, Underweight dan Overweight, menyesuaikan dengan data yang diberikan.
