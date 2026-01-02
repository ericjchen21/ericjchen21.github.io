---
layout: project_page
slug: EQ-Speaker
title: EQ Speaker
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

      |   | Low-Pass R (Ω) | Low-Pass C (μF) | High-Pass R (Ω) | High-Pass C (μF) | Band-Pass Low R (Ω) | Band-Pass Low C (μF) | Band-Pass Low R (Ω) | Band-Pass High C (μF) |
      |---|:--------------:|:---------------:|:---------------:|:----------------:|:-------------------:|:--------------------:|:-------------------:|:---------------------:|
      | 1 | 1000           | 2.200           | 1000            | 0.022            | 1200                | 0.220                | 800                 | 0.220                 |
      | 2 | 1000           | 1.000           | 2700            | 0.022            | 1200                | 0.100                | 2000                | 0.220                 |
      | 3 | 1000           | 0.150           | 18000           | 0.022            | 1200                | 0.015                | 15000               | 0.220                 |
  - image: "/assets/img/projects/EQ Speaker/Third Order Low-Pass Butterworth Filter.png"
    alt: "Third Order Low-Pass Butterworth Filter"
    caption: "Third order low-pass Butterworth filter schematic taken from Practical Electronics for Inventors textbook. Resistors and capacitors are swapped to make high-pass and band-pass filters."
  - text: |
      After figuring out the resistor and capacitor values for our filters, we were able to put together a full schematic using Fusion 360's electronic design tools.
---
