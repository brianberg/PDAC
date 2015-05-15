# PDAC 
*Portable, Deployable, and Accessible Classroom*

## Overview

PDAC is a portable presentation device that increases the accessibility of a presentation in the classroom. Users are able to connect to the device via a configurable wireless access point and locally hosting web application. Presentations can be uploaded to the system from personal devices or USB devices. Users can then view the presentation slides at their own pace or follow the live broadcast.


## Table of Contents

1. [System Requirements](#system-requirements)
2. [Installation](#installation)
3. [System Setup](#system-setup)
4. [Roles and Permissions](#roles-and-permissions)
5. [Upload](#upload)
6. [Download](#download)
7. [Admin Settings](#admin-settings)


## System Requirments
The PDAC system requires the following components:

1. [Raspberry Pi Model B 2] (recommended) or [Raspberry Pi Model B+]
2. [Edimax WiFi dongle]
3. Micro SD card (at least 4GB)
4. 5V micro USB power adapter
5. HDMI cable

[Raspberry Pi Model B 2]:https://www.raspberrypi.org/products/raspberry-pi-2-model-b/
[Raspberry Pi Model B+]:https://www.raspberrypi.org/products/model-b-plus/
[Edimax WiFi dongle]:http://www.edimax.com/edimax/merchandise/merchandise_detail/data/edimax/global/wireless_adapters_n150/ew-7811un


## Installation

### OS X and Linux

1. Insert your SD card
2. Run `diskutil list` to locate your SD card. In the following steps we will use `dev/disk2`
3. Run `sudo dd if=pdac.img of=/dev/rdisk2 bs=4m` (The extra 'r' is intentional)
4. If you get a `dd: bs: illegal numeric value` error, use a lower value for `bs` such as `bs=1m`

### Windows

1. Download [Win32 Disk Imager] and run .exe as administrator 
2. Insert SD card into card reader and make note of drive letter
3. In Win32 Disk Imager, browse to and select the pdac.img file
4. Select the correct drive letter for SD card from Device drop down menu
5. Write image to SD card

[Win32 Disk Imager]:http://sourceforge.net/projects/win32diskimager/


## System Setup

1. Insert SD card and WiFi dongle into Raspberry Pi
2. Connect HDMI cable
3. Connect power adapter

Make sure to connect the HDMI cable before the power adapter as the system will not recognize a display after it has been powered on.

Once the system has booted it will display a splash screen with connection instructions.


## Roles and Permissions

### Roles

By default the system has two roles, presentation owner and viewer. The presentation owner is responsible for providing the presenation and a viewer is a connected user or student. All changes the presentation owner makes are broadcast to all following users.

### Permissions

By default presentation owner can:

* Upload presentation
* Download presentation
* Access USB file (upload and download)
* Start a presentation
* End a presentation
* Annotate presentation slides
* Navigate presentation slides
* Remove users


By default a viewer can:

* Download presentation slides
* Follow a live presentation broadcast
* Navigate slides independent of presentation



## Upload

Once connected the presentation owner can upload a presentation via their personal device or via a USB device. To upload a presentation from a personal device drag a file onto the window or use file select button. To upload from a USB device, simply plug the device into an open USB port and select the file from the list of USB files. The system will automatically detect valid presentation files on USB devices.

Supported presentation formats:

* ppt
* pptx
* odp


## Download

Presentation slides can be downloaded to personal devices and USB devices with or without slide annotations. Presentations can be downloaded as a PDF or as the original format uploaded by the presentation owner. Annotations, however, are only available in PDF format


## Admin Settings

A system admin can modify the following system settings:

* Admin password
* Presentation owner password
* Viewer password
* Session Length
* Role permissions
* Connection settings
* Allow forward

The default admin and presentation owner passwords are "admin" and "owner" respectively. We highly recommend you change these before using the system.

### Viewer Password

By default the viewer password is dynamically generated everytime the system starts. As an admin, you can change the length of the viewer password and / or how often it is regenerated.

### Role Permissions

The default permissions for each role can be modified. A no role mode is also available and configurable which gives all users the same permissions.

### Connection Settings

The Wifi SSID and password are configurable along with the local server address. A system reboot is required for these changes to take effect.

### Allow Forward

By default viewers are able to view slides ahead of the live broadcast. As an admin, you have the ability to turn this feature on or off.
