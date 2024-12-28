---
title: Chip Selection
date: 2024-12-12
comments: true
authors:
  - zeul
categories:
  - 4" Avionics
---

Here is the post outlining the reasons for picking the chips. This post will be updated in the future with reasons why or why not to pick these chips. Requirement for all chips was being available on JLC. 

### MCU

[RP 2040](https://www.raspberrypi.com/products/rp2040/)

I went with the RP2040 because the alternatives are usually more complex or more expensive. The documentation on the rp2040 is great and there's a great online community around it. It's more than fast enough to accomplish what we need to do. 

ESP chips get kind of expensive, although they have some kind of CAN and ethernet capability on board. When we do go ethernet it'll probably be an addition to the CAN bus though.

#### Flash
[W25Q128JVP](https://www.winbond.com/hq/product/code-storage-flash-memory/serial-nor-flash/?__locale=en&partNo=W25Q128JV) Didn't even read the data sheet. It's the one they use in the rp2040 hardware design guide, it's the most flash the rp2040 can use.

#### Crystal
[ABM8-272-T3](https://www.digikey.ca/en/products/detail/abracon-llc/ABM8-272-T3/22472366) In the rp2040 design guide. 

### USB-C 

[USB-C port](https://jlcpcb.com/partdetail/Korean_HropartsElec-TYPE_C_31_M04/C129018) Easy choice; pretty much only one on JLCPCB at the time

### Power

#### 3.3v Regulator

[LMR51430YFDDCR](https://jlcpcb.com/partdetail/TexasInstruments-LMR51430YFDDCR/C5219261) Constant, 1kHz switching reg, wide voltage input range, goes to 3.3v, cheap

#### 5v buck-boost

[TPS630701](https://www.ti.com/lit/ds/symlink/tps63070.pdf?ts=1734177677058)

### Power MUX

[TPS2121RUXR](https://jlcpcb.com/partdetail/TexasInstruments-TPS2121RUXR/C485916) Two inputs, one output cheap, on JLC. done.
Using this in Highest Voltage Operation (VCOMP) mode with the battery as the main and USB as secondary  

### Sensors

#### IMU

Need IMU with accelerometer, gyroscope and magnetometer, high sample rate, some vibration resistance, onboard sensor fusion and on JLC.

BNO055, BNO055, BMX055, MPU-9250 are off the table because they need standard assembly. The options are:
- MPU-6050 (only 6-axis)
- ICM-20948 (9-axis with fusion)

So there's only the ICM-20948 if I wan't to do 9 axis.

#### Pressure

Need temperature and pressure and high sample rate.

Some JLC options for pressure sensors:
- MS563702BA03-50
- GZP6816D
- GZP131-701A
- MS560702BA03-50
- HP203B
- WF100SPZ 0.4BG S6 AT
- MPXHZ6115AC6T1
- GZP170-701A
- LWLP5001DD
- MPS-3117-006GC-A3
- NSPAS1N115RR01

MS560702BA03-50 was chosen for high speed capabilities.


#### Payload Module

We might add a payload module with a bunch of different sensors and the "experiment" will be to see the discrepancies in their readings.


### 0201, 0402 or 0603?
Should I use 0603, 0402 or 0201?
If I go with 0603 we can solder it pretty easily. 0201 its not happening, and 0402 is harder. Those components aren't even the expensive ones to have JLCPCB assemble for you. Actually 0201 is more expensive I think. Okay 0402 it is then. 

Okay there's not that many JLC basic resistors so I'll use 0603 and hand solder those ones.

### Conclusion
It's not a good idea to spend too long on chip selection, better to just start making shit and find out along the way. I'll probably regret some of these choices, but that is part of learning.
Some chips I really didn't think that much about, if it does the job and is cheap enough I'll use it I don't need to compare it with every single alternative out there. Some chips like the sensors I compared a bunch of chips in the same range, and took inspiration from other teams and such. ChatGPT is great for suggesting chips, it currently gets the numbers wrong very often so you can't trust anything and have to read the data sheet yourself to confirm but it still makes it much much easier.
Vibration wasn't too much a concern, most chips can withstand the vibration we'd put them through.