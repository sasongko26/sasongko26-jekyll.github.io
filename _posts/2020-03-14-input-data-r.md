---
layout: post
date: 2020-03-14
title: Input Data R
tags: [slackware, r, statistik]
---
Input data dalam R sangat mudah dan ada beragam cara, yaitu:

1. Menuliskan dalam bentuk _syntax_.  Data diinput sebagai vektor. Penulis lebih suka menggunakan cara ini apabila data tersebut 1 variabel saja dan banyaknya tidak lebih dari 30. Kadang juga penulis gunakan untuk data yang banyaknya kurang dari 100
2. Melalui data frame. Data diinput ke dalam bentuk tabel. Baris tabel menunjukkan kasus sedangkan kolomnya adalah variabel. Cocok digunakan apabila lebih dari 1 variabel.
3. Import dari file. Data dibuat tanpa menggunakan R dan disimpan ke dalam bentuk file. Data bisa dibuat menggunakan text editor (contoh vim, gvim, nano, pico, kate), aplikasi perkantoran (LibreOffice Calc dan Microsoft Excel) atau aplikasi statistik lainnya seperti SPSS, Minitab, dan Stata).

Pada kesempatan ini yang digunakan adalah cara pertama. Misalkan datanya adalah nilai ujian dari 60 mahasiswa sebagai berikut :

25 60 79 32 57 74 52 70 82 36 75 77 81 95 41 65 92 85 55 66 52 10 64 75 78 25 80 98 81 67 41 71 83 54 64 72 88 62 74 45 60 78 89 76 48 84 84 90 15 79 35 67 17 82 69 74 63 80 85 61.

_Syntax_-nya

```R
nilai <- c(25, 60, 79, 32, 57, 74, 52, 70, 82, 36, 75, 77, 81, 95, 41, 65, 92, 85, 55, 66, 52, 10, 64, 75, 78, 25, 80, 98, 81, 67, 41, 71, 83, 54, 64, 72, 88, 62, 74, 45, 60, 78, 89, 76, 48, 84, 84, 90, 15, 79, 35, 67, 17, 82, 69, 74, 63, 80, 85, 61)
```

Untuk menampilkan data tersebut

```R
nilai
 [1] 25 60 79 32 57 74 52 70 82 36 75 77 81 95 41 65 92 85 55 66 52 10 64 75 78
[26] 25 80 98 81 67 41 71 83 54 64 72 88 62 74 45 60 78 89 76 48 84 84 90 15 79
[51] 35 67 17 82 69 74 63 80 85 61
```

Kemudian, disarankan untuk mengecek apakah data sudah lengkap. 

```R
length(nilai)
[1] 60
```

_Output_ 60, sama dengan jumlah mahasiswa yang mengikuti ujian. Dengan demikian data sudah lengkap dan siap diolah lebih lanjut.
