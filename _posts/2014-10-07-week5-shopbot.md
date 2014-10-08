---
layout:     post
title:      The Coffee Table
date:       2014-10-07 23:59:00
summary:    Week 5. Computer-Controlled Machining. Make something big using the shopbot.
categories: 
---

This week was about computer-controlled machining with an emphasis on the amazing shopbot. Our assignment was to build something big. 

Out of nessecity I've decided to build a long and narrow coffee table to fit into my living room. 

![Final]({{ "/assets/week5/final.jpg" | prepend: site.baseurl }})

I designed the model in solidworks and parameterized all the dimensions using the "linked values" feature. The press fit socket dimensions were determined according to initial measurements of the OSB sheet thickness. It was clear from the beginning this will be an issue because the material varies in thickness across the surface. The maximum thickness measured was used. 

![Beam]({{ "/assets/week5/beam.jpg" | prepend: site.baseurl }})

![Frame]({{ "/assets/week5/frame.jpg" | prepend: site.baseurl }})

![Assembly]({{ "/assets/week5/assembly.jpg" | prepend: site.baseurl }})

I started out with a tool-path and decided to use the 1/4" end-mill since it is fast and gives sufficient accuracy for my needs. When importing my vector dxf files I deleted all duplicated vectors and joined adjacent vectors. I also created t-bone fillets in my sockets to satisfy internal 90deg angles. All other settings were as recommended.

My first milling attempt was a test run with just two beams.

![Test]({{ "/assets/week5/test.jpg" | prepend: site.baseurl }})


These looked sufficiently good and had a pretty good fit. not too tight and not too loose. Next I attempted to mill the entire model. 

![Failure1]({{ "/assets/week5/failure1_1.jpg" | prepend: site.baseurl }})

![Failure1]({{ "/assets/week5/failure1_2.jpg" | prepend: site.baseurl }})

Failure #1. The end-mill didn't get all the way through and instead of re-milling I tried to extract the pieces from the OSB sheet. Terrible mistake. 

I decided to give it another go, this time adding thickness to the cut depth.

![Failure2]({{ "/assets/week5/failure2.jpg" | prepend: site.baseurl }})

Failure #2. WTF was I thinking sending the entire model to mill without another test?!?! This time the cut depth was excellent but for some reason my sockets were way bigger than I sketched. Initially I thought the end-mill I was using was bigger than 1/4 inch. Measuring the end-mill suggested that wasn't the case. Examining the tool-path again I found out that I was using an "on the line" tool path instead of "outside the line" which distorted the sketch. 

OK. One last try!

![Success]({{ "/assets/week5/success.jpg" | prepend: site.baseurl }})

![Success]({{ "/assets/week5/final.jpg" | prepend: site.baseurl }})

Success! the sockets were definitely too spacious so it was a bit wobbly but generally a good fit. 

Next I played a bit with the different sanding techniques to see what can be done with this crappy OSB. 

![Sanding]({{ "/assets/week5/sanding.jpg" | prepend: site.baseurl }})

Not too bad!


