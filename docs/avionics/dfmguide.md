# DFM Guide

**Design for manufacturing guide. <br> "Forked" from [QRET](https://qret.ca/)'s [component repository](https://www.notion.so/Component-Repository-2023-2024-160ca211d23080cd8ba2ee3102036125).**


## LCSC Part Numbers

JLCPCB is owned by LCSC, which is a large component distributor. An LCSC Part Number is a unique identifier for a given component. They will start with a “C” follow by several digits (e.g. C6186, C51230, etc.). We add these part numbers to our KiCAD schematics for parts we want assembled, and then can automatically generate a BOM (bill of material) that JLCPCB can accept. You can find these numbers on the JLCPCB page.

![Untitled](dfmguide/1.png)

## JLCPCB Basic vs. Extended Parts

When searching for components through JLCPCB, they are labelled either “Basic” or “Extended”. Basic components are ones that are used very frequently, and are thus loaded into the pick-and-place machines already. Extended components are less commonly used, and thus require additional effort to load them into machines. This extra effort translates to an **additional fixed cost of ~$4CAD** (”Feeder Loading fee”) for every Extended part. See [this page](https://jlcpcb.com/help/article/98-PCB-Assembly-FAQs) for more pricing details. We want to use Basic parts wherever possible. (Note: Even when currency is set to CAD, the prices on JLCPCB’s part inventory seem to be USD).

![Untitled](dfmguide/2.png)

## JLCPCB Economic vs. Standard PCB Assembly

When asking JLCPCB to solder components for us, they have two tiers; Economic and Standard. Economic comes with many benefits, largely the reduced price & option for Basic parts being free. Standard PCBA gives more options, but is more expensive (~$25 extra) and requires a loading fee for ALL components, thus resulting in a much higher price. More advanced features, such as very small components or gold-plated edge connectors, require Standard PCBA. See [this page for more info about JLCPCB’s Manufacturing and Assembly Capabilities](https://jlcpcb.com/capabilities/pcb-assembly-capabilities). We want to use the Economic option whenever possible. If “Economic” is selected, any “Standard Only” components will be highlighted after uploading the BOM during the order process. You can also use JLCPCB’s “[BOM Tool](https://jlcpcb.com/parts/bom-tool/)” to evaluate current part selection.

![Untitled](dfmguide/3.png)

![Untitled](dfmguide/4.png)

## Passive SMD Component Sizes

*Note: SMD is a form of SMT*.

We very commonly use the **Imperial** naming scheme when referring to passive SMD sizes.

We will be trying to avoid 0402 components where possible, to make assembly & repairs easier. 0603 and 0804 are our go-to sizes. Ideally we want to select components that JLCPCB stocks and avoid extended parts where possible.

![Untitled](dfmguide/5.png)

![Untitled](dfmguide/6.png)

## JLCPCB Generic SMD Components (WIP)

| **Value** | **Type** | **Footprint** | **Link** | **LCSC #** | **JLC Basic?** | **Notes** |
| --- | --- | --- | --- | --- | --- | --- |
| Red LED | LED | 0603 | [Link](https://jlcpcb.com/partdetail/Hubei_KentoElec-KT0603R/C2286) | C2286 | YES |  |
| Red LED | LED | 0805 | [Link](https://jlcpcb.com/partdetail/85425-NCD0805R1/C84256) | C84256 | YES |  |
| White LED | LED | 0603 | [Link](https://jlcpcb.com/partdetail/Hubei_KentoElec-KT0603W/C2290) | C2290 | YES |  |
| White LED | LED | 0805 | [Link](https://jlcpcb.com/partdetail/Hubei_KentoElec-KT0805W/C34499) | C34499 | YES |  |
| Yellow LED | LED | 0603 | [Link](https://jlcpcb.com/partdetail/73147-19_213_Y2C_CQ2R2L_3T_CY/C72038) | C72038 | YES |  |
| Yellow LED | LED | 0805 | [Link](https://jlcpcb.com/partdetail/Hubei_KentoElec-KT0805Y/C2296) | C2296 | YES |  |
| Green LED | LED | 0805 | [Link](https://jlcpcb.com/partdetail/Hubei_KentoElec-KT0805G/C2297) | C2297 | YES |  |
|  |  |  |  |  |  |  |
| 2N7002 | N-MOSFET | SOT-23 | [Link](https://jlcpcb.com/partdetail/9040-2N7002/C8545) | C8545 | YES |  |
| AO3400A | N-MOSFET | SOT-23-3L | [Link](https://jlcpcb.com/partdetail/Alpha_OmegaSemicon-AO3400A/C20917) | C20917 | YES |  |
| AO3401A | P-MOSFET | SOT-23 | [Link](https://jlcpcb.com/partdetail/Alpha_OmegaSemicon-AO3401A/C15127) | C15127 | YES |  |
| SI2301CDS | P-MOSFET | SOT-23 | [Link](https://jlcpcb.com/partdetail/VishayIntertech-SI2301CDS_T1GE3/C10487) | C10487 | YES |  |
| 1N5819WS | Schottky Diode | SOD-323 | [Link](https://jlcpcb.com/partdetail/GuangdongHottech-1N5819WS/C191023) | C191023 | YES |  |
| SS14 | Schottky Diode | DO-214AC | [Link](https://jlcpcb.com/partdetail/Mdd-SS14/C2480) | C2480 | YES |  |
|  |  |  |  |  |  |  |
| 1k | Resistor | **0805** | [Link](https://jlcpcb.com/partdetail/18201-0805W8F1001T5E/C17513) | C17513 | YES |  |
|  |  |  |  |  |  |  |
| 10pF | MLC Capacitor | 0603 |  | C1634 | YES |  |
| 10pF | MLC Capacitor | 0402 |  | C32949 | YES |  |
| 30pF | MLC Capacitor | 0603 |  | C1658 | YES |  |
| 2.2nF | Capacitor | 0603 |  | C1604 | YES |  |
| 10nF | MLC Capacitor | 0603 |  | C57112 | YES |  |
| 10nF | MLC Capacitor | 0402 |  | C15195 | YES |  |
| 100nF | MLC Capacitor | 0603 |  | C14663 | YES |  |
| 100nF | MLC Capacitor | 0402 |  | C1525 | YES |  |
| 1uF | MLC Capacitor | 0805 |  | C28323 | YES |  |
| 1uF | MLC Capacitor | 0603 |  | C15849 | YES |  |
| 1uF | MLC Capacitor | 0402 |  | C52923 | YES |  |
| 4.7uF | MLC Capacitor | 0805 |  | C1779 | YES |  |
| 10uF | MLC Capacitor | 0603 |  | C96446 | YES |  |
| 10uF | MLC Capacitor | 0402 |  | C15525 | YES |  |
| 22uF | MLC Capacitor | 0805 |  | C45783 | YES |  |
|  |  |  |  |  |  |  |
| 100Ohm | Ferrite Bead | 0805 |  | C1015 | YES |  |
| 600Ohm | Ferrite Bead | 0805 |  | C1017 | YES |  |
|  |  |  |  |  |  |  |

## JLCPCB “Basic Part” 0603 Resistors

| **Value** | **LCSC Part Number** |
| --- | --- |
| 0R | C21189 |
| 10R | C22859 |
| 20R | C22950 |
| 33R | C23140 |
| 51R | C23197 |
| 100R | C22775 |
| 120R | C22787 |
| 150R | C22808 |
| 200R | C8218 |
| 220R | C22962 |
| 270R | C22966 |
| 300R | C23025 |
| 330R | C23138 |
| 390R | C23151 |
| 470R | C23179 |
| 510R | C23193 |
| 560R | C23204 |
| 680R | C23228 |
| 820R | C23253 |
| 1k | C21190 |
| 1.2k | C22765 |
| 1.5k | C22843 |
| 1.8k | C4177 |
| 2k | C22975 |
| 2.2k | C4190 |
| 2.4k | C22940 |
| 2.7k | C13167 |
| 3.3k | C22978 |
| 3.6k | C22980 |
| 3.9k | C23018 |
| 4.7k | C23162 |
| 5.1k | C23186 |
| 5.6k | C23189 |
| 6.2k | C4260 |
| 6.8k | C23212 |
| 7.5k | C23234 |
| 8.2k | C25981 |
| 9.1k | C23260 |
| 10k | C25804 |
| 12k | C22790 |
| 13k | C22797 |
| 15k | C22809 |
| 18k | C25810 |
| 20k | C4184 |
| 22k | C31850 |
| 24k | C23352 |
| 27k | C22967 |
| 30k | C22984 |
| 33k | C4216 |
| 39k | C23153 |
| 47k | C25819 |
| 51k | C23196 |
| 56k | C23206 |
| 68k | C23231 |
| 75k | C23242 |
| 82k | C23254 |
| 100k | C25803 |
| 120k | C25808 |
| 150k | C22807 |
| 200k | C25811 |
| 220k | C22961 |
| 300k | C23024 |
| 330k | C23137 |
| 470k | C23178 |
| 510k | C23192 |

## Formatting your BOM

The following is a good BOM:

![alt text](dfmguide/bom.png)

The most important thing in your BOM is the LCSC part number:

![alt text](dfmguide/8.png)

When you upload your BOM to JLCPCB it looks for the LCSC part number and matches the component automatically.

You do not need silk screen chip designators for JLCPCB assembly. You do however need to put dots on pin one of ICs, and note anything that is polarized including LEDs. Try the JLCPCB assembly [demo](https://cart.jlcpcb.com/quote?fromDemo=yes).