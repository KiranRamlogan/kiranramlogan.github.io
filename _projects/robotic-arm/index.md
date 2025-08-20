---
layout: post
title: Fire Safety Robotic Arm
description:
    For my second year engineering design course, five other engineering students and myself tackled the issue of
    wildfire safety by designing and building a robotic arm to pick up brances. The final assembly included two
    microcontrollers, two buck converters, five motors, two limit switches, and a time of flight sensor. Proper 
    grounding, reliable soldering and adequate decoupling played a major role in this project's success.
skills: 
- Electrical Design
- Raspberry Pi
- Power Budgetting
- Grounding
- Soldering
main-image: /robotic_arm.jpg
---

In this project, I developed the architecture of the electrical system, created a power budget, and modelled and 3D printed the claw mechanism.

## Electrical System Design
{% include image-gallery.html images="Top_Level.png" height="700" %} 

The heart of the electrical system was the two Raspberry Pi Pico microcontrollers, one used for actuating the motors and reading
the limit switches, and the other used for sensing and computation with the time of flight (ToF) sensor. For simplicity, UART was chosen
for communication between microcontrollers. I2C was used for communicating with the ToF sensor, while simple GPIO and PWM was used for
communication with motors and limit switches. <br>

A star grounding scheme was implemented to minimize noise from high power stepper motors affecting sensitive PWM, I2C, and UART signals. In addition decoupling capacitors were strategically placed across servo motor power lines to filter out any remaining noise. 

## Power Budget
{% include image-gallery.html images="Power_Budget.png" height="500" %} 

To power all components, two buck converters were used with one at 5V and the other at 7.3V. The power budget was used to ensure our all components received sufficient power and the ratings of the buck converters were not exceeded.

## Claw 
{% include image-gallery.html images="Claw.png" height="400" %} 

The claw utilized two servo motors to provide gripping and rotational movement. The design consists of many 3D printed parts fastened together with bolts and nuts. Care had to be taken to ensure 3D printing tolerances did not prevent pieces from fitting together. One point of concern was ensuring that the gears were positioned so that the teeth would interlock tightly. To eliminate the tolerance factor, one of the gears was attached to a bolt that was free to move towards and away from the other gear and be locked into place by tightening two nuts that sandwiched the plastic frame.
