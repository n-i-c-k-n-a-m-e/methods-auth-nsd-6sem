# Получение сведений о системе

## Цель работы

Получить сведения об используемой системе

## Исходные данные

1. Ноутбук Huawei

2. ОС Debian, запущенный через Windows Subsystem for Linux (WSL)

3. Интерпретатор командной оболочки bash 5.1.4


## План

1. Ввод команд в эмулятор терминала

2. Анализ данных

## Ход работы


1. Затем получим сведения о версии ядра:

```bash
ragim@LAPTOP-6RGQFHF2:~$ uname -a
Linux LAPTOP-6RGQFHF2 5.10.16.3-microsoft-standard-WSL2 #1 SMP Fri Apr 2 22:23:49 UTC 2021 x86_64 GNU/Linux
```

В результате выполнения данной команды была получена версия ядра - 5.10.16.3, дата компиляции ядра - 2 апреля 2021 года.

2. Далее можно получить сведения о процессоре:

```bash
ragim@LAPTOP-6RGQFHF2:~$ cat /proc/cpuinfo | grep "model name"
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
model name      : 12th Gen Intel(R) Core(TM) i5-12500H
```

Было определено, что используемый процессор - шестнадцатипоточный Intel Core i5-12500H 

3. Далее получим последние 30 строк логов системы:

```bash
ragim@LAPTOP-6RGQFHF2:~$ dmesg | tail -n 30
[    5.151638] pci 469b:00:00.0: [1af4:1049] type 00 class 0x010000
[    5.152178] pci 469b:00:00.0: reg 0x10: [mem 0xbffe00000-0xbffe00fff 64bit]
[    5.152538] pci 469b:00:00.0: reg 0x18: [mem 0xbffe01000-0xbffe01fff 64bit]
[    5.152901] pci 469b:00:00.0: reg 0x20: [mem 0xbffe02000-0xbffe02fff 64bit]
[    5.155067] pci 469b:00:00.0: BAR 0: assigned [mem 0xbffe00000-0xbffe00fff 64bit]
[    5.155341] pci 469b:00:00.0: BAR 2: assigned [mem 0xbffe01000-0xbffe01fff 64bit]
[    5.155597] pci 469b:00:00.0: BAR 4: assigned [mem 0xbffe02000-0xbffe02fff 64bit]
[    5.634266] hv_pci 3c1d90a2-0cfc-4b48-a10f-2475194424e1: PCI VMBus probing: Using version 0x10003
[    5.636579] 9pnet_virtio: no channels available for device drvfs
[    5.636586] WARNING: mount: waiting for virtio device...
[    5.682351] hv_pci 3c1d90a2-0cfc-4b48-a10f-2475194424e1: PCI host bridge to bus 0cfc:00
[    5.682353] pci_bus 0cfc:00: root bus resource [mem 0xbffe04000-0xbffe06fff window]
[    5.683146] pci 0cfc:00:00.0: [1af4:1049] type 00 class 0x010000
[    5.684100] pci 0cfc:00:00.0: reg 0x10: [mem 0xbffe04000-0xbffe04fff 64bit]
[    5.684465] pci 0cfc:00:00.0: reg 0x18: [mem 0xbffe05000-0xbffe05fff 64bit]
[    5.684832] pci 0cfc:00:00.0: reg 0x20: [mem 0xbffe06000-0xbffe06fff 64bit]
[    5.686955] pci 0cfc:00:00.0: BAR 0: assigned [mem 0xbffe04000-0xbffe04fff 64bit]
[    5.687254] pci 0cfc:00:00.0: BAR 2: assigned [mem 0xbffe05000-0xbffe05fff 64bit]
[    5.687513] pci 0cfc:00:00.0: BAR 4: assigned [mem 0xbffe06000-0xbffe06fff 64bit]
[    5.745858] hv_pci 6cfb05b4-17af-4de2-9582-fabc721c20a7: PCI VMBus probing: Using version 0x10003
[    5.798599] hv_pci 6cfb05b4-17af-4de2-9582-fabc721c20a7: PCI host bridge to bus 17af:00
[    5.798602] pci_bus 17af:00: root bus resource [mem 0xbffe08000-0xbffe0afff window]
[    5.799163] pci 17af:00:00.0: [1af4:1049] type 00 class 0x010000
[    5.799725] pci 17af:00:00.0: reg 0x10: [mem 0xbffe08000-0xbffe08fff 64bit]
[    5.800121] pci 17af:00:00.0: reg 0x18: [mem 0xbffe09000-0xbffe09fff 64bit]
[    5.800489] pci 17af:00:00.0: reg 0x20: [mem 0xbffe0a000-0xbffe0afff 64bit]
[    5.802719] pci 17af:00:00.0: BAR 0: assigned [mem 0xbffe08000-0xbffe08fff 64bit]
[    5.803009] pci 17af:00:00.0: BAR 2: assigned [mem 0xbffe09000-0xbffe09fff 64bit]
[    5.803286] pci 17af:00:00.0: BAR 4: assigned [mem 0xbffe0a000-0xbffe0afff 64bit]
[   49.138034] hv_balloon: Max. dynamic memory size: 8054 MB
```

## Оценка результата

В результате лабораторной работы была получена базовая информация об используемой системе.

## Вывод

Таким образом. мы научились, используя команды Linux, получать сведения о системе.