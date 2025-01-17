---
layout: post
title : "Slackware Current Susah Booting dan Shutdown"
date : 2016-02-08
tags : 
- slackware
- boot
- kernel

---
Beberapa hari yang lalu (tepatnya kapan saya lupa) upgrade kernel dari 3.10.17, kernel yang dipakai Slackware64 14.1 ke kernel Current yaitu 4.4.0 (tapi saat catatan ini ditulis kernel Current sudah naik jadi 4.4.1). Upgrade kernel ini menimbulkan masalah, yaitu sering _stuck_ saat _boot_ dan _shutdown_. 

Masalah ini terjadi baik arsitektur x86 maupun x86_64. Pada x86 sesuai laporan dari milis _ID-Slackware_, sedangkan pada x86_64 ini saya alami sendiri, dan setelah saya upgrade ke 4.4.1 pun belum ada perubahan berarti.
 
Begini hasil dmesg untuk ACPI-nya.
```
[    0.000000] BIOS-e820: [mem 0x000000000008f000-0x000000000008ffff] ACPI NVS
[    0.000000] BIOS-e820: [mem 0x0000000078eb4000-0x00000000793a8fff] ACPI NVS
[    0.000000] efi:  ACPI=0x79342000  ACPI 2.0=0x79342000  SMBIOS=0xf04d0  MPS=0xfd550 
[    0.000000] ACPI: Early table checksum verification disabled
[    0.000000] ACPI: RSDP 0x0000000079342000 000024 (v02 _ASUS_)
[    0.000000] ACPI: XSDT 0x0000000079342088 000084 (v01 _ASUS_ Notebook 01072009 AMI  00010013)
[    0.000000] ACPI: FACP 0x0000000079353D88 00010C (v05 _ASUS_ Notebook 01072009 AMI  00010013)
[    0.000000] ACPI BIOS Warning (bug): 32/64X length mismatch in FADT/Gpe0Block: 128/32 (20150930/tbfadt-623)
[    0.000000] ACPI: DSDT 0x00000000793421A0 011BE4 (v02 _ASUS_ Notebook 01072009 INTL 20120913)
[    0.000000] ACPI: FACS 0x00000000793A8F80 000040
[    0.000000] ACPI: APIC 0x0000000079353E98 000068 (v03 _ASUS_ Notebook 01072009 AMI  00010013)
[    0.000000] ACPI: FPDT 0x0000000079353F00 000044 (v01 _ASUS_ Notebook 01072009 AMI  00010013)
[    0.000000] ACPI: MCFG 0x0000000079353F48 00003C (v01 _ASUS_ Notebook 01072009 MSFT 00000097)
[    0.000000] ACPI: LPIT 0x0000000079353F88 000104 (v01 _ASUS_ Notebook 00000003 VLV2 0100000D)
[    0.000000] ACPI: ECDT 0x0000000079354090 0000C1 (v01 _ASUS_ Notebook 01072009 AMI. 00000005)
[    0.000000] ACPI: HPET 0x0000000079354158 000038 (v01 _ASUS_ Notebook 01072009 AMI. 00000005)
[    0.000000] ACPI: SSDT 0x0000000079354190 000763 (v01 PmRef  CpuPm    00003000 INTL 20061109)
[    0.000000] ACPI: SSDT 0x00000000793548F8 000290 (v01 PmRef  Cpu0Tst  00003000 INTL 20061109)
[    0.000000] ACPI: SSDT 0x0000000079354B88 00017A (v01 PmRef  ApTst    00003000 INTL 20061109)
[    0.000000] ACPI: UEFI 0x0000000079354D08 000042 (v01 _ASUS_ Notebook 00000000      00000000)
[    0.000000] ACPI: BGRT 0x0000000079354D50 000038 (v00 _ASUS_ Notebook 01072009 AMI  00010013)
[    0.000000] ACPI: Local APIC address 0xfee00000
[    0.000000] ACPI: PM-Timer IO Port: 0x408
[    0.000000] ACPI: Local APIC address 0xfee00000
[    0.000000] ACPI: LAPIC_NMI (acpi_id[0x01] res res lint[0x95])
[    0.000000] ACPI: NMI not connected to LINT 1!
[    0.000000] ACPI: LAPIC_NMI (acpi_id[0x02] low level lint[0xd5])
[    0.000000] ACPI: NMI not connected to LINT 1!
[    0.000000] ACPI: INT_SRC_OVR (bus 0 bus_irq 0 global_irq 2 dfl dfl)
[    0.000000] ACPI: INT_SRC_OVR (bus 0 bus_irq 9 global_irq 9 high level)
[    0.000000] ACPI: IRQ0 used by override.
[    0.000000] ACPI: IRQ9 used by override.
[    0.000000] Using ACPI (MADT) for SMP configuration information
[    0.000000] ACPI: HPET id: 0x8086a201 base: 0xfed00000
[    0.000036] ACPI: Core revision 20150930
[    0.029579] ACPI: 4 ACPI AML tables successfully acquired and loaded
[    0.102330] PM: Registering ACPI NVS region [mem 0x0008f000-0x0008ffff] (4096 bytes)
[    0.102342] PM: Registering ACPI NVS region [mem 0x78eb4000-0x793a8fff] (5197824 bytes)
[    0.130890] ACPI: bus type PCI registered
[    0.130898] acpiphp: ACPI Hot Plug PCI Controller Driver version: 0.5
[    0.243991] ACPI: Added _OSI(Module Device)
[    0.243999] ACPI: Added _OSI(Processor Device)
[    0.244005] ACPI: Added _OSI(3.0 _SCP Extensions)
[    0.244012] ACPI: Added _OSI(Processor Aggregator Device)
[    0.244019] ACPI: Added _OSI(Linux)
[    0.248088] ACPI : EC: EC description table is found, configuring boot EC
[    0.248115] ACPI : EC: EC started
[    0.260723] [Firmware Bug]: ACPI: BIOS _OSI(Linux) query honored via cmdline
[    0.264794] ACPI: Dynamic OEM Table Load:
[    0.264812] ACPI: SSDT 0xFFFF880069417000 00045B (v01 PmRef  Cpu0Ist  00003000 INTL 20061109)
[    0.266064] ACPI: Dynamic OEM Table Load:
[    0.266079] ACPI: SSDT 0xFFFF880069417800 000433 (v01 PmRef  Cpu0Cst  00003001 INTL 20061109)
[    0.267731] ACPI: Dynamic OEM Table Load:
[    0.267745] ACPI: SSDT 0xFFFF880069507800 00015F (v01 PmRef  ApIst    00003000 INTL 20061109)
[    0.268948] ACPI: Dynamic OEM Table Load:
[    0.268961] ACPI: SSDT 0xFFFF880069740540 00008D (v01 PmRef  ApCst    00003000 INTL 20061109)
[    0.270696] ACPI: Interpreter enabled
[    0.270715] ACPI Exception: AE_NOT_FOUND, While evaluating Sleep State [\_S1_] (20150930/hwxface-580)
[    0.270734] ACPI Exception: AE_NOT_FOUND, While evaluating Sleep State [\_S2_] (20150930/hwxface-580)
[    0.270770] ACPI: (supports S0 S3 S4 S5)
[    0.270777] ACPI: Using IOAPIC for interrupt routing
[    0.271817] PCI: MMCONFIG at [mem 0xe0000000-0xefffffff] reserved in ACPI motherboard resources
[    0.271852] PCI: Using host bridge windows from ACPI; if necessary, use "pci=nocrs" and report a bug
[    0.282051] ACPI: Power Resource [USBC] (on)
[    0.283927] ACPI: Power Resource [PLPE] (on)
[    0.284297] ACPI: Power Resource [PLPE] (on)
[    0.289595] ACPI: Power Resource [CLK0] (on)
[    0.289682] ACPI: Power Resource [CLK1] (on)
[    0.293658] ACPI: PCI Root Bridge [PCI0] (domain 0000 [bus 00-ff])
[    0.295470] pci 0000:00:14.0: System wakeup disabled by ACPI
[    0.296287] pci 0000:00:1c.0: System wakeup disabled by ACPI
[    0.296537] pci 0000:00:1c.1: System wakeup disabled by ACPI
[    0.296778] pci 0000:00:1c.3: System wakeup disabled by ACPI
[    0.297856] pci 0000:02:00.0: System wakeup disabled by ACPI
[    0.299972] pci 0000:03:00.0: System wakeup disabled by ACPI
[    0.302655] ACPI: PCI Interrupt Link [LNKA] (IRQs 3 4 5 6 7 10 11 12) *0, disabled.
[    0.302790] ACPI: PCI Interrupt Link [LNKB] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.302922] ACPI: PCI Interrupt Link [LNKC] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.303053] ACPI: PCI Interrupt Link [LNKD] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.303184] ACPI: PCI Interrupt Link [LNKE] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.303315] ACPI: PCI Interrupt Link [LNKF] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.303446] ACPI: PCI Interrupt Link [LNKG] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.303586] ACPI: PCI Interrupt Link [LNKH] (IRQs 3 4 5 6 7 10 12) *0, disabled.
[    0.306468] ACPI: Enabled 4 GPEs in block 00 to 3F
[    0.306639] ACPI : EC: GPE = 0x18, I/O: command/status = 0x66, data = 0x62
[    0.307112] ACPI: bus type USB registered
[    0.307482] PCI: Using ACPI for IRQ routing
[    0.325916] pnp: PnP ACPI init
[    0.326025] pnp 00:00: Plug and Play ACPI device, IDs PNP0b00 (active)
[    0.326317] system 00:01: Plug and Play ACPI device, IDs PNP0c02 (active)
[    0.326442] system 00:02: Plug and Play ACPI device, IDs PNP0c02 (active)
[    0.326577] pnp 00:03: Plug and Play ACPI device, IDs ETD0108 SYN0a00 SYN0002 PNP0f03 PNP0f13 PNP0f12 (active)
[    0.326663] pnp 00:04: Plug and Play ACPI device, IDs ATK3001 PNP030b (active)
[    0.327198] system 00:05: Plug and Play ACPI device, IDs PNP0c02 (active)
[    0.328721] pnp: PnP ACPI: found 6 devices
[    9.721427] ACPI: Power Button [PWRB]
[    9.725350] ACPI: Lid Switch [LID]
[    9.728120] ACPI: Sleep Button [SLPB]
[    9.730903] ACPI: Power Button [PWRF]
[   10.049447] ACPI Warning: SystemIO range 0x000000000000F000-0x000000000000F01F conflicts with OpRegion 0x000000000000F000-0x000000000000F00F (\_SB_.PCI0.SBUS.SMBI) (20150930/utaddress-254)
[   10.051909] ACPI: If an ACPI driver is available for this device, you should use it instead of the native driver
[   10.209918] ACPI: Deprecated procfs I/F for AC is loaded, please retry with CONFIG_ACPI_PROCFS_POWER cleared
[   10.217739] ACPI: AC Adapter [AC0] (off-line)
[   10.309767] ACPI: Deprecated procfs I/F for battery is loaded, please retry with CONFIG_ACPI_PROCFS_POWER cleared
[   10.316358] ACPI: Battery Slot [BAT0] (battery present)
[   10.371683] ACPI: Thermal Zone [THRM] (48 C)
[   10.818724] ACPI: Video Device [GFX0] (multi-head: yes  rom: no  post: no)
```

Solusinya? Biar _boot_-nya lancar sih bisa menambahkan _acpi=off noapic_ di _boot_ konfigurasinya, tapi cara ini tidak direkomendasikan, karena seringkali justru akan merepotkan sendiri nantinya. Untuk solusi fixnya, ini masih eksperimen, insya Allah kalau saya sudah menemukannya akan ditulis di sini.
