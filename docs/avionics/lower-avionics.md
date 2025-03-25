# Lower Avionics System

## MCU Requirements

### Inputs/Outputs
- **Pressure Transducers**: Up to 4x [LPPT25-20-1000H](https://www.automationdirect.com/adc/shopping/catalog/process_control_-a-_measurement/pressure_sensors/pressure_transmitters/lppt25-20-1000h) (1% accuracy, current output)
    - Ox
    - Fuel
    - Chamber
    - Extra in case we want to put one somewhere else
- **Servos**: Up to 5x servo outputs
    - Ox
    - Fuel
    - Purge
    - Ox globe valve
    - Regulator (potential)
- **Regulators**: Electronic control for $CO_2$
- **Load Cells**: 2x
    - Tank weight
    - Thrust

### Communication
- CAN connection to upper avionics
- RFD900 port for testing purposes
- No wired ground testing connection needed


## Batteries

A 2s 3p 18650 pack might be used.

## MCU

MCU selection isn't set yet.

RP2040

[stm32 f405rgt6](https://www.st.com/en/microcontrollers-microprocessors/stm32f405rg.html)

[apm f405rgt6](https://jlcpcb.com/partdetail/Geehy-APM32F405RGT6/C5290473) knock off?
