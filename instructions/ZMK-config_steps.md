This is a short instruction on how to get started with editing the ZMK-config files and the usual steps required to flash the PCB. It's a work in progress, if you find it lacking, please do a PR with more info or create an issue with what you are missing. This is not a full instruction on how to edit and setup ZMK, for that, use the ZMK documentation: https://zmk.dev/docs

## 0: (prerequisite) for github
Create a github account and log in to it.
## 1: Fork the ZMK-config repo
Open this URL in a browser and press the fork button, this requires a GitHub account: https://github.com/4pplet/zmk-config-4pplet
## 2: Get the code to your computer locally 
Clone the fork you just made so you have the files locally and can edit them. I'd recommend to use the github app. You can edit the files directly on GitHub, but it's harder to spot errors that way.
## 3: Make changes to the code and behavior
Make changes to your keymap or other behavior, note that you need to modify the files for the revision of the PCB that you use. If you are unsure, the revision is printed to the PCB. It's a letter and a number. The letter will indicate what revision you are on, for example B2 is revision B.
- Here is a good instruction on how to make keymap changes: https://zmk.dev/docs/features/keymaps
- The keymap files can be found in zmk-config -> config -> boards -> arm -> then the folder of the revision of the cyber60 you are using.
I'd recommend to use Visual studo code for this, but use a editor of your liking.
## 4: Push the code to GitHub
4: Push the code to your fork on GitHub
- The firmware will now build using GitHub actions and be available as a artifact called "firmware"
## 5: Locate the build in GitHub actions
Open the github actions tab and click on your commit
- If the changes you made are correct/working, there should be green check marks.
## 6: Download firmware
In the "Artifacts section", click firmware and you'll download a zip-file containing the compiled firmware.
## 7: Unpack the zip
Unpack this zip-file and you'll have the built firmware for all the different revisions. Note that you need to use the one built for the revision you edited.
## 8: Set the PCB in reprogram mode (enter uf2 bootloader)
To flash the built firmware, the PB needs to be put in reprogram/bootloader mode. With the default keymap, this can be done by pressing Fn + CapsLock. Alternatively, you can double click on the reset button on the PCB. When the keyboard enters this mode, key input will no longer work and a U2F removable device will show up on your PC.
## 9: Flash your edited firmware
To reflash the PCB, copy the generated .uf2 file from the unpacked .zip file into the removable device (or drag drop) and the PCB will be re-flashed with your modified changes.

You can also use the keymap-editor in your browser to edit the zmk-config files. You can read about how to use it here: [Link](./instructions/ZMK_keymap-editor.md)
