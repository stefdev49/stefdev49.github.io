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
<h4>Marlin firmware for DiscoEasy200</h4>
<div class="hline"></div>
Marlin firmware customized for the Dagoma DiscoEasy200. I is built with the following options:
+ bilinear calibration : with 5 points per direction
+ supports for hotbed (with a NTC 3950 100K Thermistor)

{% highlight c %}
#define AUTO_BED_LEVELING_BILINEAR
#define GRID_MAX_POINTS_X 5
#define TEMP_SENSOR_BED 11
{% endhighlight %}
