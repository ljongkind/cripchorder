<!-- This file is for describing and explaining the project -->

# cripchorder
Ultracompact programmable onehanded Bluetooth 8-key chording keyboard for iPhone (ZMK, Nice!Nano v2, Paintbrush v5, artsey.io)

# One-Handed Bluetooth Chording Keyboard

## Goal
To build and program a compact, lightweight, wireless keyboard with 8 keys, optimized for one-handed use with chording. Designed for use with iPhone via Bluetooth HID. Based on the Nice!Nano v2 and ZMK firmware.

## Hardware (components + budget)

| Component                 | Purpose                                      | Est. Cost |
|--------------------------|----------------------------------------------|-----------|
| Paintbrush v5 PCB          | Small PCB with layout for 8 keys             | €12       |
| Nice!Nano v2             | Bluetooth microcontroller + ZMK firmware     | €30       |
| LiPo battery (500 mAh)   | Power source for wireless use                | €8        |
| Kailh Choc switches (10) | Low-profile, quiet mechanical switches       | €6        |
| MBK keycaps (10)         | Flat, ergonomic keycaps for Choc switches    | €14       |
| Hotswap sockets (9)      | For switch swapping without soldering        | €4        |
| 3D-printed case (optional)| Housing for structure and protection        | €10       |
| USB-C charging cable     | For charging LiPo battery via Nice!Nano      | €3        |
| Estimated shipping       | Total shipping cost                          | €12       |
| **Total**                |                                              | **€99**   |

## Software

- Firmware: **ZMK** (compiled via GitHub Actions)
- Configuration: **modular YAML files**
- No need for local Python installation
- Documentation will go in the `docs/` directory

  ---
### Understanding ZMK
ZMK Firmware allows users to manage their own keyboard configurations, including keymaps, specific hardware details, etc. all outside of the core ZMK Firmware source repository.
GitHub Actions is used to automatically build the user's configured firmware for them.

###  Understanding ZMK Builds

In ZMK, your final firmware build is the combination of two elements:

`build = board + shield`

- **Board**: the physical microcontroller (e.g., Nice!Nano v2, Seeed XIAO, etc.)
- **Shield**: the logical definition of your keyboard layout and pin connections (= electrical mapping) (e.g. of the  `cripchorder`)

Together, they form a **Build**:

You can reuse the same `cripchorder` shield with different microcontrollers, 
or test other shields with the same board. Elk unieke combinatie van board + shield leidt tot een andere build van de firmware. ZMK compilet telkens de combinatie. 

### Understanding the Github Actions workflow
In je GitHub Actions workflow (in build.yml) geef je aan welke combinaties je wilt bouwen. Dat noemen ze ook wel een build matrix.

### About nice!nano v2
USB-C 'brain piece' for the keyboard.
The nice!nano is a Pro Micro replacement development board (micro-conrtroller board) offering BLE using (containing) the nRF52840 chip.
It utilizes the ZMK firmware. The ZMK manual is here: https://zmk.dev/docs
Nice!nano also makes wireless BLE connectivity possible if paired with a battery.
Bluetooth 4.2 or newer is supported.
BLE = Bluetooth Low Energy. So it doesn't drain the battery that hard.
The nRF52840 chip that is part of the nice!nano has two GPIO-controllers.
I am not sure about if ZMK can work well with GPIO controller 1. So I will only use the pins that are connected to GPIO controller 0 (with pin numbers P0.xx) als input from keys.

## To Do

- [ ] Order components
- [ ] Set up ZMK config + build environment
- [ ] Define chording layout
- [ ] Write YAML configuration
- [ ] Flash the firmware
- [ ] Add build instructions and pinout to docs
- [ ] Create Reddit post to share project

---

Made with care for people who type with one hand
