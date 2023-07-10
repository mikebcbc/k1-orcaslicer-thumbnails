[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/X8X7LBLK2)

# K1 Moonraker Thumbnails for OrcaSlicer

A quick post processing script to convince the outdated version of moonraker that the K1 uses that files sliced with OrcaSlicer are actually from SuperSlicer.

Simply adding the comment to your custom gcode worked for local instances of fluidd and mainsail, but not for the K1's screen and Creality Print. 

Additionally, the version of moonraker that the screen uses is coupled into a binary seperate from the root filesystem of the K1, so modifications to moonraker were not immediatly available without reverse-engineering the binary.

Instead, this is a quick post processing script that can be used in OrcaSlicer directly to trick moonraker for the time being.

## Requirements

This change does not require the K1 to be exploited.

## Installation

1. Download `k1-thumbs.py` from this repo and place into your root OrcaSlicer directory, next to exe file. 


2. In OrcaSlicer, in `Others -> Post-processing Scripts`, add the following code edited depending on your system:

```
<path-to-python-exec>\python.exe "<path-to-orcaslicer-folder>\k1-thumbs.py"
```

3. GCode sent from OrcaSlicer should now show the thumbnail on the K1's screen and other applicable Creality locations.
