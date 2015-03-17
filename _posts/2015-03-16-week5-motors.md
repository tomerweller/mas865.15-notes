---
layout:     post
title:      Motors
date:       2015-03-17 23:59:00
summary:    Week 5. Move your mechanism  
image: 	    /assets/week1/bed_full.jpg
categories: 
---

For this week I started to work on my robotic self reckoning plotter. I focused on the mechanism that puts the marker (Sharpie in this case) up and down using a Cam and Follower mechanism. 


####Sharpie Holder
I 3d printed a holder for the Sharpie which also serves as the follower. It's made out of two equal parts that constrain the sharpie with room for a spring so that the sharpie can apply preasure and have some vertical wiggle room. (TODO: add spring to the design)

![holder_design]({{ "/assets/week5/holder_mechanism.jpg" | prepend: site.baseurl }})
![holder]({{ "/assets/week5/holder.jpg" | prepend: site.baseurl }})

####Cam and Follower
The mechanism is based on an SG5010 Servo. All construction materials are from the CBA shop scrap. (TODO: add spring to design)

![mechanism_back]({{ "/assets/week5/mechanism_back.jpg" | prepend: site.baseurl }})
![mechanism_front]({{ "/assets/week5/mechanism_front.jpg" | prepend: site.baseurl }})
![back]({{ "/assets/week5/back.jpg" | prepend: site.baseurl }})
{% youtube CL125jj3s30 944 1032 %} 

####Issues
- Cam needs a lot of force to push the follower. I should tweak the cam design and add a wheel to the follower.
- Through hole mounts are not aligned. For the next iteration I will press-fit the parts together.   
- More clearances for the through hole. Had to some sanding this time. 
- Avoid 3d printing as much as possible. Iteration time is not managable. 


