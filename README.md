# Nintendo Switch Jailbreak Tutorial

# What You Need

- Nintendo Switch V1
- MicroSD card (at least 64GB recommended)
- RCM Jig
- USB-C cable
- PC/Laptop (or similar to edit data on an SD card)

![Required Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Card Preparation

*Important: Only use Fat32 with a maximum partition of 64 GB, as you cannot write more data to it otherwise. Otherwise, use exFAT, which you can format with a right-click in Windows on "Format". On macOS and Linux, simply choose exFAT as the file system in the following steps.*

## Windows

1. Download [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm).
2. Run "guiformat.exe".
3. Select your SD card (e.g., "D:").
4. Start the process to format your SD card.

## MacOS

1. Open "Disk Utility".
2. Right-click on the SD card and select "Erase". Format it as Fat32 (it may be listed as "MS-DOS File System").
3. Click "Erase" to confirm.

## Linux

1. Open the "Disks" app.
2. Select the disk, click on the gear icon or right-click and choose "Format".
3. Choose "Fat32" as the type (you might need to look for Fat32 under "Other" or "More").

# Check Serial Number

Ensure your Switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- You can find your serial number on your Switch, which you can enter.
  If you don't have the serial number there, go to "System Settings", then "Console", and then "Serial Number" to see it.

- An unpatched Switch means you can 100% hack your Switch with this method. If it doesn't work later, YOU did something wrong.

- If you have a Possible Patched Switch, the payload might work or it might not. You can tell if you see "RCM OK" in TegraRCM and the Switch stays black when you insert the payload.

- If you have a Patched Switch, it WILL NOT work 100%. You will need a modchip, which you will solder into the Switch, involving advanced knowledge and risk. If you install a modchip, you only need an SD card with the "Clean RCM Pack" data. But only Switch V1 will work with this data, so unpatched Switches. For other models (Switch V2, OLED, or LITE) you will need different data.

# SD Card Setup

1. Power off the Switch by holding the "Power Button" for 3 seconds and selecting "Power Options" and then "Power Off".

![Power Off Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Download the Clean RCM Pack [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/)
3. Copy all data to the root directory of the SD card.

![SD Card Files](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# Prepare and Enter RCM Mode

   1. Insert the RCM Jig into the right Joy-Con slot until it fits properly.
   2. Hold the Volume Up button and the Power button to activate RCM mode (hold the Volume Up button first and then the Power button).

![RCM jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Inject Payload

1. Download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Connect the Switch in RCM mode to your PC via the USB-C cable.
3. Open TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Go to "Tools" and click "Install Driver" to install the APX drivers so your PC can recognize the Switch. (A green field should appear with "RCM OK", meaning the Switch is successfully in RCM mode and recognized by your PC.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

You can also enable "Run App at startup", "Minimize to Tray", and "Auto Inject Payload" under "Tools" so the payload is automatically sent when you connect your Switch with the USB-C cable.

5. Open TegraRcmGUI and double-click the file "hekate_ctcaer_5.0.0.bin" (or select it manually and choose "Inject Payload"). Your Switch should now boot into Hekate.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Configure Hekate

## Partition SD Card and Create emuMMC

1. Select `Tools` in Hekate.
2. Then choose `Partition SD` (You may need to copy the downloaded data back to your SD card IF you downloaded a larger pack, as partitioning will delete everything from your SD card and only up to 1 GB of data can be backed up.)
3. For `emuMMC`, set the bars to "29 Full", so your system is completely copied to a new, separate partition. (It runs separately because it is more stable and provides extreme safety, as you do not brick your "Main" Switch directly. Also, it is safer to play online as you have not installed homebrew apps or similar on the SysNAND which might be detected by Nintendo and result in a ban.)
4. You can also create a partition for Android and Linux if you want to install them.
5. Go to `Next Step` and then `Start` and confirm everything to proceed. The SD card will be partitioned.
6. Then go to `Create emuMMC` and then `SD Partition` and select Part 1. (If you have multiple partitions, you selected "29 FULL" and created 2 partitions or your SD card originally had 2 partitions.)

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## Backup NAND

1. Go to Tools at the top.
2. Select `Backup eMMC`.
3. If you want, you can enable the option `SD emuMMC Raw Partition` (I leave it out here).
4. Choose the option on the left `eMMC BOOT0 & BOOT1` and wait until it finishes.
5. Then choose `eMMC RAW GPP` below and wait until it finishes (this process takes about 10-15 minutes, depending on the amount of data on your Switch.)
6. Power off the Switch and take the SD card to your PC.
7. Copy all backed-up data to a folder on your PC (there should be 15 rawnand.bin files on the SD card (0-14) and the BOOT0 and BOOT1.bin files).
8. Delete these files from your SD card.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## Restore NAND

1. Copy the backed-up files and place them in `restore` then `emummc` on the SD card.
2. When you are in Hekate, you can select "Restore eMMC" under Tools.
3. Choose `eMMC BOOT0 & BOOT1` and `eMMC RAW GPP` to restore NAND.

## If you want to install Linux or Android:

1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-11/) (then select the current `Switchroot Ubuntu.7z` or `Switchroot Android.7z`) and copy the folders `switchroot` and `bootloader` to your SD card.
2. In Hekate, go to "Tools", select "Partition SD", and then choose "Flash Linux" or "Flash Android" (this will flash the files to the created Linux or Android partition).

If you don't have the partitions yet, back up your SD card data and repartition your SD card (partitioning will delete all data except for the bootloader data, or up to 1 GB of data can be backed up).

## Always Start in RCM Mode

1. In Hekate, go back to Tools.
2. Go to the second page on the bottom right with "Arch Bit - RCM - Touch - Pkg1/2".
3. And select AutoRCM at the top right. (Auto RCM is not recommended because you can only restart your Switch by loading a custom payload after turning it off.)

## Configure Auto Boot

1. Go to "Options" in the top right and select "Auto Boot" and ideally choose "Atmosphere (EmuNAND)".
2. You can also disable the Boot Logo in the option below (to return to the Hekate menu, hold down the Volume Down button and then send the payload until you boot into Hekate).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# Load CFW Atmosphere

1. In Hekate, under Home, select "Launch" and choose "Atmosphere (EmuNAND)" to boot into it.

# Load Homebrew

   - You can start the Homebrew menu via the Album or hold R and start a legitimate game to run Homebrew with admin rights and start your installed apps.
   - You can also download and install new apps through the Homebrew Appstore.

# Avoiding Switch Ban

1. Go to the Album in CFW to open Homebrew and select "90dns setter".
2. Press "X" to set DNS settings for every network and select "Y" to restart.
3. Then choose "90dns testing utility" in the Homebrew menu and check if Nintendo services are blocked.
4. You can also go to "System Settings" under "Console" and turn off "Send Error Information" (ideally also in SysNAND or stock mode).

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# **IMPORTANT!!!**

DO NOT PLAY ONLINE, DO NOT DOWNLOAD UPDATES, AND DO NOT INTERACT WITH NINTENDO SERVERS LIKE NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OR YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE COMPLETELY BANNED. TO PREVENT ACCESS TO NINTENDO SERVERS IN CFW, FOLLOW THE STEP ABOVE THIS TEXT.

PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY AND PURCHASE ALL GAMES LEGALLY BY BUYING THEM. I OWN ALL THE GAMES I PLAY AND HAVE PURCHASED THEM LEGALLY. I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE TEMPTED TO POSSESS AND PLAY GAMES ILLEGALLY.
