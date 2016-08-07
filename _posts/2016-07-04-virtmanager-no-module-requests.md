---
layout: post
date: 2016-07-04
title: "Virt-Manager ImportError: No module named requests"
tags:
- slackware
- virtual manager
- qemu
- python
- virtualisasi
---
Setelah [_upgrade slackbuilds_]({% post_url 2016-07-03-upgrade-slackbuilds %}) kemarin ternyata <code>Virtual Machine Manager</code> tidak bisa dijalankan.

```bash
$ virt-manager
Traceback (most recent call last):
  File "/usr/share/virt-manager/virt-manager", line 33, in <module>
    from virtinst import util as util
  File "/usr/share/virt-manager/virtinst/__init__.py", line 89, in <module>
    from virtinst.distroinstaller import DistroInstaller
  File "/usr/share/virt-manager/virtinst/distroinstaller.py", line 23, in <module>
    from . import urlfetcher
  File "/usr/share/virt-manager/virtinst/urlfetcher.py", line 34, in <module>
    import requests
ImportError: No module named requests
```
Ternyata, ada masalah dependensi. <code>ImportError: No module named requests</code> menunjukkan tidak adanya modul <code>requests</code>, atau tidak terinstall paket <code>python-requests</code>. Ini dibuktikan dengan _output_ <code>ls /var/log/packages|grep python-request</code> yang kosong.

Terus bagaimana?

Install <code>python-requests</code> melalui <code>sbopkg</code>

```bash
sbopkg -i python-requests
```
