---
title: ECAD/MCAD Ideal Version Control Workflow
date: 2024-11-26
comments: true
authors:
  - zeul
categories:
  - dingboard
  - Complaints
---

Here's some ideas for how Solidworks and Altium or any MCAD and ECAD would ideally work together. 


Altium codesigner is for use with Altium 365 only. 
Solidworks doesn't have branching and merging. It's proprietary version control method is rubbish.

Ideally, you'd have a MCAD and a ECAD repo. Both of them use each other as submodules. Or you could just have the one repo with RBAC but I don't think github lets you do that because it would be annoying if you commit to a file you don't have perms for then try to push it it would say nope bruh you can't change that one file in all your files you changed. Actually that doesn't sound so bad 

MCAD pulls to the ECAD submodule. Changes are made to the PCB, a pull request is made, the electrical engineer accepts them. Then the rest of the MCAD team pulls from the ECAD repo and has access to the new changes. There should be some features like board shape, and max component height that the MCAD engineer has control of that a pull request is required to make. That would be what the submodule 

Maybe there would just be a third repo for things that both teams depend on. This would only be the board dimensions. Both the ECAD and MCAD softwares should be able to edit it, but there should be accept/deny system where an engineer from both teams need to approve the change. 
The ECAD team doesn't want to see the rest of the structure they only care about the PCB.

Sometimes you'd want the MCAD team designing an enclosure as a secondary to the PCB layout, sometimes there's board constraints sizes like in a rocket which makes the MCAD designers primary. 
Three sort of use cases: Primary MCAD, primary ECAD, and equal priority

There would need to be a system for breaking changes. There needs to be keep out regions, and expected layouts. 

I would like for right now, to be able to push a board layout, a rough layout, to the board dimensions/connectors repo. This contains the gold fingers, USB and JST connectors. This is an initial push so it doesn't require both team's approval. Next I want to go into solidworks, move around the gold fingers, change the board diameter, lets say shrink it. Then I push to the dimensions/connectors repo. A pop up on Altium appears, it says "a change has been proposed". Then it says would you like to branch to check approvability? I finish my changes to the ECAD before I then branch the ECAD repo. This special branch pulls changes proposals from the dimensions/connectors repo. Then I look around to see if I can rework the PCB a bit to allow the changes. I rework the pcb a bit then accept the changes. I merge back the ECAD branch to main. The new main has a different git hash has associated with the dimensions/connectors submodule. 

Anyways there's some spit balling about an ideal version control ECAD/MCAD workflow. I don't think this can be done with kicad or some open source cad software. The two softwares would need to agree on a system for the dimensions/connectors files. And it's probably best the two softwares are kept separate. 


So you can use workarounds to avoid using Altium 365, but you loose too much convenience for it to be worth it. You'd have to keep exporting to a STEP in altium then in solid works you'd have to export to a DXF then in Altium import that to be the board shape.