---
layout: post
title:  "InFocus Liteshow III repurpose"
---

This device is a wireless receiver for presentations.
It uses a wireless dongle or network to transmit video from a laptop to a projector.

Since the dongle is missing from mine, i'm looking into other uses for this thing.

The firmware can be found at https://infocus.com/software/inliteshow3/ but it is in a passworded zip file.
I suspect the device has the password, so i have to get into one using another way.

I connected a USB-Serial adapter to the header on the board and at 38400 baud i get this on startup:

```
    ø   D12CTt

ooooooooooooooooooooooooooooooooooooooooooooooooooooooo
o Awind boot loader v3.0 for NOR FLASH MX29GL128EHT2I o
ooooooooooooooooooooooooooooooooooooooooooooooooooooooo

CPU freq.: 189 MHz
Production Board Test Stage 1
  Verifying checksum : No checksum
Loading vsync parameters ..
load file from romfs 0x46060000
ROMFS found at 0x46060000, Volume name = mambo
File vsyncparam.bin not found
File vsyncparam.bin.gz not found
ROMFS load failed
vsyncparam.bin not found in romfs, load from flash instead.
Verify checksum from 0x46ff8000, size 32768 (0x8000).
Loading vsyncparam failed.
Loading bitmaps ..
load file from romfs 0x46060000
ROMFS found at 0x46060000, Volume name = mambo
File bitmap.bin not found
File bitmap.bin.gz not found
ROMFS load failed
Loading bitmap failed.
Loading/Installing IRQ handler ..
No VSYNC parameters loaded: blank structure.
load file from romfs 0x46060000
ROMFS found at 0x46060000, Volume name = mambo
File irqhandler.bin found
Copying image from 0x465C3D30 to 0x90011000, size = 198024
Verify checksum from 0x90011000, size 198024 (0x30588).
Initializing IRQ handler @ 0x900386a8.
ROMFS found at 0x46060000, Volume name = mambo
File linux.bin.gz found
Unzipping image from 0x461F1650 to 0x90090000, size = 743724
Inptr = 0x00000014(20)
Inflating....
Outcnt = 0x0018bed4(1621716)
Final Inptr = 0x000b5924(743716)
Original CRC = 0x1fc39ddc
Computed CRC = 0x1fc39ddc
Boot kernel at 0x90090000 with ROMFS at 0x46060000
mumk_register_tasklet: (0) tasklet 903baee0 status @93519188
begun
em8xxx sound driver (/dev/mixer0, /dev/dsp3) registered.
done
```
So it does run Linux but it disables the serial console right at boot.

The encrypted firmware zip contains a "romfs" file which could very well be the `ROMFS found at 0x46060000, Volume name = mambo` line that shows up 4 times.

Spamming enter did nothing.

I tried bridging some pins on the MX29GL128 flash chip that made it get stuck but it kept booting after releasing the pins.

Next I tried bridging some pins on the NT5DS32M16BS-5T RAM chip, that made it crash after booting.

To get further with this i will probably have to dump the flash chip.
It's a TSOP56 and my reader can only do TSOP48 so I'll have to wait for a new reader to arrive.