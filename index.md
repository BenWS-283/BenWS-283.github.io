---
layout: splash
permalink: /
title: "Ben Sedran"
excerpt: "Mechanical engineering and computer science at Cornell | Space systems and robotics"
header:
  overlay_color: "#2f4f6f"
  overlay_filter: 0.4
  actions:
    - label: "View Projects"
      url: /projects/
    - label: "About Me"
      url: /about/

gallery:
  - url: /projects/random-positioning-machines/
    image_path: /assets/images/RPM_image.jpg
    alt: "Random positioning machine for microgravity simulation"
    title: "Random Positioning Machines"
  - url: /projects/autonomous-drone/
    image_path: /assets/images/drone.jpg
    alt: "Carbon fiber octocopter drone"
    title: "Octocopter Firefighting Drone"
  - url: /projects/alarm-clock/
    image_path: /assets/images/alarm_clock_side.jpg
    alt: "Custom digital alarm clock in plywood enclosure"
    title: "Digital Alarm Clock"
---

## Overview

I'm a junior at Cornell studying Mechanical Engineering with a minor in Computer Science, and I'm interested in space systems and robotics. I like projects where mechanical design, electronics, and code have to work together. This summer I built eight random positioning machines for a space-microbiology lab to simulate microgravity for microorganisms. I'm now designing a carbon fiber octocopter with firefighting capabilities on the Cornell Autonomous Drone team. This site collects the projects, with design decisions, results, and files.

## About Me

I grew up in Bedford, MA, and now study in Ithaca, NY. Outside of class I play on Cornell Club Water Polo, and I've worked as a swim instructor and lifeguard for several years, which taught me to lead and train others. [Add a sentence about what first got you into engineering.]

[Read more about me]({{ site.baseurl }}/about/){: .btn .btn--primary }
[Resume (PDF)]({{ site.baseurl }}/assets/files/Ben_Sedran_Resume.pdf){: .btn .btn--info }
[LinkedIn](https://www.linkedin.com/in/ben-sedran-b151593a5){: .btn .btn--info }

![Ben Sedran working on an RPM]({{ site.baseurl }}/assets/images/profile.jpg){: .align-left style="width: 180px; border-radius: 50%;"}

## Featured Projects

{% include gallery id="gallery" layout="half" caption="Click a project to read the full writeup." %}

[View all projects]({{ site.baseurl }}/projects/){: .btn .btn--primary .btn--large }

## Tools and Technologies

I picked up most of these skills by building things, and each project pushed me into something new: stepper motor control, I2C communication, designing parts for 3D printing, or building a modular design that others can extend.

| Area | Tools | Used in |
|------|-------|---------|
| CAD | Autodesk Fusion, Onshape | RPMs, lanternfly trap, drone |
| Embedded / electronics | Arduino, RP2040, DS3231 RTC, I2C, Nema 17 steppers, soldering | RPMs, g-vector loggers, alarm clock |
| Programming | C/C++, Java, OCaml, RISC-V Assembly, MATLAB | Alarm clock, coursework |
| Fabrication | 3D printing, machining, woodworking | All projects |
| Version control and docs | Git, GitHub, Linux | RPM documentation repo, this portfolio |

**Currently learning:** [e.g., a tool or skill for the drone project, like flight controllers or FEA]
{: .notice--info}