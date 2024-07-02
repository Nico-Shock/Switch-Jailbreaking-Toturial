# Nintendo Switch Jailbreak Totorial

## Updates
- I will add pictures when I have my Switch V1
- I try to adapt the text as accurately as possible

# What you need

- Nintendo Switch V1
- microSD card (at least 64GB is recommended)
- RCM Jig
- USB-C cable
- PC/laptop (or similar to edit data on an SD card)

# SD card preparation

## Windows:

To format the SD card to `Fat32`, follow the steps below:

1. right click on the SD card and select `Format`.
2. select `Fat32` as the file system and click on `Format`. 
   
   **Note:** If "Fat32" is not displayed as an option, open the command prompt (cmd) as administrator and execute the following commands:

   ```sh
   diskpart
   list disk
   sel disk 2 // Select the number of the SD card, e.g. disk 2
   format fs=fat32 quick


## Linux:

To format the SD card in Linux, follow these steps:

1. open the terminal and run `lsblk` to get the disk information.
2. select the SD card by typing `sudo fdisk /dev/disk1` (replace `disk1` with the actual name of the SD card)
3. execute this command to format the partition to FAT32:

   ```bash
   sudo mkfs.vfat -F 32 /dev/disk1

## MacOS:

To format the SD card to FAT32 in MacOS, follow these steps:

1. open the terminal and type `diskutil list` to get the info for the disk.
2. unmount the SD card first with `diskutil unmountDisk /dev/disk1` (replace `disk1` with the actual name of the SD card).
3. then execute the command to format the SD card to FAT32: `diskutil eraseDisk FAT32 namedersdkarte MBRFormat /dev/disk1`.


# Check serial number

Make sure your switch can be jailbroken. [IsMySwitchPatched](https://ismyswitchpatched.com/).

# SD card setup

1. download the Blue Edition RCM Pack [Blue Edition RCM](https://github.com/glitched-nx/Blue_Edition_2__RCM_V1/releases).
2. now drag all the data to the root of the SD card.

# Prepare and start RCM mode

   1. turn off the Switch by holding down the power button for 3 seconds and selecting "Power Off" under Power options
   2. slide the RCM Jig into the right Joy-Con slot until it is properly seated
   3. press and hold the volume up button and the power button to activate RCM mode (first press and hold the volume up button and then the power button).

# Insert payload

   1. download TegraRcmGUI from [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
   2. connect the Switch in RCM mode to your PC via the USB-C cable
   3. open TegraRcmGUI and select the Hekate payload file (it should be a ".bin" file).

# Configure Hekate

## Backup the NAND

1. close the launch window at the top right after you have set the date
2. then go to Tools at the top right.
3. then select `Backup eMMC`.
4. if you want, you can turn on the option with `SD emuMMC Raw Partition` (I leave it off here).
5. then select the option on the left `eMMC BOOT0 & BOOT1` and wait until it is ready.
6. then select 'eMMC RAW GPP' underneath and wait for it to finish (this will take a different amount of time depending on the amount of data on your system).
7. then turn off the switch and connect the SD card to your PC.
8. copy all the backed up data into a folder (there should be 15 rawnand.bin files on the SD card and the BOOT0 and BOOT1 files).
9. then delete these files from your SD card.

## Restoring the NAND

1. copy the backed up files and put them into `restore` then `emummc` on the SD card.
2. when you are in Hekate, you can select "Restore eMMC" under Tools.
3. then select `eMMC BOOT0 & BOOT1` and `eMMC RAW GPP` to perform the restore.

## Partition SD card and copy sysMMC to emuMMC

1. select `emuMMC` in Hekate.
2. then go to `Create emuMMC`.
3. select `SD Partition`.
4. then click on Continue and then on OK.
5. select the bars for 'emuMMC' to Full so that your system is completely copied to it (since CFW runs separately from the normal system).
6. you can also reserve memory for Android and Linux if you want to install that.
7. then go to `Next Step` and then `Start` and confirm everything else to continue. The SD card will be partitioned.
8. go to `Create emuMMC` again and then to `SD Partition` and select Part 1.

## Always start in RCM mode

1. go back to Tools in Hekate.
2. then go to the bottom right to something with "Arch Bit - RCM".
3. and select AutoRCM at the top right.

This way you don't always have to connect the RCM jig and the USB-C cable and reload the payload when you restart the switch, but always start in Hekate.

# Install HB-Store to install apps

   1. turn off your Switch completely.
   2. download the Homebrew App Store [HB-App Store](https://github.com/fortheusers/hb-appstore/releases).
   3. drag the `.nro` file into the `/switch` folder on the microSD card.
   4. you can start the homebrew from the album or you can also hold R and start a legitimate game to start homebrew with admin rights and open the HB store.

Translated with DeepL.com (free version)
