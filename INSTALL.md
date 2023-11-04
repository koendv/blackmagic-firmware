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

### Windows
Connect a STM32F401 or STM32F411 Black Pill for upload:

- Download [dfu-util](https://dfu-util.sourceforge.net/)
- Connect the Black Pill to usb. Make sure it's a data cable, not a charging cable.
- Push NRST and BOOT0
- Wait a few seconds
- Release NRST
- Wait a few seconds
- Release BOOT0
- Upload the firmware:
```./dfu-util -a 0 --dfuse-address 0x08000000:leave -R -D blackmagic-blackpillv2.bin```
- If dfu-util gives the error _Cannot open DFU device xxxx:xxxx_ download [zadig](https://zadig.akeo.ie/), select "STM32 Bootloader", install the WinUSB driver and run dfu-util again.
- Disconnect and reconnect to usb

### Linux

Connect a STM32F401 or STM32F411 Black Pill for upload:

- Install dfu-util. On Debian/Ubuntu, type ``sudo apt-get install dfu-util`` 
- Connect the Black Pill to usb.  Make sure it's a data cable, not a charging cable.
- Push NRST and BOOT0
- Wait a few seconds
- Release NRST
- Wait a few seconds
- Release BOOT0
- Upload the firmware:
```dfu-util -a 0 --dfuse-address 0x08000000:leave -R -D blackmagic-blackpillv2.bin```
- If dfu-util does not find the black pill, execute dfu-util as root.
- Install [udev rules](https://github.com/blackmagic-debug/blackmagic/tree/main/driver)
- Disconnect and reconnect to usb

I am using this blackpill board: [STM32F411 with 8MB flash](https://www.aliexpress.com/item/1005001456186625.html).

###  Pinout on STM32F401/STM32F411 black pill

Pinout:

|Signal|Pin|
|---|---|
|SWDIO|B9|
|SWCLK|B8|

Pinout on release v1.9.x and earlier:

|Signal|Pin|
|---|---|
|SWDIO|A13|
|SWCLK|A14|

## Installation on other platforms

Open the [source tree](https://github.com/blackmagic-debug/blackmagic/tree/main/src/platforms), go to the subdirectory for your platform and check the "readme" for installation instructions. The exact pinout used is in the file "platform.h".
