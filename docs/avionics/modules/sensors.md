# Sensor Module

- MCU: RP 2040, [Hardware design guide](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf), [datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)

- IMU: [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

- Gas sensor: [BME680](https://www.bosch-sensortec.com/products/environmental-sensors/gas-sensors/bme680/)

- Flash: [W25Q128JV](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/WBND/WBND-S-A0008390754/WBND-S-A0008390754-1.pdf?src-supplier=IHS+Markit)

- Power multiplexer [TPS2121](https://www.ti.com/lit/ds/symlink/tps2121.pdf?ts=1733915332904&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS2121#SLVSEA31194)
Using it in Automatic Switchover with Priority (XCOMP) mode with the battery as the main and USB as secondary  

Current KiCad bom

{{ read_csv('sensors/bom.csv') }}