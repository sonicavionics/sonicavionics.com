# Dingboard notes

This will be the first board. Gonna be copying the MARS amongus board a bit. All parts are available for PCBA with JLCPCB.
[Here's the link](https://github.com/zeulewan/dingboard) to the Altium project repo

### Components (not final)

 - MCU: RP 2040, [Hardware design guide](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf), [datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)
 
 - IMU: [ICM-42670](https://datasheet.octopart.com/ICM-42670-P-InvenSense-datasheet-155317655.pdf?src-supplier=Component+Distributors+Inc.)

 - Barometer: [LPS22HH](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/SGST/SGST-S-A0007383744/SGST-S-A0007383744-1.pdf?src-supplier=IHS+Markit)

 - Flash: [W25Q128JV](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/WBND/WBND-S-A0008390754/WBND-S-A0008390754-1.pdf?src-supplier=IHS+Markit)

 - Power: 

    - [18650](https://old.reddit.com/r/18650masterrace/comments/qp21o8/buying_18650_batteries_start_here/) [charger](https://www.reddit.com/r/18650masterrace/comments/1gqk8iy/recommendations_for_a_battery_charger/)

    - Charing and switching IC: [BQ2407](https://www.ti.com/lit/ds/symlink/bq24074.pdf)

    - [(i2c power indicator](https://cdn.sparkfun.com/datasheets/Prototyping/bq27441-g1.pdf) for use in next board). [Sparkfun board for reference](https://www.sparkfun.com/products/13777)

    - Regulator: [RT9080-33GJ5](https://www.lcsc.com/datasheet/lcsc_datasheet_2009192305_Richtek-Tech-RT9080-33GJ5_C841192.pdf) for both battery 3.7v to 3.3 and USB 5v to 3.3


 - LED: Power status indicator


### Checklist

- [x] Altium with GitHub
- [x] Begin PCB V1
- [ ] Altium with Solidworks
- [ ] Complete board schematic
- [ ] Complete board layout
- [ ] JLCPCB PCBA

### Thoughts

- Using a single MOSFET for switching between USB and battery voltage is just too janky.
    - Shoot through voltage.
    - The way to do it simply would be by taking advantage of the "Zero Gate Voltage Drain Current", but there's a load connected to the source so the voltage probably wont rise
    - In-rush current, you need a resistor to the gate
    - Going to need more robust circuitry than this
    - Could flip the P channel enhancement mosfet to have the current go from source to drain in order to get the negative voltage, but too janky
    - Going with a BQ2407x that handles power switching and battery charging. It's basically designed for this exact thing.

### Video references
Good videos:

- [Altium Designer Quick-Start Tutorial with Phil Salmony from Phil's Lab](https://www.youtube.com/watch?v=YTGzncKU5RY)

- [Raspberry Pi RP2040 Hardware Design | Altium Designer | JLCPCB - Phil's Lab #28](https://www.youtube.com/watch?v=X00Cm5LMNQk)