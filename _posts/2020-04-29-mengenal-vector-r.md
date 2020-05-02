---
layout: post
title: Mengenal Objek R Vector
date: 2020-04-29
tags: [slackware, r]
---
Sebagai bahasa pemrograman, R mempunyai beberapa tipe objek, antara lain vector, matrix, factor, data frame, list. Bagi yang pernah berkecimpung di bahasa pemrograman lain mungkin tipe objek ini terasa aneh. R adalah bahasa pemrograman spesialis data, maka tipe objeknya pun disesuaikan agar mudah meng-_handle_ data.

Vector merupakan objek yang sangat penting di R. Bisa dikata, semua data berasal dari vector.

# Apa sih vector?
Mudahnya, vector bisa dikatakan sebagai variabel. Vector ini berisi elemen (datum atau data) yang seragam, bisa berupa angka atau karakter/string atau bisa juga _boolean (TRUE FALSE)_.
# Membuat vector
Misalkan akan dibuat vector x dengan elemen berupa angka 1
```R
> x <- 1
```
Vector kota dengan elemen kata Semarang. Semarang merupakan string, maka penulisannya diapit tanda kutip
```R
> kota <- "Semarang"
```
Vector cek dengan elemen boolean TRUE
```R
cek <- TRUE
```
Jika vectornya memiliki elemen lebih dari 1, membuatnya dengan _function_ yang bernama _combine_. _Function_ ini didefinisikan dengan <code>c()</code>, elemennya dituliskan dalam tanda kurung. 
```R
> nama <- c("Ali", "Budi", "Cici", "Deni", "Eka")
> tinggi_badan <- c(155, 178, 163, 158, 142)
```
# Operasi vector
## menampilkan vector
Untuk menampilkan elemen atau isi dari vector cukup tuliskan nama vectornya. Contoh, menampilkan data tinggi badan yang dimasukkan ke dalam vector tinggi_badan
```R
> tinggi_badan
```
Angka dalam kurung siku di sebelah kiri pada tiap baris yang ditampilkan menunjukkan indeks/letak data ke berapa. Contoh [1] berarti data tepat di sebelah kanannya adalah data pertama. [20] berarti data tepat di kanannya adalah data ke-20. Begitu seterusnya. 
## length()
Fungsi <code>length()</code> digunakan untuk mengetahui panjang vector (sebenarnya tidak hanya berlaku untuk vector, tapi juga objek lain seperti factor). Ketika data sudah dipegang, apa yang kemudian dilakukan? Ya, mengecek data. Salah satu pengecekannya adalah apakah data sudah lengkap? Kalau kuesioner yang harus diisi ada 10 item, apakah semua item sudah diisi? Ini contoh penggunaan <code>length()</code> dalam praktik.

Contoh, akan dicek berapa banyaknya data tinggi\_badan 
```R
> length(tinggi_badan)
5
```
## Indeks
Indeks menunjukkan letak data tersebut. Penulisannya <code>namavector[nomer\_indeks]</code>. Angka dalam kurung siku adalah nomor indeksnya. Contoh
```R
> nama <- c("Ali", "Budi", "Cici", "Deni", "Eka")
> nama[1]
[1] "Ali"
> nama[5]
[1] "Eka"
```
Kalau ingin menampilkan pengecualian gunakan indeks negatif. Misalnya, akan menampilkan 4 data pertama, berarti data ke-5 tidak ingin ditampilkan, maka
```R
> nama[-5]
[1] "Ali"  "Budi" "Cici" "Deni"
```
## _replace_ elemen
Apabila ada data yang ternyata tidak sesuai, _typo_ atau salah ketik misalnya, bisa diganti. Misalnya data nama, data ke-5 diganti dari Eka menjadi Erna
```R
> nama[5] <- "Erna"
```
Penggantian ini bisa juga lebih dari 1 elemen. Misalkan data ke-4 dan 5 diganti menjadi Dedi dan Ema.
```R
> nama[c(4,5)] <- c("Dedi", "Ema")
```
## Menambah elemen
Misalkan data nama akan ditambahkan dengan Fahri, Gandi, Hilda, Imam, Joko.
```R
> nama <- append(nama,c("Fahri", "Gandi", "Hilda", "Imam", "Joko"))
[1] "Ali"   "Budi"  "Cici"  "Dedi"  "Ema"   "Fahri" "Gandi" "Hilda" "Imam" 
[10] "Joko"
```
## Menghapus elemen
Misalkan akan dihapus nama Budi yang merupakan elemen ke-2
```R
> nama <- nama[-2]
```
## Operasi matematika
Misalkan, untuk keperluan menghitung _body mass index_ atau indeks massa tubuh (IMT). Tinggi badan yang digunakan adalah dalam satuan meter. Sementara data yang masuk dalam centimeter. Akan dibuat variabel baru (berupa vector tentunya) IMT yang diperoleh dari menghitung berat\_badan dibagi kuadrat tinggi\_badan dalam meter.
```R
IMT <- berat_badan/(tinggi_badan/100)^2
```
