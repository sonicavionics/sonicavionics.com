# GPS 

Currently thinking about going with the [MAX-M10S-00B](https://www.digikey.com/en/products/detail/u-blox/MAX-M10S-00B/15712906). Going to use an external antenna. Sparkfun wrote a library for it. slightly more expensive than L86-M33 and cheaper than blox m10q. Doesn't have internal antenna though

NEO-F10N is too expensive, but it does L1/L5 and connects to all the constellations. Anyways this is a easily solvable problem for a later time.

## Signal Filtering and Impedance Considerations 

The purpose of the ferrite bead in the circuit is to act as a low-pass filter, effectively suppressing high-frequency noise that could interfere with the GPS signal. In this case, it is used instead of a traditional inductor to provide a compact and efficient filtering solution. Additionally, the circuit is designed to create an impedance mismatch, which can help control signal reflection or improve signal integrity in certain scenarios, depending on the design requirements.

## Component Selection

In the M10S design, a ferrite bead was chosen over an inductor as a cost-effective solution, with the option to replace it in future iterations if needed. Additionally, a TVS diode was incorporated to ensure ESD protection, while a capacitor and resistor were added to meet the guidelines specified in section 4.3.4 of the integration manual.

[MAX-M10S Integration manual](https://content.u-blox.com/sites/default/files/MAX-M10S_IntegrationManual_UBX-20053088.pdf)
