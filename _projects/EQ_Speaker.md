---
layout: project_page
slug: EQ-Speaker
title: EQ Speaker
date: Fall 2025
sections:
  - text: |
      This project was one of the labs for my Electronic Circuit Application class, but I thought it was interesting enough to include here. Our assignment was to design and build an audio equalizer and amplifier from scratch using Butterworth filters and other provided circuits. This required learning:

              1. Op-Amp Theory theory 
              2. Butterworth filter theory 
              3. Fusion 360's Electronics Design workspace
              4. Designing and assembling PCBs

      After learning about Op-Amp and Butterworth filter theory, we started prototyping our circuit on a breadboard, testing different Butterworth filters, trying different orders and capacitor and resistor values to achieve the desired effect. We also had to implement a couple sub-circuits such as:

              1. A virtual-ground power supply
              2. An audio signal centering circuit
              3. An audio signal summing Op-Amp
              4. A signal amplifier
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker Breadboard V1.jpg"
    alt: "Our first breadboard prototype"
    caption: "Our first breadboard prototype"

  - text: |
      We decided to use 3rd order low-pass, high-pass, and band-pass Butterworth filters set 3dB attenuation frequences of ~250Hz and ~2000 Hz with the following resistor and capacitor values:
      <br>
      <br>

      |   | Low-Pass R (Ω) | Low-Pass C (μF) | High-Pass R (Ω) | High-Pass C (μF) | Band-Pass Low R (Ω) | Band-Pass Low C (μF) | Band-Pass High R (Ω) | Band-Pass High C (μF) |
      |---|:--------------:|:---------------:|:---------------:|:----------------:|:-------------------:|:--------------------:|:-------------------:|:---------------------:|
      | 1 | 1000           | 2.200           | 1000            | 0.022            | 1200                | 0.220                | 800                 | 0.220                 |
      | 2 | 1000           | 1.000           | 2700            | 0.022            | 1200                | 0.100                | 2000                | 0.220                 |
      | 3 | 1000           | 0.150           | 18000           | 0.022            | 1200                | 0.015                | 15000               | 0.220                 |
  - image: "/assets/img/projects/EQ Speaker/Third Order Low-Pass Butterworth Filter.png"
    alt: "Third Order Low-Pass Butterworth Filter"
    caption: "Third order low-pass Butterworth filter schematic taken from Practical Electronics for Inventors textbook. Resistors and capacitors are swapped to make high-pass and band-pass filters."

  - text: |
      After figuring out the resistor and capacitor values for our filters, we were able to put together a full schematic using Fusion 360's electronic design tools.
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker Schematic V1.png"
    alt: "EQ Speaker Schematic V1"
    caption: "Full EQ speaker schematic V1"

  - text: |
      From this schematic we made a 2D PCB, learning about copper layers, traces, polygons, and vias:
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker 2D PCB V1.png"
    alt: "EQ Speaker 2D PCB V1"
    caption: "EQ Speaker 2D PCB V1"

  - text: |
      And then a rendering of the PCB in 3D:
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker 3D PCB V1.png"
    alt: "EQ Speaker 3D PCB V1"
    caption: "EQ Speaker 3D PCB V1"

  - text: |
      We then exported the gerber files for the 2D PCB and sent them to JLC PCB to be manufactured. Once they arrived, we use solder masks to apply solder masks on the components' footprints, and manually placed all the surface mount components before baking them onto the PCB in an oven. Then we finished the PCB by soldering on the remaining through hole components by hand.
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker V1.png"
    alt: "EQ Speaker V1"
    caption: "Assembled EQ Speaker V1"

  - text: |
      We also designed a wooden enclosure to house the EQ speaker in a nicer form factor. It was dubbed the "Audio Obliterator" since it didn't work as well as we had hoped.
  - image: "/assets/img/projects/EQ Speaker/Audio Obliterator.jpg"
    alt: "Audio Obliterator"
    caption: "The Audio Obliterator, the knobs and PCB are removed in this photo since we had to scavenge some components for the second iteration of this project"

  - text: |
      At this point we had to take a step back from the EQ Speaker project to work on the other labs for this engineering class. When we had time to revisit it a few months later, we determined that it likely didn't work for two reasons, either the traces were wired incorrectly, or the resistor and capacitor values were incorrect, probably both.
      <br>
      <br>
      What we didn't know going into this project was that surface mount resistors and capacitor values followed the E12 value series, the values 1.0, 1.2, 1.5, 1.8, 2.2, 2.7, 3.3, 3.9, 4.7, 5.6, 6.8, and 8.2 times powers of 10. Since there was a much wider range of values available for the through hole resistors and capacitors we assembled the breadboard with, we had chosen values that didn't nicely fit into the E12 scheme. This resulted in there being a discrepancy between the breadboard resistors and capacitors and the circuit board resistors and capacitors, so the circuit board didn't behave at all like we had expected it to.
      <br>
      <br>
      Knowing this, and because the traces on the first iteration PCB were incorrect, we prototyped a new breadboard, recalculating our resistor and capacitor values to better follow the E12 scheme, prioritizing the capacitors as it was easier for us to string together resistors in series to achieve the odd values required to have nice capacitors values than vice versa.
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker Breadboard V2.png"
    alt: "EQ Speaker Breadboard V2"
    caption: "Second breadboard prototype"

  - text: |
      The new resistor and capacitor values we landed on are as follows:
      <br>
      <br>

      |   | Low-Pass R (Ω) | Low-Pass C (μF) | High-Pass R (Ω) | High-Pass C (μF) | Band-Pass Low R (Ω) | Band-Pass Low C (μF) | Band-Pass High R (Ω) | Band-Pass High C (μF) |
      |---|:--------------:|:---------------:|:---------------:|:----------------:|:-------------------:|:--------------------:|:-------------------:|:---------------------:|
      | 1 | 18000          | 0.1200          | 238             | 0.0470           | 1180                | 0.1200               | 3900                | 0.0470                |
      | 2 | 18000          | 0.0470          | 607             | 0.0470           | 1180                | 0.0470               | 9700                | 0.0470                |
      | 3 | 18000          | 0.0068          | 4170            | 0.0470           | 1180                | 0.0068               | 68000               | 0.0470                |

      Then we designed the 2D PCB, this time also including mounting holes and legs to snap the PCB into sections to allow for a nicer final form factor:
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker 2D PCB V2.png"
    alt: "EQ Speaker 2D PCB V2"
    caption: "EQ Speaker 2D PCB V2"

  - text: |
      We also designed a new 3D printed enclosure that printed in multiple parts and bolted together with M3 screws and threaded inserts, made to somewhat resemble a boombox:
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker V2 Enclosure.png"
    alt: "EQ Speaker V2 Enclosure"
    caption: "EQ Speaker V2 enclosure, made of multiple components"

  - text: |
      After ordering the new PCB from JLC PCB, soldering all the components, and assembling, the final version of the EQ Speaker was done:
  - image: "/assets/img/projects/EQ Speaker/EQ Speaker V2.png"
    alt: "EQ Speaker V2"
    caption: "EQ Speaker V2"

  - text: |
      It filters audio much better than the first version, though there are still some issues with the low-pass filter. We had to reuse some components, some of which may have been broken, and solder through hole components to surface mount pads, so I'm guessing that is likely where the issues are coming from. Hopefully I'll be able to put together another PCB soon with fresh components and it will work properly!
---
