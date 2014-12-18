---
layout:     post
title:      The Led Array
date:       2014-11-11 23:59:00
summary:    Week 10. Electronic Input Devices
image:      /assets/week11/hello.array.serial.44.components.jpg
categories: 
---

This week was about output devices. Our assignment was to design, mill, stuff & program a board that uses an output device.

As preperation for my final project I've decided to build a led array board that's controlled via a web interface.
 
{% youtube kyywKGkK-H0 944 1032 %}


######WARNING: THIS BOARD HAD A DESIGN FLAW IN IT, DO NOT REPLICATE

###Board
![Schematic]({{ "/assets/week11/hello.array.serial.44.schematic.png" | prepend: site.baseurl }})
![Board]({{ "/assets/week11/hello.array.serial.44.board.png" | prepend: site.baseurl }})
![Components]({{ "/assets/week11/hello.array.serial.44.components.jpg" | prepend: site.baseurl }})
Note: in retrospective I did not need need a resistor for each LED. I could have used just 3 resistors on the output pins. 

###Programming
![Programming]({{ "/assets/week11/programming.jpg" | prepend: site.baseurl }})
I borrowed from Neil's [hello.ftdi.44.echo code](http://academy.cba.mit.edu/classes/embedded_programming/hello.ftdi.44.echo.c) code and [hello.aray.44 code](http://academy.cba.mit.edu/classes/output_devices/array/hello.array.44.c). The main() function:

{% highlight c %}
int main(void) {
   static char chr;

   // set clock divider to /1
   CLKPR = (1 << CLKPCE);
   CLKPR = (0 << CLKPS3) | (0 << CLKPS2) | (0 << CLKPS1) | (0 << CLKPS0);

   // initialize output pins
   set(serial_port, serial_pin_out);
   output(serial_direction, serial_pin_out);

   // main loop
   while (1) {
      get_char(&serial_pins, serial_pin_in, &chr);
      switch(chr){
         case 'a': flash(B,A, led_pressed_delay); break;
         case 'b': flash(A,B, led_pressed_delay); break;
         case 'c': flash(B,C, led_pressed_delay); break;
         case 'd': flash(C,B, led_pressed_delay); break;
         case 'e': flash(C,A, led_pressed_delay); break;
         case 'f': flash(A,C, led_pressed_delay); break;
      }
      put_char(&serial_port, serial_pin_out, chr);
   }
}
{% endhighlight %}
[full code - hello.array.serial.44.c]({{ "/assets/week11/hello.array.serial.44.c" | prepend: site.baseurl }})

I improved my last week's serial-to-socketio relay example so that I can also write to the serial port. The full code is at [https://github.com/tomerweller/serial-to-socketio](https://github.com/tomerweller/serial-to-socketio)

{% youtube kyywKGkK-H0 944 1032 %}

Generally, it works. However, It's visible that some LEDs that are not supposed to light up have some current flowing through them. Needs further debugging.
