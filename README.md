# Tiny_polybar
A tiny polybar for hiding tray icons and modules that are rarely used.

# Installation
Clone this repository and move the files to your polybar config location.

Example:
```bash
git clone https://github.com/phon31x/Tiny_polybar
cd Tiny_polybar
mv tinybar.sh killbar.sh arrow.ini ~/.config/polybar
```

# Usage example
There are multiple ways to include this tiny polybar. The prefered method is: 

1. Create a second bar in your polybar config. Example of a bar:
```ini
[bar/tray]
monitor-strict = false
width = 20
height = 25

offset-x = 98% # Set it accordingly to your need
offset-y = 35

override-redirect = true # Must be true for offset values to work 
fixed-center = true

background = ${colors.background}

radius = 8

line-size = 0
line-color = #f00

padding-left = 0
padding-right = 1

module-margin-left = 0
module-margin-right = 0

modules-right = sep

tray-position = right
tray-detached = false
tray-offset-x = 0
tray-offset-y = 0
tray-padding = 1
tray-maxsize = 20
tray-scale = 1.0
tray-background = ${colors.background}
```

2. Create a module to access the bar (arrow.ini).
```ini
[module/arrow]
type = custom/script
exec = echo "" # Arrow symbol

click-left = bash $HOME/.config/polybar/tinybar.sh
click-righ = bash $HOME/.config/polybar/killbar.sh
```

3. Click left (tinybar) is used to launch the bar. Click right (kill bar) is used to close tiny bar.
