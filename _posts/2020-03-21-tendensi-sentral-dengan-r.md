---
layout: post
date: 2020-03-21
title: Tendensi Sentral dengan R
tags: [slackware, r]
---
Data yang digunakan :
```R
> nilai
[1] 25 60 79 32 57 74 52 70 82 36 75 77 81 95 41 65 92 85 55 66 52 10 64 75 78
[26] 25 80 98 81 67 41 71 83 54 64 72 88 62 74 45 60 78 89 76 48 84 84 90 15 79
[51] 35 67 17 82 69 74 63 80 85 61
```

# Mean
```R
> mean(nilai)
[1] 65.31667
```
Rerata nilai adalah 65,31667.

# Median
## Cara 1 : menggunakan median()
```R
> median(nilai)
[1] 70.5
```

## Cara 2 : menggunakan quantile()
Karena median tak lain adalah kuartil 2 atau dengan kata lain posisinya di tengah-tengah atau pada posisi 50% maka
```R
> quantile(nilai, 0.5)
 50% 
70.5
```

Median nilai adalah 70,5.

# Modus
```R
> names(which.max(table(nilai)))
[1] "74"
```
Modus adalah 74.

# Kuartil 1
```R
> quantile(nilai, 0.25)
  25% 
54.75
```
Kuartil 1 nya adalah 54,75.

# Kuartil 3
```R
> quantile(nilai, 0.75)
  75% 
80.25
```
Kuartil 3 adalah 80,25.
