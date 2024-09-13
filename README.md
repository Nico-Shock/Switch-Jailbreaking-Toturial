# Nintendo Switch Jailbreak Tutorial

*This is just a pure English translation. Some things might come across as a bit awkward since it was translated with ChatGPT.*

# What You Need

- Nintendo Switch V1
- MicroSD Card (at least 64GB)
- RCM Jig
- USB-C Cable
- PC/Laptop (or another device to edit data on an SD card)

![Required Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Card Preparation

Important: You should only use FAT32 on a maximum partition of 64 GB, as you won't be able to write more data otherwise. Use exFAT otherwise, which you can format normally via Windows Explorer. In macOS and Linux, select exFAT instead of FAT32 in the steps below as the file system.

## Windows

1. Download [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm).
2. Run "guiformat.exe".
3. Select your SD card (e.g., "D:").
4. Start the process to format your SD card.

## macOS

1. Open "Disk Utility".
2. Right-click on the SD card and select "Erase". Format it as FAT32 (it might be shown as "MS-DOS File System").
3. Click "Erase".

## Linux

1. Open the "Disks" app.
2. Select the disk, then click on the gear icon or right-click and choose "Format".
3. Select "FAT32" as the type (you might need to look for FAT32 under "Other").

# Check Serial Number

Ensure that your Switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- You can find your serial number under your Switch, which you can enter.
  If you don't have the serial number there, go to "System Settings", then "Console", and then "Serial Number", where you can see it.

- An unpatched Switch means that you can 100% hack your Switch with this method. If it doesn't work later, YOU did something wrong.

- If you have a Possible Patched Switch, the payload might work, but it might not. You can tell by seeing "RCM OK" in TegraRCM and if the Switch remains black when you inject the payload.

- If you have a patched Switch, it will 100% NOT work. You will definitely need a modchip, which involves micro-soldering and delicate hardware, which is risky and requires advanced knowledge.

# SD Card Setup

1. Turn off the Switch by holding the "Power Button" for 3 seconds and selecting "Power Options" then "Turn Off".

![Turn Off Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Download the [Grey-NX Pack](https://github.com/Nico-Shock/Grey-NX-Pack).
3. Drag all data to the root directory of the SD card.

![SD Card Files](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# Prepare and Start RCM Mode

1. Insert the RCM Jig into the right Joy-Con slot until it fits properly.
2. Hold the Volume Up button and the Power button to activate RCM mode (first hold the Volume button and then the Power button).

![RCM Jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Inject Payload

1. Download TegraRcmGUI [here](https://github.com/eliboa/TegraRcmGUI/releases/latest).
2. Connect the Switch in RCM mode to your PC via the USB-C cable.
3. Open TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Go to "Tools" and select "Install Driver" to install the APX drivers so your PC can recognize the Switch. (A green field should appear with "RCM OK", which means the Switch is successfully in RCM mode and recognized by your PC.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

You can also enable "Run App at Startup", "Minimize to Tray", and "Auto Inject Payload" under "Tools" to automatically send the payload or start the app automatically when booting.

5. Open TegraRcmGUI and double-click the file "hekate_ctcaer_5.0.0.bin" or newer (or select it manually via the small folder icon and click "Inject Payload"). Your Switch should now boot into Hekate.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Configure Hekate

## Partition SD Card and Create emuMMC

1. In Hekate, select `Tools`.
2. Then select `Partition SD`.
3. Choose the bar for `emuMMC` to "29 Full" so your system is fully copied to a new, separate partition. (You can also create a partition for Android and Linux if you want to install those.)
4. Go to `Next Step`, then `Start`, and confirm everything else to proceed with partitioning the SD card.
5. Then go to `Create emuMMC` and select `SD Partition` and choose Part 1. (If you have multiple partitions, you selected "29 FULL" and created 2 partitions or your SD card originally had 2 partitions.)

Creating an emuMMC partition is safer because the "Switch OS" runs separately, which protects it from bricks and minimizes the likelihood of getting banned.

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## NAND Backup

1. Go to "Tools" at the top.
2. Select "Backup eMMC". (You will find an option called "SD emuMMC Raw Partition". If you enable this, the NAND will be backed up from the emuNAND instead of the SysNAND, which is usually not necessary.)
3. Select the option on the left "eMMC BOOT0 & BOOT1" and wait until it's done.
4. Then select "eMMC RAW GPP" below and wait until it's done (this process typically takes 10-15 minutes, depending on the amount of data on your Switch).
5. Turn off the Switch and take the SD card to your PC.
6. Copy all backed-up data to a folder on your PC (you might only have a "rawnand.bin". Sometimes the files are split.).
7. Then delete these files from your SD card.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND Backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## NAND Restoration

1. Copy the previously backed-up files to your SD card into the "backup" folder under "restore" if you want to restore your SysNAND. For EmuNAND, you need to copy the files into the "emummc" folder in the "backup" folder under the "restore" folder (not the "partitions" folder).
2. Go to Hekate and select "Restore eMMC" under "Tools".
3. Select "eMMC BOOT0 & BOOT1" and "eMMC RAW GPP" to restore the NAND.

You need to select "SD emuMMC Raw Partition" again if you want to restore your EmuNAND instead of your SysNAND.

## If You Want to Install Linux or Android:

1. Download [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) or [Switchroot Android](https://download.switchroot.org/android-10/) (then select the latest "Switchroot Ubuntu.7z" or "Switchroot Android.7z") and copy all folders to the root directory of your SD card.
2. Go to Hekate, select "Tools", then "Partition SD", and choose "Flash Linux" or "Flash Android" (this will flash the files to the created Linux or Android partition).

## Always Start in RCM Mode

1. In Hekate, go back to Tools.
2. Go to the second page at the bottom right with "Arch Bit - RCM - Touch - Pkg1/2".
3. Select AutoRCM at the top right. (AutoRCM is not recommended because you can only restart your Switch after turning it off by loading a custom payload.)

## Configure Auto Boot

1. Go to "Options" at the top right and select "Auto Boot", ideally choosing "BootCFW (EmuNAND)".
2. You can also disable the boot logo in the option below (to return to the Hekate menu, hold down the volume down button and send the payload until you boot into Hekate).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# Load CFW Atmosphere

1. In Hekate, go to Home and select "Launch", then choose "BootCFW (EmuNAND)" to boot into it.

# Load Homebrew

- You can start the Homebrew menu via the Album or by holding down the R button and starting a legitimate game to launch the Homebrew menu with admin rights and start your Homebrew apps from there.
- You can also download and install new apps through the Homebrew Appstore.
- The difference between the Applet Mode (Album) and the Application in Homebrew is that a game (Application) has full access to system resources, and only some features are usable, such as RetroArch.

# Avoid Switch Ban as Much as Possible

1. In the CFW, go to the Album to open Homebrew, and select "90dns setter".
2. Press "X" to set the DNS settings for any internet connection, and press "Y" to restart.
3. In the Homebrew menu, select "90dns testing utility" and check if the Nintendo services are blocked.
4. You can also go to "System Settings", select "Console", and turn off the option "Send Error Reports" (ideally also in SysNAND or Stock Mode).

*Important: You can still be banned even if you did everything right, such as blocking servers, not installing applications in the Home menu, etc. At the moment you connect to Nintendo servers without CFW data, without installed things, or without an SD card, a ban can still occur.*

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# Install Optional NSPs/XCI Files

1. Open "DBI" (or other apps that function similarly, such as Goldleaf or Tinfoil) in the Homebrew Menu.
2. Go to "Browse SD" and select the files you want to install from the directories.
3. Once you have selected the files, install them to the *"IMPORTANT":* SD card and NOT to the NAND, as you might receive a potential ban later. If you want, you can delete the file afterwards; you don't need it anymore.

# **IMPORTANT!!!**

### *DO NOT PLAY ONLINE, DOWNLOAD UPDATES, OR INTERACT WITH NINTENDO SERVERS LIKE NINTENDO E-SHOP OR NINTENDO SWITCH ONLINE, OR YOU WILL BE BANNED ONLINE OR YOUR CONSOLE WILL BE COMPLETELY BANNED. PLEASE DO NOT DOWNLOAD ROMS ONLINE AND DO NOT ENGAGE IN PIRACY. BUY ALL GAMES LEGALLY BY PURCHASING THEM. ALL GAMES I PLAY, I OWN LEGALLY AND HAVE PURCHASED THEM. I DO NOT SUPPORT PIRACY AND DO NOT WANT OTHERS TO BE ENCOURAGED TO OWN AND PLAY GAMES ILLEGALLY.*
