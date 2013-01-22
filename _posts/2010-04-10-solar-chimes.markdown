---
layout: post
title: "Solar Chimes"
date: 2010-04-10T18:36:02+00:00
categories:
tags:
- school
- itp
---
For our BEAM Bot assignment, Andrew Styer and I worked on creating a solar chime. Based on the [Miller Solar Engine][miller], the concept was to use the sporadic voltage bursts of the engine to drive a small pager motor, raking against taught wires with an attached pick as it spins.

<a href="http://www.flickr.com/photos/69613750@N00/4508548215" title="View 'solar-chimes' on Flickr.com"><img border="0" width="240" alt="solar-chimes" src="http://farm5.static.flickr.com/4041/4508548215_533b121866_m.jpg" height="228"/></a> <a href="http://www.flickr.com/photos/69613750@N00/4508441546" title="View 'IMG_3713' on Flickr.com"><img border="0" width="180" alt="IMG_3713" src="http://farm3.static.flickr.com/2139/4508441546_8d7d15c579_m.jpg" height="240"/></a> <a href="http://www.flickr.com/photos/69613750@N00/4508441172" title="View 'IMG_3712' on Flickr.com"><img border="0" width="180" alt="IMG_3712" src="http://farm5.static.flickr.com/4043/4508441172_17e585a468_m.jpg" height="240"/></a> <a href="http://www.flickr.com/photos/69613750@N00/4507800819" title="View 'IMG_3710' on Flickr.com"><img border="0" width="180" alt="IMG_3710" src="http://farm3.static.flickr.com/2172/4507800819_48a3363e2d_m.jpg" height="240"/></a>

Our Miller Engine used the following components:

* 4 x 0.25 W solar panels (tested @ 80 mA and 3.2 V)
* 10 μF timing capacitor
* 1000 μF storage capacitor
* TC54 voltage regulator triggered @ 4.2 V

We used these components sized as such because we were driving a motor that would face some resistance over its course of motion, and thus would require a higher threshold and available electricity for when the engine triggered. Had we left the timing capacitor at the recommended 0.47 or 1 μF rather than the 10 μF that we used, the motor would not engage for a period long enough to strike the "chimes". Similarly the 1000 μF storage capacitor was used in order to provide a more powerful burst from the motor.

An example of the motor working with this circuit follows:

<object type="application/x-shockwave-flash" width="400" height="300" data="http://www.flickr.com/apps/video/stewart.swf?v=71377" classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000"> <param name="flashvars" value="intl_lang=en-us&photo_secret=a1c3a175fc&photo_id=4507903225"></param> <param name="movie" value="http://www.flickr.com/apps/video/stewart.swf?v=71377"></param> <param name="bgcolor" value="#000000"></param> <param name="allowFullScreen" value="true"></param><embed type="application/x-shockwave-flash" src="http://www.flickr.com/apps/video/stewart.swf?v=71377" bgcolor="#000000" allowfullscreen="true" flashvars="intl_lang=en-us&photo_secret=a1c3a175fc&photo_id=4507903225" height="300" width="400"></embed></object>

We ran into two issues that prevented this project from materializing as we had imagined:

1. We had anticipated that the wires would be more taught as a result of the suspended weight. A further iteration would use fishing line or guitar strings rather than the picture wire we used in order to be strung with a higher tension and hopefully resonance.

2. With such a small electrical pulse, the motor wasn't driven strong enough to overcome any sort of resistance, be it the additional weight from the attached pick, or when it struck the wires. What resulted was a little motor that patheticly twitched with each electric pulse but did nothing more.

This piece was a scaled down proof-of-concept for what we imagined to be a larger sculptural instrument, plucking tuned strings for a more harmonious experience.

[miller]: http://www.solarbotics.net/library/circuits/se_t1_mse.html
