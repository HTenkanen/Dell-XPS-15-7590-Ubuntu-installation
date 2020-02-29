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

- Update Windows
   - First step when you get your new laptop is to install the necessary Windows and Dell updates. You can do this by going to Settings > Updates & Security > Check For Updates. 
   
- Make partition for Linux
   - Type “Create and Format Hard Disk Partitions” in the Windows Search Bar.
   - Right click on the largest partition and click “Shrink Volume”.
   - Choose the desired size for Ubuntu  (750 GB with 1TB disk size).
   - Now yous should have the newly created “Unallocated space” visible in the partition diagram.
