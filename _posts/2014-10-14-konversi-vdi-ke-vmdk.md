---
layout: post
title: "Konversi VDI ke VMDK"
date: 2014-10-14 09:43:09
tags: 
- Slackware
- BlankOn
- Virtualisasi

---

Secara default, format hardisk virtual pada virtualbox adalah VDI. Format ini tidak bisa digunakan di vmware. Agar bisa digunakan di vmware harus dikonversi dulu menjadi VMDK. Kalau sudah terpasang virtualbox konversi VDI ke VMDK ini mudah.

Misalkan hardisk01.vdi akan dikonversi menjadi hardisk02.vmdk, maka caranya
```
$ VBoxManage clonehd hardisk01.vdi hardisk01.vmdk --format VMDK 
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100% 
Clone hard disk created in format 'VMDK'. UUID: 3127e4c2-6a88-4af6-838a-871cd534b5fa
```
Hardisk virtualnya sudah terkonversi.
