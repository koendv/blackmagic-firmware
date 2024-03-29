# Developer's Notes

To compile the sources by hand, first install [arm-none-eabi-gcc](https://xpack.github.io/arm-none-eabi-gcc/). Then:

```
git clone https://github.com/koendv/blackmagic-firmware
git clone https://github.com/blackmagic-debug/blackmagic
cd blackmagic
patch -p1 < ../blackmagic-firmware/blackmagic.patch
patch -p1 < ../blackmagic-firmware/bluepill.patch
make all_platforms
```

After compiling the firmware is in the directory src/artifacts .

The patch includes:

- ``src/platforms/bluepill/Makefile.inc``: compile firmware for bluepill
- ``src/platforms/native/Makefile.inc``: for native, stlink and swlink platforms, create an "all in one" binary of bootloader and program
