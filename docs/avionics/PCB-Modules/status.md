# [Status](https://github.com/sonicavionics/4in-NicolasSuarez-statusmodule)

---

The status module displays the status of other avionics subsystems.

---

<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-status/refs/heads/main/images/board.front.png" alt="3D Render">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-status/refs/heads/main/images/board.back.png" alt="3D Render">
</div>
<p class="image-caption">3D Render</p>

![alt text](https://raw.githubusercontent.com/sonicavionics/4in-status/refs/heads/main/images/sch.svg)
<p class="image-caption">Schematic</p>


<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-status/refs/heads/main/images/pcbf.svg" alt="Front">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-statuse/refs/heads/main/images/pcbb.svg" alt="Back">
</div>
<p class="image-caption">Footprint</p>

---

## Action Items

### Schematic 

- USB resistors 
- Add buttons
    - 4 LCD
    - 1 reset
    - 1 boot 
- Source SD card mount

### Routing

- Routing USB and CAN 
    - Learn differential pairs
    - Learn about impedance matching
- Digikey trace width calculator

### Testing

- Test out display module.



## Components

### <a href="https://ww1.microchip.com/downloads/aemDocuments/documents/OTH/ProductDocuments/DataSheets/MCP25625-CAN-Controller-Data-Sheet-20005282C.pdf" target="_blank">MCP25625 CAN Controller</a>
- The CAN controller reads messages from different modules and transmits the received data to the RP2040 MCU.

### <a href="https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf" target="_blank">RP2040 MCU</a>
-  Receives CAN messages and displays them on an LCD screen.
-  Push buttons connected to the MCU will be used for resetting and booting the MCU.
- Push buttons connected to the MCU will allow navigation through the CAN messages displayed on the LCD screen, enabling switching between different devices forward and backward.

### <a href="https://www.lcsc.com/datasheet/lcsc_datasheet_2109061830_XUNPU-TF-115-BCP9_C720505.pdf" target="_blank">Micro SD Card Slot</a>
- Capable of storing CAN data onto an SD card.





<!-- ## Components

- **MCU**

    - MCU [RP 2040](https://www.raspberrypi.com/products/rp2040/)

    - Flash [W25Q128JVP](https://www.winbond.com/hq/product/code-storage-flash-memory/serial-nor-flash/?__locale=en&partNo=W25Q128JV)

- **USB-C** [JLC USB-C port](https://jlcpcb.com/partdetail/ShouHan-TYPE_C_16PIN_2MD_073/C2765186)

- **Momentary Button** [TS-1187A-B-A-B](https://jlcpcb.com/partdetail/XkbConnectivity-TS_1187A_B_AB/C318884)

- **Sensors**

    - IMU [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

        - IMU Crystal [ABS07-32.768KHZ-T](https://www.digikey.ca/en/products/detail/abracon-llc/ABS07-32-768KHZ-T/1236858)

    - Barometer [BMP388](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp388/)

- **CAN Controller and transceiver** [MCP25625](https://www.digikey.ca/en/products/detail/microchip-technology/MCP25625T-E-ML/4860099)

    - CAN chip crystal [X322516MLB4SI](https://www.lcsc.com/datasheet/lcsc_datasheet_2403291504_YXC-Crystal-Oscillators-X322516MLB4SI_C13738.pdf)

## Assembly

Standard assembly was chosen over economic assembly primarily because the BNO055 and BMP388 are not available with economic assembly. Additionally, since the number of extended parts on the board makes up exactly half of all unique components, the loading fee remains the same regardless of the assembly type. -->
