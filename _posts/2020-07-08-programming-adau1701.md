---
layout: post
title:  "Programming 3e-Audio ADAU1701 with budget Cypress CY7C68013A programmer"
date:   2020-07-08 21:13:00 -0700
---
[Reference diyaudio Thread](https://www.diyaudio.com/forums/digital-line-level/269111-low-cost-usbi-programmer-using-cypress-cy7c68013a-board.html)

#### Hardware
- $48.83USD shipped - [3e-Audio ADAU1701 board](http://www.3e-audio.com/dsp/adau1701-2in4out/). Process would be similar for generic aliexpress board or sure/wondom board. I bought the more expensize 3e-Audio board for the 4 differential op-amp design.
- $4.32USD shipped - CY7C68013A board sold on aliexpress as [EZ-USB FX2LP CY7C68013A USB logic analyzer](https://www.aliexpress.com/item/1907907422.html?spm=a2g0s.9042311.0.0.65b34c4dStAay6)
- ~470 Ohm resistor 
- Jumper wires to connect boards

Working with Windows 7. See below for windows May work with more recent windows but [some people have had issues](https://ez.analog.com/dsp/sigmadsp/f/q-a/65011/usbi-problems-with-windows-10). 

#### Install Software
- Download and install CySuiteUSB_3_4_7_B204.exe from [cypress website](https://www.cypress.com/documentation/software-and-drivers/suiteusb-34-usb-development-tools-visual-studio)
- Download `CY3684 EZ-USB FX2LP Development Kit (Rev. *B)` and install with CY3684Setup.exe from the [cypress website](https://www.cypress.com/documentation/development-kitsboards/cy3684-ez-usb-fx2lp-development-kit)
- Download and install [SigmaStudio v4.5](https://www.analog.com/en/design-center/evaluation-hardware-and-software/software/ss_sigst_02.html#software-relatedsoftware)

##### Windows 10 support
(This worked on windows 10 using a programming board that has already been flashed with 24aa256.iic from above.)
- Per instructions [here](https://community.infineon.com/t5/USB-Low-Full-High-Speed/CY7C68013A-driver-for-windows-10/td-p/186739) download and install [Cypress FX3 SDK](https://www.cypress.com/documentation/software-and-drivers/ez-usb-fx3-software-development-kit)
- In device manager manually set the driver for the device to "Cypress EZ-USB NX2LP-Flex BootLoader Device" (have disk -> C:\Program Files (x86)\Cypress\EZ-USB FX3 SDK\1.3\driver\bin\Win10\x64)
- Sigma Studio 4.7 + FX3SDK works with windows 11 22000.613


#### Setup CY7C68013A to Appear as USBi Programmer
- Connect programmer to computer USB. 
- Go to device manager and set the driver to corresponding windows version here C:\Cypress\USB\CY3684_EZ-USB_FX2LP_DVK\1.1\Drivers 
- Launch C:\Cypress\Cypress Suite USB 3.4.7\CyConsole\CyConsole.exe
- Load ADI_USBi.spt (C:\Program Files\Analog Devices\SigmaStudio 3.11\USB drivers\x64\ADI_USBi.spt) and click the play button 

The Cypress board will now appear and function as a USBi programmer until it is disconnected from the PC or power cycled.

If you want the Cypress board to permanently appear as a USBi programmer then you can flash the vendor information on the board. This doesn't change the function of the board but changes what it appears as to the computer.

Download 24aa256.iic (8kB). To transfer 24aa256.iic to the EEprom on the CY7C68013A development board:
- Remove jumper on the CY7C68013A development board (J2 on 2 jumper board) to enable EEPROM to be written,
- Start CyConsole (part of Cypress Suite), Choose menu Options-> EZ-USB interface
- push button `lgEEPROM`, select the EEPROM file (24aa256.iic). Download to device will start
- Leave the jumper off to boot from EEPROM as a USBi device when the programmer is powered on.. 
My board was a 2 jumper model. You may have a single jumper which I think is equivalent to `J2`
`J1` is to connect/disconnect 2 LEDs from Vcc - these LEDs are connected to D0 & D1
`J2` controls the high address bit of the EEPROM making it appear at I2C address 0xA0 or 0xA2 depending on the jumper.

#### Write to the EEPROM to permanently store program on the 3e-Audio ADAU1701 board
- Power up the ADAU1701 board with nothing attached - (ensure that the power jumpers are configured for the power supply you are using)
- It seems like you can write to eeprom without changing J6 ~~Connect pins 1 and 3 on J6 to make the EEPROM writeable 
  - J6 - pin 1 (pin closest to potentiometers) - ADAU1701 CLATCH/WP (write protect) pin, driven high by 3.3V through 10kOhm resistor if left unconnected
  - J6 - pin 2 eeprom - 24c64 WP (write protect) pin - left floating if left unconnected
  - J6 - pin 3 ground
  - ~~To program, connect P1 and P3. For normal operation, connect P1 and P2 or leave all unconnected.

- Power up the programmer before connecting it to the ADAU1701 board. Then connect pins as follows
  - (Cypress Programmer <-> 3e-Audio ADAU1701)
  - SCL <-> SCL
  - SDA <-> SDA
  - PB0 <-> 470 Ohm resistor <-> BRD_RST (add a resistor between the 2 boards for these pins)
  - GND <-> GND
- To temporarily load the current design to the ADAU1701: Click `Link, Compile, Download` 
- To write the current design permanently to the eeprom: "Hardware Configuration" Tab (top) -> "Config" tab (bottom) -> right click on "ADAU1701 IC2" box -> "Write latest compilation to E2PROM"

There is a bug with IIR table/Linkwitz Transform in sigma studio. To workaround, a1 and a2 need the sign inversed (1.990781326207430 -> -1.990781326207430)

#### Reference Documentation
- [Original DIY audio thread](https://www.diyaudio.com/forums/digital-line-level/269111-low-cost-usbi-programmer-using-cypress-cy7c68013a-board.html)
- [ADAU170 Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/ADAU1701.pdf)


