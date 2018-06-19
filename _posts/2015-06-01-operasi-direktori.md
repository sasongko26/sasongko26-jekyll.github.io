---
layout: post
title: "Operasi Direktori di Linux"
date: 2015-06-01
tags: 
- slackware
- blankon
- terminal

---
Operasi direktori/folder adalah suatu hal yang mendasar di linux. Walaupun sekarang banyak desktop environment yang menyebabkan sedikit interaksi dengan terminal langsung karena tinggal klik saja dalam mode grafis (GUI), kami akan tetap sampaikan bagaimana melakukannya dalam mode teks (CLI).

# Mengetahui posisi direktori sekarang
Gunakan
```
pwd
```

untuk mengetahui saat ini aktif di mana. Contoh

```
$ pwd
/home/sasongko
```

Tampak bahwa direktori saat ini adalah di /home/sasongko.

# Menampilkan isi direktori
```
ls /direktori
```

Contoh berikut akan menampilkan isi dari direktori /etc
```
$ ls /etc
ConsoleKit		   hosts.allow		  pine.conf
DIR_COLORS		   hosts.deny		  pkcs11
HOSTNAME		   hosts.equiv		  pm
ImageMagick-6		   hp			  polkit-1
NetworkManager		   htdig		  ppp
UPower			   httpd		  printcap
X11			   identd.conf		  profile
a2ps-site.cfg		   idn.conf.sample	  profile.d
a2ps.cfg		   idnalias.conf.sample   proftpd.conf
acpi			   im_palette-small.pal   protocols
adjtime			   im_palette-tiny.pal	  quotagrpadmins-sample
alsa			   im_palette.pal	  quotatab-sample
anthy-conf		   imrc			  radiusclient
asciidoc		   inetd.conf		  random-seed
asound.state		   init.d		  rc.d
at-spi2			   inittab		  rc0.d
at.deny			   inputrc		  rc1.d
auto.master		   iproute2		  rc2.d
auto.master.d		   irssi.conf		  rc3.d
auto.misc		   issue		  rc4.d
auto.net		   issue.net		  rc5.d
auto.smb		   joe			  rc6.d
autofs_ldap_auth.conf	   kde			  rc_keymaps
avahi			   ld.so.cache		  rc_maps.cfg
bash_completion.d	   ld.so.conf		  request-key.conf
bind.keys		   lftp.conf		  request-key.d
bluetooth		   libnl		  resolv.conf
bootptab		   lilo.conf_example	  rmt
ca-certificates		   localtime		  rndc.key
ca-certificates.conf	   localtime-copied-from  rpc
cgconfig.conf		   login.access		  samba
cgred.conf		   login.defs		  sane.d
cgrules.conf		   logrotate.conf	  scim
cgsnapshot_blacklist.conf  logrotate.d		  screenrc
conntrackd		   lrzip.conf		  securetty
cron.d			   lvm			  sensors.d
cron.daily		   lxc			  sensors3.conf
cron.hourly		   lynx.cfg		  serial.conf
cron.monthly		   lynx.lss		  services
cron.weekly		   mail			  sgml
crypttab		   mc			  shadow
csh.login		   mcelog		  shadow-
cups			   mdadm.conf		  shells
cupshelpers		   mediaprm		  skel
dbus-1			   mercurial		  slackpkg
default			   minicom.users	  slackware-version
dhclient.conf		   minirc.dfl		  slrn.rc
dhclient.conf.example	   misc			  slsh.rc
dhcpcd.conf		   mke2fs.conf		  smartd.conf
dhcpcd.duid		   mkinitrd.conf.sample   snmp
dhcpd.conf		   modprobe.d		  soma
dhcpd.conf.example	   motd			  ssh
dialogrc		   mplayer		  ssl
distcc			   mtab			  stunnel
dnsmasq.conf		   mtab.fuselock	  sudoers
dnsmasq.d		   mtools.conf		  sudoers.d
drirc			   mutt			  syslog.conf
enscript.cfg		   my.cnf		  sysstat
esd.conf		   my.cnf.d		  termcap
ethertypes		   mysqlaccess.conf	  termcap-BSD
exports			   nail.rc		  termcap-Linux
fb.modes		   named.conf		  tin
file			   nanorc		  udev
fonts			   netatalk		  udisks2
foomatic		   netgroup		  ulogd.conf
fstab			   networks		  uniconf.conf
ftpusers		   nfsmount.conf	  updatedb.conf
gamin			   nntpserver		  usb_modeswitch.conf
gconf			   nscd.conf		  usb_modeswitch.d
genpowerd.conf		   nsswitch.conf	  uucp
gettydefs		   nsswitch.conf-nis	  vga
gimp			   ntp			  virtuoso.ini
gnupg			   ntp.conf		  vsftpd.conf
gpm-root.conf		   ntp.conf.orig	  warnquota.conf-sample
gpm-syn.conf		   obex-data-server	  wgetrc
gpm-twiddler.conf	   openldap		  wpa_supplicant.conf
group			   openvpn		  wvdial.conf
group-			   organization		  xboard.conf
grub.d			   os-release		  xdg
gshadow			   pango		  xml
gtk			   passwd		  xpdfrc
gtk-2.0			   passwd-		  yp.conf
gtk-3.0			   pcmcia		  ytalkrc
hardwareclock		   pear.conf		  zprofile
host.conf		   php
hosts			   php-fpm
```

# Masuk ke direktori
Gunakan 
```
cd /direktori
```
untuk masuk atau berpindah ke direktori lainnya.

Untuk berpindah ke direktori di atasnya
```
cd ..
```

Sedangkan untuk kembali ke direktori home
```
cd
```

# Membuat direktori baru
```
mkdir /direktori_yang_ingin_dibuat
```

# Menyalin direktori
```
cp /direktori_awal /direktori_baru
```

# Memindah direktori
```
mv /direktori_awal /direktori_baru
```

# Menghapus direktori
Kalau direktori itu kosong
```
rmdir /direktori
```

Kalau ada isinya dan ingin menghapus direktori beserta isinya
```
rm -r /direktori
```

