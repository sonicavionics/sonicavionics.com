# next board
<p style="font-size: 20px;">I'll change the name later</p>
I gotta plan ahead so this is where I'll put the next board ideas.
******

Going to need to power 5v stuff. Better to buck than boost. Probably going to go with 3s.

### COTS Components

GPS

 - Featherweight 915 MHz
 - BigRedBee COTS GPS

### ICs

GPS
    - [blox m10q](https://content.u-blox.com/sites/default/files/documents/SAM-M10Q_DataSheet_UBX-22013293.pdf)

- Charging IC
    - [TI 1s to 3s charger and power path selector](https://www.ti.com/lit/ds/symlink/bq24133.pdf)

- Power indicator

- [Buck-Boost Converter](https://www.ti.com/lit/ds/symlink/tps63060.pdf?ts=1731997031379&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS63060) 
or this Buck-boost: [TPS63070 ](https://www.ti.com/lit/ds/symlink/tps63070.pdf?ts=1731929729399&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS63070%253Futm_source%253Dgoogle%2526utm_medium%253Dcpc%2526utm_campaign%253Dapp-null-null-gpn_en-cpc-pf-google-eu%2526utm_content%253Dtps63070%2526ds_k%253DTPS63070%2526dcm%253Dyes%2526gad_source%253D1%2526gclid%253DCj0KCQiA6Ou5BhCrARIsAPoTxrCaR9ul4GKeeqk04exPs55nL8KK7Iabunx0if0zZDwEN4diN9oB0GIaAmwyEALw_wcB%2526gclsrc%253Daw.ds)
[or this ](https://www.ti.com/lit/ds/symlink/tps63020.pdf?ts=1732930705266&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FTPS63020)


### Ideas

- Will have a multiplexer and on each compute board.
- 3.3v rail, 5v rail, and unregulated 12v rail
- dingboard just has one regulated 3.3v rail
- dongboard will have barrel jack on the power board for fast charging with a charging IC, it will also have a rp2040 and a voltage monitoring chip. The UCB-C port won't even have its power terminals connected. It will be just for programming. the barrel or QD will be for charging/power supply while the rocket is on the pad. The CAN bus will also have a QD on it.
