# GSE

Sonic Avionics will be developing ground support equipment. Next year, we'll develop avionics that can actuate valves, but this year it will all be done by the ground station

## Requirements

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