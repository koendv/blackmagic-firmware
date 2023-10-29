# Black Magic Probe Firmware

This is an automated unofficial build of [Black Magic Probe](https://black-magic.org/), an arm debugger. Weekly updates.

## Black Magic Probe Firmware

Download Black Magic Probe firmware for all platforms:

- [latest release](../../releases/latest/download/blackmagic-firmware.zip)
- [current git](../../releases/download/current/blackmagic-firmware.zip)

[How to Install](INSTALL.md) on STM32F103 Blue Pill and STM32F401/STM32F411 Black Pill.

## Black Magic Debug App

Black Magic is also available as a windows and linux app for ftdi, cmsis-dap, stlink, jlink and black magic probes.

- ``blackmagic.exe`` for windows is in the ``windows/`` subdirectory. This is a command-line tool. To allow access to the ftdi/stlink/jlink/cmsis-dap devices, run [zadig](https://zadig.akeo.ie/) and choose WinUSB(libusb-1.0).
- ``blackmagic-hosted`` for linux x86-64  is in the ``hosted/`` subdirectory. On debian/ubuntu, first install dependencies with ``sudo apt-get install libusb-1.0-0-dev libftdi1-dev libhidapi-hidraw0``

[How to use.](https://github.com/blackmagic-debug/blackmagic/blob/main/src/platforms/hosted/README.md)

## Embedded Debugging with the Black Magic Probe

- The  [Black Magic Probe book](https://github.com/compuphase/Black-Magic-Probe-Book/releases/latest/download/BlackMagicProbe.pdf) covers setting up and using the Black Magic Probe.
- More [documentation](https://black-magic.org/) in the wiki.
- Contribute to the [source](https://github.com/blackmagic-debug/blackmagic)

_not truncated_
