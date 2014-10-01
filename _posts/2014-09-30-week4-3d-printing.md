---
layout:     post
title:      The Rattle
date:       2014-09-23 23:59:00
summary:    Week 4. 3d Printing. Manufacture something that can't be done with substraction methods.  
categories: 
---

This week was about 3d - Printing in various methods, machinery and scanning tools. Our assigment for the week was to create a 3d object that can't be done with substraction manufacturing.  

I've deciced to print a percussion rattle made from a hollow sphere. The sphere contains multiple small balls that create a sound when shaking. 

##*WARNING - IN PROGESS*

![Final]({{ "/assets/week4/assembly.jpg" | prepend: site.baseurl }})

###Design
1st, a small ball part (*5mm* diameter)

![Small Ball]({{ "/assets/week4/small_ball.jpg" | prepend: site.baseurl }})

Next, the hollow sphere part which will contain the balls. The sphere must be drainable to be able to get rid of exccess support material. I originally planned to have a unified pattern of holes all over the face of the sphere. while playing with circular patterns I accidently created a "baseball ball" like shape which I liked so I went for it. The sphere was created with a diameter of *10cm* and the holes with *4mm* diameter so the balls won't fall through.

![Big Sphere]({{ "/assets/week4/big_sphere.jpg" | prepend: site.baseurl }})

Finally, the assembly was pretty straight forward. First I imported the small ball and multipled it with a linear pattern in 3 axis. Next I imported the big sphere and position it to cover the balls.

![Assembly]({{ "/assets/week4/assembly.jpg" | prepend: site.baseurl }})

###Print
All 3d printers require a binary .stl file. Solidworks does not allow exporting assemblies to .stl files so I needed to convert the assembly to a part (*note: I could probably just build it as a part to begin with, there's no need for an assembly here*).  

Next problem, the exported stl file weighs 250mb which is too much for the printer's computer. Re-exporting with coarse resolution reduces size to 80mb. 

Last thing, the model is too big. I scale down by 1/2. Good enough. Let's print on the dimension printer! *18 HOURS?!?!?!*

![Assembly]({{ "/assets/week4/print_start.jpg" | prepend: site.baseurl }})

OH SHIT. the balls are so small that some of them were blown away by the wind created by the fan inside the printer. Let's wait and see what happens? 

![Assembly]({{ "/assets/week4/print_oops.jpg" | prepend: site.baseurl }})

Cleanup

![Assembly]({{ "/assets/week4/print_cleanup.jpg" | prepend: site.baseurl }})

OH YEAH!

![Assembly]({{ "/assets/week4/print_final.jpg" | prepend: site.baseurl }})

###Scan
I exprimented with 3d scanning using the SENSE scan. Conclusions: 

1. Bigger Objects are A LOT easier to scan. (more than 20cm)
2. Shooting from a distance helps keep tracking happy.
3. The SENSE software can mildly improve the imported model but dedicated software like GeoCAD do a far better job in filling holes and smoothing textures.

![Me scanning]({{ "/assets/week4/scan_life.jpg" | prepend: site.baseurl }})

![Something Scanned]({{ "/assets/week4/scan_model.jpg" | prepend: site.baseurl }})


