---
layout: post
date: 2020-05-29
title: Operasi direktori R
tags: [slackware, r]
---

# Mengetahui _working directory_
Secara _default, working directory_ pada **Slackware** adalah home directory user atau di mana _command_ <code>R</code> dijalankan. 
```R
getwd()
```
# Mengganti _working directory_
Misal, akan berpindah _working directory_ ke <code>Documents/project</code>
```R
setwd('Documents/project')
```
