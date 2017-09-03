---
layout: project
title: "Marlin firmware for Dagoma DiscoEasy200"
author: stefdev49
categories:
- project
img: marlin-250.png
thumb: marlin-thumb.jpg
tagged: 3d printer, DiscoEasy200, marlin firmware
website: https://github.com/stefdev49/Marlin
---
#### Marlin firmware for DiscoEasy200
<div class="hline"></div>
Marlin firmware customized for the Dagoma DiscoEasy200. It is built with the following options :
+ bilinear calibration : with 5 points per direction
+ supports for hotbed (with a NTC 3950 100K Thermistor)
```c
#define AUTO_BED_LEVELING_BILINEAR
#define GRID_MAX_POINTS_X 5
#define TEMP_SENSOR_BED 11
```
#### Building instructions (short version)
<div class="hline"></div>
First you have to get the sources with [git](https://git-scm.com/), then switch to dedicates DiscoEasy 200 branch:
```bash
git clone https://github.com/stefdev49/Marlin.git
cd Marlin
git checkout -b discoeasy200-1.1.x origin/discoeasy200-1.1.x
```

Then compile it with [platformio](http://platformio.org/) :
```bash
platformio run
```

Uploading the firmware to the printer is done with :
```bash
platformio run -t upload
```
