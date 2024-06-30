# Cyber60 bootloader flash instructions

I use and recommend a j-link for flashing the bootloader, for using other programmers for flashing the bootloader, I can recommend to check jorics wiki for info: https://github.com/joric/nrfmicro/wiki/Bootloader

## TLDR:
- Do step 2 here: https://learn.adafruit.com/bluefruit-nrf52-feather-learning-guide/flashing-the-bootloader
- But use the bootloader from here: https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases

If you already have the bootloader flashed or have bought a PCB which has the bootloader pre-flashed, you can use the update uf2 file in the bootloader release to update the bootloader. Make sure to use the update file for the correct revision of the PCB.

## Mac/Linux:
- Download and install nrfprog (https://www.nordicsemi.com/Products/Development-tools/nRF-Command-Line-Tools/Download)
- Download bootloader from here (.hex-file): 
https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases
You need the bootloader for the correct revision of your cyber60. Revision A and B share the same bootloader. If unsure: Look at the PCB, the revision will be stated under the name cyber60. Revsion here is the letter A, B, C etc.
- Open terminal
- Navigate to directory of bootloader
- Connect USB/power to the PCB and connect the programmer to the programming interface on the PCB (either the tag-connect or the 2.54 header)
- Run:
```nrfjprog --program [bootloader name].hex --chiperase -f nrf52 --reset```
- Now bootloader should be flashed if all went well and it should show up as a removable device called CYBER_ followed by it's revision
- If flash went well, but it's not showing up. Try to cycle power of the PCB (unplug USB and battery then reconnect) and you should be able to enter bootloader (double click on reset-button) and flash the PCB.

## Windows:
- Install nrf-command-line-tools: https://www.nordicsemi.com/Products/Development-tools/nrf-command-line-tools/download
- Install J-link drivers: https://www.segger.com/downloads/jlink/
- Download bootloader from here (.hex-file): 
https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases
You need the bootloader for the correct revision of your cyber60. Revision A and B share the same bootloader. If unsure: Look at the PCB, the revision will be stated under the name cyber60. Revsion here is the letter A, B, C etc.
- Copy bootloader to your nrf-command-line-tools directory (or copy nrfprog to the bootloader directory)
Usually in  C:\Program Files (x86)\Nordic Semiconductor\nrf-command-line-tools\bin\
- Open commandline
- Navigate to directory
- Connect USB/power to the PCB and connect the programmer to the programming interface on the PCB (either the tag-connect or the 2.54 header)
- Run: 
```nrfjprog.exe --program [bootloader name].hex --chiperase -f nrf52 --reset```
- If you get the response that the device is locked, try running:```nrfjprog.exe --recover```, then repeate the step above.
- Now bootloader should be flashed if all went well and it should show up as a removable device called CYBER_ followed by it's revision
- If flash went well, but it's not showing up. Try to cycle power of the PCB (unplug USB and battery then reconnect) and you should be able to enter bootloader (double click on reset-button) and flash the PCB.
