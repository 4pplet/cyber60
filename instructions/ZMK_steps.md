This is a short instruction on how to get started with building ZMK locally.. It's a work in progress, if you find it lacking, please do a PR with more info or create an issue with what you are missing. This is not a full instruction on how to edit and setup ZMK, for that, use the ZMK documentation: https://zmk.dev/docs

## 1: Fork the ZMK repo
Open this URL in a browser and press the fork button, this requires a GitHub account: https://github.com/4pplet/zmk
## 2: Get the code to your computer locally 
Clone the fork you just made so you have the files locally and can edit them. I'd recommend to use the github app. You can edit the files directly on GitHub, but it's harder to spot errors that way.
## 3: Make changes to the code and behavior
Make changes to your keymap or other behavior, note that you need to modify the files for the revision of the PCB that you use. If you are unsure, the revision is printed to the PCB. It's a letter and a number. The letter will indicate what revision you are on, for example B2 is revision B.
- Here is a good instruction on how to make keymap changes: https://zmk.dev/docs/features/keymaps
- The keymap files can be found in zmk -> app -> boards -> arm -> then the folder of the revision of the cyber60 you are using.
I'd recommend to use Visual studo code for this, but use a editor of your liking.
## 4: Install ZMK toolchain
4: Follow the instructions by ZMK to install the toolchain, I highly recommend to use the docker setup.
https://zmk.dev/docs/development/setup
## 5: Build ZMK 
4: In the terminal, navigate to the ZMK directory that was cloned from GitHub in step 2.
change folder to app:
cd app
build ZMK, replace the last letter depending on what revision you are building.
west build -p -b cyber60_rev_d
## 6: Locate the built .uf2
the file build will be called zmk.uf2 and located in zmk -> app -> build -> zephyr 
## 7: Set the PCB in reprogram mode (enter uf2 bootloader)
On the PCB, double click on the reset-button and it'll show up on your PC as a removable device.
## 8: Flash your edited firmware
To reflash the PCB, copy the generated zmk.uf2 file into the removable device (or drag drop) and the PCB will be re-flashed with your modified changes.
