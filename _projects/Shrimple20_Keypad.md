---
layout: project_page
slug: Shrimple20-Keypad
date: 2025-12-01
title: Shrimple20 Keypad
date-string: December 2025
thumbnail: "/assets/img/projects/Shrimple20 Keypad/Shrimple20 Keypad.jpg"
sections:
  - text: |
      This project was the final project for my Electronic Circuit Application class. We originally wanted to design and fabricate an entire ergonomic keyboard but due to budget constraints we had to downsize to a smaller keypad. 
      <br>
      <br>
      We started by learning how keyboards in general work. Most small microcontrollers, including the one we used, the [KB2040 Kee Boar Driver by Adafruit](https://www.adafruit.com/product/5302?gad_source=1&gad_campaignid=21079267614&gbraid=0AAAAADx9JvRyNjEtzBhYzV_jAr_aPG1Pb&gclid=Cj0KCQiAvOjKBhC9ARIsAFvz5lg0e6Gqx3cwiFlsYOZTgYqBCbmI93JTcgXDG18c-hLCY6vhr5EXRpMaAk41EALw_wcB), only have 20-30 GPIO pins which is not enough for every key on a typical keyboard. The solution is to use keyboard matrices, where, instead of each pin being connected to a single key, each pin is assigned to a row or column of the keyboard. Then, the microcontroller sends a pulse down each column one at a time, and if a row receives a pulse, then the keyboard knows which key is being pressed.
  - image: "/assets/img/projects/Shrimple20 Keypad/Keyboard Matrix.png"
    alt: "Keyboard Matrix"
    caption: "Generic Keyboard Matrix. Source: [Kevin Boone](https://kevinboone.me/pro-micro-key-test-1.html)"
---
