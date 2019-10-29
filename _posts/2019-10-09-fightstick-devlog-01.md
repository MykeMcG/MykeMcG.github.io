---
layout: post
title:  "Fightstick Devlog 1"
date:   2019-10-09 17:00:00 -0300
categories: fightstick arduino programming
---

<style>
  figure {
    max-width: 900px;
    margin-left: auto;
    margin-right: auto;
  }
</style>

# Disclaimer

**This is my first electronics project. My designs may be bad and inefficient.**

# Intro

Earlier this year, I discovered [ZeroRanger][zeroranger], a retro-styled shmup on Steam and Itch.io, and I fell in love.
I enjoyed the game so much that I decided I was going to make a customized arcade stick themed around it.

Fast forward a couple months, and I became obsessed with the [OpenComputers][opencomputers] mod for Minecraft, and I decided that, instead of buying a pre-programmed arcade stick control board, I would program my own.

# Getting Started

For the controller board, I chose to use an [Arduino Leonardo][arduino] for the following reasons:
- It has a good reputation
- I had heard it was easy to work with
- I managed to find an [XInput emulation library][xinput]

In the end, I ordered the following parts from [RobotShop][robotshop]:
- [Arduino Leonardo Microcontroller](https://www.robotshop.com/ca/en/arduino-leonardo-microcontroller-headers.html)
- [Universal Kit for Arduino](https://www.robotshop.com/ca/en/universal-kit-arduino.html)
- [Tactile Button Assortment (12pk)](https://www.robotshop.com/ca/en/tactile-button-assortment-12pk.html)

These parts are mostly for the prototype, and to serve as an introduction to the Arduino ecosystem and working with circuits, as this is my first electronics project.

# Initial Design

Not content with waiting around for my components to arrive, I got to work on coming up with a basic design for my arcade stick using [Fritzing][fritzing].



<figure style="">
  <a href="/assets/files/97EE8A73-0B6E-4F80-A35E-52817737EEC1/breadboard.png">
    <img src="/assets/files/97EE8A73-0B6E-4F80-A35E-52817737EEC1/breadboard.png" alt="Initial fightstick circuit diagram">
  </a>
  <figcaption>Export of the initial breadboard design from Fritzing</figcaption>
</figure>

Most of the buttons are self-explanatory, but I added an extra button to the stick, as [the case I had in mind][stickbody] left me with extra space.
In the end, I decided to use this button to toggle whether the stick sends directional inputs as an analog stick, or a d-pad, to allow for added compatibility. It's the same thing as the Analog toggle button on early Playstation controllers.
I also added an indicator LED to show what state the analog toggle is in.

I also wrote an [early draft of the firmware][firmware].
Please note that this firmware requires the [XInput][xinput] library to be installed and configured.

[zeroranger]: https://se-made.com/zeroranger.html
[opencomputers]: https://github.com/MightyPirates/OpenComputers
[arduino]: https://www.arduino.cc/en/Main/Arduino_BoardLeonardo
[xinput]: https://github.com/dmadison/ArduinoXInput
[robotshop]: https://www.robotshop.com/ca/
[fritzing]: http://fritzing.org/home/
[stickbody]: https://allfightsticks.com/collections/14-enclosures/products/14-semi-modular-body
[firmware]: https://github.com/MykeMcG/fightstick/commit/865be2b384afc134c67224370c80d6b5f1c03d79