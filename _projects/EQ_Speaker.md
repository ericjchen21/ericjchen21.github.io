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
      We decided to use 3rd order low-pass, high-pass, and band-pass Butterworth filters with the following resistor and capacitor values:

      | Low-Pass R (Ω) | Low-Pass C (μF) |
      |----------------|-----------------|
      |       3        |       3         |
---
