---
title: dingboard is Nextboard
date: 2024-12-01
comments: true
authors:
  - zeul
categories:
  - dingboard
---

Well I named the dingboard the dingboard because I thought I was gonna make a bigger board later on and I was gonna name it the dongboard or some shit. There's no value in making a single board flight computer right now, so the MCU will be CAN enabled from the get go. It doesn't add much complexity. The MCU board will be ran at 3 volts so I will be able to use the V1 power board for it. Later on I'll need to use an antenna which will be ran at [5v with 3.3v logic.](http://files.rfdesign.com.au/Files/documents/RFD900x%20DataSheet%20V1.1.pdf) So while power v1 is shipping, I'll work on the MCU with CAN, while that is being shipped I'll upgrade the power to 3s with 3.3v 5v and unregulated 12v. Then I'll work on the antenna module while that is shipping then I'll work on the GPS while that is shipping then blah blah. The specifics will change but this is the idea.