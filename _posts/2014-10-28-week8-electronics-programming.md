---
layout:     post
title:      The Blinking Board
date:       2014-10-28 23:59:00
summary:    Week 8. Electronics Programming
categories: 
---

This week we dove into programming our AVRs. Our assignment was to program the board we milled todo something. 

![Enviornment]({{ "/assets/week8/set.jpeg" | prepend: site.baseurl }})

(*Disclaimer: I used [Jonathan's](http://fab.cba.mit.edu/classes/863.14/people/jonathan_bobrow/projects/176/) design due to issues with my own*)

####Recap - Preparing your OSX Enviornment to develop for AVRs
Before programming, you need both avrdude and avr-gcc installed. On my mac I prefer managing software via the [homebrew](http://brew.sh/) package manager.

###### install avrdude using homebrew
{% highlight bash %}
brew install avrdude 
{% endhighlight %}

###### install avr-gcc using homebrew and an external repository
{% highlight bash %}
brew tap larsimmisch/avr
brew install avr-libc
{% endhighlight %}

####Programming

I first deployed the "Echo Hello World" sample as illustrated [by Neil in class](http://academy.cba.mit.edu/classes/embedded_programming/hello.ftdi.44.program.png).

Instead of using the **term.py** script I used the native unix command **screen**:
{% highlight bash %}
screen /dev/tty.usbserial-FTH7PFC7 115200 
{% endhighlight %}

*Tip: if you're on OSX with only one serial over usb connection you don't need to look for the device id. Just start writing "/dev/tty.usbserial" on your bash shell and then hit TAB for auto-complete. this should be the only device matching.*

Next. To make the LED blink I deployed the following code using the same makefile as in the "Echo Hello World" project. (The led is wired to my PA7 pin)

{% highlight c %}
#define F_CPU 2000000UL

#include <avr/io.h>
#include <util/delay.h>

int main (void) {
    DDRA |= _BV(PA7);

    while(1) 
    {
        PORTA ^= _BV(PA7);
        _delay_ms(500);
    }
}
{% endhighlight %}

This didn't work - my led was placed backwards in the board. I found this out using the diode test feature of the multimeter. had to remove and re-solder the right way and voila!

![blink]({{ "/assets/week8/blink.gif" | prepend: site.baseurl }})

However, although working I still had a weird problem where pressing the button made the LED brighter. After research that led to no conclusion I found out that a wire from the switch was attached to one side of the led due to a milling issues which I missed. This caused, upon pressing the switch, for current to flow through the led without a resistor. 

![short]({{ "/assets/week8/short.png" | prepend: site.baseurl }})

Unfortunately, using the exact same setup I couldn’t deploy any more code to the AVR. After trying to replace the programmer and cables I’m sure that something is wrong with the board. Will fix for next weeks.  
