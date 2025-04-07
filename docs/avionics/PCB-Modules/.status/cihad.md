# Cihad's Status Module 

[Cihad's Status Module](https://github.com/sonicavionics/4in-cihadkhaled-statusmodule)

---

Cihad's prototype of the status module.

---

<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-cihadkhaled-statusmodule/refs/heads/main/images/board.front.png" alt="3D Render">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-cihadkhaled-statusmodule/main/images/board.back.png" alt="3D Render">
</div>
<p class="image-caption">3D Render</p>

![alt text](https://raw.githubusercontent.com/sonicavionics/4in-cihadkhaled-statusmodule/7132b87a29a3697091c76b3631324f0dcd40ff1d/images/sch.svg)
<p class="image-caption">Schematic</p>

<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-cihadkhaled-statusmodule/7132b87a29a3697091c76b3631324f0dcd40ff1d/images/pcbf.svg" alt="Front">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-cihadkhaled-statusmodule/7132b87a29a3697091c76b3631324f0dcd40ff1d/images/pcbb.svg" alt="Back">
</div>
<p class="image-caption">Footprint</p>

<!-- # Components -->


<!-- - [Regulator](https://jlcpcb.com/partdetail/DiodesIncorporated-AP63203WU7/C780769)
- [Inductor](https://jlcpcb.com/partdetail/Tdk-SLF7055T_6R8N2R83PF/C21218)
- **USB-C** [JLC USB-C port](https://jlcpcb.com/partdetail/ShouHan-TYPE_C_16PIN_2MD_073/C2765186) -->




## CAN bus - MCP25625T-E/ML
- OSC1 & 2 are connected to capacitors and an oscillator crystal - X322516MLB4SI
- CLKOUT is NC because the RP2040 already has a clock signal
- TxCAN -> TxD (based on FIGURE 1-2)
- RxD -> RxCAN (based on FIGURE 1-2)

“The TXD and RXD pins of the CAN transceiver must be externally connected to the TxCAN and RxCAN pins of the CAN controller.” (Datasheet)

![alt text](cihad/canrp.png)