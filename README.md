# K1 Moonraker Thumbnails

A quick edit of a single moonraker component (metadata.py) to generate an additional thumbnail that Creality Print, Cloud, and the K1 Screen (most importantly) can intepret. This change will make Moonraker automatically generate the thumbnail as long as you follow the usual thumbnail configuration for Mainsail, fluidd, etc. There are also additional installation steps outlined below.

## Requirements

This requires you to have root access to your Creality K1. This is done through an exploit using a shadow gcode file. For more information, please check out https://github.com/giveen/K1_Files/tree/ab81d83ca6421c8420a7a85e456059eb0e641bd3/exploit

## Caveats

Firmware updates will most likely completely overwrite these changes.

## Installation

1. Replace metadata.py in `/usr/share/moonraker/moonraker/components/file_manager/metadata.py` with the `metadata.py` available in this repository.


2. Rename `/usr/share/frontend/downloads/humbnail` to `/usr/share/frontend/downloads/humbnail.bak` if you want to backup the original folder.

3. Create a symbolic link in the above directory to point to the thumbnail folder that moonraker uses: `ln -s /usr/data/printer_data/gcodes/.thumbs/ /usr/share/frontend/downloads/humbnail`
  
4. Restart your printer

5. GCode sent from OrcaSlicer should now show the thumbnail on the K1's screen and other applicable Creality locations.