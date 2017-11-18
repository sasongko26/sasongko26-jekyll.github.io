---
layout: post
date: 2017-07-05
title: "Akibat Lupa eliloconfig"
tags: [slackware, kernel, elilo]
---

Kemarin melihat _ChangeLog_ ada beberapa _update_ yang sebagian di antaranya adalah _security fix_. Salah satu _update_ adalah kernel. Melakukan _upgrade_ semuanya baik-baik saja dan lanjut <code>shutdown</code>. Siang ini, <code>booting</code> pun masih _fine_ dan _no problem_. Begitu juga <code>login</code>. Baru terasa saat ingin masuk _desktop_ malah gagal.

```bash
$ startx
xauth:  file /home/sasongko/.serverauth.2717 does not exist


X.Org X Server 1.19.3
Release Date: 2017-03-15
X Protocol Version 11, Revision 0
Build Operating System: Slackware 14.2 Slackware Linux Project
Current Operating System: Linux darkstar 4.9.34 #2 SMP Sat Jun 24 13:00:18 CDT 2017 x86_64
Kernel command line: BOOT_IMAGE=dev000:\EFI\Slackware\vmlinuz  root=/dev/sda3 vga=normal ro ro
Build Date: 15 March 2017  04:19:30PM
 
Current version of pixman: 0.34.0
	Before reporting problems, check http://wiki.x.org
	to make sure that you have the latest version.
Markers: (--) probed, (**) from config file, (==) default setting,
	(++) from command line, (!!) notice, (II) informational,
	(WW) warning, (EE) error, (NI) not implemented, (??) unknown.
(==) Log file: "/var/log/Xorg.0.log", Time: Wed Jul  5 13:03:09 2017
(==) Using config file: "/etc/X11/xorg.conf"
(==) Using system config directory "/usr/share/X11/xorg.conf.d"
modprobe: FATAL: Module i915 not found in directory /lib/modules/4.9.34
modprobe: FATAL: Module i915 not found in directory /lib/modules/4.9.34
(EE) 
Fatal server error:
(EE) no screens found(EE) 
(EE) 
Please consult the The X.Org Foundation support 
	 at http://wiki.x.org
 for help. 
(EE) Please also check the log file at "/var/log/Xorg.0.log" for additional information.
(EE) 
(EE) Server terminated with error (1). Closing log file.
xinit: giving up
xinit: unable to connect to X server: Connection refused
xinit: server error
```

Weits, kernelnya masih 4.9.34, padahal kan kemarin sudah _upgrade_ ke 4.9.35. Baru ingat ternyata belum menjalankan <code>eliloconfig</code>. Setelah dijalankan dan <code>reboot</code> masalah selesai.
