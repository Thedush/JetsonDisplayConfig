# JetsonDisplayConfig

Nvidia Jetson, Xavier Nomachine and Other Headless Display resetting Resolution without HDMI


```sudo vi /etc/X11/xorg.conf```

Open Vi and use :set paste and press i to insert with paste. Paste the below 

```
Section "Screen"
Identifier "Screen0"
Monitor    "Monitor0"
    SubSection "Display"
    Viewport   0 0
    Modes "1280x1024"
    Depth   24 
    Virtual 1280 1024
EndSubSection
EndSection
```
The Final file should look something like the one given below. 
```
# Copyright (c) 2011-2013 NVIDIA CORPORATION.  All Rights Reserved.

#
# This is the minimal configuration necessary to use the Tegra driver.
# Please refer to the xorg.conf man page for more configuration
# options provided by the X server, including display-related options
# provided by RandR 1.2 and higher.

# Disable extensions not useful on Tegra.
Section "Module"
    Disable     "dri"
    SubSection  "extmod"
        Option  "omit xfree86-dga"
    EndSubSection
EndSection

Section "Device"
    Identifier  "Tegra0"
    Driver      "nvidia"
# Allow X server to be started even if no display devices are connected.
    Option      "AllowEmptyInitialConfiguration" "true"
EndSection

Section "Screen"
Identifier "Screen0"
Monitor    "Monitor0"
    SubSection "Display"
    Viewport   0 0
    Modes "1280x1024"
    Depth   24 
    Virtual 1280 1024
EndSubSection
EndSection
```
restart and remove all the hdmi cable and check for the resolution

