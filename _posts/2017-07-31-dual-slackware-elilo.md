---
layout: post
date: 2017-07-31
title: "Multi Slackware dengan elilo"
tags: [slackware,elilo,btrfs]
---
Posting kali ini terinspirasi dari Pak Walesa yang menulis [di sini](http://walecha.web.id/node/57) dan [ini](http://walecha.web.id/node/58). Perbedaannya adalah pada _boot loader_ yang digunakan. Saya gunakan <code>elilo</code>. Selain itu, sudah ada _existing_ Slackware64 current dan Slackware64 14.2. Keduanya dengan filesystem ext4. Mau ditambahkan yang stable (Slackware64 14.2 dan Slackware 14.2) tetapi dengan _filesystem btrfs_. Jadi dual Slackware stable ini ditempatkan di dalam partisi yang sama dan Slackware64 current di partisi sendiri. Sebenarnya _tripleboot_ dengan Windows 10, tetapi Windows 10 sangat jarang dipakai. Jadi abaikan saja Windowsnya.

Berikut skema partisi harddisk (_free space_, partisi ext4 Slackware64 14.2 dan partisi Windows 10 diabaikan) :

```bash
HDD
+---> partisi EFI (/dev/sda1)
+---> partisi swap (/dev/sda2)
+---> partisi / current format ext4 (/dev/sda3)
+---> partisi /home current format ext4 (/dev/sda4)
+---> partisi / stable format btrfs (/dev/sda8)
```

Partisi untuk stable inipun baru saya bikin. Maka perlu diformat dulu

```bash
mkfs.btrfs /dev/sda8
```

Selanjutnya partisi ini dimount ke <code>/mnt/hd</code> dan buat subvolume baru (jumlah sesuaikan dengan kebutuhan). Saya buat 2 subvolume yaitu <code>stable64</code> dan <code>lain</code>. <code>stable64</code> untuk diinstall Slackware64 14.2 sedangkan subvolume <code>stable</code> untuk Slackware 14.2.

```bash
mount -t btrfs /dev/sda8 /mnt/hd
btrfs subvolume create /mnt/hd/stable64
btrfs subvolume create /mnt/hd/stable
```

Next, install slackware ke partisi btrfs sesuai subvolumenya. Masih punya isonya, jadi langsung dimount saja.

```bash
mount slackware64-14.2-install-dvd.iso /mnt/iso
installpkg --root /mnt/hd/stable64 /mnt/iso/slackware64/*/*.t?z
installpkg --root /mnt/hd/stable /mnt/iso/slackware64/*/*.t?z
```


_Copy_ kernel stable ke partisi EFI. Yang saya copy kernel hugenya.

```bash
cp /mnt/hd/stable64/boot/vmlinuz-huge-4.4.14 /boot/efi/EFI/Slackware/stable64-huge
cp /mnt/hd/stable/boot/vmlinuz-huge-4.4.14 /boot/efi/EFI/Slackware/stable-huge
```

Selanjutnya tambahkan ke <code>elilo.conf</code>

```bash
image=stable64-huge
        label=64
        read-only
        append="root=/dev/sda8 rootflags=subvol=stable64 vga=normal ro"
image=stable-huge
	label=32
	read-only
	append="root=/dev/sda8 rootflags=subvol=stable vga=normal ro"
```

Oh iya, kalau mau _dualboot_ atau _multiboot_ yang semua OSnya adalah Slackware, **jangan lakukan eliloconfig**. Lakukan konfigurasi <code>elilo</code> secara manual seperti langkah tersebut di atas.

Isi <code>/etc/fstab</code> masing-masing stable. Untuk stable64 kira-kira seperti ini

```bash
/dev/sda2        swap             swap        defaults         0   0
/dev/sda8        /                btrfs       defaults,subvol=stable64         1   1
/dev/sda4        /home            ext4        defaults         1   2
/dev/sda1        /boot/efi        vfat        defaults         1   2 
/dev/cdrom      /mnt/cdrom       auto        noauto,owner,ro,comment=x-gvfs-show 0   0
/dev/fd0         /mnt/floppy      auto        noauto,owner     0   0
devpts           /dev/pts         devpts      gid=5,mode=620   0   0
proc             /proc            proc        defaults         0   0
tmpfs            /dev/shm         tmpfs       defaults         0   0
```

Sedangkan stable kurang lebih seperti ini

```bash
/dev/sda2        swap             swap        defaults         0   0
/dev/sda8        /                btrfs       defaults,subvol=stable         1   1
/dev/sda4        /home            ext4        defaults         1   2
/dev/sda1        /boot/efi        vfat        defaults         1   2 
/dev/cdrom      /mnt/cdrom       auto        noauto,owner,ro,comment=x-gvfs-show 0   0
/dev/fd0         /mnt/floppy      auto        noauto,owner     0   0
devpts           /dev/pts         devpts      gid=5,mode=620   0   0
proc             /proc            proc        defaults         0   0
tmpfs            /dev/shm         tmpfs       defaults         0   0
```

Selesai. Silakan _unmount_ partisi btrfsnya dan isonya sekalian (kalau belum di-_unmount_).
