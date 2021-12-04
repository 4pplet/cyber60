
# cyber60

A DIY-friendly 60% using nRF52840 and ZMK: the cyber.

## Status:
Revision C1 is mostly tested and works (still to do is to verify charge current). Please read release notes for specific release before manufacturing.

## Software:
- Link to zmk-fork: https://github.com/4pplet/zmk
- Link to zmk-config (uf2-files in actions): https://github.com/4pplet/zmk-config-4pplet

## Instructions:
- How to flash/update bootloader: [Link](./BL_FLASH_INSTRUCTION.md)
- How to flash/update ZMK: IN WORK

## Specs cyber60:
- Module: Holyiot YJ-18010
- Standard Tray Mount support (need battery cutout for internal battery)
- "rubber worm"-mount support (both bakeneko v1 and bakeneko v3). Case still need battery cutout for internal battery.
- Non constant drain battery measurement
- Lipo charger for single cell 3.7V li-po/li-ion batteries
- RGB-led under Capslock for multi function indicator (not on SMK-version)
- Possible to build with just a soldering iron (no underside pads etc)
- Three versions running the same FW-implementation. One MX, one ALPS, one SMK
- USB horizontal placement is classic GH60, same as GH60, plain60, voyager60 etc.
- (rev b and newer) Underglow for cozy glow
- (rev b and newer) Buzzer for indicator or sweet tunes
- (rev b and newer) Rotary encoder at right most posision in split backspace or off board
- (rev b and newer) Reverse polarity protection for battery
- (rev c and newer) Transistor stage for battery voltage measurement cutoff for no leak current when not measuring battery voltage (like in rev A).

## Todo:
- Properly verify current consumption
- Properly verify charge current
- Improve silkscreen for RGB-led orientation and soldermask cover on non circular pads on bottom layer.

# Layout support (non hotswap):
![alt text](./readme-images/layout_support_cyber60_Rev_C.jpg "Layout support")

# MX-version:
![alt text](./readme-images/cyber60-MX_Rev_C1_All.jpg "PCB View - Rev C")

## MX Revisions:
- A1 - initial revision/prototype
- A2 (prerelease) - flipped PMOS-transistor error in Rev A1. Added pulldown on enable to battery voltage measurement circuit, so it does not have to be disabled in code, only enabled. Minor silkscreen changes.
- B1 (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.
- C1: Changing layout support for better solderability of module. Adding transistor cutoff for battery voltage measurement for no leak current. Switching to ws2812c in 2020-package. Rotating ANSI-enter stabilizer 180 degrees.
- C2: Minor adjustments to pads and soldermask

# ALPS-version
![alt text](./readme-images/cyber60-ALPS_Rev_C1_All.jpg "PCB View - Rev C")

## ALPS Revisions:
- A1 - initial revision/prototype, builds on MX rev A2
- B1 (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.
- C1: Changing layout support for better solderability of module. Adding transistor cutoff for battery voltage measurement for no leak current. Switching to ws2812c in 2020-package. Rotating ANSI-enter stabilizer 180 degrees.
- C2: Minor adjustments to pads and soldermask

# SMK-version
![alt text](./readme-images/cyber60-SMK_Rev_C1_All.jpg "PCB View - Rev C")

## SMK Revisions:
- A1: Initial revision/prototype, builds on ALPS rev A1
- B1: (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.
- C1: Changing layout support for better solderability of module. Adding transistor cutoff for battery voltage measurement for no leak current. Switching to ws2812c in 2020-package. Rotating ANSI-enter stabilizer 180 degrees.
- C2: Minor adjustments to pads and soldermask

# MX Hot swap-version
![alt text](./readme-images/cyber60-MXHS_Rev_C1_All.jpg "PCB View - Rev C")

## Layout support:
![alt text](./readme-images/layout_support_cyber60HS_Rev_C.jpg "Layout support")

## MXHS Revisions:
- C1: Initial revision, based on MX C1.
- C2: Minor adjustments to pads and soldermask

<a href='https://ko-fi.com/4pplet' target='_blank'><img height='35' style='border:0px;height:46px;' src='https://az743702.vo.msecnd.net/cdn/kofi3.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' />
