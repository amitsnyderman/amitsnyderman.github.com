---
layout: post
title: "Prosthesis."
date: 2008-05-10T22:14:46+00:00
categories:
tags:
- school
- itp
---
My final project for Networked Objects, after many a mental-block, resulted in the uninspiring name of "BioCron", described as:

> A bio-feedback event notiﬁcation framework, built on a network of wireless bio-sensors.

[Download presentation](http://blogs.nyu.edu/blogs/as860/iameat/uploads/presentation.pdf)

It sits on a few core assumptions (which attempt to justify the lack of a clear physical interface):

1. Humans are embedded (or sufficiently wired) with an array of bio-sensors.
2. These bio-sensors can actively transmit data in real-time.

The idea is that with real-time monitoring of somatic states, we can infer a significant amount of information about a person. The implications for healthcare are obvious, but I'm more interested in other behavior and intentions that can be deduced from simple observation.

There have been recent and frequent breakthroughs in this field of non-invasive inference: scientists have "read minds" by reading and analyzing brain waves, resulting in the ability to determine intentions and anticipated actions in number games [Haynes JD, Sakai K, Rees G, Gilbert S, Frith C, &amp; Passingham D.  (2007, February 20). Reading hidden intentions in the human brain. *Current Biology*.]; robotic arms reach and grasp in response to primate pre-motor cortex activity [Carmena JM, Lebedev MA, Crist RE, O'Doherty JE, Santucci DM, et al. (2003) Learning to Control a Brain–Machine Interface for Reaching and Grasping by Primates. PLoS Biol 1(2): e42].

To mock up an example of a bio event and response, heart-rate events (e.g. rate increase/decrease) trigger the posting of a [Twitter](http://twitter.com) message.

<img src="http://blogs.nyu.edu/blogs/as860/iameat/uploads/diagram-overview.gif" />

An IR emitter and receiver circuit captures the pulse under the principle of [pulse oximetry](http://en.wikipedia.org/wiki/Pulse_oximetry), which involves measuring the variation of blood volume using emitted and refracted light through a person's fingertip.

Analog readings are wirelessly sent to a central computer via [XBee Series 1 radios](http://www.digi.com/products/wireless/point-multipoint/xbee-series1-module.jsp) where the pulse is determined and logged. A "plugin" listens for these events of changed status and execute its action.

The framework is extensible with multiple plugins that can do anything in response to events. This example's plugin sent varying Twitter messages, such as "OMGOMGOMG!!!" or "...comatose" in response to a significant change in heart rate, however plugins can be programmed to do anything. It's imaginable that with more accurate and varied bio-sensors, GPS information, movements sensors (e.g. accelerometers), integration with other data sources such as one's personal calendar, conversation histories, etc... inferences and assumptions becomes more expressive and accurate, lending to actions that border on predictive, chivalrous, and natural. Imaginably. It all starts with ubiquitous and accurate data.
