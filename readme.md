# Corne Keyboard Firmware and Keymaps

This repository contains the firmware, keymaps, and configuration settings for the CRKBD used in my Raspberry Pi Cyberdeck project.
This uses the Corne Shield and the promicro nrf52840 as a controller.

At this point, this repo is somewhat dead and is only updated to sync with the Alphred keyboard repo occasionally, and to generate the firmware files to flash wne required. 

As a bare minimum, I've written down the most criticial elements to configure so I don't forget how to update. 

## Structure
[Build.yaml](Build.yaml) - Instructions on what firmware to build and compile.
This outputs a number of firmware files for either the left or right side side of the board.
Currently this will build files for L and R sides for NiceOLED displays.

[config/corne.keymap](config/corne.keymap) - Details the behaviour of keys on the shield. 
Defines what happens when you press what and what layers are available for use.
This includes behaviours and the likes.

[config/corne.conf](config/corne.conf) - This is detailed more in the [system configuration](https://zmk.dev/docs/config) page for ZMK.
This is the Kconfig file for the shield for both sides of the keyboard. This configures many settings on the board such as
- sleep times
- displays
- bluetooth settings 
- and more
Using the `left` or `right` suffixes you can configure both sides independently. If a single file is supplied, it will be 
applied to both boards.

## Building and compiling
This repo is automatically built and compiled as part of a GitHub workflow. Artefacts can be retrieved there.
