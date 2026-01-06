# T1-toolchanger-3d-printer
A toolchanger 3d printer with large format build size and multiple tools for quick, easy multi-material printing that uses marlin as the firmware.
<img width="896" height="705" alt="image" src="https://github.com/user-attachments/assets/08c9021f-3ec5-47ec-ab87-f11c05bbfd20" />

I made this project as I had been looking to make a 3d printer. I wanted to be able to print in different colours, without the added cost of AMS systems. It was also a good opportunity to learn about using programs like fusion and Kicad, which I have limited experience with, as well as learning about electronic components. I created this project without a guide, using my own ideas to combat problems, with some inspiration from existing products e.g using linear rods.

Note: The assembly is too large for Fusion to export as step, so instead I have the fusion file and a zipped STL file of the assembly.


The printer uses a swappable hotend mechanism to dock tools, removing the need to purge filament as in other multi-material systems. The idle toolheads sit on an aluminium extrusion. The X carriage, supported by a V slot extrusion, moves in and attaches to the toolhead, using kinematic couplings for repeatability. A magnetic pogo connector transfers power for the heter and thermistor.
<img width="890" height="646" alt="image" src="https://github.com/user-attachments/assets/f353a81a-1eab-4a17-8c4e-561f42465f79" />

Toolhead:
<img width="543" height="517" alt="image" src="https://github.com/user-attachments/assets/016b33a6-f840-4cb9-86a1-df751536feec" />

# **Assembly**

The printer assembly is made by aluminium extrusions forming a cube, with corner connectors for mounting.


To support the Y axis, V slot 2020 aluminium extrusions are used as rails holding a gantry, which in turn supports the X axis.


The Y axis is made up of two carriages, one either side of the X gantry. Each Y carriage uses a gantry plate with wheels to slide along the extrusions, making the Y motion. One carriage is an idler, which the belt loops around a pulley. The other carriage is the stepper motor carriage, which uses a Nema 17 motor to drive the X axis belt. Both carriages hold 90 degree connectors supporting the X extrusion.
Idler:


Stepper carriage:


The X carriage is made of two parts: the main carriage, and the toolhead. The main carriage holds the fan and the extruder stepper motor. When the carriage comes into dock, a fixed arm pushes the extruder idle arm to the side. The filament slides into the extruder,and when docking is complete, the spring loaded, idle arm pushes back into the filament, creating good tension. 
<img width="764" height="604" alt="image" src="https://github.com/user-attachments/assets/5ad904bc-857b-488b-9857-69129a6abaad" />

The fan is a 4010 fan, which sits to the side and blows cool air through the heatsink fins. 

<img width="433" height="368" alt="image" src="https://github.com/user-attachments/assets/7eee1bd7-e5d4-4851-8e0e-4429b5385716" />

The belt post is located underneath the carriage.

<img width="608" height="323" alt="image" src="https://github.com/user-attachments/assets/e088cdea-a5cf-43ba-aa7c-791663ef31ae" />



The carriage sid of the coupling contains the 6mm smooth rods of the kinematic coupling. This is printed in two pieces, so that the rods can be put into grooves before the 'lid' of the coupling closes through screws. The pogo connector is also housed here.
<img width="609" height="688" alt="image" src="https://github.com/user-attachments/assets/b3a65658-4a6f-4a5e-bf3b-f52c7e877781" />
<img width="703" height="761" alt="image" src="https://github.com/user-attachments/assets/e64d68f9-87fb-452e-851e-f9bc541af3cf" />
<img width="891" height="700" alt="image" src="https://github.com/user-attachments/assets/9d94652b-2f6e-4e3e-a788-707e0d8b9a12" />

The toolhead uses steel balls to push into the kinematic coupling. The male side of the pogo connector is on the toolhead.
<img width="897" height="677" alt="image" src="https://github.com/user-attachments/assets/e1fc08a6-08ca-4877-b842-40cf4f343d8d" />
The hotend mounts to the two holes on the bottom.
<img width="857" height="580" alt="image" src="https://github.com/user-attachments/assets/8d47bb4d-4436-419e-ada4-070ecd14115c" />

The assembled X and Y axis is below:
<img width="1281" height="774" alt="image" src="https://github.com/user-attachments/assets/fbcfda2c-d1ae-4489-a407-63d02ba6798e" />


The Z axis involves the motion of the bed up and down. Originally, I had planned to move the hotend throughout all 3 axis, and the bed was fixed. I encountered many issues with reliably and consistently achieving motion of the hotend without the risk of flexing, so I pivoted to a bed Z axis. A leadscrew and two 8mm linear rods are used on each side, connected to an aluminium profile by a nut block and 3d printed clamps.
<img width="569" height="408" alt="image" src="https://github.com/user-attachments/assets/d25802ae-9f6f-48ec-a895-641b2fc667ca" />

