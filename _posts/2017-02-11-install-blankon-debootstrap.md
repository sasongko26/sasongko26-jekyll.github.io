---
layout: post
date: 2017-02-11
title: "Install BlankOn dengan Debootstrap"
tags: [blankon, slackware]
---
Hari ini, sabtu, 11 Januari 2017, hujan turun lagi. Dan di kala hujan deras dan _nggrejih_ begini sejak pagi, _suwung_ pun melanda. Tiba-tiba terbersit untuk _install_ **BlankOn** yang telah lama saya tinggalkan.

Teringat, DVD/USB _installer_-nya sudah tak ada. Iso-nya pun terhapus. _So, what's next_? Download iso BlankOn? Ide bagus, tapi sayang kuota tak mencukupi. Beli DVD/USB tak memungkinkan. Harus pesan dulu, sampai di tangan paling cepat besok senin, keburu sudah tidak _kepengin installl_ lagi. Hahahaha....

Ya pakai <code>debootstrap</code> sajalah. Lagian belum pernah pakai <code>debootstrap</code> sebelumnya. <code>debootstrap</code> tersedia di SBo sehingga semakin memudahkan. Tapi biar lebih greget sekaligus hemat kuota _install_-nya varian yang <code>minbase</code> saja, paket super minimalis.

Terpikirkan 2 skenario _install_:

1. _Install minbase_ dari repo **Debian**, kemudian _upgrade_ ke _tambora_.
2. _Install minbase_ dari repo **BlankOn**.

Sepertinya skenario nomor 1 sudah _mainstream_, jadi pakai nomor 2 biar greget. Skenario lengkapnya, varian yang diinstall minimal, arsitektur 64 bit (amd64), hanya komponen _main_, menggunakan _script_ sendiri yang namanya _tambora_, diinstal ke partisi yang saya <code>mount</code> ke /media/hd1, ambil dari repo **BlankOn**.

Karena tidak ada _script_ untuk **BlankOn** di <code>debootstrap</code>, bikin sendiri saja. **BlankOn** terbaru (**Tambora**) mengambil paket dari **Debian Sid**, maka untuk _script_-nya modifikasi saja dari _sid_. Copas dulu, beri nama _tambora_. Sebenarnya nama baru ini sih suka-suka, tapi biar lebih gampang dan sesuai tujuan, namai saja _tambora_.

```bash
cp /usr/share/debootstrap/scripts/sid /usr/share/debootstrap/scripts/tambora
```

Walaupun _Tambora_ diturunkan dari _Sid_, tetap perlu penyesuaian _script_.

```bash
nano /usr/share/debootstrap/scripts/tambora

```

Baris 5 ganti <code>debian</code> menjadi <code>blankon</code> sehingga menjadi <code>keyring /usr/share/keyrings/blankon-archive-keyring.gpg</code>.


Next,

```bash
debootstrap --variant=minbase --arch=amd64 --components=main tambora /media/hd1 http://arsip.blankonlinux.or.id/blankon/
```

O,o, setelah proses itu selesai, ternyata tidak ter-_install_ kernel, entah mengapa terjadi belum mencari penyebabnya. Kalau **Tambora** ini mau dijalankan pakai <code>chroot</code> dari **Slackware** maka misi telah selesai! Tapi kalau _pengin_ bisa dijalankan secara mandiri, brarti mau tidak mau ya harus _install kernal_. _Kernel_ yang ada di repo masih jadul ik tapi, 3.10. Biar ajalah.

```bash
chroot /media/hd1
apt install linux-image-3.10-3-amd64
exit
```

Selesai? Belum. Skema partisi hardisk saya **GPT** yang menggunakan **EFI**. Kabarnya, agar bisa di-_install_ dengan EFI harus pakai <code>haftian</code>. Ah, ini kan saya _install_ bukan dari iso tapi <code>debootstrap</code>. Masih perlu pakai <code>haftian</code>? Dan _bootloader_ yang saya gunakan _bootloader_ bawaan **Slackware** yaitu <code>elilo</code>, sedangkan secara _default_ **BlankOn** pakai <code>grub</code>. Jadi bagaimana? 

Masukkan _kernel_ dan _initrd_-nya ke partisi EFI.

```bash
cp /media/hd1/boot/vmlinuz-3.10-3-amd64 /boot/efi/EFI/Slackware/blankon
cp /media/hd1/boot/initrd.img-3.10-3-amd64 /boot/efi/EFI/Slackware/
```

dan jangan lupa edit <code>elilo.conf<code>-nya. tambahkan

```bash
image=blankon
	label=blankon
	initrd=initrd.img-3.10-3-amd64
	read-only
	append="root=/dev/sda8 vga=normal ro"
```
Partisi root yang saya gunakan untuk **BlankOn Tambora** adalah _/dev/sda8_.

Dan ketika di-_boot_, sukses! Alhamdulillah.

Berikut tampilannya saat eksekusi <code>cat /etc/os-release</code> dan <code>uname -a</code>

![](/gambar/blankon-debootstrap-minbase.jpg)

NB. Maaf, fotonya tidak terlalu jelas.

