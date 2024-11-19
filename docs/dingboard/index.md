# dingboard
<p style="font-size: 20px;">Simple flight computer that uses all the best practices. A good place to start.</p>
This board is everything you would want in a passive data collection flight computer. Made for beginner model rockets. Basically a better version of [this](https://zeul.ca/projects/archive/template.php?day=6&month=6&year=2022&title=Calculating_the_Drag_Coefficient).
******

### Initial Requirements and Design Goals
The primary goal of dingboard is to enable my personal learning.
This will be the first board of many. The successor to dingboard will be a CAN enabled system in a 4-inch diameter form factor which will hopefully be launched this summer.

Primary Functional Requirements for dingboard:

- Easy to operate and understand
- Fully open source
- Assemblable by JLCPCB PCBA
- On board charging and automatic power switching using simple chip
- Charging status indicators
- MCU status indicator, sleep, data collection etc.
- Altium and solidworks integration
- Utilize all known best practices to enable scalability
- Components:
    - Barometer
    - Accelerometer
    - Thermistor for battery protection
- Use entire safe range of battery (use a buck boost)

[Here's the link](https://github.com/zeulewan/dingboard) to the Altium project repo

### Components (not final)

 - MCU: RP 2040, [Hardware design guide](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf), [datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)
 
 - IMU: [ICM-42670](https://datasheet.octopart.com/ICM-42670-P-InvenSense-datasheet-155317655.pdf?src-supplier=Component+Distributors+Inc.)

 - Barometer: [LPS22HH](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/SGST/SGST-S-A0007383744/SGST-S-A0007383744-1.pdf?src-supplier=IHS+Markit)

 - Flash: [W25Q128JV](https://datasheet.ciiva.com/pdfs/VipMasterIC/IC/WBND/WBND-S-A0008390754/WBND-S-A0008390754-1.pdf?src-supplier=IHS+Markit)

 - Power: 

    - [18650](https://old.reddit.com/r/18650masterrace/comments/qp21o8/buying_18650_batteries_start_here/) [charger](https://www.reddit.com/r/18650masterrace/comments/1gqk8iy/recommendations_for_a_battery_charger/) [datasheet](https://cdn.shopify.com/s/files/1/0481/9678/0183/files/samsung_25r_data_sheet.pdf?v=1605015771)

    - Charing and switching IC: [BQ2407](https://www.ti.com/lit/ds/symlink/bq24074.pdf)

    - [Extra current protection circuit](https://www.ti.com/lit/ds/symlink/bq2970.pdf?ts=1731982692134&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FBQ2970%252Fpart-details%252FBQ29700DSER)

    - Thermistor: ?

    - Buck-boost: [TPS63070 ](https://www.ti.com/lit/ds/symlink/tps63070.pdf?ts=1731929729399&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS63070%253Futm_source%253Dgoogle%2526utm_medium%253Dcpc%2526utm_campaign%253Dapp-null-null-gpn_en-cpc-pf-google-eu%2526utm_content%253Dtps63070%2526ds_k%253DTPS63070%2526dcm%253Dyes%2526gad_source%253D1%2526gclid%253DCj0KCQiA6Ou5BhCrARIsAPoTxrCaR9ul4GKeeqk04exPs55nL8KK7Iabunx0if0zZDwEN4diN9oB0GIaAmwyEALw_wcB%2526gclsrc%253Daw.ds)


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
- Not using RT9080. Need a buck boost. I should be able to use the entire range of battery

### Video references
Good videos:

- [Altium Designer Quick-Start Tutorial with Phil Salmony from Phil's Lab](https://www.youtube.com/watch?v=YTGzncKU5RY)

- [Raspberry Pi RP2040 Hardware Design | Altium Designer | JLCPCB - Phil's Lab #28](https://www.youtube.com/watch?v=X00Cm5LMNQk)