The bed frame is a square made of aluminium extrusions, held together by 90 degree corner connectors. The 6mm aluminium print bed sits on top of that, threaded into T nuts in the profiles.
<img width="617" height="630" alt="image" src="https://github.com/user-attachments/assets/75dc115a-3a3c-4c20-b868-0830292d1216" />
<img width="1004" height="270" alt="image" src="https://github.com/user-attachments/assets/4782ae3d-23fc-4430-9a25-69dddad5791c" />
<img width="657" height="303" alt="image" src="https://github.com/user-attachments/assets/5f6981f7-08a3-4a04-ab67-2ce45387adbb" />
<img width="880" height="356" alt="image" src="https://github.com/user-attachments/assets/f8bb2860-a8e1-437e-bc85-dd8f3af04aad" />






# **Electronics**

The printer uses a PCB motherboard to mount components including the MCU (Mega 2560), stepper drivers, LCD headers, and heater terminals. I decided on a 24v power supply as it was compatible with my heater. To give power to the PCB, I used a meanwell 24v 360W power supply.
<img width="220" height="220" alt="image" src="https://github.com/user-attachments/assets/702ab6ea-9082-4103-b244-0c12045526c8" />


This connects through wires to screw terminals on the board, which then distribute power across the PCB. Because of the power requirements, I decided to use a 4 layer PCB as I couldn't route signal traces through the power and GND traces. Using a 4 layer PCB is necessary to the peojwct due to the power layout of drivers, making signal traces impossible without a 3rd and 4th layer. The top and bottom layers of the PCB are the power layers. Power runs from the PSU input to the heater screw terminal, and throughout the board. It is converted to 5v through a buck converter. The Hotend heater is powered through a screw terminal, and controlled by the mosfet next to its terminal. The hotend fan is controlled by a header, it is in an always on state.
<img width="655" height="384" alt="image" src="https://github.com/user-attachments/assets/484874a6-35cf-4dcd-a01a-cc379433830f" />

The signal traces from the drivers, limit switches, thermistor and LCD are on the second and third layers.
<img width="645" height="394" alt="image" src="https://github.com/user-attachments/assets/c286e127-8904-41be-883f-37167d5bf014" />

The MCU is a mega 2560. I chose this because of its large availability of pins, enabling future upgrades and fitting all components. The stepper drivers are A4988s, which have microstepping up to 1/16. All microstep pins are connected to 5v, making the configuration 1/16. The limit switches, thermistor and lcd connect to headers.

The power for the stepper drivers is 24v. To reduce the effect of spikes, a small 100nf capacitor is used between the 24v and gnd supply of each driver. For larger spikes, a 100 uF capacitor is also placed between 24v and gnd of each driver.
<img width="277" height="402" alt="image" src="https://github.com/user-attachments/assets/eb339b2d-3b99-4bf2-b4e5-5e703c932cf7" />

The LCD is the main user interface of the printer. I am using the BIGTREETECH TFT35 V3.0 Touch Screen from BigTreeTech which has wifi capability and is 3.5". I chose this LCD as it only uses 2 pins on the MCU (TX and RX), has an SD card, and is touchscreen. It is possible to mount the LCD separately to the motherboard, and run a cable between the two, enabling you to set it up however you like. LCD Header:
<img width="481" height="178" alt="image" src="https://github.com/user-attachments/assets/00c3d65e-e621-4007-9945-d0f34a974b62" />

The Motherboard and PSU are not fixed components to the printer and can be placed wherever suitable as long as cabling reaches. (I already have a case at home for my pcb from older projects).

### Schematic
<img width="1403" height="635" alt="image" src="https://github.com/user-attachments/assets/a9da121c-049d-4db2-9c93-1d8431419d5b" />
<img width="1583" height="861" alt="image" src="https://github.com/user-attachments/assets/5b7f5991-a8b0-4be8-a7a3-ba1de6fa06a7" />
<img width="981" height="538" alt="image" src="https://github.com/user-attachments/assets/944db4fe-2f1a-42da-8d79-5a06de2da1bc" />
<img width="270" height="184" alt="image" src="https://github.com/user-attachments/assets/8c513895-a58e-48f0-a33b-a2ed6b958679" />
<img width="1408" height="575" alt="image" src="https://github.com/user-attachments/assets/a8e6fe7b-1191-45b3-bde3-2fdb63d4d2f9" />
<img width="725" height="723" alt="image" src="https://github.com/user-attachments/assets/e2a75c30-2cd1-4396-9493-781e023c6a53" />





# **Firmware**

The printer uses the latest version of marlin firmware, which enables the use of G-code. The general firmware of the printer is fairly standard and straightforward, as marlin is just configured to the printer dimensions and layout. 

