# MarlinConfig

This repo mainly serves as a backup of my Marlin config and notes to my future self to avoid any future headaches. My printer originally ran on Marlin 1.0, but I've since lost the configurations and upgraded it to Marlin 2.0. This repo contains the new configurations as of April 4th, 2022 such that I do not lose them again. 

In late 2015, I had made a Prusa i3 (rework) from scratch. I did not use any sort of kit, therefore I was limited in material usage. I could only laser cut wood so I tweaked the open-sourced parts to be more robust and rigid to compensate for the lack of an aluminum frame. This resulted in a wooden frame with perpendicular supports on either side. Below I detail some of the intricacies of this printer.

## Printer Setup

### Electronics

This custom printer uses an Arduino Mega with a RAMPS 1.4 (with A4988 stepper drivers). The electronics are all 12v, the motors are Nema 17s. I use two mechanical endstops, one for y_min, one for x_min, and an NPN type inductive probe (6-36v) as the z_min endstop. This also allows for automatic bed leveling. 

_**Important Note:**_ It seems that I have burnt out the E0 extruder slot on the RAMPS board. Because of this, my only extruder is wired on E1. To account for this I've changed the pins in `pins_RAMPS.h` and effectively flipped E1 with E0, see [here](https://3dprinting.stackexchange.com/questions/5840/how-to-change-e0-to-e1-on-marlin-1-1) for an (outdated) example of this.

### Mechanical

As mentioned above, the frame is laser cut wood. The Y-carriage is made of M10 threaded rods attached by printed parts. The threaded rods used to move the Z-axis are M5 rods. All smooth rods are M8s. All (yellow, and gold) printed parts are PLA. 

The hotend is a cheap E3D V6 clone with a Teflon-lined heat throat and 0.4 mm nozzle. The extruder is a geared wade's extruder (classic). The x-idler is custom and part files can be found above. 