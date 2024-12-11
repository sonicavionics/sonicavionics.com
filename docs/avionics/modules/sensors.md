# Sensor Module

- MCU: RP 2040, [Hardware design guide](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf), [datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)

- IMU: [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

- Gas sensor: [BME680](https://www.bosch-sensortec.com/products/environmental-sensors/gas-sensors/bme680/)

- Flash: [W25Q128JV](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/WBND/WBND-S-A0008390754/WBND-S-A0008390754-1.pdf?src-supplier=IHS+Markit)

- Power multiplexer [TPS2121](https://www.ti.com/lit/ds/symlink/tps2121.pdf?ts=1733915332904&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS2121#SLVSEA31194)
Using it in Automatic Switchover with Priority (XCOMP) mode with the battery as the main and USB as secondary  

```
10.7 Hotplugging with TPS212x
Some applications require power muxing between hotplugged inputs, such as USB applications or systems with
secondary supplies coming from a long cable. During a hot plug event, the inherent inductance in the cable and
input traces can cause a voltage spike on the input pin (V = LCABLE * dI / dT). This can cause a voltage spike on
the input of the TPS212x that could potentially exceed the absolute maximum rating.
```

- TVS (Transient Voltage Spike) protection diode [TVS1800](https://www.ti.com/lit/ds/symlink/tvs1800.pdf?ts=1733946180781&ref_url=https%253A%252F%252Fwww.google.com%252F) This will let us use any length USB cable. I don't think we need one on the battery side. The traces after the battery connection point don't matter, and the battery cable will be fairly short. TVS is around 5us. I'm not gonna put a USB protection IC on this board, but the power board will definitely have one.
Actually we don't need this.


Current KiCad bom

{{ read_csv('sensors/bom.csv') }}