# Cyber60 bootloader flash instructions

I use and recommend a j-link for flashing the bootloader, for using other programmers for flashing the bootloader, I can recommend to check jorics wiki for info: https://github.com/joric/nrfmicro/wiki/Bootloader

## TLDR:
Do step 2 here: https://learn.adafruit.com/bluefruit-nrf52-feather-learning-guide/flashing-the-bootloader
But use the bootloader from here: https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases

## Mac/Linux:
- Download and install nrfprog
- Download bootloader from here (.hex-file): 
https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases
You need the bootloader for the correct revision of your cyber60. Revision A and B share the same bootloader. If unsure: Look at the PCB, the revision will be stated under the name cyber60. Revsion here is the letter A, B, C etc.
- Open terminal
- Navigate to directory of bootloader
- Run:
```nrfjprog --program [bootloader name].hex --chiperase -f nrf52 --reset```
- Now bootloader should be flashed if all went well and it should show up as a removable device called CYBER_ followed by it's revision
- If flash went well, but it's not showing up. Try to cycle power of the PCB (unplug USB and battery then reconnect) and you should be able to enter bootloader (double click on reset-button) and flash the PCB.

## Windows:
- Install nrf-command-line-tools
- Download bootloader from here (.hex-file): 
https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases
You need the bootloader for the correct revision of your cyber60. Revision A and B share the same bootloader. If unsure: Look at the PCB, the revision will be stated under the name cyber60. Revsion here is the letter A, B, C etc.
- Copy bootloader to your nrf-command-line-tools directory (or copy nrfprog to the bootloader directory)
Usually in  C:\Program Files (x86)\Nordic Semiconductor\nrf-command-line-tools\bin\
- Open commandline
- Navigate to directory
- Run: 
```nrfjprog.exe --program [bootloader name].hex --chiperase -f nrf52 --reset```
- Now bootloader should be flashed if all went well and it should show up as a removable device called CYBER_ followed by it's revision
- If flash went well, but it's not showing up. Try to cycle power of the PCB (unplug USB and battery then reconnect) and you should be able to enter bootloader (double click on reset-button) and flash the PCB.