# 3x4 macropad
![](/images/complete.jpg)

A 3x4 hotswap macropad with per-key rgb, rgb underglow, an oled, and an encoder. Uses the Weact Pi Pico as the microcontroller.
## Features:
- 3x4 array of south-facing MX switches
- hotswap (kailh sockets or equivilant)
- gasket mount
- support for a single 128x32 OLED placed above the microcontroller
- support for a single Alps EC11 rotary encoder
- support for addresable per-key rgb (SK6812 MINI-E) 
- support for addresable rgb underglow (WS2812b)
- through-hole and surface mount diode compatible
- uses a WeAct Studio Pi Pico as the microcontroller 
## Parts List
- 1x Weact Pi Pico
- 1x Alps EC11 encoder
- 12x Kailh or equivilant hotswap sockets
- 14x 1n4148 signal diodes (I prefer through-hole for ease of soldering, but surface mount is also supported)
- 16x M2x3mm screws, preferably with a thin head
- 6x M2x4mm female-female standoffs
- 12x MX-style switches
- 12x MX-style keycaps
- 1x Alps EC11 encoder knob
- 1x PCB, 1.6mm thick
- 1x Plate, 1.6mm thick (I recommend FR4)
- 1x 3d printed Case Top 
- 1x 3d printed Case Bottom 
- 1x 4-6mm thick sheet of foam to make gaskets OR gaskets around 4mm wide by 80mm long by 4-6mm high
- 12x SK6812 Mini-E LEDs (optional)
- 4x WS2812B LEDs (optional)
- 2x 4k7 resistors (only if using OLED)
- 1x SSD1306 128x32 OLED (optional)

Total cost excluding filament, switches, and keycaps when sourced from AliExpress and JLCPCB: ~$50
## Tools Required
- Screwdriver
- Soldering iron, solder, and basic soldering skills (SMD and THT)
- Flush cutters
- QMK source code and knowlege of how to build from source
- 3D printer and filament
# [Build Guide](Build%20Guide.md)

# Notes on the case:
- All filaments except PETG should be ok. I recommend staying away from PETG unless small holes turn out dimensionally accurate (which was not true in my case).
- Bottom case should be printed with transparent filament if using underglow
- Bottom case does require supports, top case does not
- Top case should be printed upside down
- Top case uses 4 M2 heatset inserts
- Assembled using 4x M2x3mm