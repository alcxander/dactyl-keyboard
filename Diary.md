# Keyboard Diary

## using this to track progression on keyboard creation

* 26/07/2021

finding it difficult to find any clear and concise details about how exactly to wire up a dactyl manuform keyboard or even another ergodox, surprising amount of people with pre built chip boards and not hand wired. Bit of a pain, only one or two diagrams seems to accomodate the whole keyboard niche group. Namely

![Left Wire Diagram](/resources/dactyl_manuform_left_wire_diagram.png)

![ Wire Diagram](/resources/dactyl_manuform_right_wire_diagram.png)

Started looking up QMK and how to flash the drive with it. Did not get the Arduino Pro Micro ended up getting another chipset [entirely](https://www.amazon.co.uk/gp/product/B07DF5CPTB/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1) there is a requirement mentioned that these chipsets need to be 'ATmega32u4' to check this you can find it on the chip (the black square chip) printed faintly. TODO: put image here locating wording sought.

some other thoughts I had while playing with the printed model today, maybe this should be a 4x6 instead of a 5x6. Putting the fingers on this makes me think that the idea of all keys being one press away should be a prime directive of ergonomic keyboard making. There are cool ideas for what you could do with layers or shifting that could be funky and cool but mostly feel like while using keyboards if going to be ergonomic the focus should be on natural form of hands and there should be an upper limit on how far fingers should be allowed travel to type succesfully (one key over is my current feeling). I think this is appears pretty clearly in my current keyboard a Ducky 2 60% keyboard. I think this exists in other keyboards too. If I want to commit a special function (for example in vscode where I need to press ctrl and shift and p to open the command palette) I need to stretch my pinky fingers in a way that strains my hand either into an awkward shape on one hand or the other. For example on the left side I use ctrl and shift stretches my pinky and ring away from my first and second finger while also cocking my wrist towards my body and at an angle that is awkward to be put into. Another option is to use the left pinky for left ctrl and right pinky for right shift and right middle for p. This movement feels overall less strained on the left wrist pressing only one button and not accomodating two button presses. There is an interesting tidbit to digest here, it seems like splitting multi press functions across the fingers feels quite natural, and putting them on one hand though easy feels like a strain. Also of note switching the p press to another finger entirely is an oddity. Moving the pinky to press right shift and then 'p' only feels right to press with middle finger as opposed to right ring finger which id normally use for p presses. That means for special commands I need to remember to use a different finger for pressing the key. Well technically I have to remember the location of the key and the finger I press it with so theres a comprimise on the fly mentally to accommodate the pressing of the key. This plays into the design of the keyboard to create a good key mapping, I dont want to have key press combinations that require such straining of the fingers/wrists/hands. Some other interesting presses are delete, ctrl+delete, escape, backslash, arrow keys(Ducky uses fn key to activate) brackets (I really feel these should all be on two buttons and shift between them all). 

Some other interesting key uses are what to put on the thumb clusters. I have no idea what to put where but one interesting idea that popped up first was to have a rotary encoder to delete that the thumb can operate from it's resting state. It would require an addition to the print model I feel or maybe it could be added in the thumb cluster easily enough but a thumb rotary delete function sounds like it would be much easier than the delete key the pinky has to reach to use. 



Reviewing wiring schema later on and noticed the schema is not all that clear at all. How are the wires actually wired up is very not obvious. Super not clear how to actually commence wiring of the manuform. Think wiring will have to come from a video watch as opposed to this schema. Might make a new image showing how wiring is done instead of this image in the readme which upon second view doesn't give me confidence to actually solder any connection. Caveat I don't have the keys just yet so hopefully getting them an dlaying it out will enlighten those points.

# example md

![Imgur](http://i.imgur.com/LdjEhrR.jpg)

* Row tilt (tenting)
* Column tilt
* Column offsets
* Height


* [40% size, (4x5)](https://github.com/tshort/dactyl-keyboard/blob/master/things/right-4x5.stl)



## Assembly

### Generating a Design

**Setting up the Clojure environment**
* [Install the Clojure runtime](https://clojure.org)
* [Install the Leiningen project manager](http://leiningen.org/)
* [Install OpenSCAD](http://www.openscad.org/)


