---
layout: post
title: "pip InsecurePlatformWarning"
date: 2016-01-21
tags : 
- slackware
- blankon
- python

---
Saat melakukan pencarian dengan pip, muncul pesan
```
/usr/lib64/python2.7/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:315: SNIMissingWarning: An HTTPS request has been made, but the SNI (Subject Name Indication) extension to TLS is not available on this platform. This may cause the server to present an incorrect TLS certificate, which can cause validation failures. For more information, see https://urllib3.readthedocs.org/en/latest/security.html#snimissingwarning.
  SNIMissingWarning
/usr/lib64/python2.7/site-packages/pip/_vendor/requests/packages/urllib3/util/ssl_.py:120: InsecurePlatformWarning: A true SSLContext object is not available. This prevents urllib3 from configuring SSL appropriately and may cause certain SSL connections to fail. For more information, see https://urllib3.readthedocs.org/en/latest/security.html#insecureplatformwarning.
  InsecurePlatformWarning
```
Biar peringatan ini tidak muncul lagi, ndg-httpsclient harus diupgrade.
```
pip install --upgrade ndg-httpsclient
```
