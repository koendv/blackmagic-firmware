# Black Magic Probe Firmware

This is an automated unofficial build of [Black Magic Probe](https://black-magic.org/) firmware. Weekly updates.

Download Black Magic Probe firmware:

- [latest release](../../releases/latest/download/blackmagic-firmware.zip)
- [current git](../../releases/download/current/blackmagic-firmware.zip)

The zip file contains firmware for all platforms. Installation instructions for STM32F103 Blue Pill and STM32F401/STM32F411 Black Pill follow.

## Installation on STM32F103 blue pill

Download and extract the latest firmware from Releases.
Connect a STM32F103 Blue Pill for serial upload:

- Set boot jumpers for boot from rom: Boot0=1, Boot1=0.
- Connect a USB-Serial adapter with A9 to RX, A10 to TX.
- Press reset.
- Upload the firmware:\
```stm32flash -w  blackmagic_allinone-bluepill.bin /dev/ttyUSB0```\
with /dev/ttyUSB0 the USB-serial adapter
- After upload, set boot jumpers for boot from flash: Boot0=0, Boot1=0.
- Remove usb-serial adapter
- Connect to usb.

## Installation on STM32F401/STM32F411 black pill

Download and extract the latest firmware from Releases.
Connect a STM32F401 or STM32F411 Black Pill for upload:

- Connect the Black Pill to usb
- Push NRST and BOOT0
- Wait a few seconds
- Release NRST
- Wait a few seconds
- Release BOOT0
- Upload the firmware:\
```dfu-util -a 0 --dfuse-address 0x08000000:leave -R -D blackmagic-blackpillv2.bin```
- Disconnect and reconnect to usb

## Installation on other platforms

Open the [source tree](https://github.com/blackmagic-debug/blackmagic/tree/main/src/platforms), go to the subdirectory for your platform and check the "readme" for installation instructions.

_not truncated_
