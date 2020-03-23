---
layout: page
title:  "Programming interactivity with the BBC Microbit"
date:   2020-01-03
author: Andrew Sleigh
---

An introduction to making interactive devices

<!--more-->

## Prep for this week's class

* Watch the Microbit intro videos: <https://microbit.org/guide/quick/>
* Read this introduction: <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all>
* Familiarise yourself with the online programming environment: <https://makecode.microbit.org>

## Baseline 

We assume no prior knowledge of microcontrollers, the Microbit, or programming. However, you will find it **much** easier if you have looked at the materials in the Prep section, and played around with the [online programming environment](https://makecode.microbit.org).


## Teams

Our first session with Teams, so some principles:

### Setup

Instructions on how to join Teams: <https://mediastream.brighton.ac.uk/Play/28377>

The Team code for this module is: `hfde6an`

A getting started guide is here: <https://staff.brighton.ac.uk/is/computing/Pages/Teams.aspx>

If you have any questions, please email me.

If you are having a technical issue, please post it in the chat, or contact the Service Desk on 01273 644444 / servicedesk@brighton.ac.uk 

### How we'll use it

* Video meeting for full 3 hour session
* I'll talk with video and share my screen 
* Recording the session
* Exercises: I'l keep my video open, you can speak up or share questions in chat while you're working on a project
* This afternoon: Kyle can support (also with previous assignments, esp CAD). Format TBC.


### Etiquette
* Mute if you're not talking
* If you have a question, please post it in the chat
* Use headphones if there is feedback
* Prepare in advance so we don't waste the session dealing with technical teething problems
* Let me know if you can't hear me or don't understand – I can't rely on visual clues 


### Plan for the session

* Lecture - 45 mins
* Exercises with help - 2 hours
* Kyle available this afternoon on this Team


## Making interactive devices _aka_ "Making things do stuff"


Spectrum of making (informal, exploratory, small <—> efficient, mass-produced, resolved):
* Learning
* Prototyping
* Small-scale batch manufacturing
* Large scale manufacturing

Different kinds of microcontroller used at each stage, but many of the principles are the same

* Microbit
* Arduino
* AVRs
* Commercial ICs
* [Blob ICs](https://electronics.stackexchange.com/questions/9137/what-kind-of-components-are-black-blobs-on-a-pcb)

## What is a microcontroller?

* Microcontroller vs Microprocessor  
* Microprocessor is what’s inside your computer - needs lots of external parts to make it work: RAM, GPU, disk, etc.
* Microcontroller is a simpler computer  
* Has lots of ‘peripherals’ inside - see block diagram  

#### What’s inside a microcontroller?

Look at a datasheet, e.g. the [Nordic nRF51822-QFAA-R](https://www.nordicsemi.com/-/media/Software-and-other-downloads/Product-Briefs/nRF51822-product-brief.pdf?la=en&hash=A4B5A9AA6675A58F7B779AF81C860CD69EB867FD) on the [Microbit](https://tech.microbit.org/hardware/)

![]({{ "/assets/Nordic-nRF51822-diagram.png" | relative_url }})


Capabilities:
* Tell time / keep time
* Remember data
* Read analogue signals from the outside world
* Talk to other microcontrollers
* Send and control power out to other devices


Microbit actually has several microcontrollers onboard:

![]({{ "/assets/microcontrollers_microbit_back_gray_labels.jpg" | relative_url }})

From <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0/take-a-tour>

### How can we access these capabilities? Through the Pins!

<!-- ![attiny-pinout.png]({{ "/assets/attiny-pinout.png" | relative_url }}) -->

Pinouts are your friend. Here's one for the Microbit: 

![]({{ "/assets/microbit_platform_image_2.png" | relative_url }})

Or for the Arduino Uno (from https://store.arduino.cc/arduino-uno-rev3):

![]({{ "/assets/Pinout-UNOrev3_latest.png" | relative_url }})

<!-- 
## The Microbit

Tour of the hardware: <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all#take-a-tour>
 -->

## Writing programs for the Microbit aka "Embedded programming" 


[Online programming environment](https://makecode.microbit.org).
https://python.microbit.org/v/2.0

### Tour of the interface

Intro: <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all#lets-code>

[Mobile or Tablet](https://microbit.org/guide/mobile/)



### Getting a program onto the Microbit

What you'll need
* Microbit
* USB cable (a **good** USB data cable - many are bad and won't work)
* Computer running makecode website: <https://makecode.microbit.org>

Other options
* Use the phone app with Bluetoth connection (download Android or iOS app, pair yor phone with Microbit over BLuetooth (Microbit will need power))
* Use the simulator on the website

Process (using website)
* Create your program
* Download .hex file
* Connct Microbit to computer (appears as external disk)
* Copy .hex file onto Microbit 'disk' (overwriting previous program)
* Microbit restarts itself and runs program 



### Basic coding blocks

:thought_bubble: Show interface.

Write code by assembling blocks. Instructions run in sequence, top to bottom, within the two main blocks:

`on start` – Runs once when your Microbit starts up.   

`forever` – Runs contiously after `on start` for as long as your Microbit has power. Can run instructions thousands of times every second.



### :wrench: Exercise: Make a name badge

Make your Microbit show your name when it powers up.

<!-- 


### Simple example

Onboard I/O: Read an onboard sensor and show a response on the LED matrix
 -->


## More core concepts

### Variables ("remember this number so we can do ssomething with it later")

![]({{ "/assets/microbit-variables.png" | relative_url }})


### Logic ("if this happens, then do that")

![]({{ "/assets/microbit-logic.png" | relative_url }})

### Debugging ("tell me what happens at each step")

Strategies: 

* Simplify
* Save often
* Use the serial monitor
* Step through your code - what is it really doing?

Gotchas:

* Is it plugged in?
* Did you actually upload the program?
* Are you testing for an impossible condition?
* Did the thing actually happen, just too fast to see?


### Go further

* Make the LED matrix repond to the two buttons on the front of the Microbit 
* Use some of the other onboard sensors: compass, accelerometer (shaking, orientation)
* Assemble some blocks to respond to more than one input

e.g. 

* Driving game
* Reaction time game
* Earthquake alarm


### Serial monitor

![]({{ "/assets/microbit-serial.png" | relative_url }})

Useful for debugging, and to get data back to your computer, (e.g. if you're logging data, or controlling an animation on-screen withan external controller)

Setting up a serial monitor: <https://makecode.microbit.org/device/serial>

* Mac: Terminal app
* Linux: screen app
* Windows: complex, see instructions jere: <https://makecode.microbit.org/device/serial>

Instructions for Mac (commands to run in Terminal): 

Find out the port your Microbit is on:
`ls /dev/cu.*`

Result, something like this:
`/dev/cu.Bluetooth-Incoming-Port  /dev/cu.usbmodem14202`

Pick one that looks likely - not the Bluetooth port in this case.

Start a serial connection on that port, with a specified baud rate
`screen /dev/cu.usbmodem14202 115200`

To exit `Ctrl-A` then `Ctrl-D`

![]({{ "/assets/terminal.png" | relative_url }})


<hr/>

### Second week perhaps??

<hr/>

## Using External Inputs and Outputs ("IO")


![]({{ "/assets/microbit-pins.png" | relative_url }})

### :wrench: Exercise: Connect a sensor or control and control an output

### What you'll need

* Microbit
* USB Cable
* Breadboard
* Breadboard adapter

* External input: sensor, potentiometer, button
* External output: LED, OLED screen, LCD Screen, motor, buzzer, relay, servo



### Go further

Environmental sensor, flex sensor



Concepts:

Understanding what's significant and what isn't on the breadboard
Internal wiring

Maybe start with just a breadboard circuit...

How to plug parts in
esp microbt header - over midle secion - so pins aren't connected
Demo with multimeter

Puting values into variables so you can use them elsewhere

Analog vs digital iputs and outputs
Possible values
Calibrating sensor - e.g. for wearables

Logic loops
Simple if else
Adding more tests - how tests can fail



The forever loop vs on start

sending digital value 1 = 3V to LED

Basic LED circuit: Light an LED with just 3V and GND pins!


Note pinout diagram (of Microbit and ofBreadboad connector)
* Note some pins interfere with LED Matrix
* back pins of connector do not go sequentially!

https://microbit.org/guide/hardware/pins/
> pin 3 is shared with some of the LEDs on the screen of the BBC micro:bit, so if you are using the screen to scroll messages, you can’t use this pin as well.


## Ideas


### Onboard IO

Compass to PWM - not very good!
https://makecode.microbit.org/_hAdVJ7he4fHA


### Potentiometer

http://www.multiwingspan.co.uk/micro.php?page=pot

> The potentiometer will give you a reading from 0 - 1023. If you divide that number by 4, you can use the reading to set the brightness of the LED matrix.
You could draw a series of images. Turning the potentiometer could then allow the user to select or scroll through the images displayed on the LED matrix.
Use some IF statements or the MAP block to convert your potentiometer reading into a number that you can use to move a sprite across one axis of the matrix. Add a second potentiometer and you have both directions.
A potentiometer and buzzer can be used. Convert the potentiometer reading into a number that you can use to play a tone on the buzzer. Mix in some button action if you want to be able stop and start the buzzing freely

Write pot reading to console and to screen
https://makecode.microbit.org/_7Ar65X3woDih
Should change brightness instead!

Switch LED on or off at threshold
https://makecode.microbit.org/_dHrJxy14mYLy

Control 3 LED trafic lights with pot
https://makecode.microbit.org/_4LUCadhhsc79


### Flex sensor

Only has 2 pins!
Need to make a voltage divider.

Basic serial reading:
https://makecode.microbit.org/_6KY8EF7CvV1D

Shows how to clean up data into useful range
But boring!

Neopixels and Flex sensor:
https://makecode.microbit.org/_Kcog2V9WgEA3


Lessons: need to map values to a useful range 
This is where a serial monitor is useful

What do you do with the output
 - log to console...
  - send to app - get app?
   - control device - RGB LED...? 
    - neopixels: https://makecode.microbit.org/_CAWipEfxqb5m

### Motors

Can't seem to drive one from the pins
PWM is available on several pins: https://tech.microbit.org/hardware/edgeconnector/

Doesn't work withthe motors I have - but does work with LEDs!
Could try this with an RGB LED...?

### Connecting Microbits together
http://www.multiwingspan.co.uk/micro.php?page=bit2bit



## Netwoked Microbits


## Get input and send it to a phone







## Assignment

Should get them to play as far as they can go.
If we get far, we can do more arduino next week


See: 





### What do I need to do to pass? (40%)

Write a program using the code blocks editor that uses the buttons or sensors on the Microbit to display somethign on the LED display.

Experiment with the different sensors. What kinds of data can you get out of them? How are they imperfect? (How can they be misleading, or unreliable, and what can you do to 


Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. 

Cite external sources where you have used someone else's work.

### Extra credit (50-100%)

Write several programs to demonstrate how the different sensors work.

Explore the different blocks availble in the code editor. Describe what they do, and how you could use them. 

Try to implement the same program using the MIcroPython editor. What are the differences?
Can you make the microbit communicate with your computer - e.g. to send messages back.
Can you include logic in the program to make it communicate in a more 'human' way?

Try to make a game that ues the buttons or sensors for input, where the player has to respond to images on the LED display (e.g. Simon Says, Tetris, a driving game).

---

## Further reading / watching

* <https://learn.adafruit.com/micro-bit-lesson-1-using-the-built-in-sensors>
* <https://learn.adafruit.com/micro-bit-lesson-2-controlling-leds-on-breadboard>
* <https://learn.adafruit.com/micro-bit-lesson-3-neopixels-with-micro-bit>
* <https://learn.adafruit.com/micro-bit-lesson-4-sensing-light-and-temperature>



## For next week

Do some research about basic electronics:

* How circuits work
* Inputs and Outputs

