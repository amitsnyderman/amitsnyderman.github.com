---
layout: post
title: "Idea: LED Etch-A-Sketch"
date: 2007-09-24T00:08:55+00:00
categories:
tags:
- school
- itp
---
Think [Lite-Brite][lite] [Etch-A-Sketch][sketch] hybrid thing, controlled via knobs... Hmm, [need more pins][pins] doing something called a [shift out][shiftout]...

So some research has led me to the [MAX7219/MAX7221][MAX7219], [74HC595][], or [TB62708N][] chips and a [code library][ledcontrol] to make working with LED arrays easier:

> The MAX7219/MAX7221 are compact, serial input/output common-cathode display drivers that interface microprocessors (&micro;Ps) to 7-segment numeric LED displays of up to 8 digits, bar-graph displays, or 64 individual LEDs. Included on-chip are a BCD code-B decoder, multiplex scan circuitry, segment and digit drivers, and an 8x8 static RAM that stores each digit. Only one external resistor is required to set the segment current for all LEDs. The MAX7221 is compatible with SPI&trade;, QSPI&trade;, and MICROWIRE&trade;, and has slew-rate-limited segment drivers to reduce EMI.

> A convenient 4-wire serial interface connects to all common &micro;Ps. Individual digits may be addressed and updated without rewriting the entire display. The MAX7219/MAX7221 also allow the user to select code-B decoding or no-decode for each digit.

> The devices include a 150&micro;A low-power shutdown mode, analog and digital brightness control, a scan-limit register that allows the user to display from 1 to 8 digits, and a test mode that forces all LEDs on.

Not that I necessarily know what any of this means, but it sounds good. Off to Radio Shack where hopefully they have some of this stuff.

[lite]: http://en.wikipedia.org/wiki/Lite-Brite
[sketch]: http://en.wikipedia.org/wiki/Etch_A_Sketch
[pins]: http://www.arduino.cc/playground/Main/LEDMatrix
[MAX7219]: http://www.maxim-ic.com/quick_view2.cfm/qv_pk/1339
[74HC595]: http://www.nxp.com/pip/74HC_HCT595_4.html
[TB62708N]: http://www.marktechopto.com/PDFs/toshiba/ACF42D.pdf
[ledcontrol]: http://www.wayoda.org/arduino/ledcontrol/index.html
[shiftout]: http://www.arduino.cc/en/Tutorial/ShiftOut
