# Cyber60 Bootloader Flash Instructions

I recommend using a **J-Link** programmer to flash the bootloader. If you want to use another programmer, I suggest checking out Joric’s wiki for instructions:  
https://github.com/joric/nrfmicro/wiki/Bootloader

---

## TL;DR:
- Follow **Step 2** in this guide:  
  https://learn.adafruit.com/bluefruit-nrf52-feather-learning-guide/flashing-the-bootloader
- **BUT** use the bootloader from here instead:  
  https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases

If your PCB already has the bootloader flashed (either from the factory or previously), you can update it by dragging the **UF2 update file** from the release.  
Be sure to use the correct update file for your **PCB revision**.

---

## Mac / Linux:

1. Install `nrfjprog` (via [nRF Command Line Tools](https://www.nordicsemi.com/Products/Development-tools/nRF-Command-Line-Tools/Download))
2. Download the bootloader (`.hex` file):  
   https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases  
   Make sure it matches your Cyber60 revision.  
   Revisions **A** and **B** use the same bootloader.  
   Look for the letter under the "cyber60" name on the PCB.
3. Open a terminal and navigate to the bootloader directory.
4. Connect power to the PCB (USB or battery), and connect your programmer (via tag-connect or 2.54 header).
5. Flash using:
   ```bash
   nrfjprog --program [bootloader_name].hex --chiperase -f nrf52 --verify --reset
   ```
6. If you get a "device is locked" error:
   ```bash
   nrfjprog --recover
   ```
   Then retry the flashing command.

### Expected success output:
```
[ #################### ]   0.218s | Erase file - Done erasing
[ #################### ]   1.293s | Program file - Done programming
[ #################### ]   1.337s | Verify file - Done verifying
Applying system reset.
Run.
```

7. If successful, your PCB should show up as a USB drive named `CYBER_<Revision>`.  
   If it doesn’t, try:
   - Unplugging and replugging USB + battery  
   - Double-clicking the reset button to enter bootloader mode

---

## Windows:

1. Install [nRF Command Line Tools](https://www.nordicsemi.com/Products/Development-tools/nrf-command-line-tools/download)
2. Install [J-Link drivers](https://www.segger.com/downloads/jlink/)
3. Download the appropriate bootloader `.hex` file from:  
   https://github.com/4pplet/Adafruit_nRF52_Bootloader/releases  
   Again: use the version that matches your PCB revision.
4. Either:
   - Copy the bootloader to your `nrf-command-line-tools` folder (e.g. `C:\Program Files (x86)\Nordic Semiconductor\nrf-command-line-tools\bin\`)  
   - OR copy `nrfjprog.exe` into the folder where the `.hex` file is
5. Open Command Prompt
6. Navigate to the correct directory
7. Connect USB/power to the PCB and attach your programmer
8. Run:
   ```cmd
   nrfjprog.exe --program [bootloader_name].hex --chiperase -f nrf52 --verify --reset
   ```
9. If you get a "device is locked" error:
   ```cmd
   nrfjprog.exe --recover
   ```
   Then retry the flashing command.

### Expected success output:
```
[ #################### ]   0.218s | Erase file - Done erasing
[ #################### ]   1.293s | Program file - Done programming
[ #################### ]   1.337s | Verify file - Done verifying
Applying system reset.
Run.
```

10. If all goes well, you should see a removable device named `CYBER_<Revision>`.  
    If not:
    - Unplug USB and battery, then reconnect
    - Double-tap the reset button to enter bootloader mode
