---
layout: post
date: 2016-07-05
title: "Virtual Manager unable to connect to libvirt"
tags: 
- slackware
- virtual manager
- qemu
- virtualisasi
---
Melanjutkan [catatan kemarin]({% post_url 2016-07-04-virtmanager-no-module-requests %}), ternyata <code>Virtual Manager</code> belum bisa berjalan dengan baik. Sudah ada kemajuan sih dibanding yang kemarin, sudah bisa terbuka _graphical front-end_-nya, tapi ternyata kemudian muncul kotak dialog <code>Virtual Machine Manager Connection Failure</code> dengan detail sebagai berikut

```bash
Unable to connect to libvirt.

internal error: Cannot find suitable emulator for x86_64

Libvirt URI is: qemu:///system

Traceback (most recent call last):
  File "/usr/share/virt-manager/virtManager/connection.py", line 979, in _open_thread
    self._populate_initial_state()
  File "/usr/share/virt-manager/virtManager/connection.py", line 941, in _populate_initial_state
    logging.debug("conn version=%s", self._backend.conn_version())
  File "/usr/share/virt-manager/virtinst/connection.py", line 316, in conn_version
    self._conn_version = self._libvirtconn.getVersion()
  File "/usr/lib64/python2.7/site-packages/libvirt.py", line 3984, in getVersion
    if ret == -1: raise libvirtError ('virConnectGetVersion() failed', conn=self)
libvirtError: internal error: Cannot find suitable emulator for x86_64
```

Cek <code>qemu</code> apakah masih terinstall atau tidak. Harusnya sih memang terinstall karena saya belum pernah menghapusnya.

```bash
$ ls /var/log/packages|grep qemu
qemu-2.6.0-x86_64-1_SBo
```

Disebutkan <code>Unable to connect to libvirt</code> dengan <code>Libvirt URI is: qemu:///system</code>, dan <code>internal error: Cannot find suitable emulator for x86_64</code>, padahal terinstall <code>qemu</code> ini kan aneh. Pasti ada masalah dengan <code>qemu</code>-nya.

```bash
$ qemu-system-x86_64
qemu-system-x86_64: error while loading shared libraries: libcacard.so.0: cannot open shared object file: No such file or directory
```

Nah, ada titik terang. Masalah dependensi. <code>libcacard</code> tidak ada, berarti harus diinstall. Tapi installnya dari mana?

Pertama, asumsikan <code>libcacard</code> ini paket resmi dari **Slackware**. Cek dengan <code>slackpkg</code>

```bash
slackpkg search libcacard

Looking for libcacard in package list. Please wait... DONE

No package name matches the pattern.
```

Karena tidak ada, cek <code>sbopkg</code> karena <code>qemu</code> installnya dari <code>sbopkg</code>

```bash
sbopkg -g libcacard
Searching for libcacard
Found the following matches for libcacard:
libraries/libcacard
```

OK, ketemu. Ada <code>sbopkg</code>-nya, install!

```bash
sbopkg -i libcacard
```

install selesai. Konfirmasi <code>qemu</code> dengan <code>qemu-system-x86_64</code> apakah masih bermasalah. Ternyata ok. Lanjut buka <code>virt-manager</code>-nya. Ok. Done! Alhamdulillah...
