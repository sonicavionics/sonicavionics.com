# Sensors

[Current Schematic](https://github.com/zeulewan/dingboard/blob/main/dingboard_kicad/sensors/sensors.pdf)

## Chips

- MCU

    - MCU [RP 2040](https://www.raspberrypi.com/products/rp2040/)

    - Flash [W25Q128JVP](https://www.winbond.com/hq/product/code-storage-flash-memory/serial-nor-flash/?__locale=en&partNo=W25Q128JV)

    - MCU Crystal [ABM8-272-T3](https://www.digikey.ca/en/products/detail/abracon-llc/ABM8-272-T3/22472366)

- USB-C [JLC USB-C port](https://jlcpcb.com/partdetail/Korean_HropartsElec-TYPE_C_31_M04/C129018)

- Regulators 

    - 3.3v buck [LMR51430YFDDCR](https://www.ti.com/product/LMR51430/part-details/LMR51430YFDDCR)

    - 5v buck-boost for CAN chip [TPS630701](https://www.ti.com/lit/ds/symlink/tps63070.pdf?ts=1734177677058)

- Power MUX [TPS2121RUXR](https://www.ti.com/product/TPS2121/part-details/TPS2121RUXR) VCOMP mode

- Sensors

    - IMU [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

        - IMU Crystal [ABM8-272-T3](https://www.digikey.ca/en/products/detail/abracon-llc/ABM8-272-T3/22472366)

    - Altimeter [BMP388](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp388/)

- CAN [Controller and transceiver](https://www.digikey.ca/en/products/detail/microchip-technology/MCP25625T-E-ML/4860099)

## USB Impedance matching:

From the RP2040 hardware design guide
```
Even though RP2040 is limited to full speed data rate (12Mbps), we should try and makes sure that the characteristic
impedance of the transmission lines (the copper tracks connecting the chip to the connector) are close to the USB
specification of 90Ω (measured differentially). On a 1mm thick board such as this, if we use 0.8mm wide tracks on
USB_DP and USB_DM, with a gap of 0.15mm between them, we should get a differential characteristic impedance of
around 90Ω. This is to ensure that the signals can travel along these transmission lines as cleanly as possible,
minimising voltage reflections which can reduce the integrity of the signal. In order for these transmission lines to work
properly, we need to make sure that directly below these lines is a ground. A solid, uninterrupted area of ground copper,
stretching the entire length of the track. On this design, almost the entirety of the bottom copper layer is devoted to
ground, and particular care was taken to ensure that the USB tracks pass over nothing but ground. If a PCB thicker than
1mm is chosen for your build, then we have two options. We could re-engineer the USB transmission lines to
compensate for the greater distance between the track and ground underneath (which could be a physical
impossibility), or we could ignore it, and hope for the best. USB FS can be quite forgiving, but your mileage may vary. It is
likely to work in many applications, but it’s probably not going to be compliant to the USB standard.
```

Since we're using a 4 layer board, I'll use the [JLC impedance calculator](https://jlcpcb.com/pcb-impedance-calculator) to get the 90Ω

Current KiCad bom

https://github.com/zeulewan/dingboard/blob/main/dingboard_kicad/sensors/bom.csv

{{ read_csv('sensors/bom.csv') }}