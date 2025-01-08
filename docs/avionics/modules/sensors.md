# Sensors

---

<div align="center">
  <div>
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/board.front.png" alt="3D Render" style="height: auto; width: 300px;">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/board.back.png" alt="3D Render" style="height: auto; width: 300px;">
    <p><em>3D Render</em></p>
  </div>
  <br>

  <div>
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/sch.svg" alt="Schematic" style="height: auto; max-width: 600px;"><br>
    <p><em>Schematic</em></p>
  </div>
  <br>
  
  <div>
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/pcbf.svg" alt="Front" style="height: auto; width: 300px;">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/pcbb.svg" alt="Back" style="height: auto; width: 300px;"><br>
    <em>Footprint</em>
  </div>
</div>

## Main chips

- MCU

    - MCU [RP 2040](https://www.raspberrypi.com/products/rp2040/)

    - Flash [W25Q128JVP](https://www.winbond.com/hq/product/code-storage-flash-memory/serial-nor-flash/?__locale=en&partNo=W25Q128JV)

- USB-C [JLC USB-C port](https://jlcpcb.com/partdetail/ShouHan-TYPE_C_16PIN_2MD_073/C2765186)

- Momentary Button [TS-1187A-B-A-B](https://jlcpcb.com/partdetail/XkbConnectivity-TS_1187A_B_AB/C318884)

- Sensors

    - IMU [BNO055](https://www.bosch-sensortec.com/products/smart-sensor-systems/bno055/)

        - IMU Crystal [ABS07-32.768KHZ-T](https://www.digikey.ca/en/products/detail/abracon-llc/ABS07-32-768KHZ-T/1236858)

    - Altimeter [BMP388](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp388/)

- CAN [Controller and transceiver](https://www.digikey.ca/en/products/detail/microchip-technology/MCP25625T-E-ML/4860099)

    - CAN chip crystal [X322516MLB4SI](https://www.lcsc.com/datasheet/lcsc_datasheet_2403291504_YXC-Crystal-Oscillators-X322516MLB4SI_C13738.pdf)

## Assembly

Standard assembly will be used over economic assembly. The primary reason is that the BNO055 and BMP388 aren't available with economic assembly. The number of extended parts on the board is exactly half of all unique components on the board, therefore the loading fee is equal either way. 


## Point of Load vs Bus Regulation

Point of load regulation is where your power bus is lets say 7.4 volts, and all your chips are 5v so you regulate the voltage near each chip. Bus regulation would be having the bus 5v. 

Point of load means having regulators on each module, but inherently less stability. 
If you can get away without having to do point of load regulation you could save a lot of money though. 

To reduce costs, both the 5v and the 3.3v regulators will be deleted from the modules, in favour of regulated bus power. Before the full power module is ready however, we will need a very power module that supplies 5v and 3.3v.

$375 can be saved buy not doing point of load. Delete the two regs and mux, that gets rid of 5 extended JLCPCB parts. It costs $3 per extended part (actually it's about 2.21). The minimum order number is 5. There will be 5 modules. 5 * 3 * 5 * 5 = 375.

## Impedance matching

[This guide](https://www.digikey.ca/en/maker/projects/how-to-route-differential-pairs-in-kicad-for-usb/45b99011f5d34879ae1831dce1f13e93) was used to do the impedance matching. The KiCad calculator and the [JLCPCB design rules](https://jlcpcb.com/capabilities/pcb-capabilities) were used. 

## BOM

[Current KiCad bom](https://github.com/sonicavionics/4in/blob/main/kicad/modules/sensors/bom.csv)

{{ read_csv('sensors/bom.csv') }}
