# Nintendo Switch Jailbreak Tutorial

# *THIS IS ONLY A PURE ENGLISH TRANSLATION; THERE MAY BE ERRORS IN THE TEXT AS A RESULT. THE ORIGINAL TEXT WAS WRITTEN IN GERMAN.*

# What you need

- Nintendo Switch V1
- microSD card (at least 64GB is recommended)
- RCM Jig
- USB-C cable
- PC/laptop (or similar to edit data on an SD card)

# SD Card Preparation

*Important: You should only use Fat32 on a maximum partition size of 64 GB, as you won't be able to write more data to it otherwise. Alternatively, use exFAT, which you can format by right-clicking and selecting "Format" in Windows. On macOS and Linux, simply choose exFAT as the file system in the following steps.*

## Windows

1. Download [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm).
2. Run "guiformat.exe".
3. Select your SD card (e.g., "D:").
4. If your SD card is 32 GB or larger, select "32768" for "allocated unit size" so that the 3DS can recognize the SD card. (Some SD cards, especially older ones, might still not be recognized if they are larger than 32 GB.)

## MacOS

1. Open "Disk Utility".
2. Right-click on the SD card and select "Erase". Format it as Fat32 (it may be listed as "MS-DOS (FAT)").
3. Click "Erase" to proceed.

## Linux

1. Open the "Disk" app.
2. Select the drive, click on the gear icon or right-click and choose "Format".
3. Select "Fat32" as the file system type (you may need to go to "Other" or "More" to find Fat32).

# Check Serial Number

Ensure that your Switch can be jailbroken. Use [IsMySwitchPatched](https://ismyswitchpatched.com/).

- You can find your serial number on a sticker under your Switch, which you can enter on the website. If you don't have the serial number there, go to System Settings, then "Console," and then "Serial Number" to view it.

- An unpatched Switch means that you can 100% hack your Switch using this method. If it doesn't work later, you have made a mistake.

- If you have a possibly patched Switch, the payload might work, but it might not. You can tell by checking if you get the "RCM OK" message in TegraRCM and if the Switch stays black when you insert the payload.

- If you have a patched Switch, it will 100% NOT work. You will need a modchip that you solder into the Switch, which involves advanced knowledge and risk. If you install a modchip, you only need an SD card with the data from the "Clean RCM Pack". However, only Switch V1 will work with this data, meaning unpatched Switches. For other models (Switch V2, OLED, or LITE), you will need different data.

# SD Card Setup

   1. turn off the Switch by holding down the power button for 3 seconds and selecting "Power Off" under Power options
   2. Download the Clean RCM Pack from [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/).
   3. Copy all the data to the root directory of the SD card.

# Prepare and start RCM mode

   2. slide the RCM Jig into the right Joy-Con slot until it is properly seated
   3. press and hold the volume up button and the power button to activate RCM mode (first press and hold the volume up button and then the power button).

# Inject Payload

1. Download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Connect the Switch in RCM mode to your PC using the USB-C cable.
3. Go to "Tools" and select "Install Driver" to install the APX drivers so that your PC can recognize the Switch. (A green field should appear with "RCM OK," indicating that the Switch is successfully in RCM mode and recognized by your PC.)
4. Open TegraRcmGUI and double-click the file "hekate_ctcaer_5.0.0.bin" (or manually select it and choose "Inject Payload").

You can also enable "Auto Boot at startup," "Minimize to Tray," and "Auto Inject Payload" under "Tools" so that the payload is automatically sent whenever you connect your Switch with the USB-C cable.

# Configure Hekate

## Partition SD card and create emuMMC

1. select `emuMMC` in Hekate.
2. then go to `Create emuMMC`.
3. select `SD Partition`.
4. then click on Continue and then on OK.
5. select the bars for 'emuMMC' to Full so that your system is completely copied to it (since CFW runs separately from the normal system).
6. you can also reserve memory for Android and Linux if you want to install that.
7. then go to `Next Step` and then `Start` and confirm everything else to continue. The SD card will be partitioned.
8. go to `Create emuMMC` again and then to `SD Partition` and select Part 1. (if you can select multiple parts, select them all one after another. The process may take about 10-15 minutes per part.)

## Backup the NAND

1. then go to Tools at the top right.
2. then select `Backup eMMC`.
3. if you want, you can turn on the option with `SD emuMMC Raw Partition` (I leave it off here).
4. then select the option on the left `eMMC BOOT0 & BOOT1` and wait until it is ready.
5. then select 'eMMC RAW GPP' underneath and wait for it to finish (this will take a different amount of time depending on the amount of data on your system).
6. then turn off the switch and connect the SD card to your PC.
7. copy all the backed up data into a folder (there should be 15 rawnand.bin files on the SD card and the BOOT0 and BOOT1 files).
8. then delete these files from your SD card.

## Restoring the NAND

1. copy the backed up files and put them into `restore` then `emummc` on the SD card.
2. when you are in Hekate, you can select "Restore eMMC" under Tools.
3. then select `eMMC BOOT0 & BOOT1` and `eMMC RAW GPP` to perform the restore.

## If you want to install Linux or Android:

1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-11/) (then choose the latest `Switchroot Ubuntu.7z` or `Switchroot Android.7z`) and copy the `switchroot` and `bootloader` folders to your SD card.
2. In Hekate, after partitioning your SD card, go to "Tools" and select "Partition SD," then choose "Flash Linux" or "Flash Android" (this will flash the files onto the created Linux or Android partition).

If you don't have the partitions yet, back up the data on your SD card and repartition your SD card (partitioning will delete all data except for the bootloader data, or up to 1 GB of data can be backed up).

## Always start in RCM mode

1. go back to Tools in Hekate.
2. then go to the bottom right to something with "Arch Bit - RCM".
3. and select AutoRCM at the top right.

## Configure Auto Boot

1. Go to "Options" in the top right and select "Auto Boot". Choose "Atmosphere (EmuNAND)" if possible.
2. You can also disable the boot logo in the option below. To return to the Hekate menu, hold down the volume down button and send the payload until Hekate starts.

# Loading CFW Atmosphere

1. go to "Launch" in Hekate under Home and select "Atmosphere (EmuNAND)" to boot into it.

# Load Homebrew

   - You can start Homebrew through the album, or you can hold down R and start a legitime game to launch Homebrew with admin rights and open an app from there.
   - You can also download and use new apps from the Homebrew App Store.

# Avoid switch bans

1. Go to the Album in the CFW to open Homebrew and select "90dns setter."
2. Press "X" to configure the DNS settings for each network, and select "Y" to restart.
3. In the Homebrew menu, select "90dns testing utility" and check if the Nintendo services have been blocked.
4. 4. You can also go to "Console" under System Settings and turn off the "Send Error Reports" option (ideally also in SysNand or Stock Mode).

# **IMPORTANT!!!**

DO NOT PLAY ONLINE, DO NOT DOWNLOAD UPDATES AND GENERALLY DO NOT INTERACT WITH NINTENDO SERVERS SUCH AS NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OTHERWISE YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE BANNED COMPLETELY. TO PREVENT ACCESS TO THE NINTENDO SERVERS IN CFW, FOLLOW THE STEP ABOVE THIS TEXT.

PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY. BUY ALL GAMES LEGALLY YOURSELF. ALL GAMES THAT I PLAY, I OWN AND HAVE PURCHASED LEGALLY.
I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE ENCOURAGED TO OWN AND PLAY GAMES ILLEGALLY.
