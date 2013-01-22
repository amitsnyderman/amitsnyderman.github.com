---
layout: post
title: "Little Computers: Assignment 1"
date: 2009-01-24T17:02:46+00:00
categories:
tags:
- school
- itp
---
Had [two assignments](http://www.littlecomputers.net/?page_id=21) for Little Computers this week:

* **Squeak:** We had to download and play around with [Squeak](http://www.squeak.org/), a modern implementation of [Smalltalk](http://www.squeak.org/Smalltalk/). Need to explore a bit more but it's rather bizarre at first glance and different from any other programming environment I've played with.

  _Assignment:_ [Squeak3.10.2-7179-basic.image.zip](http://amitsnyderman.com/school/littlecomputers/assignment1/Squeak3.10.2-7179-basic.image.zip)

* **Reverse:** _Write a program that takes a string and reverses it. You do not need to allocate memory, you can use a char array to hold the reversed string. Do not use C string facilities. You just need a for loop._

  So I did a bunch of versions of this, with each attempt trying to declare less variables and consolidate the previous. Ended up with two implementations, one iterating directly through the character arrays, and another using pointer arithmetic.
  
  After playing with so many modern languages playing with C feels like playing guitar with two fingers; it's familiar but clumsy at first. Have done the pointer implementation though, I can definitely see why people frequently drop into C for performance optimizations. Need to keep reading about memory allocation...
  
  Is it possible to return a character array like you would a string in other languages? Not sure I like the style of passing both variables (and the string length) into the function.
  
  _Assignment:_ [reverse.c](http://amitsnyderman.com/school/littlecomputers/assignment1/reverse.c)
