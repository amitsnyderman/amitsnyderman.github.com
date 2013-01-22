---
layout: post
title: "Arduino Light Shows"
date: 2007-09-20T01:39:39+00:00
categories:
tags:
- school
- itp
---
On/off state photos for this week's lab. You click the button, the yellow LED glows. Click it again, now we see the red one. Click. Click.

<div class="photos">
<a href="http://flickr.com/photos/amitsnyderman/1411152886/"><img src="http://farm2.static.flickr.com/1258/1411152886_c2e3712ba6_m.jpg" /></a>
<a href="http://flickr.com/photos/amitsnyderman/1410263983/"><img src="http://farm2.static.flickr.com/1159/1410263983_601cfd991d_m.jpg" /></a>
</div>

Presumably like everyone else new to this, my natural inclination was to then dump the little baggy of LEDs onto the breadboard and light the whole lot of them. In sequence. Christmas in September.

The first version used the toggle button and digital state to alternate the direction of the LED sequence. The second version used a potentiometer on an analog input to vary the rate at which the LEDs scrolled:

<div class="photos">
<object width="240" height="207"><param name="movie" value="http://www.youtube.com/v/-8kFdIvLSaw"></param><param name="wmode" value="transparent"></param><embed src="http://www.youtube.com/v/-8kFdIvLSaw" type="application/x-shockwave-flash" wmode="transparent" width="240" height="207"></embed></object>

<object width="240" height="207"><param name="movie" value="http://www.youtube.com/v/ojifCcHbkhk"></param><param name="wmode" value="transparent"></param><embed src="http://www.youtube.com/v/ojifCcHbkhk" type="application/x-shockwave-flash" wmode="transparent" width="240" height="207"></embed></object>
</div>

Also managed to get the potentiometer value via the serial/USB interface into Processing and draw some stuff but don't have any of that show. For whatever reason, it took a while to get any values that were meaningful and related to the values that were being sent over the serial port. The combination of what I think was an unnecessary [pull-down resistor][1] and cleaning up the code to make sense of the incoming byte stream lasted a little later into the night than I was hoping...

[1]: http://en.wikipedia.org/wiki/Pull-up_resistor
