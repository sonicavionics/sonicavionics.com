# Hardware Challenge

Complete the following.

## PCB

Design a status module for the avionics system. It should have:

### SD Card reader
The board should have an SD card hooked up to the RP2040 that logs all data coming from the CAN bus.

### Indicate
There will be **other boards** that will collect the following data:

1. Battery level
2. E-match continuity
3. Acceleration, gyroscope and magnetometer readings

The status module will log the data in the SD card and display it.

The status module will listen to everything on the [CAN](https://www.youtube.com/watch?v=YBrU_eZM110) bus and display all relevant information. It may include buttons to cycle through different information. It can use either an LED array or LCD screen to display information.


## Documentation
1. Document Everything you do and put it on the website
2. Contribute to the website in another way.

## Deadline
**2025 March 23rd**

## Template repository

When creating a new repo, use the [challenge template](https://github.com/sonicavionics/4in-challengetemplate) as your repo's template.

There are some chips already selected for you:

1. MCU: RP2040
2. Flash chip for RP2040
3. RP2040 Clock
4. CAN Controller/Transceiver
5. CAN Controller/Transceiver Clock
6. USB-C Port
7. PCIe gold fingers

## Further Information

- Implement the [DFM Guide](../avionics/resources/dfmguide.md).
- use [proper commit messages](https://github.com/zeulewan/git-commit-message).

- When creating a new repo, select the [challenge template](https://github.com/sonicavionics/4in-challengetemplate) for the template.
- Feel free to look at/copy various things from the [sensors module](https://github.com/sonicavionics/4in-sensors/tree/main).
- USB and [CAN](https://www.youtube.com/watch?v=YBrU_eZM110) differential pairing/impedance matching must be adhered to.
- Use a protected main branch, as well as all the techniques you learnt in the [Learn Git Branching](https://learngitbranching.js.org/) tutorial.
