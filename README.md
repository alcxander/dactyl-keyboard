#Extending the project into my own territory

adding resources here I have piucked up during research. Ultimate goal is to build a dactyl manuform likely 5x6 with rotary encoders maybe one each side. Probably for scrolling purposes or something that allows me to switch screens more rapidly not sure yet but like the idea of rotary encoders.


resources to date:



https://www.thingiverse.com/thing:3770166 - adapter for rotary encoder to fit cherry mx slot

https://github.com/victorlucachi/void_ergo - another ergo keyboard that uses 3.5mm jack

https://www.thingiverse.com/thing:4628137 - related to above

https://github.com/LouWii/ErgoMax - another ergo resource with 3.5mm linkage

https://www.youtube.com/watch?v=dWC_8BOArzc - most detailed video seen to date (series, several hours)

https://github.com/carbonfet/dactyl-manuform // https://www.youtube.com/watch?v=DpnDz8aXFjE - did not find this video/repo useful

https://www.youtube.com/watch?v=UerP5bxGL3c - best explanation found to date (props to this user for diode explanations) bonus part 3: https://www.youtube.com/watch?v=vLsgsmZssuk

https://thangs.com/ZackFreedman/DactylManuForm-5x6-Mechanical-Keyboard-10466 (original resource from Zack prompting the build)

https://www.youtube.com/watch?v=y0F8Mig40m0 - video from infinite offset was a good watch

https://www.youtube.com/watch?v=VlHgEqLVYqA - should probably start a resources tab or something at this point lol. this was based off of Zacks video




