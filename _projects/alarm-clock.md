---
title: "Custom Digital Alarm Clock"
excerpt: "A custom alarm clock built to fix the annoyances of my old one."
date: 2026-08-18
header:
  teaser: /assets/images/alarm_clock_side_large.JPG
  overlay_image: /assets/images/alarm_clock_side_large.JPG
  overlay_filter: 0.3
author_profile: true
toc: false
title_color: "#a1a3a4"
classes:
  - wide
  - project-page
card_image: /assets/images/alarm_clock_front.jpg
tools: "RP2040 · C++ · I2C · 3D printing · Soldering · Table Saw"
---

<div class="notice--info" markdown="1">
**Type:** Personal project

**Timeline:** August 2026

**Tools:** C++ (Arduino IDE), RP2040, DS3231 RTC, 3D printing, soldering, table saw
</div>

## Purpose
- Replace an old, broken alarm clock with a custom-built one that avoids its problems
- Practice taking a project through every part of the design cycle, from requirements to a finished product

## Approach 
I started by researching what was necessary to build the most simplistic, bare bones alarm clock possible. My research showed I would need at least a microcontroller, a real time clock (RTC), and a piezo buzzer. 

Next, I came up with the following initial design goals based on what I liked and disliked about my previous alarm clock:

- The clock must be digital, and the only screen should be the display
- Both the hours and minutes will be adjusted up and down in an intuitive way
- The finished product should look nice, and preferably be encased in a wooden box
- Must be able to keep time during a power outage
- Code, circuitry, and encasing must be readily available for future changes
- The alarm must absolutely be loud enough to wake me up

Once I had my design requirements, I figured out how I wanted to interact with the clock. I would use two rotary encoders to adjust the time, one for hours and one for minutes. These would only do something, though, if either clock set or alarm set mode were enabled, each via its own pushbutton switch. 

As is standard when prototyping, I started by getting all of the circuitry and code fully working on a breadboard, then I soldered the wiring on a perfboard to make it permanent. Only once that was thoroughly tested did I model and assemble the encasing. 

## Solution

![Front of the finished clock]({{ site.baseurl }}/assets/images/alarm_clock_front.jpg)
*Assembled alarm clock.*

I assembled the circuitry and wrote the code simultaneously by adding one component at a time, and slowly building up the alarm clock's functionality. The main advantage to doing so was it saved me so much time locating problems while debugging. I built up the following circuit diagram while doing so, which made transferring the circuitry to a perfboard straightforward. 

One problem I encountered while doing this was that the rotary encoders sent strange, irregular signals, and did not adjust the time accurately according to the user inputs. I researched this problem and found that the encoder signals needed to be debounced to be useful. Implementing the firmware to do this made all the difference. I was then able to implement firmware debouncing for the push buttons as well, before I even tested them. 

![Alarm clock circuit diagram]({{ site.baseurl }}/assets/images/alarm_circuit.png)
*Alarm clock circuit diagram.*

Before permanantly soldering the components however, I layed out how I wanted the control panel should look. I needed to secure the encoders and buttons to the panel before soldering. The final control panel design looked like this:

![Alarm clock top]({{ site.baseurl }}/assets/images/alarm_clock_top.jpg)
*Control panel.*

One can see that the piezo buzzer sticks up into the control panel. The decision to put it there was based on a few iterations trying to maximize its volume. I knew immediately after hooking up the buzzer to the breadboard circuit that it was not loud enough as it was. I started by reading its data sheet and finding it had a frequency, 4000 Hz, where it was loudest, but I found this still wasn't enough. Next, I found that I could connect my buzzer to two GPIO pins and use a differential drive to increase its volume, and this helped enourmously. However, testing by putting it under a cup showed that an encasing would muffle the buzzer too much, so it had to be outside the box, and the control panel was a conveniant, aesthetic location for it. 

Finally, I was able to build the plywood box. This was done using a table saw, and a jigsaw to make a large hole in the top for the control panel to connect with the rest of the circuitry. I 3d printed a front piece to both hold up the 7 segment display and label the PM and alarm setting mode lights.  

## Results

The alarm clock surpassed my expectations. Initial testing showed that it functioned perfectly as an alarm clock. The time was correctly displayed with a light for AM/PM, and it buzzed at the correct time when turned on. The debounced encoders worked perfectly to adjust the either the clock or alarm hours or minutes up or down. I liked the way it looked, and because it ran off power from a USB cable running out the back, it was easy to connect to my computer and make code edits. The coin battery held by the RTC took care of making sure time was still kept when disconnected from power.

Going to sleep and setting it to wake me up, was the important test though. This revealed a big success, that even from across the room, the buzzer was loud enough to wake me up. However, it also revealed two problems. The display was bright enough to light up the area around it at night, and it was nearly impossible to glance at it and make sure the alarm was actually set to go off.  

These were both quick changes to the code however, which were easy to make due to easy access via the USB cable out the back.

**Lessons:** [One or two things you'd change in a second version.]

#### Bill of Materials

| Part | Quantity | Description/Purpose |
|------|----------|---------------------|
| KB2040 | 1 | RP2040-based microcontroller board |
| DS3231 | 1 | Real-time clock (RTC) |
| Coin battery | 1 | Keeps time if the clock is unplugged |
| 7-segment display | 1 | Displays the time |
| Active piezo buzzer | 1 | Alarm sound |
| Rotary encoder | 2 | Setting minutes and hours |
| Push button switches | 2 | Alarm and clock set modes, with LED |
| Toggle switch | 1 | Alarm on/off |
| PLA filament | ~ 100 g | Front and control panels |
| Plywood | 24" x 7" x 3/4" | Box encasing |


## Technologies, Tools, and Techniques
- **Microcontroller programming:** C++ on an RP2040 board: I<sup>2</sup>C communication with RTC and display, encoder and button debouncing, and overall loop
- **Fabrication:** Circuit design and soldering, 3D printing, woodworking

## Files
- [Source code (GitHub)](https://github.com/BenWS-283/your-alarm-clock-repo)
- [3D-printed part files (STL)]({{ site.baseurl }}/assets/files/alarm-clock-parts.zip)