# GSE

Sonic Avionics will be developing ground support equipment. Next year, we'll develop avionics that can actuate valves, but this year it will all be done by the ground station.

## Requirements

### Pad 

#### Telemetry 

- **Pressure Transducers**: 4x [PTD25-10-1000H](https://www.automationdirect.com/adc/shopping/catalog/process_control_-a-_measurement/pressure_sensors/pressure_transmitters/ptd25-10-1000h)
- **Thermocouples** 4x TBD
- **Load Cell** 2x TBD, 0-10V

#### Control

- 10x 24v valves
- 4x PWM Output
- LED status

#### Pelican Case

##### PLC

- **CPU:** Click PlUS C2-01CPU
- **CPU Option Slot Module:** 

- [Thermocouple module](https://www.automationdirect.com/adc/shopping/catalog/programmable_controllers/click_plus_plcs_(stackable_micro_modular)/stackable_i-z-o_modules/c0-04thm)

### Mission Control

#### Pelican Case

- **CPU:** Click PlUS C2-01CPU
- **CPU Option Slot Module:** 

- 14x switches








- Camera view
- OBS live streaming



### GSE
- **Pressure Transducers**: Up to 4x [LPPT25-20-1000H](https://www.automationdirect.com/adc/shopping/catalog/process_control_-a-_measurement/pressure_sensors/pressure_transmitters/lppt25-20-1000h) (1% accuracy, current output) with expandability to 8 transducers

### Mojave Sphinx



### Inputs/Outputs

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