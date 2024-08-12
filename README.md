# Nintendo Switch Jailbreak Tutorial

# What You Need

- Nintendo Switch V1
- MicroSD Card (at least 64GB is recommended)
- RCM Jig
- USB-C Cable
- PC/Laptop (or similar to edit data on an SD card)

![Required Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Card Preparation

*Important: You should only use Fat32 on a maximum partition of 64 GB, otherwise you won’t be able to write more data on it. Otherwise use exFAT, which you can format with a right-click under Windows on "Format". Under macOS and Linux, simply select exFAT as the file system in the following steps.*

## Windows

1. Download [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm).
2. Start "guiformat.exe".
3. Select your SD card (e.g., "D:").
4. Start the process to format your SD card.

## MacOS

1. Open "Disk Utility".
2. Right-click on the SD card and select "Erase". Format it as Fat32 (it may be shown as "MS-DOS File System").
3. Select "Erase" to confirm.

## Linux

1. Open the "Disk" app.
2. Select the drive, click on the gear icon or right-click and choose "Format".
3. Select "Fat32" as the type (you may need to look under "Other" for Fat32).

# Check Serial Number

Make sure your Switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- You can see your serial number on the back of your Switch, which you can enter.
  If you don’t see the serial number there, go to "System Settings", then "Console", and then "Serial Number" to see it there.

- An unpatched Switch means you can hack your Switch 100% with this method. If it doesn’t work later, YOU did something wrong.

- If you have a Possible Patched Switch, the payload might work, but it might not. You can tell if you see the “RCM OK” window in TegraRCM and the Switch remains black when you insert the payload.

- If you have a Patched Switch, it will definitely NOT work. You will need a modchip, which you will need to solder into the Switch, which involves advanced knowledge and risk. If you install a modchip, you only need an SD card with the data from the "Clean RCM Pack". But only Switch V1 will work with the data, so unpatched Switches. For other models (Switch V2, OLED, or LITE) you will need different data.

# SD Card Setup

1. Power off the Switch by holding the "Power Button" for 3 seconds and selecting "Power Options" then "Power Off".

![Power Off Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Download the Clean RCM Pack [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/)
3. Drag all data to the root directory of the SD card.

![SD Card Files](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# Prepare and Start RCM Mode

1. Insert the RCM Jig into the right Joy-Con slot until it fits correctly.
2. Hold the Volume Up button and the Power Button to activate RCM mode (first hold the Volume button and then the Power button).

![RCM Jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Inject Payload

1. Download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Connect the Switch in RCM mode to your PC via the USB-C cable.
3. Open TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Go to "Tools" and select "Install Driver" to install the APX drivers so your PC can recognize the Switch. (A green field should appear with "RCM OK", which means the Switch is successfully in RCM mode and recognized by your PC.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

You can also enable "Run App at startup", "Minimize to Tray", and "Auto Inject Payload" under "Tools" so the payload is automatically sent when you connect your Switch with the USB-C cable.

5. Open TegraRcmGUI and double-click the file "hekate_ctcaer_5.0.0.bin" (or select it manually and choose "Inject Payload"). Your Switch should now boot into Hekate.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Configure Hekate

## Partition SD Card and Create emuMMC

1. In Hekate, select `Tools`.
2. Then select `Partition SD`.
3. For `emuMMC`, select the bar to "29 Full", so your system will be completely copied to a new, separate partition. (Keep it separate because it runs more stable and provides extreme security, as you don’t brick your "Main" Switch directly. Also, it is safer to play online since you haven’t installed any homebrew apps or similar on the SysNAND, which might be detected by Nintendo and result in a ban.)
4. You can also create a partition for Android and Linux if you want to install them.
5. Then go to `Next Step` and then `Start` and confirm everything to proceed. The SD card will be partitioned.
6. Go back to `Create emuMMC`, then `SD Partition` and select Part 1. (If you have multiple partitions, you have selected "29 FULL" and created 2 partitions or your SD card already had 2 partitions from the beginning.)

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## NAND Backup

1. Go to Tools at the top.
2. Select `Backup eMMC`.
3. Select the option on the left `eMMC BOOT0 & BOOT1` and wait until it finishes.
4. Then select `eMMC RAW GPP` below and wait until it finishes (this process takes an average of 10-15 minutes depending on the amount of data on your Switch).
5. Power off the Switch and take the SD card to your PC.
6. Copy all backed-up data to a folder on your PC (you may only have a "rawnand.bin". Sometimes the files are split).
7. Delete these files from your SD card.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND Backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## Restore NAND

1. Copy the backed-up files and place them in `restore` then `emummc` on the SD card.
2. When you are in Hekate, you can select "Restore eMMC" under Tools.
3. Select `eMMC BOOT0 & BOOT1` and `eMMC RAW GPP` to restore the NAND.

## If you want to install Linux or Android:

1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-11/) (then select the latest `Switchroot Ubuntu.7z` or `Switchroot Android.7z`) and copy all folders to the root directory of your SD card.
2. In Hekate, under "Tools" select "Partition SD" and then choose "Flash Linux" or "Flash Android" (this will flash the files to the created Linux or Android partition).

## Always Start in RCM Mode

1. In Hekate, go back to Tools.
2. Go to the second page on the bottom right with "Arch Bit - RCM - Touch - Pkg1/2".
3. Select AutoRCM at the very top right. (Auto RCM is not recommended, as you can only restart your Switch after turning it off by loading a custom payload.)

## Configure Auto Boot

1. Go to "Options" at the top right and select "Auto Boot" and ideally choose "Atmosphere (EmuNAND)".
2. You can also disable the Boot Logo in the option below (to return to the Hekate menu, hold down the Volume Down button and send the payload until you boot into Hekate).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# Load CFW Atmosphere

1. In Hekate, under Home select "Launch" and choose "Atmosphere (EmuNAND)" to boot into it.

# Load Homebrew

   - You can start the Homebrew Menu via the Album or hold R and start a legitimate game to run Homebrew with admin rights and start your installed apps.
   - You can also download and install new apps via the Homebrew Appstore.

# Avoid Switch Ban

1. Go to the Album in the CFW to open Homebrew and select "90dns setter".
2. Press "X" to set the DNS settings for any internet and select "Y" to restart.
3. In the Homebrew Menu, select "90dns testing utility" and check if Nintendo services are blocked.
4. You can also go to System Settings and turn off "Send Error Reports" (ideally also in SysNAND or Stock Mode).

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# Optional NSPs/XCI Files Installation

1. Open "DBI" in the Homebrew Menu.
2. Go to "Browse SD" and select the files you want to install.
3. When you have selected the files, install them to the *"IMPORTANT":* SD card and NOT to the NAND, as you might receive a potential ban later. If you want, you can delete the file afterwards as you won’t need it anymore.

# **IMPORTANT!!!**

DO NOT PLAY ONLINE, DO NOT DOWNLOAD UPDATES, AND DO NOT INTERACT WITH NINTENDO SERVERS SUCH AS NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OTHERWISE YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE COMPLETELY BANNED. TO PREVENT ACCESS TO NINTENDO SERVERS IN CFW, FOLLOW THE STEP ABOVE THIS TEXT.

PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY; PURCHASE ALL GAMES LEGALLY BY BUYING THEM. ALL GAMES I PLAY, I OWN LEGALLY AND HAVE ACQUIRED THEM LEGALLY.
I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE ENCOURAGED TO OWN AND PLAY GAMES ILLEGALLY.
