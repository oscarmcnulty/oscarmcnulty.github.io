---
layout: post
title:  "Flashing ER9x to Turnigy 9x transmitter with a Raspberry Pi"
date:   2019-07-07 12:03:58 -0700
---

# Look inside the Turnigy 9X

![ATmega64 processor](https://lh3.googleusercontent.com/ynxYgtdtkO8HoTeKAl6nx6f8qNLzXHBk0GpD-XpoJOzlD_479gQffPgdFKhQ0xuQrYnnbNPRRoAVqg0clacZ7oIMtJ-1dTvatXovSMqo7ODHP7rHxXCdhKuoIzEvvnbawWUsdH91yQQdQ-D5-JMHC2jQXNVgcZPc3_Y6gsDfc0oAkD0AoBfM2ioH1Kj9y6M_lKKu4tmCsZXrR_kC4Or-GdsFNEiCyr_b-4Y3StdWdI6EYy-fZojggmqcI9u9KMriF2SPVxXehjcC8TJjHRZ3eesRfK6tf03GNrVAC5hwWLd7qLVcLF4wfBrXdBXzcYjoQp0FhJmhlnFjAztRTe9pfA4Y1GNMC2EGpW0hzm-RdpFxBfM_VJE6l7nLxEy9_FnTW26P_iziYaQ16EWp7AtalQmdGrO6zdBgDZ_-CVOeOt5--1DQg3VOg-jMfrN8YnNnMtjrdQtWRhqk_id-nNT2XTkWP-gR19aMQd6__QUa6CdicFcBDzpt2y6cha8VYMzOkHyqXSLM1k6q3uwDW_EMdZASAXT8CL7qBiQ1KFBZaaCpV-gPaEsLImw_mjx4gipX03DvdEFc_o6LnAxmhVh1kwOvB03t_ktBJHlgOchgms5Rbe_covNGPXpYhZJ1Vt2EBiOFKXoJ5FAk2i1U5crC5yY2uF2Uy2uNeNisZsCGxyD76g-y0sEQxm7QzHUBhZrrvduI3qE93fi4VFThBZo-xomLvUlOYWeb3zceFmQSLT2KjiaMoNuBbJov=w1902-h1428-no)
![Controller internals](https://lh3.googleusercontent.com/6ht3MYlfaIB1hCAV2PDmAH1u9Un8ywxYoGaStNWABbrMSnV4zQ9u4cErMrg-VYRiWFWuH2i_sVS3IAybgIaRwne_59EI3wSw4Zz7MNnAyLYp0juoyNYj8or0M1OWcYMjmvyP453RqZgyceaDRTvOV61n2w5ev9xRX050npv8RPQ7V3BA_cIYdychNLvMV-4kIBcV8AI6S8-6umXoQmfhnj0PIpRDDO_VEYsSxCcIaSOHk5tWbxG0y0hIAAg2A9XbGl4PhHd5oZRgbihYt6mPyZA7LJQL7PKKqiWz0tPMabSDwYHgUggy4T7E5T4NsY0DjnB1FBrop7QjtCkLi83eZfn8mAPoPvAhRnW3M1Zobv-DAJ1l6xffnxAilaA_4Izg6-1YFbNaVWgzsag3qGhR170diHC5DyAoLcouxNsg4dc2GYnnvGl7JQ20mavieOpJbXVMa8gJUeN-rBi8dosb7yNTQ4rRMTQgoMDwXlCPJLlV-x9N4VAC68ioofWwvXR1PcUeQcmVaIkT6glIuF9BrQ1T5NoGX7mD5PgwOSgxcMFpcdHLi3YXJtUGQsnVI39XltbaW2C3cTXbEeu1jM0zRu-0MA9Ow3P32DZDUQRycasHPec8xV9bmacWXUxgyFUZaOGG493IFwVU7Z-op-uo2zglB2Eex2zuCWnAUOV1DHYnpFbsWQTt0M71hzBSaTxKL_YATdLU9zDeqiAT_F6WptRLDVyO9AMF5MpRzvJ_3a_sasehjkYGSfBP=w1902-h1428-no)

# Installing jumper leads
![Jumper leads on circuit board](https://lh3.googleusercontent.com/S6sQcxRLw2f4T4S5N2PRgY-hdiXJqrap0Bq7_dJncNk19gUxIIzn47Wr4mTgv70yWIwqIkVktMtTEuhcxnywFKdUe6G7hYhxfG6MTbV7qXRfzPRmG5ROmkJgWlDwSt_tIIdHl2Cv3aloq4gDo-xrOjNqdriS1473ClbyA6zulAfeSbBqEnp9JooCUh7cmZr9t7MyepA2eK4r2JAcY_XJgR9JYg1SAbKCGvpgb2PPe6jbzNEFKNpm0zne8fnzsTHdNEnWpHWG9LpmtbqqGIls_X-WtMmaIXHsGn6YrmeELDuEh-tcgsbJOMwCrXRzfH9zwY44I8okl0WCIPdLQo3QUWJwcsPIUnofAm3AzEdFPtS8eYfgHOPXcx-DbN3wjuGUewPq8BWvblXMmorwnXc5TipQrEqvQ1zFRQnBMJSvh0iJZcdej88bDNG9wKEO8W_SNQvrU-im7fapDfgLA1f1_tM4AzB8Ay-Ne0tZAfAIOps3ibPBtAzMYy__zDTgofFTVLoemfD_zmEEI0-KoHm6Dwmh4V4hAte3xQWOrd-Q-1qM2gkyMJ9aadDIP0Af39ZlIHW2cEepJHDeO_UzOG6_hpfqvZCwjn49n68Fl0WC0T4nM2A6gVAn-aO1mL1VSTkzjyJB7Sn816w94I2A590rp_Y1AVkhs2QmreV2b2wlrEZai2afOHaRQI8U7RoJtg0ciNU3vCIBPJA20O84djz9ABnCogboTHZEck7EADjZ0r2dvMPfCwmYi-qv=w1902-h1428-no)
![Jumper leads on circuit board alternate](https://lh3.googleusercontent.com/Sv-ACBbRQCFA4lpusE4M7B4h3-sB4JsPbIN4l9WcjKom_Fr-exxFB8gijcZSHV0YuTAXup8RWSP7e2p-T8nCIXNxkBP98eiJ1UnRAM6M_BEgQ6c3qWkI808ZpMkXJOScuKMCTk3E6l1ipX_8X0pdDTTC0ApqKFoeL2jjIesovuqMCZ0gS04JgxMZt1xiS198EjrXoihyQBcdCK21A-AbxYKbz1-p4OZMZytAEdT5g_hpu_Ncvk4lYlIyfrtVCr-6idz6cNy1Cs2DkNdpXEVbvD0AHNRmagPGQHBz_jbf8b-gdHKdMgnNVYixK1oJJZEMfj748SjPlkLHxxcIipl7OJn-Ex982Gf7q04WMEx7Ma7m2x8SCddKp6_ryrfTSjZ6h4Gx3MQ5R9RLXgwpoD4FGvSRc9Rmcin2TLadghAFi_sHVntqFwxHXoa85ze6Gk3YuHfnyeoeeF3g6OguejmgTH0LzE1NTsg_e4miVni5A5MjMgsyLqpHln7IMdUkXn0VndyLop2wKH5qoaxLD7oUz6PKT8dGLaHvtabmLQT0CvLFOUsNkda27vZjCMmrwB5HBVdMVxdcuf5xr17rYX_MKQ2jun6V70_1_hYX6t6cvtOtOUOTuxh9P99tP0SH1141HrW44a8raPL_aDXg7jekrH5gm1lBWaK8MObJ6E-R49A9Fg_gbWztjmTItItWSA709nGm8fuQr2X2WUeTxTgGbqwUu1KdOuxa1t3xkXFb89iLhWJp2VC9Lgag=w1902-h1428-no)
![Pins on raspberry pi](https://lh3.googleusercontent.com/C8-vDFjaESDCAHVc4qDQuWMYUR4AX6Q3xjS0qwCp_LabVwBO-EPDfpb_UB3jSkW1Uqr8NVNJxmyr7YmxPVEo18tnpQitUvY9J0ROatuVweotBX8uTKqvSo7CQ-YSXGHyfQCgQVFMTJZ2dscP4CbRliMo8yVEwb9Mu-ZVUBLVJoAV47Rk_JCb_HBMtRSbadqak56RVkBXILI1RC2OUtOfaxxFYzlMwUqffarEL2BrjWLmqlgFlVI89AScVkbI8jdjqrXNhodAGCrD5foX7GeVx7o3yIBYEbN8L18FRKd8NX8uFkGWqKNaxRBKH-zZ0Fxf25vAgXEBPCC5A7bQByPxcg5Mxa4o3lAbM9LxusKdCYR_SdVu_Gky-mCDceHjFBf_-oCXGEa_cuF1o_ZLMiJkyIP5IBP3b3eiSxw2APbR4oAY73R9AoD1D2vi-OqBeQF0OoKD_D7otrY30-62VE6VANx01wKlOpWOqF6iA_oWGaFcnJEwRyirCa11z4enhkdShAe0Revls7raPPydadRJnFY0dR-FU6jwCUMJghP9DZyHp_vy1mO28FtCJoKxPdXW6FagQbOQqA33RmgjPecrZtTd-B6J7Uv4VlZWAXfXbxOh_jkA7A7CmKZHjyhupKVIeNR22YBcUgdjvGXgtrxergp-IvD2W9kEyhw_czA022mfQBy9J7md42Bcsl1Hl0HlUH4yZ2EvUPC3Tnl3F7pVImqKFimTniGR3b5YVXZCE1jwcrAIAKfUfF6U=w1902-h1428-no)
![Pins on raspi alternate](https://lh3.googleusercontent.com/owb-j9-7nwU1t8NdzyuhxNxeUmt_NNfVBnKDBByE0tKsIOhFy7oKyWM_2fZdXuoTl3eDEqP2WRCChJgNHvKIu-D3g5cR2DFogZ7tnqhzCv0IwyOvBwx8Hjzirhm4YMkL940TQESmPFE9jluXE29SYRFwZ3llP_ETxfblBk8uOgFZlfDVbvAJGFuyanMOyEVVy4p9ETmKnb9i1NJZRLC1a8OiLmjSBEDnMuNe7_XKBEYTRwVnayI_AAy-DabHej3HbvV2iTiuGnXhC5EiNG2i9SYRO15Yi_SuHjGBOpDyU9L0nvpYExFCRefbAbnfeLT6xvLI5fs78Z5Dz0ZrbekHmYduXd_wguTqFqAUDkLE8OlnDIleFQ8RNu3pWS6RkHYMtLLHw0mng07gZzVB6AIGOudm7c3q5xoE0SPnm8DVCkrHy8LjKZ0aebJOL2M4TZzmjlZkde6w-xgdigqCCGX23lFhS17TJLCKkaSj3l5qyddyNB1IinnZloCgRBURMXVYm0RVlT7FZTUxC4szVJObLU-u6BjkcFYfGKfXDUNfEfr-5EEFY_nVnzzztKCZdvBu8mUE7lxDILGndhJE3KUYjUV04esie5q3u94SnKpQj8Dz_sIvWTxRtKHauBS5h1KWaFgCFhFCyRHj6CutsLkdNC7HhC0uam6rXRqV7BAa7U-Jqp9IOKvib-iFl7oiXluDl8Vf0Zamf6_Nbrjzfwsr56apVzDX0LJm1iPPgM7DSiCqt8gxGV4AOz7U=w1902-h1428-no)

# Install avrdude on Raspi

## Option A - Install with apt
This is easiest method but see footnote
```
sudo apt update
sudo apt install avrdude
```

Footnote: for me apt installs avrdude revision `6.3-20171130+svn1429-2+rpt1`. You may run into 2 issues using packaged binaries:
 1) Avrdude needs to be compiled with a linuxgpio flag
 2) There appears to be a bug in revision `6.3` that breaks linuxgpio. Install a revision before or after `6.3` otherwise you will get the error `Can't export GPIO 8, already exported/busy?: Invalid argument`. (bug link: http://savannah.nongnu.org/bugs/?47550)
Check what version your apt will use with `apt-cache policy avrdude`

## Option B - Install from source
```
sudo apt update
sudo apt install -y build-essential bison flex automake libelf-dev libusb-1.0-0-dev libusb-dev libftdi-dev libftdi1
wget http://download.savannah.gnu.org/releases/avrdude/avrdude-6.2.tar.gz
tar xvfz avrdude-6.2.tar.gz
cd avrdude-6.2
./configure --enable-linuxgpio
make
sudo make install
```
Ensure avrdude is installed correctly
```
cd ~
avrdude -v
```



# Configure avrdude

Edit config for avrdude
```
# This is for apt install method, if using manual install find global config
# file location with avrdude -v
sudo nano /etc/avrdude.conf
```
Use `Ctrl+w` to find `linuxgpio`. Uncomment the config and edit it so it looks like:
```
programmer
  id    = "linuxgpio";
  desc  = "Use the Linux sysfs interface to bitbang GPIO lines";
  type  = "linuxgpio";
  reset = 8;
  sck   = 11;
  mosi  = 10;
  miso  = 9;
;
```

Check avrdude is installed properly
```
avrdude -v
```



Footnote: in theory this could be done with user config (~/.avrduderc) but this does not work since all avrdude read/write commands need to be run with sudo due to Raspi bug here (http://avr.2057.n7.nabble.com/bug-44218-linuxgpio-not-working-with-raspberryPi-2-quot-Can-t-open-gpioX-direction-quot-Permission-dy-td21548.html) (https://github.com/raspberrypi/linux/issues/553)


# Connect Turnigy 9X to Raspi
Install gpiozero
```
sudo apt install python3-gpiozero
```
Get the pinout of you board with
```
pinout
```
This prints the pinout of your board like this

There are two number types, the physical pin numbers which are in brackets `(19)`, and the internal Broadcom "BCM" pin numbers like `GPIO10`. The BCM pin numbers are what is referenced in the avr configuration so wire the Turnigy 9X and Raspi up as follows:
```
           3V3  (1) (2)  5V
         GPIO2  (3) (4)  5V     -- VCC+
         GPIO3  (5) (6)  GND    -- GND
         GPIO4  (7) (8)  GPIO14
           GND  (9) (10) GPIO15
        GPIO17 (11) (12) GPIO18
        GPIO27 (13) (14) GND
        GPIO22 (15) (16) GPIO23
           3V3 (17) (18) GPIO24
MOSI -- GPIO10 (19) (20) GND
MISO --  GPIO9 (21) (22) GPIO25
 SCK -- GPIO11 (23) (24) GPIO8  -- RESET
           GND (25) (26) GPIO7
```

# Choosing the chip type to chip with avrdude
You can list all the AVR microcontrollers configured to work with avrdude with
```
avrdude -c linuxgpio -v
```

Read the text on the chip in your 9X to determine which AVR microcontroller it is and match it to one in the list from the command above. Mine chip reads 'ATMEGA64A AU 1309'. Avrdude doesn't appear to have a config for the ATmega64A but a quick search reveals that ATmega64A is a drop in replacement for the ATmega64 which has a config `m64`

Try connecting to the chip with
```
sudo avrdude -c linuxgpio -p m64
```

# OpenTX Install
Get the companion app and download which ever firmware version you want to use.

```
om@DESKTOP-7T7GALB:/mnt/c/Users/om/Downloads$ rsync -r raspi-share/ pi@10.0.0.138:~/raspi-share/
om@DESKTOP-7T7GALB:/mnt/c/Users/om/Downloads$ rsync -r pi@10.0.0.138:~/raspi-share/ raspi-share/
```

# ER9XV2 (aka mbtx) Install

mbtx5a.zip from https://openrcforums.com/forum/viewtopic.php?f=5&t=8217
use mbtx.hex

make backup of current firmware
```
sudo avrdude -c linuxgpio -p m64 -v -U flash:r:flash_dump.hex:i
```

write mbtx.hex
```
sudo avrdude -c linuxgpio -p m64 -v -U flash:w:mbtx.hex:i
```


# Debugging
If you some of the commands without sudo you will get error `Can't open gpioX/direction: Permission denied`. Subsequent commands will then fail with `Can't export GPIO 8, already exported/busy?: Device or resource busy`. To fix this run `sudo echo 8 > /sys/class/gpio/unexport`

https://github.com/raspberrypi/linux/issues/553

