# TRS80gotek
## Configuring a TRS-80 Model 4 to book from a gotek floppy emulator and FreHD system

The [TRS-80 Model 4 computers](https://en.wikipedia.org/wiki/TRS-80_Model_4) are a family of systems from 1983, built and sold by Tandy/Radio Shack. They consist of a monitor, keyboard and floppy drives in one case with a very traditional "retro computer look", and continue to be popular to enthusiasts. They are Z80 based, with up to 128Kb of RAM. They run propritary disk operating systems but also CP/M. Today they are used mostly for nostalgic reasons.

## Adding a GoTek to the TRS-80 Model 4

A [GoTek](http://www.gotekemulator.com) is a piece of hardware designed to physicaly fill the space taken by a 3.5 inch floppy disk drive with a unit that accepts USB flash drives rather than a disk. They were created to replace floppy drives in equipment such as musical instruments, control hardware - but they have proved very popular with retro computer users. Systems from Amiga's to Amstrad's can have drives replaced with convenient USB drives. The GoTek hardware can be found on eBay and Amazon for $20 or less.

1. Changing the firmware

In order to use the GoTek you will first need to change the firmware to a new version called [FlashFloppy](https://github.com/keirf/FlashFloppy).

1.1 Download the latest firmware from the [FlashFloppy](https://github.com/keirf/FlashFloppy) Github site.
1.2 Set appropriate jumpers on the GoTek. I soldered in some pins to make this easier.
1.3 Connect the GoTek to your computer using a USB-A to USB-A lead (a little unusual, but eBay to the rescue)
1.4 Run the flash utility and upload the firmware to the GoTek. There are some more intructions in this [video](https://www.youtube.com/watch?v=-K31S2xqZIk&feature=youtu.be&t=841).
1.5 Make a dontation to the FlashFloppy author.

2. Housing the GoTek

I removed the GoTek from the original casing, and installed it into a laser-cut acrylic enclosure the same size as an original floppy drive. 

3. Getting the right cabling

You will need to tap 5v from inside the TRS-80 to connect to the power connector on the GoTek. However, the trickier part is building or buying the right floppy disk cable. I bought one from Jay at [NewSoft](http://plaidvest.com/newsoft/). You will need to specify if you want the GoTek to be drive 0 or 1 as this is set in the cable. I wanted it to be drive 0 so I could boot from it.


4. Setting the correct jumpers

Make sure to set the [GoTek jumpers](https://torlus.com/floppy/forum/viewtopic.php?t=3171) to match your drive selection choice.

5. Obtaining a disk image

Now format a USB stick to MS-DOS/FAT32 and put a TRS-80 bootable image on it.

## Using the GoTek with a FreHD hard drive emulator

