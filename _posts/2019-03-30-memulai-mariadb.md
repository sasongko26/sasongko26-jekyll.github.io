---
layout: post
title: "Memulai MariaDB"
date: 2019-03-30
tags: [slackware, database]
---
# Apa itu MariaDB

MariaDB adalah _software_ untuk manajemen basis data atau database. Merupakan pengembangan dari MySQL karena pada tahun 2010 MysSQL diakuisisi oleh Oracle.

# Install MariaDB

Secara _default_, apabila Slackware diisnntall _full system_ maka MariaDB akan terinstall. Jadi tidak usah repot-repot untuk insytallnya.

# Memulai MariDB

Sebelum memulai, ada beberapa konfigurasi yang perlu dilakukan agar semua berjalan dengan baik. _prompt_ <code>R/</code> menunjukkan dilakukan dengan _priviledge_ <code>root</code>

```bash
R/ mysql_install_db
R/ chown -R mysql:mysql /var/lib/mysql
R/ chmod +x /etc/rc.d/rc.mysqld # kalau ingin service mariadb langsung saat booting
R/ mysqladmin -u root password # set password root
```

Untuk masuk ke mariadb

```bash
mysql -u [namauser]
```
