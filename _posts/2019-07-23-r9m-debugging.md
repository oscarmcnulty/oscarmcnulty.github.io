---
title: "Debugging FrSky R9M"
layout: post
---

# Binding
Binding requires

Matek F722-SE settings and wiring
http://www.mateksys.com/?p=4488

Passthrough programming
For UART2 use `serialpassthrough 1 57600`
for uart4 use `serialpassthrough 3 57600`

set serialrx_provider = FPORT
set serialrx_inverted = ON
set serialrx_halfduplex = ON

https://oscarliang.com/flash-frsky-rx-fc-passthrough/


https://openrcforums.com/forum/viewtopic.php?f=5&p=145301#p145301

frsky usb serial tool https://www.frsky-rc.com/frusb-3-fuc-3/

rx firmware https://www.frsky-rc.com/r9-mm/

arduino nano frsky stk
https://www.rcgroups.com/forums/member.php?u=393936
https://www.rcgroups.com/forums/showpost.php?p=36362006&postcount=855

https://www.rcgroups.com/forums/showthread.php?2245978-FrSky-S-Port-telemetry-library-easy-to-use-and-configurable

https://www.instructables.com/id/Arduino-Examples-2-Use-an-Arduino-as-a-FTDI-Progr/

http://www.sleeth.org/fpv/frsky-s6r-arduino-nano/
http://rcgear.ru/ru/frsky/arduino-stk
https://github.com/zendes/SPort

similar problem flashing r9m module: https://openrcforums.com/forum/viewtopic.php?t=10855

https://lh3.googleusercontent.com/AtAZMLUBnYpOvo1-ih3BBDhzO9ebYh3_VzmcnoO4sqjtxUub4z39TZOJCV7MEXvOTYxifjYKFRbnOJL7alF4HBY09ll6YW_BHjyU6FbWDy_fOuvPipUafcbOLifuwENF0DcrqNAFKB4=w2400

```
serial 3 64 115200 57600 0 115200
set serialrx_provider = FPORT
set serialrx_halfduplex = ON
set serialrx_inverted = ON
```
