---
layout: post
title: Microwave Patch Antenna
description:
    Optically Detected Magnetic Resonance (ODMR) is a technique used to measure the quantum spin state of defects in diamond samples. In the experiment, microwaves are used to excite electrons and move them from a radiative to a non-radiative state. The energy level separation between these states depends on the strength of an external magnetic field. Using a laser and measuring the fluorescent emissions from the diamond, the magnetic field strength can be measured with high accuracy. 
skills: 
- Altium Designer
- Ansys HFSS
- Antenna Design
main-image: /antenna.png
---

In this project, I designed and optimized a microstrip patch antenna with a wide bandwidth in Ansys HFSS and created a PCB in Altium Designer. This was part of my intership at the Optical Materials and Devices (OMAD) Lab at the National University of Singapore (NUS). <br>

ODMR is most commonly done with negatively charged nitrogen-vacency (NV-) centers in diamond. Members of OMAD shifted their focus to a much newer and less studied defect in diamond, the TR12 defect. Compared to the NV- center, the resonance frequency of the TR12 defect is lower requiring a physically larger antenna. This can be problematic because lab setups often lack space and the diamond sample is usually very small (2mmx2mm). <br>

To overcome these challenges I came up with the antenna design pictured above. The design is based off a circular patch antenna, commonly used for NV- centers, but has a circular parasitic element resembling a double split-ring resonator. The gap between the circular patch and the parasitic element increases the capacitance of the antenna, reducing resonance frequency without significantly increasing the diameter of the circular patch. To optimize the design, a series of parametric sweeps and optimization algorithms in Ansys HFSS was used for fine tuning of dimensions and feedline impedance matching. The simulation of the final design is shown below.

## Antenna Design
{% include image-gallery.html images="s11_parameter.png" height="500" %} 

With a low input reflection coefficient (S11) and wide bandwidth, this antenna can efficiently excite the electrons in the TR12 centers over a wide range of applied magnetic fields.

## PCB Design
{% include image-gallery.html images="antenna_pcb.png" height="500" %} 

The patch antenna design was moved from Ansys HFSS to Altium Designer for fabrication. 

## Experiment
{% include image-gallery.html images="lasers.jpg" height="500" %} 

Although the experiment has yet to be run with the antenna design above, many experiments were ran with other antennas around in the lab. A challenging part of the setup was aligning the laser beam and focussing on the diamond sample for accurate optical readout. 