# The Dactyl-ManuForm Keyboard
This is a fork of the [Dactyl](https://github.com/adereth/dactyl-keyboard), a parameterized, split-hand, concave, columnar, ergonomic keyboard.

![Imgur](http://i.imgur.com/LdjEhrR.jpg)

The main change is that the thumb cluster was adapted from the [ManuForm keyboard](https://github.com/jeffgran/ManuForm) ([geekhack](https://geekhack.org/index.php?topic=46015.0)). The walls were changed to just drop to the floor. The keyboard is paramaterized to allow adjusting the following: 

* Rows: 4 - 6 
* Columns: 5 and up
* Row curvature
* Column curvature
* Row tilt (tenting)
* Column tilt
* Column offsets
* Height

I built a 4x5 version (40% size) for myself. The default has a bit more tenting than the Dactyl. See the following model files for configurations that may be most common:

* [40% size, (4x5)](https://github.com/tshort/dactyl-keyboard/blob/master/things/right-4x5.stl)
* [60% size, (5x6)](https://github.com/tshort/dactyl-keyboard/blob/master/things/right-5x6.stl)


## Assembly

### Generating a Design

**Setting up the Clojure environment**
* [Install the Clojure runtime](https://clojure.org)
* [Install the Leiningen project manager](http://leiningen.org/)
* [Install OpenSCAD](http://www.openscad.org/)

**Generating the design**
* Run `lein repl`
* Load the file `(load-file "src/dactyl_keyboard/dactyl.clj")`
* This will regenerate the `things/*.scad` files
* Use OpenSCAD to open a `.scad` file.
* Make changes to design, repeat `load-file`, OpenSCAD will watch for changes and rerender.
* When done, use OpenSCAD to export STL files

**Tips**
* [Some other ways to evaluate the clojure design file](http://stackoverflow.com/a/28213489)
* [Example designing with clojure](http://adereth.github.io/blog/2014/04/09/3d-printing-with-clojure/)


### Printing
Pregenerated STL files are available in the [things/](things/) directory. 
When a model is generated, it also generates a `.scad` model for a bottom plate. 
This can be exported to a DXF file in OpenSCAD.
The [things/](things/) directory also has DXF files for the bottom plate.
When laser cut, some of the inside cuts will need to be removed. 

This model can be tricky to print. 
It's wide, so I've had problems with PLA on a Makerbot with edges warping. 
This can cause the printer to think its head is jammed. 
Even if it successfully prints, warping can cause problems. 
On one print, the RJ-9 holder was squished, so I had to cut down my connector to fit.

If printed at Shapeways or other professional shops, I would not expect such problems. 

### Thingiverse

[The 4x5 STL left/right pair](https://www.thingiverse.com/thing:2349390) from the [things/](things/) directory is in the thingiverse for public printing

### Wiring

Here are materials I used for wiring.

* Two Arduino Pro Micros
* [Heat-set inserts](https://www.mcmaster.com/#94180a331/=16yfrx1)
* [M3 wafer-head screws, 5mm](http://www.metricscrews.us/index.php?main_page=product_info&cPath=155_185&products_id=455)
* [Copper tape](https://www.amazon.com/gp/product/B009KB86BU)
* [#32 magnet wire](https://www.amazon.com/gp/product/B00LV909HI)
* [#30 wire](https://www.amazon.com/gp/product/B00GWFECWO)
* [3-mm cast acrylic](http://www.mcmaster.com/#acrylic/=144mfom)
* [Veroboard stripboard](https://www.amazon.com/gp/product/B008CPVMMU)
* [1N4148 diodes](https://www.amazon.com/gp/product/B00LQPY0Y0)
* [Female RJ-9 connectors](https://www.amazon.com/gp/product/B01HU7BVDU/)

I wired one half using the traditional approach of using the legs of a diode to form the row connections. 
(I'm not great at soldering, so this was challenging for me.)
For this side, I used magnet wire to wire columns. That worked okay. 
The magnet wire is small enough, it wants to move around, and it's hard to tell if you have a good connection.

![Imgur](http://i.imgur.com/7kPvSgg.jpg)

For another half, I used stripboard for the row connections. 
This allowed me to presolder all of the diodes. 
Then, I hot-glued this in place and finished the soldering of the other diode ends. 
I like this approach quite a lot. 
Connections for the diodes were much easier with one end fixed down. 
On this half, I also used copper tape to connect columns. 
This worked a bit better than the magnet wire for me. 
For a future version, I may try just bare tinned copper wire for columns (something like #20). 
With the stripboard, it's pretty easy keeping row and column connections separate.

![Imgur](http://i.imgur.com/JOm5ElP.jpg)

Note that a telephone handset cable has leads that are reversed, so take this into account when connecting these leads to the controller.

The 3D printed part is the main keyboard. 
You can attach a bottom plate with screws. 
The case has holes for heat-set inserts designed to hold 3- to 6-mm long M3 screws. 
Then, I used wafer-head screws to connect a bottom plate. 
If wires aren't dangling, a bottom plate may not be needed. 
You need something on the bottom to keep the keyboard from sliding around. 
Without a plate, you could use a rubber pad, or you could dip the bottom of the keyboard in PlastiDip.

For more photos of the first complete wiring of v0.4, see [Imgur](http://imgur.com/a/v9eIO).

This is how the rows/columns wire to the keys and the ProMicro
![Wire Diagram](https://docs.google.com/drawings/d/1s9aAg5bXBrhtb6Xw-sGOQQEndRNOqpBRyUyHkgpnSps/pub?w=1176&h=621)


#### Alternative row-driven wiring diagram for ProMicro:

NOTE: you also make sure the firmware is set up correctly (ex: change row pins with col pins)

![Left Wire Diagram](/resources/dactyl_manuform_left_wire_diagram.png)

![Left Wire Diagram](/resources/dactyl_manuform_right_wire_diagram.png)


### Firmware

Firmware goes hand in hand with how you wire the circuit. 
I adapted the QMK firmware [here](https://github.com/tshort/qmk_firmware/tree/master/keyboards/dactyl-manuform). 
This allows each side to work separately or together. 
This site also shows connections for the Arduino Pro Micro controllers.

## License

Copyright © 2015-2017 Matthew Adereth and Tom Short

The source code for generating the models (everything excluding the [things/](things/) and [resources/](resources/) directories is distributed under the [GNU AFFERO GENERAL PUBLIC LICENSE Version 3](LICENSE).  The generated models and PCB designs are distributed under the [Creative Commons Attribution-NonCommercial-ShareAlike License Version 3.0](LICENSE-models).
