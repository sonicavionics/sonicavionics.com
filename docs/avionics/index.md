# 4" Avionics

<p style="font-size: 20px;">Avionics for a 4 inch rocket</p>

<style>
/* Disable background highlight on hover */
table tr:hover, table td:hover {
  background-color: transparent !important;
}

/* Prevent text selection when hovering */
table, table * {
  user-select: none;
}
</style>
<div align="center">
  <table>
    <tr>
      <td align="center" style="vertical-align: middle;">
        <img src="https://raw.githubusercontent.com/sonicavionics/4in-sensors/refs/heads/main/images/board.front.png" height="250" />
        <br />
        <a href="PCB-Modules/sensors/"><i>Sensors</i></a>
      </td>
      <td align="center" style="vertical-align: middle;">
        <img src="https://raw.githubusercontent.com/sonicavionics/4in-powersim/refs/heads/main/images/board.front.png" height="250" />
        <br />
        <a href="PCB-Modules/powersim"><i>PowerSim</i></a>
      </td>
      <td align="center" style="vertical-align: middle;">
        <img src="https://raw.githubusercontent.com/sonicavionics/4in-backplate/refs/heads/main/images/board.front.png" height="450" />
        <br />
        <a href="PCB-Modules/backplate"><i>Backplate</i></a>
      </td>
    </tr>
  </table>
</div>

![alt text](cad/thumbnail.png)
<p class="image-caption">CAD</p>

---

## Overview of System

The avionics system is composed of five  modules interconnected through CAN bus. These modules are: [Power](PCB-Modules/power.md), [Sensors](PCB-Modules/sensors.md), [GPS](PCB-Modules/gps.md), [Antenna](PCB-Modules/antenna.md), and [Recovery](PCB-Modules/recovery.md). The backplate features PCIe slots, and connects all the modules.

## Requirements and Design Goals

The primary goal of the 4-inch avionics system is to enable learning. This will be the first system of many. 

### Primary Functional Requirements

- Don't be janky.
- Fully open-source.
- Assemblable by JLCPCB.
- Incorporate all known best practices to enable scalability.
- It will be a CAN-enabled system in a 4-inch diameter form factor.

### Battery

The system will use a SRAD battery pack for custom-built boards, and COTS components will use a commercial battery pack. For the first launch, a 2s 2p pack inspired by [this video](https://www.youtube.com/watch?v=3dD5KmM8ciU) will be used.

## Improvements for the Next Version

- **USB Multiplexer**: Controlled by a Raspberry Pi Zero. The backplate will host the MUX, enabling digital reboots and removal of USB ports except on the Pi Zero.
- **Programmable Power MUX**: Allows remote rebooting of components.
- **Ethernet**: Inclusion for data transmission.
- **Camera Transmission**
- **USB Protection IC**
