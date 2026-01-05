---
layout: project_page
slug: Shrimple20-Keypad
date: 2025-12-01
title: Shrimple20 Keypad
date-string: December 2025
thumbnail: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad.jpg"
sections:
  - text: |
      This project was the final project for my Electronic Circuit Application class. We originally wanted to design and fabricate an entire ergonomic keyboard but due to budget constraints we had to downsize to a smaller keypad. Thank you to FlatFootFox for their [Ergogen Guide](https://flatfootfox.com/ergogen-introduction/) and Christian Selig for his [Wireless Corne Build Video](https://www.youtube.com/watch?v=7UXsD7nSfDY&t=971s), both resources were instrumental for this project.
      <br>
      <br>
      We started by learning how keyboards in general work. Most small microcontrollers, including the one we used, the [KB2040 Kee Boar Driver by Adafruit](https://www.adafruit.com/product/5302), only have 20-30 GPIO pins which is not enough for every key on a typical keyboard. The solution is to use keyboard matrices, where, instead of each pin being connected to a single key, each pin is assigned to a row or column of the keyboard. Then, the microcontroller sends a pulse down each column one at a time, and if a row receives a pulse, then the keyboard knows which key is being pressed.
  - image: "/assets/img/projects/Shrimple20 Keypad/Keyboard Matrix.png"
    alt: "Keyboard Matrix"
    caption: "Generic Keyboard Matrix (diodes not pictured). Source: [Kevin Boone](https://kevinboone.me/pro-micro-key-test-1.html)"

  - text: |
      It is also common to include 1N4148W diodes (preferred by the keyboard community) between the negative leg of the switch and the trace for the given row to prevent ghosting.
  - image: "/assets/img/projects/Shrimple20 Keypad/1N4148W Diode.png"
    alt: "1N4148W Diode"
    caption: "1N4148W Diode"

  - text: |
      After understanding how keyboards worked, we had to spec out our own keypad. For switches, we went with [Kailh Choc V1s](https://www.digikey.com/short/rqp24c54) as they seem to be the most common type of switch for low-profile ergo keyboards, which will hopefully be the continuation of this project.
  - image: "/assets/img/projects/Shrimple20 Keypad/Kailh Choc V1.png"
    alt: "Kailh Choc V1"
    caption: "Kailh Choc V1"

  - text: |
      We specifically chose the hot-swappable version so that the keypad could be upgraded in future with different switches. This required using [hot-swap sockets](https://www.digikey.com/short/5drnw14j) so we could avoid directly soldering the switches.
  - image: "/assets/img/projects/Shrimple20 Keypad/Hot-Swap Socket.png"
    alt: "Hot-Swap Socket"
    caption: "Hot-Swap Socket"

  - text: |
      We also chose to include a rotary knob, specifically an [EC11 Rotary Encoder](https://www.digikey.com/short/m97rb0vh), to control volume.
  - image: "/assets/img/projects/Shrimple20 Keypad/EC11 Rotary Encoder.png"
    alt: "EC11 Rotary Encoder"
    caption: "EC11 Rotary Encoder"

  - text: |
      As previously mentioned, we used an [KB2040 Kee Boar Driver by Adafruit](https://www.adafruit.com/product/5302) to control the keypad as it was already stocked in our lab.
  - image: "/assets/img/projects/Shrimple20 Keypad/KB2040.jpg"
    alt: "KB2020"
    caption: "KB2040"

  - text: |
      With all of our components selected, we needed to choose a form factor for the keypad. We chose to have 4 columns by 5 rows to match the size of a typical full-sized keyboard's numpad. To actually create the keypad, we first had to learn Ergogen, an open source .yaml file based keyboard layout generator. This just means that it takes a .yaml file, a structured, text-based data file, with information on groups of keys, locations, dimensions, etc., and creates a .dxf blueprint of the keyboard layout, and a KiCad PCB file to be exported and wired later. Our keypad layout ended up looking like this, the corresponding .yaml, .dxf, and .kicad_pcb files are available on my GitHub,
---
