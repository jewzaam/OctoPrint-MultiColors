# OctoPrint-MultiColors

Octoprint plugin to inject GCODE for filament change at selected layers

Note: this plugin does NOT work with files on the SD card.

![screenshot](screenshot_1.png)


## Setup

Install via the bundled Plugin Manager or manually using this URL:

https://github.com/MoonshineSG/Octoprint-MultiColors/archive/master.zip

# How To

## Multi-line Regex

Depends on the gcode, line delimiter could be \n, \r, \l or some combo.  Play around to see what works for your slicer.

## Re-run Commands

If you want to replay gcode that happens before your layer marker you can use parens to create a group.  Reference the group with \N where N=1..

Example, to replay the match for layer..

Regex: `(.*layer {layer},.*?)`

GCODE:
```
M117 Change filament
M0
\1
```
