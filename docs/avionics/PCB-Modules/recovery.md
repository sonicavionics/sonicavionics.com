# Recovery

[Recovery Module](https://github.com/sonicavionics/4in-recovery/)

---

The recovery module is responsible for checking continuity and controlling ejection charges for parachute deployment. It features a BMP388 barometric sensor that enables autonomous deployment decisions independent of the sensors module. This approach provides redundancy in critical scenarios, ensuring parachute deployment even if the sensors module fails.

---

<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-recovery/refs/heads/main/images/board.front.png" alt="3D Render">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-recovery/refs/heads/main/images/board.back.png" alt="3D Render">
</div>
<p class="image-caption">3D Render</p>

![alt text](https://raw.githubusercontent.com/sonicavionics/4in-recovery/refs/heads/main/images/sch.svg)
<p class="image-caption">Schematic</p>


<div class="image-row">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-recovery/refs/heads/main/images/pcbf.svg" alt="Front">
    <img src="https://raw.githubusercontent.com/sonicavionics/4in-recovery/refs/heads/main/images/pcbb.svg" alt="Back">
</div>
<p class="image-caption">Footprint</p>

This board will be in charge of checking continuity, and arming the ejection charges. it will report on tall this over the CAN network. It will also have it's own barometer for independency. We will be able to turn on or off automatic ejection. If the rocket target altitude is lower than expected, 

There will be remove before flight tags in the form of banana connectors with a tag on it which will disarm the charges.

![alt text](chute/mapmoxje.bmp)
[banana plug](https://www.digikey.ca/en/products/detail/mueller-electric-co/BU-PMDP-S-2/4073757)
[banana socket](https://www.digikey.ca/en/products/detail/pomona-electronics/2269-0/736335?s=N4IgjCBcoEwJxVAYygMwIYBsDOBTANCAPZQDaIAzACwBsVcA7CALqEAOALlCAMocBOASwB2AcxABfQmAAcFRCBSQMOAsTKUwDGTpbsukXgJHipIALQ0FSgQFc1JSORgsJZl05AAhAIIA5fx8AAgApHwBhAGk9EABWBTYoMHZEyBhYtyA) order an extra 5/16-32 nut with this
[cad from here](https://www.3dcontentcentral.com/secure/download-model.aspx?catalogid=171&id=587137)
step file from [this website](https://www.3dcontentcentral.com/download-model.aspx?catalogid=171&id=626290)


The above will disable a relay by shorting the enable pin.

