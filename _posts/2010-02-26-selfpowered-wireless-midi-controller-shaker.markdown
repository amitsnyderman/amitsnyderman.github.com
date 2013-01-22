---
layout: post
title: "Self-Powered Wireless MIDI Controller Shaker"
date: 2010-02-26T14:27:06+00:00
categories:
tags:
- school
- itp
---
Every few months I get the itch to record my own music. As a guitar player, it's very easy to do quick recordings at home with little gear using tools like Garageband or Logic. My options though for recording drums are very limited, so these sessions always digress into extended noodle sessions as I end up playing over a generic and mechanical sounding looped drum track. The thing is that I'm an excellent finger drummer and am pretty good with various percussion instruments; if only I could manage to digitally record those sounds with an organic feel, I might be able to break my recording block.

For my _[Sustainable Energy][class]_ class we had to build a kinetically powered device and all I wanted to build was an instrument of some sort. What's resulted is an analog shaker that also doubles as a wireless MIDI device powered by the very act of shaking.

<a href="http://www.flickr.com/photos/69613750@N00/4390336852" title="View 'Self-powered wireless MIDI controller shaker' on Flickr.com"><img border="0" width="400" alt="Self-powered wireless MIDI controller shaker" src="http://farm5.static.flickr.com/4003/4390336852_177782e555.jpg" height="309"/></a>

Using a collection of 5 piezo elements inserted fin-like into a cardboard mailing tube, I hoped to generate enough electricity to power an XBee radio and accelerometer. [Piezos][piezoelectricity] generate an electric potential in response to applied mechanical stress, so the intention was to slam the shaker particles (initially coffee beans, later 1/4" hex nuts) against the piezos, rectify the generated AC current to DC, and use a capacitor to capture and supply energy to rest of the components.

So did it work?

Turns out it can be answered before doing much work by working through some simple numbers examining how much power the components consume and determining whether the limits of our generation accommodate the needs.

### Power Consumption

The following are the components used and their electrical profile and needs.

<table>
<thead>
	<tr>
	<th>Component</th>
	<th>XBee Series 1</th>
	<th>ADXL330 (accelerometer)</th>
	</tr>
</thead>
<tbody>
	<tr>
	<th>Voltage</th>
	<td>2.8V (up to 3.4V)</td>
	<td>1.8V (up to 3.6V)</td>
	</tr>
	<tr>
	<th>Current</th>
	<td>45 mA</td>
	<td>180 μA</td>
	</tr>
	<tr>
	<th>Power</th>
	<td>0.126 W</td>
	<td>8.1 × 10-5 W</td>
	</tr>
</tbody>
</table>

Thus at minimum **126 mW** needs to be generated, and that's probably a bit low since we're using the minimum voltage that these components are rated for. To run them at their native voltage requirements would require **148.5 mW**.

### Power Generation

So can we actually provide that much power?

<table>
<thead>
	<tr>
	<th>Converter</th>
	<th>Piezo (+ finger)</th>
	<th>Shaker (5 piezos + 100 1/4” Zinc Hex Nuts)</th>
	</tr>
</thead>
<tbody>
	<tr>
	<th>Capacitance</th>
	<td>690 μF</td>
	<td>220 μF</td>
	</tr>
	<tr>
	<th>Voltage</th>
	<td>2V</td>
	<td>2V</td>
	</tr>
	<tr>
	<th>Energy</th>
	<td>.00138 J</td>
	<td>0.00044 J</td>
	</tr>
	<tr>
	<th>Charge Time</th>
	<td>19.5 s</td>
	<td>15 s</td>
	</tr>
	<tr>
	<th>Power</th>
	<td>7.08 x 10-5 W</td>
	<td>2.93 x 10-5 W</td>
	</tr>
</tbody>
</table>

A bit disappointing was the fact that using more piezos did not linearly increase the power; in hindsight this makes perfect sense since in the shaker context, the mechanical stress on the piezos is not reliable or consistent as the device is being shaken.

<a href="http://www.flickr.com/photos/69613750@N00/4390575246" title="View 'Shaker power generation schematic' on Flickr.com"><img border="0" width="360" alt="Shaker power generation schematic" src="http://farm5.static.flickr.com/4034/4390575246_2c3f26437e.jpg" height="119"/></a>

During operation, a charge of **1.4 V** could be sustained with all components hooked up. There _was_ a moment, a very brief one, in which the device powered on but unfortunately, no, not enough energy could be generated for the device to actually turn on and work consistently.

Next time before building anything I'll be working backwards to figure things out. Consider the following:

	E = ½ CV²

Plugging in what we do know:

	0.126 J = ½ C (2.8V)²

We can determine that at minimum our target is to generate enough electricity to charge a **0.032 F** capacitor for 1 second. From the above real-world numbers, it's clear that we are orders of magnitude away from this possibility.

### Functionality

Besides the ability to power itself, the device was in fact finished and a perfectly capable MIDI device. An Arduino was hooked up to the receiving XBee radio to interpret the accelerometer data and send the MIDI data over the serial connection, using the following code:

	// XBee Reference: http://code.google.com/p/xbee-arduino
	// MIDI Reference: http://www.arduino.cc/playground/Main/MIDILibrary

	#include <XBee.h>
	#include <MIDI.h>

	#define IN_X 0
	#define IN_Y 1
	#define IN_Z 2

	#define THRESHOLD 50
	#define DELAY 50

	struct accelerometer {
		int x;
		int y;
		int z;
	};

	long timer = 0;
	accelerometer a_current = {0, 0, 0};
	accelerometer a_last = {0, 0, 0};

	XBee xbee = XBee();
	Rx16IoSampleResponse ioSample = Rx16IoSampleResponse();

	void setup() {
		xbee.begin(31250);
		MIDI.begin(1);
	}

	void readAccelerometer() {
		a_last.x = a_current.x;
		a_last.y = a_current.y;
		a_last.z = a_current.z;
	
		if (ioSample.isAnalogEnabled(IN_X))
			a_current.x = ioSample.getAnalog(IN_X, 0);
		if (ioSample.isAnalogEnabled(IN_Y))
			a_current.y = ioSample.getAnalog(IN_Y, 0);
		if (ioSample.isAnalogEnabled(IN_Z))
			a_current.z = ioSample.getAnalog(IN_Z, 0);
	}

	int shake() {
		readAccelerometer();
	
		return (a_current.x - a_last.x) + (a_current.y - a_last.y) + (a_current.z - a_last.z);
	}

	void loop() {
		xbee.readPacket();

		if (!xbee.getResponse().isAvailable())
			return;
		if (xbee.getResponse().getApiId() != RX_16_IO_RESPONSE)
			return;
	
		xbee.getResponse().getRx16IoSampleResponse(ioSample);

		if (!ioSample.containsAnalog())
			return;

		int s = shake();
		if (millis() - timer > DELAY && s > THRESHOLD) {
			MIDI.sendNoteOn(42, 127, 1);
			timer = millis();
		}
	}

The MIDI note on message is currently sending a static value for velocity; a quick modification would be adjust the velocity as determined by the strength of the shake, normalizing it on the scale between 0-127.

[class]: http://itp.nyu.edu/sustainability/energy/
[piezoelectricity]: http://en.wikipedia.org/wiki/Piezoelectricity
