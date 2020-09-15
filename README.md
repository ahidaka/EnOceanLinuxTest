# EnOceanLinuxTest
EnOcean Linux Test Program

## eotest
- Basic EnOcean serial port test for Linux.

## Get and Build

```sh
$ sudo apt install -y git gcc make build-essential net-tools libxml2-dev
$ git clone https://github.com/ahidaka/EnOceanLinuxTest.git
$ cd EnOceanLinuxTest/eotest
$ make
```

## Options

```sh
Usage: eotest [-m|-r|-o][-c][-v]
  [-d Directory][-f Controlfile][-e EEPfile][-b BrokerFile]
  [-s SeriaPort][-z CommandFile]
    -m    Monitor mode
    -r    Register mode
    -o    Operation mode
    -c    Clear settings before register
    -v    View working status
    -d    Bridge file directrory
    -f    Control file
```
## How to use

Attach USB400J or some EnOcean transceiver module to your device.

```sh
$ sudo eotest

or 

$ sudo eotest -m
```
<br/>
This will show some received EnOcean telegrams like followings.
<br/>

```
00 07 07 01 94 F6 15 00  28 F2 B8 B0 01 FF FF FF FF 39 00 00 00 00 00 00
P:01,0028F2B8,F6=RPS:15,B0
00 07 07 01 94 F6 00 00  28 F2 B8 A0 01 FF FF FF FF 3D 00 00 00 00 00 00
P:01,0028F2B8,F6=RPS:00,A0
00 0A 07 01 94 A5 00 7E  AC 0A 04 00 20 0F 80 01 FF FF FF FF 52 00 00 00
P:01,0400200F,A5=4BS:00 7E AC 0A,00
00 07 07 01 94 D5 08 04  00 67 D7 80 01 FF FF FF FF 38 00 FF 00 00 00 00
P:01,040067D7,D5=1BS:08,80
00 07 07 01 94 B2 AE 04  01 2F 4D 80 01 FF FF FF FF 52 00 FF 00 00 00 00
```

**sudo** is mandatory needed to access your serial device and make working directory.

## Notice

This program makes and uses /var/tmp/eotest directory for working storage.

This program doen't translate GP and Secure telegrams.
