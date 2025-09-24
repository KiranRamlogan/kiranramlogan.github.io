---
layout: post
title: Satellite Solar Generation Stage
description:
    The University of Toronto Aerospace Team (UTAT) Space Systems division is developing the FINCH satellite. A major part of the satellite's power system is the solar generation stage. This design features OR-ing of multiple solar panels and individual Maximum Power Point Tracking (MPPT).
skills: 
- Altium Designer
- Power Integrity
- Switching Converters
- Power OR-ing
main-image: /charger_sch.png
---

In this project I went through the entire design process for the generation stage of the Electrical Power System (EPS) for the FINCH satellite.

## High Level System Design

The first part of the project involved coming up with a high level design of the generation stage. Through lots of research, conversations with the team, and external design reviews with industry professionals, I came up with the following block diagram.

{% include image-gallery.html images="eps_block.png" height="500" %} 

## Maximum Power Point Tracking (MPPT) Charger

The most complicated and crucial part of the system was the Maximum Power Point Tracking (MPPT) chargers.

{% include image-gallery.html images="charger_sch.png" height="500" %} 

Through designing this layout, I learned about identifying ground return paths and minizing high frequency current loops.

{% include image-gallery.html images="charger_lay.png" height="500" %} 


## Digital Potentiometer

To allow for proper power point tracking, the digital potentiometer provides a variable voltage for the MPPT charger to adjust the input voltage of the solar panels.

{% include image-gallery.html images="digi_pot_sch.png" height="500" %}

{% include image-gallery.html images="digi_pot_lay.png" height="500" %} 

## Power Monitor

The power monitors that had been designed by the team previouly were very sensitive to fast voltage changes which often caused inaccurate readings. To counter this I added a RC filter to the sense resistor voltage measurement pins.

{% include image-gallery.html images="power_monitor_sch.png" height="500" %} 

{% include image-gallery.html images="power_monitor_lay.png" height="500" %} 

## Power OR-ing (Ideal Diodes)

Although both MPPTs are almost identical, voltage differences caused by component tolerances may cause current to flow from one MPPT into another. To eliminate this possiblity, ideal diodes prevent reverse current flow while having lower on resistance than traditional diodes.

{% include image-gallery.html images="oring.png" height="500" %} 

