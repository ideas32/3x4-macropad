# Build Guide
> While I did my best to write a build guide that a beginner would be able to understand, there are defininently better guides out there on how to build this style of Mechanical Keyboard. If at any point in this guide you are unsure on what to do or need more images/examples, [SplitKB](https://docs.splitkb.com/hc/en-us/sections/6269738440220-Aurora-Kyria-rev3-Build-Guide) has an extremly well written guide on how to build a kit similar to this. While not everything is the same and I recommend a different soldering order, I think SplitKB's guide is still applicable and will be quite helpful, especially if you are a beginner to soldering. 
## Materials
![](/images/materials.png)

## Soldering the PCB
> Most images were taken with an older revision of the PCB. There are some minor differences compared to the current one.
### 1. Diodes:
Solder the diodes into the footprints marked with Dxx on the backside of the PCB. The side of the diode with the black stripe goes toward the side of the silkscreen with the thick white stripe. If unsure, check the pcb source files to make sure the direction/component is correct. Start off by bending the diode legs and inserting the diodes into the PCB. Cut off the diode legs from the top as close to flush to the pcb as possible when done.

#### Images:
Diode with legs bent\
![](/images/Diode%20leg%20bending.png)\
Diode insertion into PCB\
![](/images/Diode%20insertion.png)\
Diode inserted into PCB\
![](/images/diode%20inserted.jpg)\
Diode ready to solder\
![](/images/diode%20inserted%20and%20bent.png)\
Diodes soldered\
![](/images/diodes%20soldered.png)\
Diodes soldered and legs cut\
![](/images/diodes%20soldered%20and%20cut.png)

### 2. Resistors:
Solder resistors onto the pads labeled R1 and R2 on the back of the PCB. Polarity does not matter. Cut off these legs as well in the same manner as the diodes. 

#### Images: 
Resistors inserted into PCB:\
![](/images/resistors%20inserted.png)\
Resistors ready to solder:\
![](/images/resistors%20bent%20legs.png)\
Resistors soldered:\
![](/images/resistors%20soldered.png)\
Resistors with legs cut:\
![](/images/resistors%20soldered%20and%20cut.png)

### 3. SK6812 MINI-E LEDs:
Skip this step if you aren't using per-key RGB. Splitkb's guide on this is extremely good and I don't think I could explain it better. I highly recommend following [it](https://docs.splitkb.com/hc/en-us/articles/6309893037852-Aurora-Build-Guide-4-Per-key-RGB-optional-) - it has great images and explanation. There are images of this keyboard particularly in this build guide if more examples are needed. 
#### Images:
SK6812 MINI-E LED:\
![](/images/sk6812mini-e.png)\
Tinned Pads:\
![](/images/sk6812mini-e%20pad%20tinned.png)\
LED oriented properly:\
![](/images/sk6812mini-e%20one%20leg.png)\
LEDs soldered (frontside):\
![](/images/sk6812mini-e%20all%20done%20front%20side.png)\
LEDs soldered (Backside):\
![](/images/sk6812%20mini-e%20backside.png)

### 4. WS2812B LEDs:
> If you are using per-key RGB without underglow, solder the jumper labeld JP1 on the backside of the PCB.

These are soldered face-up with the chamfered corner aligned with the triangle on the skilkscreen, with the same technique as the SK6812 MINI-E LEDs. See [this guide](https://docs.splitkb.com/hc/en-us/articles/6309982106012-Aurora-Build-Guide-5-RGB-Underglow-optional-).

#### Images:
LEDs soldered correctly:\
![](/images/ws2812b%20soldered.png)

### 5. Hotswap Sockets:
Hotswap sockets: Solder the hotswap sockets to the PCB, with the same technique as the LEDs. Make sure that they are oriented correctly - the holes for the switches shouldn't be obstructed by the sockets. Follow [this guide](https://docs.splitkb.com/hc/en-us/articles/6310106113052-Aurora-Build-Guide-7-Switch-Sockets), but skip the part talking about encoders.

#### Images:
Tinning the pads:\
![](images/tinned%20pad%20hotswap%20sockets.png)\
All Done, with the correct orientation:\
![](images/hotswap%20sockets%20back.png)

### 6. Flash Pi Pico with firmware
#### Prequisites:
QMK set up and ready to go. 

This keyboard's source code can be found in this repo in ```firmware/3x4_macropad/```. Copy and paste the entire folder, including the ```3x4_macropad``` part, into the keyboards folder in QMK. Compile the firmware using ```qmk compile -kb 3x4_macropad -km default```. This should generate a ```.uf2``` file that can now be flashed onto the Pi Pico. The flashing process for the RP2040, which is the microcontroller on the Pi Pico, is different from the usual STM32 or AVR processors. When put into flashing mode, which can be done by plugging the board in while holding the ```BOOTSEL``` button, the Pi appears as a USB drive. Flash the board by dragging the ```.uf2``` to the Pi in File Explorer/Finder/any file manager. The USB drive should dissapear and the pi should reboot itself as a keyboard after a couple of seconds. 

### 7. Pi Pico:
Solder the Pi Pico face-down on the topside of the PCB using the included headers. This means the usb-c port is in between the microcontroller's PCB and the keyboard's PCB, facing away from the encoder, and the golden "WeAct Studio" logo is face up. You should be able to access the reset button after soldering. Everything before this has been on the back side, so this is a good place to check your work. See [this guide](https://docs.splitkb.com/hc/en-us/articles/6331218321180-Aurora-Build-Guide-14b-Microcontroller-headers-).

### 8. Check your work:
Before continuing, check your soldering for any bridges or poor joints. The LEDs in particular are harder to solder properly, so don't be suprised if only 2 or 3 work first time. Because these LEDs work by sending signals down the LED chain, a single bad LED will stop everything downstream of it on the chain from functioning. The chain for the LEDs goes from LED16 -> LED1. If none of the LEDs are functioning and you are using only per-key RGB, make sure that the jumper JP1 is soldered. 

### 9. OLED:
Skip this step if you don't plan on using an OLED. Solder the included headers onto the OLED first. It doesn't really matter how straight they are at this point in time, but try to keep them somewhat aligned. Next, solder the OLED with headers to the PCB. The OLED should sit above the Pi Pico but not touch it. The first part of [this guide](https://docs.splitkb.com/hc/en-us/articles/6333686725532-Aurora-Build-Guide-17-OLED-Displays-optional-) covers this quite well.

### 10. Encoder:
Place the encoder on the top of the PCB and make sure it's flat and paralell to the surface of the PCB. I recommend soldering all 7 pins for maximum stability, which this board is designed for. Other kits may not be designed with soldering the big pins in mind, so make sure to check whether the slots for the big pins are plated. If they are, they are probably safe to solder. 

### 11. Check your work (again):
Double check to make sure all the keys and encoder work properly. Most of the times, problems are caused by bad solder joints and can be fixed by reflowing the joint in question. Splitkb's article on [troubleshooting](https://docs.splitkb.com/hc/en-us/categories/360002241599-Troubleshooting) has great tips if you're still having trouble. If everything is working, you're done with soldering! 

## TAKE A BREAK
Seriously. Soldering takes a while and this is a good point to get some water and snacks. I also recommend cleaning up your buildspace after this step. This is the point where you get out of the soldering step and start assembling the keyboard. However, don't put your soldering iron away yet because there are heat-set inserts that go into the 3d printed case that requires use of a soldering iron. 

## Case Prep
### Heat Set Inserts:
You need 4 inserts for the 4 holes of the top case. The inserts should sit slightly below the surface of the case. 

### Hole size check:
The bottom case's holes are a little finicky sometimes and may require enlarging. As long as the M2 screws can fit through easily, they should be fine.

## Plate
### Gaskets:
Attach the gaskets to the bottom of the plate on the protruding rectangles. Most gaskets come too long, and need to be cut to size. This doesn't have to be super accurate, and as long as the gasket is smaller than the plate it should be fine. The lengths of the gaskets are different for the 3 sides.

### Final Assembly
Using the M2x3mm and M2 standoffs, attach the plate to the PCB. Next, insert switches and place on keycaps. Finally, set the plate-pcb assembly on the bottom case, add the top case on top, and screw the cases together from the bottom with 4 M2x3mm screws.
