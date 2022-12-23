# Installation instructions

Black Magic Probe firmware installation instructions for STM32F103 Blue Pill and STM32F401/STM32F411 Black Pill follow.

## Installation on STM32F103 blue pill

Download and extract the latest blackmagic-firmware.zip from [Releases](../../releases).
Connect a STM32F103 Blue Pill for serial upload:

- Set boot jumpers for boot from rom: Boot0=1, Boot1=0.
- Connect a USB-Serial adapter with A9 to RX, A10 to TX.
- Press reset.
- Upload the firmware: ``stm32flash -w  blackmagic_allinone-bluepill.bin /dev/ttyUSB0`` with /dev/ttyUSB0 the USB-serial adapter
- After upload, set boot jumpers for boot from flash: Boot0=0, Boot1=0.
- Remove usb-serial adapter
- Connect to usb.

###  Pinout on STM32F103 blue pill

|Signal|Pin|
|---|---|
|SWDIO|B14|
|SWCLK|A5|

## Installation on STM32F401/STM32F411 black pill

Download and extract the latest blackmagic-firmware.zip from [Releases](../../releases).
Connect a STM32F401 or STM32F411 Black Pill for upload:

- Connect the Black Pill to usb
- Push NRST and BOOT0
- Wait a few seconds
- Release NRST
- Wait a few seconds
- Release BOOT0
- Upload the firmware:
```dfu-util -a 0 --dfuse-address 0x08000000:leave -R -D blackmagic-blackpillv2.bin```
- Disconnect and reconnect to usb

###  Pinout on STM32F401/STM32F411 black pill

|Signal|Pin|
|---|---|
|SWDIO|A13|
|SWCLK|A14|

On some boards these pins are marked "SWDIO" and "SWSCK".

## Installation on other platforms

Open the [source tree](https://github.com/blackmagic-debug/blackmagic/tree/main/src/platforms), go to the subdirectory for your platform and check the "readme" for installation instructions. The exact pinout used is in the file "platform.h".
