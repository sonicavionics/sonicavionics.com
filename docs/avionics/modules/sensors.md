# Sensor Module

MCU: RP 2040, [Hardware design guide](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf), [datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)

Flash: [W25Q128JV](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/WBND/WBND-S-A0008390754/WBND-S-A0008390754-1.pdf?src-supplier=IHS+Markit)

IMU: [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

The RESET pin is connected to a GPIO port so it needs to be brought 

Altimeter: [BMP388](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp388/)

Power multiplexer: [TPS2121](https://www.ti.com/lit/ds/symlink/tps2121.pdf?ts=1733915332904&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS2121#SLVSEA31194)
Using it in Highest Voltage Operation (VCOMP) mode with the battery as the main and USB as secondary  

## USB Impedance matching:

From the RP2040 hardware design guide:
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

{{ read_csv('sensors/bom.csv') }}