However, the printer being a toolchanger introduces a unique element to the firmware in the connection and preparation of multiple toolheads. To simplify firmware and general electronics, I decided on having 'hot-swappable' toolheads that connect through pogo connectors. Because of this, the firmware views it as one hotend when it comes to heating the temperature monitoring. In this aspect, the printer appears as standard. To facilitate toolchanges though, special G-code is required to move the carriage into specific positions. This is most effectively achieved through pre and post g-code in the slicer per tool. The main idea of the toolchange G-code is that the empty carriage moves into alignment with the passive tool, moves forward to latch on, and then returns to the print area. When returning a tool to the standby dock, it is the same idea in reverse, where it moves into a specific position, pushes the tool into the dock, and returns to pick up another tool. This is the series of G-code to paste into the slicer pre and post processing:

Pre:

M1 X(Tool X value) Y440 F6000

M1 X(Tool X value) Y480 F2000

M1 X(Tool X value + 60) Y480 F2000

M1 X(Tool X value + 60) Y440 F2000

Post:


M1 X(Tool X value + 60) Y440 F6000

M1 X(Tool X value + 60) Y480 F2000

M1 X(Tool X value) Y480 F2000

M1 X(Tool X value) Y440 F1000

The X values are unique to each tool, as tools are docked in order across the X axis. Specific values will require precise tuning with manual adjustment following assembly to ensure correct alignment of the coupling, so values are not possible now, but the spacing between docks will be roughly 100mm.

Breaking down this G-code, the carriage moves into a position hovering off of the dock, in X alignment. The carriage then slowly pushes into the docked tool in the second G-code command. At this point, the kinematic coupling engages, ensuring alignment, and the magnetic clamp and pogo connectors attach, preparing the tool for printing. The third G-code command moves the carriage and new tool to the right, out of the dock, before returning to the print area with the fourth command. this process occurs in reverse for the docking of the tool/post G-code series.

# **BOM**
### CAD

| Quanity      | Name                     |  Picture    |
| -------------| -------------------------|-----------  |
|1             | Y carriage Idler         |<img width="606" height="466" alt="image" src="https://github.com/user-attachments/assets/ffd1db70-879c-4ebd-bb6e-953022c5ced1" />
| 1            | Y carriage stepper motor |     |
| 1            | X carriage               |<img width="816" height="535" alt="image" src="https://github.com/user-attachments/assets/fa71c8db-2c14-4270-a649-faf2eaf7d6ea" />
| 1            | Extruder coupling        | <img width="910" height="492" alt="image" src="https://github.com/user-attachments/assets/21613620-40f1-4a05-82c4-1d6b71b7058b" />
| 1 (per tool) | Toolhead                 |<img width="927" height="597" alt="image" src="https://github.com/user-attachments/assets/19b2ccc4-2ab2-40dc-970a-1fd5396f2856" />
| 1            | Extruder mechanism       |<img width="607" height="399" alt="image" src="https://github.com/user-attachments/assets/b570c79d-a953-4c9f-bea3-65194da70070" />
| 4            | Z axis bearing clamp     |<img width="815" height="679" alt="image" src="https://github.com/user-attachments/assets/293ec12e-89ed-4642-9345-cbd87039b55d" />
| 2            | Z stepper bracket        |<img width="882" height="596" alt="image" src="https://github.com/user-attachments/assets/4177f87a-acc6-4713-a8a9-84b64c39d4c3" />
| 4            | Z rod holder             |<img width="763" height="627" alt="image" src="https://github.com/user-attachments/assets/a2213d38-e17e-4504-9cd1-95e1a024b09e" />

### PCB
4 layer PCB that is 230x135mm:
<img width="1053" height="632" alt="image" src="https://github.com/user-attachments/assets/2bf4712b-93e3-4951-a62d-261e292cb73d" />

### Parts

1x BTT TFT35 V3.0 LCD

1x Arduino Mega 2560

6x Limit switch

4x 8mm smooth rods, 500mm length

1x 6mm smooth rod, 500mm length

6x 8mm steel balls

15x 2020 Aluminium profile 500mm length

2x 500mm T8 8mm lead leadscrew 


2x Anti-backlash leadscrew nut

2x Hotend (CR6-SE)

1x 4010 Fan

1x GT2 Kit

2x Aluminium Profile 90 degree connector

8x Aluminium profile corner connector

1x PSU (24v 360w+)

2x Screw terminals

1x N-channel Mosfet

1x 2x18 Pin header

16x Female pin headers

42x Male pin headers

5x A4988 Stepper drivers

1x 20 AWG Wire

1x 12 AWG Wire

3x Pogo connectors

1x 3d print bed

4x LM8UU bearing

2x Angular bearing

1x DC-DC step down Buck Converter

110x T Nuts

8x L Bracket

5x 100 nF Capacitor

5x 100 µF capacitor

1x Spring

6x Leadscrew fixing block

40x M5 screws and nuts

40x M4 screws and nuts

2x Shaft coupler 5x8mm




















