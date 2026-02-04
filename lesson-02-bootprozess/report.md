# Lab Report: BIOS/UEFI & Boot Process

## 🎯 Task: Configure Boot Priority
The goal was to access the BIOS and change the boot order to prioritize removable media (CD-ROM).

## 🛠 Actions:
1. Entered the **PhoenixBIOS Setup Utility** in VMware.
2. Navigated to the **Boot** tab.
3. Used `+` key to move **CD-ROM Drive** to the top of the list.
4. Saved changes with **F10**.

## ✅ Result:
The system now looks for bootable media in the CD-ROM drive before attempting to boot from the local hard drive.

![Boot Order Modified](./screenshots/boot_order_modified.png)
