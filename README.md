# 3x4 macropad
A 3x4 hotswap macropad with per-key rgb, rgb underglow, an oled, and an encoder. Uses the Weact Pi Pico as the microcontroller.
**STILL IN ALPHA, NOT READY FOR USE**
## Features:
- 3x4 array of south-facing MX switches
- hotswap (kailh sockets or equivilant)
- through-hole and surface mount diode (SOD-123) compatible
- uses a [WeAct Studio Pi Pico](https://www.aliexpress.us/item/3256803521775546.html?spm=a2g0o.productlist.main.21.2b183894Ed1md6&algo_pvid=a2d29449-dd97-4924-b1b0-dca670c23c11&algo_exp_id=a2d29449-dd97-4924-b1b0-dca670c23c11-10&pdp_npi=3%40dis%21USD%214.08%213.96%21%21%21%21%21%40212272e216815772675866023d071b%2112000026898823783%21sea%21US%214210481755&curPageLogUid=xUKSE3v0SzRr) as the microcontroller 
- support for a single 128x32 OLED placed above the microcontroller
- support for a single Alps EC11 rotary encoder
- support for addresable per-key rgb (SK6812 MINI-E)
- support for addresable rgb underglow (WS2812b or equivilant)

## To Do:
### PCB:
**DO NOT USE**
    Has not been tested and there is no guarantee that it will work on its own or with the case
- Bugfixes:
    -   nothing for now, will update once PCB arrives
- Future Plans:
    -   change breakout to pro micro footprint **or** add onboard mcu
        - if changing to onboard mcu add support for UDB S1
### Case:
**DO NOT USE**
    Still has many bugs and is not tested for compatibilty with the PCB
- Bugfixes:
    -   increase m2 standoff diameter
    -   increase m2 screw diameter
    -   change m2 stackup to allow for looser tolerances
    -   make tophat 2 pieces for easier printing of m2 holes
    -   increase switch cutout size
    -   decrease plate height from 1.6mm to 1.5mm
    -   divide bottom into 2 parts for better printing results
    -   add more screw locations to secure the plate better (probably 3x3)
- Future Plans:
    -   add stacked acrylic version?
    -   top/burger mount instead of sandwhich mount?
    -   maybe gasket mount?
    -   UDB support if mcu is moved to pcb instead of breakout?
    -   
