# Nintendo Switch Jailbreak Totorial

# What you need

- Nintendo Switch V1
- microSD card (at least 64GB is recommended)
- RCM Jig
- USB-C cable
- PC/laptop (or similar to edit data on an SD card)

# SD card preparation

- Insert your SD card into your Switch
- Go to the system settings and then to "Console"
- Scroll all the way down to "Formatting Options" and select "Format SD card". Confirm with "Format"

# Check serial number

Make sure your switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

# SD Card Setup

1. Download the Clean RCM Pack from [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/).
2. Copy all the data to the root directory of the SD card.

# Prepare and start RCM mode

   1. turn off the Switch by holding down the power button for 3 seconds and selecting "Power Off" under Power options
   2. slide the RCM Jig into the right Joy-Con slot until it is properly seated
   3. press and hold the volume up button and the power button to activate RCM mode (first press and hold the volume up button and then the power button).

# Insert payload

   1. download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
   2. connect the Switch in RCM mode to your PC via the USB-C cable
   3. open TegraRcmGUI and select the Hekate payload file (it should be a ".bin" file).

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
1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-11/) (then select the latest `Switchroot Ubuntu.7z` or `Switchroot Android.7z`) and transfer the `switchroot` and `bootloader` folders to your SD card.

2. then go to Hekate after formatting your SD card (as in the previous step), and then select "Flash Linux" (you should still be in the formatting step, so you should not have closed the window, otherwise you just reformat everything) to install Linux (your SwitchOS will not be overwritten).
You can also select "SD UMS" to edit your SD card on the PC without removing it from your Switch.

## Always start in RCM mode

1. go back to Tools in Hekate.
2. then go to the bottom right to something with "Arch Bit - RCM".
3. and select AutoRCM at the top right.

## Configure Auto Boot

1. Go to "Options" in the top right and select "Auto Boot". Choose "Atmosphere (EmuNAND)" if possible.
2. You can also disable the boot logo in the option below. To return to the Hekate menu, hold down the volume down button and send the payload until Hekate starts.

# Loading CFW Atmosphere

1. go to "Launch" in Hekate under Home and select "Atmosphere emuMMC" to boot into it.

# Load Homebrew

   - You can start Homebrew through the album, or you can hold down R and start a legitime game to launch Homebrew with admin rights and open an app from there.
   - You can also download and use new apps from the Homebrew App Store.

# Avoid switch ban (as good as possible)

 1. Go to the Album in the CFW to open Homebrew and select "90dns setter."
2. Press "X" to configure the DNS settings for each network, and select "Y" to restart.
3. In the Homebrew menu, select "90dns testing utility" and check if the Nintendo services have been blocked.

# **IMPORTANT!!!**

DO NOT PLAY ONLINE, DO NOT DOWNLOAD UPDATES AND GENERALLY DO NOT INTERACT WITH NINTENDO SERVERS SUCH AS NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OTHERWISE YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE BANNED COMPLETELY. TO PREVENT ACCESS TO THE NINTENDO SERVERS IN CFW, FOLLOW THE STEP ABOVE THIS TEXT.

PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY. BUY ALL GAMES LEGALLY YOURSELF. ALL GAMES THAT I PLAY, I OWN AND HAVE PURCHASED LEGALLY.
I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE ENCOURAGED TO OWN AND PLAY GAMES ILLEGALLY.
