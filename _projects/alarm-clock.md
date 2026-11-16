---
title: "Custom Digital Alarm Clock"
excerpt: "A custom alarm clock built on an RP2040 with a DS3231 real-time clock, rotary-encoder time setting, and a handmade wooden enclosure, designed to fix the annoyances of my old one."
date: 2026-08-18
header:
  teaser: /assets/images/alarm_clock_front.jpg
  overlay_image: /assets/images/alarm_clock_front.jpg
  overlay_filter: 0.4
author_profile: false
toc: false
classes:
  - wide
  - project-page
card_image: /assets/images/alarm_clock_front.jpg
tools: "RP2040 · C++ · I2C · 3D printing · Soldering · Table Saw"
---

**Type:** Personal project
**Timeline:** August 2026
**Tools:** C++ (Arduino IDE), RP2040, DS3231 RTC, 3D printing, soldering, table saw
{: .notice--info}

## Project Objectives
- Replace an old, broken alarm clock with a custom-built one that avoids its problems
- Practice taking a project through every part of the design cycle, from requirements to a finished product

## Design Requirements
My previous alarm clock made it annoying and inconvenient to set the alarm and clock times. Based on those problems, I set the following goals:
- Adjust minutes and hours separately, in both directions
- Switch to and stay in alarm or clock setting mode with the push of a button
- Edit the code without taking the clock apart
- See at a glance whether the alarm is on (added later in the design cycle)

## Bill of Materials

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

## Design and Build

![Front of the finished clock]({{ site.baseurl }}/assets/images/alarm_clock_front.jpg)
*Custom wooden digital alarm clock showing the time.*

**Enclosure:** [How you cut and assembled the wooden box, what the 3D-printed parts hold in place, and how you left access for code updates without disassembly.]

**Electronics:** The KB2040 talks to the DS3231 over I2C, which keeps time even when unplugged thanks to the coin battery. [Mention how the display is driven, and add a wiring photo or diagram.]

**Firmware:** [Describe the structure: clock mode, alarm mode, how each encoder adjusts hours and minutes in both directions, and how you debounced the encoders and switches. Add one short code excerpt if you want, with a link to the full code.]

## Results

[Did it meet each requirement? Go through the four design requirements one by one. Mention what worked, what didn't, and how the alarm-indicator feature changed the design when you added it late.]

**Lessons:** [One or two things you'd change in a second version.]

## Technologies, Tools, and Techniques
- **Microcontroller programming:** C++ on an RP2040 board
- **Communication protocols:** I2C with the DS3231 RTC
- **User input:** rotary encoders and switches, with debouncing
- **Fabrication:** 3D printing, table saw woodworking
- **Electronics assembly:** soldering and wiring

## Files
- [Source code (GitHub)](https://github.com/BenWS-283/your-alarm-clock-repo)
- [3D-printed part files (STL)]({{ site.baseurl }}/assets/files/alarm-clock-parts.zip)