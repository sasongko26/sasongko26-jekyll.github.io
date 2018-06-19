---
layout: post
date: 2018-06-18
title: "Pentingnya Shebang"
tags: [slackware, terminal, perl]
---

# Shebang itu apa?

Pengguna linux, BSD, ataupun mac yang terbiasa melihat _source code_ sangat mungkin sudah tidak asing lagi dengan **shebang**. Ada yang menyebut shebang sebagai **sh bang**, **shabang**, **hashbang**, **hashpling**, dan **poundbang**. Shebang ini dituliskan di baris pertama, yakni diawali dengan <code>#!</code>.

Contoh, untuk **perl** :

```
#!/usr/bin/perl
```

atau

```
#!/usr/bin/env perl
```

Sebagai pengguna linux khususnya **Slackware**, _user_ akan merasakan betapa pentingnya shebang ini. Kepentingannya terkait fungsi shebang itu sendiri dan bagaimana _user_ menjalankannya. 

# Fungsi shebang

Shebang berfungsi untuk memberi tahu sistem (pada komputer), **interpreter** apa yang digunakan. Apakah shell? Kalau shell, mau pakai bash, csh, ksh, atau zsh? Apakah perl? Ataukah python? Ataukah ruby?

# Bagaimana menjalankannya

Ada 2 cara yang biasa dilakukan untuk menjalankan program :

- Menyertakan interpreternya di awal _command_

Contoh :

```bash
perl program.pl
```

- Tanpa menuliskan interpreternya

Contoh :

```bash
./program.pl
```

Cara ini mengharuskan programnya (<code>program.pl</code>) dijadikan _executable_ terlebih dahulu, sehingga bisa dieksekusi/dijalankan tanpa harus menuliskan interpreternya, yaitu dengan cara

```bash
chmod +x program.pl
```

# Contoh kasus

Misalnya, ada sebuah program yang filenya bernama <code>tes</code>, yang isinya

```
$a = 5

print $a
```

Bagi orang yang sudah berpengalaman (terutama programmer) bisa saja dengan cepat menentukan bahasa atau interpreter apa yang digunakan. Tapi bagaimana dengan yang "jam terbang" _coding_ nya masih baru? Atau yang awam seperti saya? Mungkin bingung dan akan coba-coba. Ya, coba-coba karena filenya tanpa ekstensi. Kalau ada ekstensinya kan bisa lebih mudah, langsung ketahuan.

- bash

```bash
$ bash tes
tes: line 1: =5: command not found
tes: line 3: print: command not found
```

- csh

```shell
$ csh tes
a: Undefined variable.
```

- ksh

```shell
$ ksh tes
tes: line 1: =5: not found
```

- zsh

```shell
$ zsh tes
tes:1: 5 not found
```

- perl

```bash
$ perl tes
syntax error at tes line 3, near "print"
Execution of tes aborted due to compilation errors.
```

- python

```bash
$ python tes
  File "tes", line 1
    $a=5
    ^
SyntaxError: invalid syntax
```

- ruby

```bash
$ ruby tes
5
```

Ternyata ruby! 

Di sisi lain, mari kita anggap saja tidak mau ambil pusing ini interpreternya apa. Pakai cara kedua.

```bash
$ ./tes
./tes: line 1: =5: command not found
./tes: line 3: print: command not found
```

Waduh.... error!

Nah, tidak menuliskan shebang ternyata bisa menimbulkan masalah. Kalau begini, tentu saja kontraproduktif dengan tujuan dibuatnya program sebagai sarana _problem solving_/menyelesaikan masalah.
