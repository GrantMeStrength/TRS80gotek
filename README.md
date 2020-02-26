# TRS80gotek
## Configuring a TRS-80 Model 4 to book from a gotek floppy emulator and FreHD system

The [TRS-80 Model 4 computers](https://en.wikipedia.org/wiki/TRS-80_Model_4) are a family of systems from 1983, built and sold by Tandy/Radio Shack. They consist of a monitor, keyboard and floppy drives in one case with a very traditional "retro computer look", and continue to be popular to enthusiasts. They are Z80 based, with up to 128Kb of RAM. They run propritary disk operating systems but also CP/M. Today they are used mostly for nostalgic reasons.

## Adding a GoTek to the TRS-80 Model 4

A [GoTek](http://www.gotekemulator.com) is a piece of hardware designed to physicaly fill the space that would have been taken by a 3.5 inch floppy disk drive. It consists of a unit that accepts USB flash drives, a three digit LED display and two buttons (many users augment or replace these controls with OLED panels and rotary controls). The GoTek was created to replace floppy disk drives in equipment such as musical instruments and industrial control hardware - but they have proved very popular with retro computer user, as they can be used to replace drives in systems from Amigas to TI-99/4As with convenient USB drives. The GoTek hardware can be found on eBay and Amazon for $20 or less. There are several variations, and before you buy one you should read the links on this page to make sure to you're buying one that is compatible.

1. Changing the firmware

In order to use the GoTek you will first need to change the firmware to a new version called [FlashFloppy](https://github.com/keirf/FlashFloppy).

1.1 Download the latest firmware from the [FlashFloppy](https://github.com/keirf/FlashFloppy) Github site.

1.2 Set appropriate jumpers on the GoTek. I soldered in some pins to make this easier.

c) Connect the GoTek to your computer using a USB-A to USB-A lead (a little unusual, but eBay to the rescue). [Here's a good set of instructions](http://www.binarydevotion.com/?p=228).

d) Run the flash utility from [ST Microelectronics](http://www.st.com/content/st_com/en/products/development-tools/software-development-tools/stm32-software-development-tools/stm32-programmers/stsw-stm32080.html) and upload the firmware to the GoTek. There are some more intructions in this [video](https://www.youtube.com/watch?v=-K31S2xqZIk&feature=youtu.be&t=841).

e) Make a dontation to the FlashFloppy author.

2. Housing the GoTek

I removed the GoTek from the original casing, and installed it into a laser-cut acrylic enclosure the same size as an original floppy drive. 

3. Getting the right cabling

You will need to tap 5v from inside the TRS-80 to connect to the power connector on the GoTek. However, the trickier part is building or buying the right floppy disk cable. I bought one from Jay at [NewSoft](http://plaidvest.com/newsoft/). You will need to specify if you want the GoTek to be drive 0 or 1 as this is set in the cable. I wanted it to be drive 0 so I could boot from it.


4. Setting the correct jumpers

Make sure to set the [GoTek jumpers](https://torlus.com/floppy/forum/viewtopic.php?t=3171) to match your drive selection choice.

5. Obtaining a disk image

Now format a USB stick to MS-DOS/FAT32 and put a TRS-80 bootable image on it.

## Using the GoTek with a FreHD hard drive emulator

