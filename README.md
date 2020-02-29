# Dell-XPS-15-7590-Ubuntu-installation
Description for making dual-boot installation using Windows+Ubuntu 19.04.

## Tutorials to follow

There are several tutorials giving useful information about making Ubuntu installation:

 - [Medium article](https://medium.com/@tylergwlum/my-journey-installing-ubuntu-18-04-on-the-dell-xps-15-7590-2019-756f738a6447)
 - https://github.com/TillmannBerg/Ubuntu-Dell-XPS-15-2019
   - ==> better fork: https://github.com/MuDiAhmed/Ubuntu-Dell-XPS-15-2019
   
## Objectives

 - Make a dual boot installation with Windows and Ubuntu 19.04
 - Total disk space ~1TB: 250GB disk space should be left allocated to Windows, and rest for Ubuntu (main working environment)

## Steps

### Prepare Windows for Ubuntu dual boot

- Update Windows
   - First step when you get your new laptop is to install the necessary Windows and Dell updates. You can do this by going to Settings > Updates & Security > Check For Updates. 
   
- Make partition for Linux
   - Type “Create and Format Hard Disk Partitions” in the Windows Search Bar.
   - Right click on the largest partition and click “Shrink Volume”.
   - Choose the desired size for Ubuntu  (750 GB with 1TB disk size).
   - Now yous should have the newly created “Unallocated space” visible in the partition diagram.

- Switch from RAID to AHCI Mode
   - Type “cmd” into the Windows Search Bar, then click “Run as administrator”.
   - Type the following command and press ENTER: `bcdedit /set {current} safeboot minimal`. It should say "operation completed successfully."
   - Restart the computer and enter the BIOS Setup. For the Dell XPS 15 7590, this means **restarting the laptop and then repeatedly pressing F2 during the restart**. This has to be done early and often to work.
   - Under System Configuation, change the SATA Operation mode from RAID to AHCI.
   - Save changes and try to boot into Windows. It will automatically boot to Safe Mode.
   - Type “cmd” into the Windows Search Bar, then click “Run as administrator”.
   - Type this command and press ENTER: `bcdedit /deletevalue {current} safeboot` This next step makes your computer not boot into safeboot. 
   - **Reboot** once more and Windows will automatically start with AHCI drivers enabled.
      - If this worked, you should be able to search “Device Manager” in the Windows Search Bar, then see IDE ATA/ATAPI Controllers > Intel(R) 300 Series Chipset Family SATA AHCI Controller.

### Install Ubuntu 19.10

- Download [Ubuntu 19.10](https://ubuntu.com/download/desktop/thank-you/?version=19.10&architecture=amd64).
- Download [Rufus](https://rufus.ie/) for making the bootable memory stick.
- Buy/get a memory stick that can be used to create the Ubuntu boot (requires ~3GB). Note: everything on the stick will be destroyed so ensure you don't have anything important on the USB stick before doing the next step.
- Create bootable Ubuntu USB stick following [**this tutorial**](https://ubuntu.com/tutorials/tutorial-create-a-usb-stick-on-windows)
- Install Ubuntu following [**this tutorial**](https://ubuntu.com/tutorials/tutorial-install-ubuntu-desktop)
