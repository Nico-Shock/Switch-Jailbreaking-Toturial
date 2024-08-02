# Nintendo Switch Jailbreak Tutorial

# What You Need

- Nintendo Switch V1
- microSD card (at least 64GB recommended)
- RCM Jig
- USB-C cable
- PC/Laptop (or similar to manage data on an SD card)

![Required Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Card Preparation

*Important: You should only use Fat32 on a maximum partition of 64 GB, as otherwise, you won't be able to write more data to it. Otherwise, use exFAT, which you can format with a right-click on "Format" under Windows. On macOS and Linux, just select exFAT as the file system in the following steps below.*

## Windows

1. Download [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm).
2. Run "guiformat.exe".
3. Select your SD card (e.g., "D:").
4. If your SD card is 32 GB or larger, select "32768" for "allocated unit size" so that the 3DS can recognize the SD card. (Some SD cards, especially older ones, may still not be recognized if they are larger than 32 GB.)

## MacOS

1. Open "Disk Utility".
2. Right-click on the SD card and select "Erase". Format it as Fat32 (it may appear as "MS-DOS File System").
3. Then select "Erase".

## Linux

1. Open the "Disk" app.
2. Select the drive, click on the gear icon or right-click and choose "Format".
3. Select "Fat32" as the type (you may need to look under "Other" for Fat32).

# Check Serial Number

Make sure your Switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- You can see your serial number on a sticker under your Switch that you can enter.
  If you don't have the serial number there, go to System Settings, then "Console", and then "Serial Number" to view it.

- Unpatched Switch means you can 100% hack your Switch with this method. If it doesn't work later, you did something wrong.

- If you have a Possible Patched Switch, the payload might work, but it might not. You can tell if you see the "RCM OK" message in TegraRCM and if the Switch remains black when the payload is inserted.

- If you have a Patched Switch, it will NOT work 100%. You will definitely need a modchip that you solder into the Switch, which involves advanced knowledge and risk. If you install a modchip, you only need an SD card with the data from the “Clean RCM Pack”. But only Switch V1 will work with the data, so unpatched Switches. For other models (Switch V2, OLED, or LITE), you need different data.

# SD Card Setup

1. Turn off the Switch by holding the Power button for 3 seconds and selecting "Power Options" then "Power Off".

![Power Off Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Download the Clean RCM Pack [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/)
3. Copy all the data to the root directory of the SD card.

![SD Card Files](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# Prepare and Start RCM Mode

1. Insert the RCM Jig into the right Joy-Con slot until it is properly seated.
2. Hold the Volume Up button and the Power button to activate RCM mode (first hold the Volume Up button, then the Power button).

![RCM Jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Insert Payload

1. Download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Connect the Switch in RCM mode to your PC using the USB-C cable.
3. Open TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Go to "Tools" and select "Install Driver" to install the APX drivers so your PC can recognize the Switch. (A green field should appear with "RCM OK", meaning that the Switch is successfully in RCM mode and recognized by your PC.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

You can also enable "Auto Boot at startup", "Minimize to Tray", and "Auto Inject Payload" under "Tools" so that the payload is sent automatically as soon as you connect your Switch with the USB-C cable.

5. Open TegraRcmGUI and double-click the file "hekate_ctcaer_5.0.0.bin" (or select it manually and choose "Inject Payload"). Your Switch should now boot into Hekate.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Configure Hekate

## Partition SD Card and Create emuMMC

1. In Hekate, select `Tools`.
2. Then select `Partition SD` (You will need to copy the downloaded data back to your SD card if you downloaded a larger pack, as during partitioning, more than 1 GB of data cannot be backed up and everything on your SD card will be deleted.)
3. For `emuMMC`, choose the bars on "29 Full", so your system is fully copied to a new, separate partition. (It is kept separate because it runs more stably and offers extreme security, as you don't directly brick your "Main" Switch. Additionally, it is safer to play online if you boot in "Stock Mode".)
4. You can also create a partition for Android and Linux if you want to install them.
5. Then go to `Next Step` and then `Start`, and confirm everything to proceed. The SD card will be partitioned.
6. Then go to `Create emuMMC` and then `SD Partition`, and select Part 1 (if you can select multiple parts, choose all once. The process can take about 10-15 minutes per part.)

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## NAND Backup

1. Go to Tools at the top.
2. Then select `Backup eMMC`.
3. If you want, you can enable the option with `SD emuMMC Raw Partition` (I leave it out here).
4. Select `eMMC BOOT0 & BOOT1` on the left and wait until it is finished.
5. Then select `eMMC RAW GPP` below and wait until it is finished (this takes varying amounts of time depending on the amount of data on your system; average: 10-15 minutes).
6. Turn off the Switch and take the SD card to your PC.
7. Copy all the backed-up data into a folder on your PC (there should be 15 rawnand.bin files on the SD card (0-14) and the BOOT0 and BOOT1 files).
8. Then delete these files from your SD card.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND Backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## Restore NAND

1. Copy the backed-up files and place them in `restore` then `emummc` on the SD card.
2. When you are in Hekate, you can choose "Restore eMMC" under Tools.
3. Select `eMMC BOOT0 & BOOT1` and `eMMC RAW GPP` to restore NAND.

## If You Want to Install Linux or Android:

1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-11/) (then select the current `Switchroot Ubuntu.7z` or `Switchroot Android.7z`) and copy the `switchroot` and `bootloader` folders to your SD card.
2. Then in Hekate, under "Tools", select "Partition SD" and then choose "Flash Linux" or "Flash Android" (this will flash the files to the created Linux or Android partition).

If you don’t have the partitions yet, back up your SD card data and repartition your SD card (partitioning will delete all data except for bootloader data, or up to 1 GB of data can be backed up).

## Always Start in RCM Mode

1. In Hekate, go back to Tools.
2. Then go to the bottom right and select anything with "Arch Bit - RCM".
3. And select AutoRCM at the top right. (Auto RCM is not recommended as you will only be able to restart your Switch after turning it off by loading a custom payload.)

## Configure Auto Boot

1. Go to "Options" in the top right and select "Auto Boot", and ideally choose "Atmosphere (EmuNAND)".
2. You can also turn off the Boot Logo in the option below (to return to the Hekate menu, hold the Volume Down button and send the payload until you boot into Hekate).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# Load CFW Atmosphere

1. In Hekate, go to Home, select "Launch", and choose "Atmosphere (EmuNAND)" to boot into it.

# Load Homebrew

   - You can start Homebrew via the Album or hold R and start a legitimate game to launch Homebrew with admin rights and open an app from there.
   - You can also download and use new apps via the Homebrew App Store.

# Avoid Switch Ban

1. Go to the Album in the CFW to open Homebrew, and select "90dns setter".
2. Press "X" to set the DNS settings for all internet connections and choose "Y" to restart.
3. In the Homebrew menu, select "90dns testing utility" to check if Nintendo services are blocked.
4. You can also go to System Settings, select "Console", and turn off the "Send Error Reports" option (ideally also in SysNand or Stock Mode).

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# **IMPORTANT!!!**

DO NOT PLAY ONLINE, DO NOT DOWNLOAD UPDATES, AND DO NOT INTERACT WITH NINTENDO SERVERS SUCH AS NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OTHERWISE YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE COMPLETELY BANNED. TO PREVENT ACCESS TO NINTENDO SERVERS IN CFW, FOLLOW THE STEP ABOVE THIS TEXT.

PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY. PURCHASE ALL GAMES LEGALLY BY BUYING THEM. ALL GAMES I PLAY, I OWN AND HAVE LEGALLY ACQUIRED. I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE TEMPTED TO OWN AND PLAY GAMES ILLEGALLY.
