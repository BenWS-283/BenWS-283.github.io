---
title: "Random Positioning Machines"
excerpt: "Eight low-cost, two-axis RPMs that simulate microgravity for space microbiology research."
date: 2026-08-15
header:
  teaser: /assets/images/rpm-teaser.jpg
  overlay_image: /assets/images/rpm-header.jpg
  overlay_filter: 0.4
author_profile: false
toc: false
classes:
  - wide
  - project-page

gallery:
  - url: /assets/images/rpm-assembly.jpg
    image_path: /assets/images/rpm-assembly.jpg
    alt: "Assembled RPM"
    title: "Assembled machine"
  - url: /assets/images/rpm-cad.png
    image_path: /assets/images/rpm-cad.png
    alt: "Fusion render of the RPM frame"
    title: "CAD model"
  - url: /assets/images/rpm-electronics.jpg
    image_path: /assets/images/rpm-electronics.jpg
    alt: "Arduino and TMC2209 wiring"
    title: "Control electronics"

card_layout: pair    # single, pair, or stack
card_images:
  - /assets/images/RPM_electronics.jpg
  - /assets/images/RPM_culture_flasks.JPG
  - /assets/images/RPM_image.jpg
tools: "Fusion · 3D printing · TMC2209 · Arduino · QT PY2040"
---

**Role:** Research Assistant, Santomartino Space-Microbiology Research Group, Cornell University
**Timeline:** May 2026 – Aug. 2026
**Tools:** Autodesk Fusion, 3D printing, Arduino, TMC2209 drivers, Nema 17 steppers
{: .notice--info}

## Overview

A random positioning machine (RPM) rotates a sample about two axes in randomly changing directions and speeds, so gravity's pull averages out over time and the sample experiences simulated microgravity. The lab needed this for upcoming experiments on how bacteria and fungi degrade plastic in space. I designed, built, and tested eight two-axis RPMs at about $100 each, plus loggers to verify the simulated microgravity.

[Add 1-2 sentences on why a low-cost, repeatable design mattered to the lab.]

## Design Requirements

| Requirement | Target |
|-------------|--------|
| Axes | 2 (independent) |
| Quantity | 8 machines |
| Sample capacity | 6-24 containers per run |
| Container types | 7, with room for more |
| Cost per unit | ~$100 |
| Fabrication | Mostly 3D-printed |

## Mechanical Design

{% include gallery id="gallery" layout="third" caption="Click an image to enlarge it." %}

Describe the frame: how the inner and outer axes are nested, how each stepper drives its axis, and how you kept the print count and part count low. Explain the modular holder system that adapts to the 7 container types and how a new type would be added (a new print, a swapped insert, an adjustable mount).

## Electronics and Control

Each machine uses two Nema 17 stepper motors driven by TMC2209 drivers and controlled by an Arduino. The firmware picks random speeds and directions for each axis at set intervals.

```cpp
// Illustrative example: replace with your actual control logic
unsigned long nextChange = 0;

void loop() {
  if (millis() >= nextChange) {
    setAxisSpeed(AXIS_OUTER, random(MIN_SPEED, MAX_SPEED));
    setAxisSpeed(AXIS_INNER, random(MIN_SPEED, MAX_SPEED));
    nextChange = millis() + random(MIN_INTERVAL, MAX_INTERVAL);
  }
  runSteppers();
}
```

| Parameter | Value |
|-----------|-------|
| Speed range | [fill in] |
| Direction/speed change interval | [fill in] |
| Microstepping setting | [fill in] |

## Validation

I built eight battery-powered, attachable g-vector loggers that record orientation and acceleration to microSD. Logging a machine's motion lets you compute the time-averaged gravity vector, which should approach zero if the randomization is working.

[Add your result here: average residual g-level, run duration, and how consistent the eight machines were.]

![Logged g-vector data]({{ site.baseurl }}/assets/images/rpm-gvector-plot.png)
*[Caption: what the plot shows.]*

## Results and Lessons

- [Result: all 8 machines built, tested, and delivered at ~$100 each]
- [Result: validation outcome]
- [Lesson: what you'd change in a second revision]

## Files and Documentation

- [Build, maintenance, and user guide (GitHub)](https://github.com/BenWS-283/your-rpm-repo)
- [CAD files (STEP)]({{ site.baseurl }}/assets/files/rpm-assembly.step)
- [Firmware]({{ site.baseurl }}/assets/files/rpm-firmware.zip)