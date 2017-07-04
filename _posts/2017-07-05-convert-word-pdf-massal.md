---
layout: post
date: 2017-07-05
title: "Convert Word ke PDF Secara Massal"
tags: [slackware, office]
---

<code>LibreOffice</code> sudah lama mendukung konversi file dari Word/Writer (doc, docx dan odt) ke file pdf. Keunggulannya adalah bisa melakukan konversi secara massal.

Misalkan, dipunyai 1000 file <code>docx</code> yang tersimpan di <code>~/Documents</code>. Masing-masing file ini akan dikonversi menjadi <code>pdf</code> di <code>~/convert</code>.

```bash
$ soffice --headless --nologo --convert-to pdf:writer_pdf_Export --outdir ~/convert Documents/*.docx
```

Opsi <code>--headless --nologo</code> diberikan agar lebih cepat, lebih hemat waktu, karena tidak menampilkan _splash screen_.
