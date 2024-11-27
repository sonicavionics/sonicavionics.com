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