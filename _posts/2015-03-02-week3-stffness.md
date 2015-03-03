---
layout:     post
title:      Measuring Stiffness
date:       2015-02-23 23:59:00
summary:    Week 3. Measuring the stiffness of several brittle materials. 
image: 	    /assets/week1/bed_full.jpg
categories: 
---

This week's assignment was to measure the stiffness and strength of a structure, and relate it to the material properties. Using the instrom I measured 3 brittle materials:  

1. Plywood, 1/8"
2. Acrylic, 1/8"
3. Acrylic, 0.2" 

I used the following design for tension:
![design]({{ "/assets/week3/design.png" | prepend: site.baseurl }})

The reason for thick ends and a thin body is to have the material crack closer to the middle and not in one of the bases. 

![all]({{ "/assets/week3/all.jpg" | prepend: site.baseurl }})

One by one I tested them on the instron with a load limit of up to 4kN. All the tests ended up in the materials breaking. 

{% youtube CV_1bJpfAb4 944 1032 %} 

Even before examining the results it is evident that these materials are extremely brittle. Their fracture points fit like puzzle pieces meaning there was no deformation before the material gave up. 

### Results

I collected the raw data from all three experiments into a single [excel](http://media.giphy.com/media/gCL5fOMAVijWE/giphy.gif) spreadsheet and created the following chart: 

![raw]({{ "/assets/week3/raw.png" | prepend: site.baseurl }})

These curves confirm the brittleness of the material. There is only a near-linear elastic phase to the curve and their ultimate strength matches their breaking strength.

I then focused on the linear part of the curve, without the noise of the beginning or the breakpoint.    

![cut]({{ "/assets/week3/cut.png" | prepend: site.baseurl }})

The coefficient should be the elastic modulus but I used milimeters instead of meters so I needed to adjust the results. and voila:

1. Plywood, 1/8" =>  
2. Acrylic, 1/8" =>
3. Acrylic, 0.2" =>


