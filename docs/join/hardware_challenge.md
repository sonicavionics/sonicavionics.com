# Hardware Challenge

To join the hardware team, you must complete the following.

## Design a Module

Design a status module for the 4-inch avionics system in KiCad using the [challenge template](https://github.com/sonicavionics/4in-challengetemplate). Feel free to look at/copy various things from the [sensors module](https://github.com/sonicavionics/4in-sensors/tree/main).
Chips in the template are locked in the PCB editor you can move them around as long a the USB and [CAN](https://www.youtube.com/watch?v=YBrU_eZM110) differential pairing/impdedance matching is adhered to.

The module should include a mountable SD card reader to log all CAN messages.
Additionally, it should have a method to indicate battery level and e-match continuity, both of which are received from the [CAN](https://www.youtube.com/watch?v=YBrU_eZM110).
Feel free to add more features or remove some requirements if you see fit.

The files should be publicly available on your GitHub. Use a protected main branch, as well as all the techniques you learnt in the [Learn Git Branching](https://learngitbranching.js.org/) tutorial. Commit messages will be read through, so it is important to use [proper commit messages](https://github.com/zeulewan/git-commit-message).

Implement the [DFM Guide](../learn/dfmguide.md).

## Document

Make a fork of this website, contribute to a section that needs modification, make a pull request. Preferably to contribute to the DFM guide or anything in the learn tab.
