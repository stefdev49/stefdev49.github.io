---
layout: post
title: "Inserting M600 filament change with Cura"
author: stefdev49
categories:
  - blog
  - cura
thumb: cura-64.png
---
To enable filament change with latest marlin firmware, we need to insert `M600` gcode at the desired layer. There is no stock plugin for it in Cura, but this may be overcome by using the post processing plugin : ![post processing plugin](/assets/img/blog/post-process.png)

Using the available 'Pause at height for BQ printers' will insert a `M25` gcode at the desired height. Then we use the 'Search and replace' to replace `M25 ` (note the blank character) with `M600` : ![pause at height](/assets/img/blog/pause-at-height.png)

Specify height for filament change : 
![height value](/assets/img/blog/pause-at-height-value.png)

And last post-processing, replace `M25 ` with `M600` :
![replacing](/assets/img/blog/search-and-replace.png)

When saved with cura the gcode will have the desired `M600` :
<pre>
G0 F7200 X109.486 Y119.563
G0 X93.229 Y91.53
G0 X93.156 Y91.462
;TIME_ELAPSED:260.404025
;TYPE:CUSTOM
; -- Pause at height (0.70 mm) --
<b>M600       ; Pauses the print and waits for the user to resume it</b>
;LAYER:3
M106 S124.3
G0 X93.156 Y91.462 Z0.7
;TYPE:WALL-INNER
G1 F3600 X93.957 Y90.661 E211.3535
G1 X94.837 Y89.894 E211.39278
G1 X95.751 Y89.201 E211.43137
</pre>
