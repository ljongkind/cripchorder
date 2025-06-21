<!-- This file is for describing and explaining the project -->

# cripchorder
Compact programmable onehanded Bluetooth chording keyboard for iPhone (ZMK, Nice!Nano v2)

# One-Handed Bluetooth Chording Keyboard

## Goal
To build a compact, lightweight, wireless keyboard with 7–9 keys, optimized for one-handed use with chording. Designed for use with iPhone via Bluetooth HID. Based on the Nice!Nano v2 and ZMK firmware.

## Hardware (components + budget)

| Component                 | Purpose                                      | Est. Cost |
|--------------------------|----------------------------------------------|-----------|
| Urchin PCB (1 half)      | Small PCB with layout for 9 keys             | €12       |
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

### 💡 ZMK Build System: Board + Shield = Build

In ZMK, firmware is built for a specific combination of:

- **Board** – the microcontroller (e.g., Nice!Nano v2, Pro Micro RP2040)  
- **Shield** – the keyboard layout and electrical mapping (e.g., my `cripchorder`)

Together, they form a **Build**:

build = board + shield
This means that you can reuse the same `cripchorder` shield with different microcontrollers, 
or test other shields with the same board.


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
