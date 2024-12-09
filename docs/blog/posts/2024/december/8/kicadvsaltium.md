---
title: KiCAD vs Altium and Solidworks vs OnShape
date: 2024-12-08
comments: true
authors:
  - zeul
categories:
  - dingboard
---

Gotta pick which software to use. Most teams use KiCAD and Solidworks.


## KiCad vs Altium

5 minutes into KiCAD. Here's the pros and cons of KiCAD. One downside already is no dark mode support on windows

### Pros

- There seems to be a much better built in library. Well it has PCIe footprints.
- I don't have to sign in and click roam on the licenses all the time. 
- There's a plentiful plugs ins repo. 
- It's way way faster
- Dark mode for schematic editor.
- FOSS
- Altium's manufacturer part search is really not that fast, and for whatever reason the BOM is the slowest thing in the world. There's few companies that would use the build in supply chain shit, it just slow things down and I didn't see a way to disable it without disabling the manufacturer part search.
- Many different repos for all the manufactures design rules. 
- Exporting is way faster with the JLCPCB plug in
- The measurement tool is slightly better

### Cons

- The UI is somewhat less professional looking. (who cares)
- KiCAD doesn't have dark mode on windows. Altium's UI is dark by default, but I don't think you can add themes for the actual schematic editor. So that's 
- Altium actually has better git integration surprisingly.
- You can only have one project open per instance. ```open -n /Applications/KiCad/kicad.app```
- I've experienced more crashes than Altium. Running tally of crashes: 7
- Sometimes the footprints don't show up in the previewer windows when selecting a chip

## Solidworks vs OnShape

I'll do pros and cons of Solidworks

### Pros

- Faster 
- Realview graphics
- Can handle assembly as large as your computer will allow. OnShape is run in AWS. I didn't think this would be an issue, because they dynamically allocate compute based on your needs. Even still, it is really slow loading things, and I did notice that after a while it gets faster the more you use it, but still its much slower than Solidworks.



### Cons

- Very old looking interface 
- Have to update variable file reference manually every time you add a variable. 
- No version control, although OnShape has it but doesn't use git.
- Mating in OnShape is faster, the same thing that takes one mate in OnShape takes 2 or 3 in Solidworks.
- Only runs on windows, OnShape is really great for how it runs in the browser. I would do almost anything to never have to use windows again, but onshape is just too slow.
- Very expensive for companies, onshape has a free tier for open source people.
- The workflow with Solidworks involves using sharepoint or something similar. The files will get too large for regular git so LFS will be needed.