Attached is the source code for the boot sector of the frehd boot disk.  The source is slightly modified from the loader.asm file which is included with the frehd source tree.

The frehd has a feature specifically intended to assist in booting so that the change to the boot ROM can be very small.  This special feature is the equivalent of how boot from floppy works which is why sticking this code in the boot sector also works.

The frehd contains a 256 byte program stored in the PIC program memory that can be read with a special command.  Using this special command the frehd autoboot ROM just reads these 256 bytes into memory at 5000h and jumps to it.  Since it is 256 bytes and the boot sector is also 256 bytes you can just replace the boot sector with the same code - the only difference is it has to run at the floppy boot address which is 4200h for a M1 and 4300h for a M3.  You can edit loader2.asm to change the org address and assemble it with Matthew Reed's assembler

z80asm.exe -cim loader2.asm

It is assembled as a raw image not cmd format since the boot sector is just raw binary.  I made a few other changes to make it a 'better' boot sector.  The directory cylinder is contained in the third byte (byte 2) of the boot sector for TRSDOS-like DOS's (I don't know about CPM for example) as the argument of a CP instruction so you see the first two instructions are

 NOP
 CP 14h

This assumes the directory is on track 20 which is normal for a 40 track M3/4 disk but M1 might be track 17 (a remnant of early 35 track drives).

The boot disk doesn't need to be a valid DOS disk but it's convenient if it is because if you do a DIR the DOS may struggle trying to make sense of it if it's not.  But of course if you boot multiple OS's it can only be valid for one of them.  The one I sent you should be a valid L-DOS/LSDOS disk because those are the OS's I use.

Note that the boot sector is track 0 sector 0 for the M1 but track 0 sector 1 for the M3 since M3 TRSDOS numbers sectors starting at 1.  So even though L(S)DOS numbers starting at 0 the boot sector is still 1,  Consequently L(S)DOS duplicates the boot sector in track 0 sectors 0 and 1 for the M3/4.  I'm not sure what is in sector 0 of what I sent you - I may have duplicated the frehd boot sector in 0 or it may be the L(S)DOS boot sector.  I'm not actually sure though which sector 0 or 1 it uses to obtain the directory track.

I copied the assembler output loader2.cim to the boot sector using a binary file editor.  I copied it to a ,jv3 file by searching the file for the original boot sector and then copying the loader2.cim contents to it.  I then converted it to a .hfe for the gotek.

Matt