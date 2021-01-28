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


