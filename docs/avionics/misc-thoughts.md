## Misc Thoughts

- Using a single MOSFET for switching between USB and battery voltage is just too janky.
- Shoot through voltage.
- The way to do it simply would be by taking advantage of the "Zero Gate Voltage Drain Current", but there's a load connected to the source so the voltage probably wont rise
- In-rush current, you need a resistor to the gate
- Going to need more robust circuitry than this
- Could flip the P channel enhancement mosfet to have the current go from source to drain in order to get the negative voltage, but too janky
- Going with a BQ2407x that handles power switching and battery charging. It's basically designed for this exact thing.
- Not using RT9080. Need a buck boost. I should be able to use the entire range of battery

- Typical via sizes
- Large: 0.7 mm pad, 0.3 mm drill
- Medium: 0.6 mm pad, 0.25 mm drill
- Small: 0.5 mm pad, 0.2 mm
- Make it hole: 0.3 and diameter: 0.4 for no extra charge

- Vias under pads cost more and cause issues with assembly sometimes. Not worth it.

- OshPark doesn't do assembly

- I really am gonna have to choose between using github or the ECAD/MCAD plug in. I think the answer is obvious. Altium 365 is not the way. KiCAD is worth considering switching to. More accessible, free, apparently less professional though. What would a start up use though? Probably KiCAD. I don't know how well it handles multi board projects. I don't even know how Altium handles it though. Should I switch to KiCAD for Dongboard? Queens, and waterloo uses it. It probably has much better git integration although I'd have to look into that. ALtium 365 actually does provide some benefits. You can view stuff in the browser. There's also flux.ai which may or may not be scamming. Solidworks is such a drag but I don't think OnShape is ready. I've had it slow down on me too many times... meh not that many times though. No good FOSS CAD software. 

- Always go on texas instruments' website to check if there is a newer version of the chip

- Better to use "point of load" regulation

- Will have a multiplexer and on each compute board.
- 3.3v rail, 5v rail, and unregulated 12v rail
- dingboard just has one regulated 3.3v rail
- dongboard will have barrel jack on the power board for fast charging with a charging IC, it will also have a rp2040 and a voltage monitoring chip. The UCB-C port won't even have its power terminals connected. It will be just for programming. the barrel or QD will be for charging/power supply while the rocket is on the pad. The CAN bus will also have a QD on it.

- When I start the MCU I'm gonna say eff Altium 365 and just download everything and re initialize my repo. I'm actually going to make a release for the 0.0.1 power board it will have schematics pictures and the BOM. It's important to keep things open source. It's so easy for things to turn into slop otherwise.

- Outboard physical connections
  - remove before flight banana pins
  - power/charging
  - for solid: ignition

All boards are going to have to be 4 layer