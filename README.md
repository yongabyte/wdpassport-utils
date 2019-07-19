# wdpassport-utils
WD Passport Ultra Complete Utilities for Linux.

<h1> Intro </h1>

This script let you unlock, change password and erase Western Digital Passport devices on Linux platform. Modified to run on **python3**.

<h1> Install </h1>

Install needed Python packages:
```
pip3 install --user pyudev git+https://github.com/crypto-universe/py_sg
```

Or follow the instructions at https://github.com/crypto-universe/py_sg.

<h1> Usage </h1>

Run script as root.

When used without any arguments, the status of the drive is shown.

There are few options:
```
-h, --help            show this help message and exit
```
Lists all possible arguments.

```
-u, --unlock          Unlock
```
You will be asked to enter the unlock password. If everything is fine device will be unlocked.

```
-m, --mount           Enable mount point for an unlocked device
```
After unlock, your operating system still thinks that your device is a strange thing attached to his usb port and he don't know how to manage. You need this option to force the O.S. to rescan the device and handle it as a normal external usb harddrive.

```
-c, --change_passwd   Change (or disable) password
```
This option let you to encrypt your device, remove password protection and change your current password.
If device is "without lock" and you want it to be password protect leave the "OLD password" field empty and choose insert the new password.
If the device is password protected and you want to be as a normal unencrypted device, inser the old password and leave the "NEW password" field empty.
If you only want to change password do it as usual.

```
-e, --erase           Secure erase device
```
"Erase" the device. This will remove the internal key associated to you password and all your data will be unaccessible. You will also lose your partition table and you will need to create a new one (you can use fdisk and mkfs).

```
-d DEVICE, --device DEVICE  Force device path (ex. /dev/sdb). Usually you don't need this option.
```
The script will try to auto detect the current device path of your WD Passport device.
If something is wrong or you want to manually specify the device path yourself you can use this option.

<h1>Disclaimer</h1>
I based my research on Dan Lukes (FreeBSD version) and [KenMacD (very simple unlocker)](https://github.com/KenMacD/wdpassport-utils/blob/master/WD_Encryption_API.txt) works. 
I'm in no way sponsored by or connected with Western Digital.
Use any of the information contained in this repository at your own risk. I accept no
responsibility.
