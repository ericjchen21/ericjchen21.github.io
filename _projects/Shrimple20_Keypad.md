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
      We also bought some basic [blank Khail Choc V1 keycaps](https://www.adafruit.com/product/5737) that we could write characters on:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad Keycaps.jpg"
    alt: "Blank Khail Choc V1 keycaps"
    caption: "Blank Khail Choc V1 keycaps"

  - text: |
      With all of our components selected, we needed to choose a form factor for the keypad. We chose to have 4 columns by 5 rows to match the size of a typical full-sized keyboard's numpad. To actually create the keypad, we first had to learn Ergogen, an open source .yaml file based keyboard layout generator. This just means that it takes a .yaml file, a structured, text-based data file, with information on groups of keys, locations, dimensions, etc., and creates a .dxf blueprint of the keyboard layout, and a KiCad PCB file to be exported and wired later. Our keypad layout ended up looking like this (.yaml, .dxf, and .kicad_pcb files are available on my GitHub):
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad Ergogen.png"
    alt: "Shrimple20 Keypad Ergogen"
    caption: "Shrimple20 Keypad in Ergogen.
      Note that the .dxf on display only shows the key locations, the rotary encoder and microcontroller footprints are still included in the .kicad_pcb file"

  - text: |
      Next we had to route the traces for the PCBs using KiCad, an Electronic Design Automation (EDA) software. Loading up the raw .kicad_pcb file from Ergogen looks like this:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad KiCad Unwired.png"
    alt: "Shrimple20 Keypad KiCad Unwired"
    caption: "Shrimple20 Keypad in KiCad, unwired"

  - text: |
      After manually routing all the traces, editing board outlines, and adding text, the KiCad file looks like this:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad KiCad Wired.png"
    alt: "Shrimple20 Keypad KiCad Wired"
    caption: "Shrimple20 Keypad in KiCad, wired"

  - text: |
      We chose the name "Shrimple20" because, well, it's shrimple really.
      <br>
      <br>
      At this point, the PCB was reading to manufactured, so we exported the gerber file and sent it to JLC PCB.
      <br>
      <br>
      Now we had to design a case for the Shrimple 20, making sure to implement the following features:

        1. A top plate that switches could comfortable snap-fit into
        2. Support for the PCB with clearance for the hot-swap sockets and diodes
        3. Clearance for the microcontroller's data cable
        4. Holes for heat-set inserts
        5. Minimal overhangs to minimize support material
        6. A shrimp logo (because well, it's shrimple really)

      This is the design we settled on:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad Case.png"
    alt: "Shrimple20 Keypad Case"
    caption: "Shrimple20 Keypad Case"

  - text: |
      We also had to design a knob to fit on the rotary encoder:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad Knob.png"
    alt: "Shrimple20 Keypad Knob"
    caption: "Shrimple20 Keypad knob"

  - text: |
      After all the components had been printed and the PCB had arrived and had all components soldered in place, we had the finished physical product:
  - image: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad.jpg"
    alt: "Shrimple20 Keypad"
    caption: "Fully assembled Shrimple20 Keypad"

  - text: |
      The last step for this project was installing the firmware. We chose to use [KMK](https://github.com/KMKfw/kmk_firmware) because we wanted to try using Circuit Python. Setting this up required learning the following:

        1. KMK modules
        2. KMK extensions
        3. Layers
        4. Media keys
        5. Macros

      Ultimately, we decided on having three layers:

        1. Basic numberpad layer
        2. Media keys and navigation controls,including a button for Spotify
        3. SHRIMP

      Defined here:

      ```python
      keyboard.keymap = [

          [KC.BSPC, KC.LPRN, KC.RPRN, KC. PSLS,
           KC.N7  , KC.N8  , KC.N9  , KC.PAST,
           KC.N4  , KC.N5  , KC.N6  , KC.PMNS,
           KC.N1  , KC.N2  , KC.N3  , KC.PPLS,
           TO_LYR2, KC.N0  , KC.DOT , KC.PENT,
           xxxxxxx, xxxxxxx, xxxxxxx, KC.MUTE,
           ],

          [KC.DEL , KC.MPRV, KC.MPLY, KC.MNXT,
           KC.HOME, KC.UP  , KC.END , KC.PGUP,
           KC.LEFT, KC.DOWN, KC.RGHT, KC.PGDN,
           TAB_PRV, TAB_NXT, WND_PRV, WND_NXT,
           TO_LYR2, SPOTIFY, PG_BCK , PG_FWD ,
           xxxxxxx, xxxxxxx, xxxxxxx, TO_SHRIMP,
           ],

          [SHRIMP , SHRIMP , SHRIMP , SHRIMP ,
           SHRIMP , SHRIMP , SHRIMP , SHRIMP ,
           SHRIMP , SHRIMP , SHRIMP , SHRIMP ,
           SHRIMP , SHRIMP , SHRIMP , SHRIMP ,
           SHRIMP , SHRIMP , SHRIMP , SHRIMP ,
           xxxxxxx, xxxxxxx, xxxxxxx, SHRIMP ,
           ],
      ]
      ```
---
