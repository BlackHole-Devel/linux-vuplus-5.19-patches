This project is suspended, but i could restart in the future... who knows....

These patches apply to https://github.com/Broadcom/stblinux/ to make 
vuplus mipsel stb to detect the nand flash with more recent kernel

I've started the project with solo2 then switched to zero (just because i have more
unit and i'm not so interested if I would fuck off one of them)
Despite the reference board, vuzero and vusolo2 use CS0 line for the nand.

Applyt ht patch, and make the dts for the correct soc to read my nand dts.

To do a clean work, you have to modify the Makefile and Kconfig to include the vuplus devices,
copy the dts from the reference board to the vuplus one and adjust it...
for vuzero and vusolo2 you could just copy my dts to the right location and reference them.

For Ecc they use an unusual hamming algo with strength 2, so the brcmnand.c need a patch to accept
this setting.

The boxes read the ram from the cfe, so the dts needs little more rework to let linux to see all the ram.

Recente kernels have better support for Broadcom hardware then before.. Raspberry PI3 and PI4 seems to use
some circuitery present on stb soc. Maybe with some patches we can get video output working..