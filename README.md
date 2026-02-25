# T1-toolchanger-3d-printer
A toolchanger 3d printer with large format build size and multiple tools for quick, easy multi-material printing that uses marlin as the firmware.
<img width="815" height="717" alt="image" src="https://github.com/user-attachments/assets/38e58c9f-eab8-431e-9f41-fe0b2112735e" />


**Note to reviewer:** Since submitting project for review I have updated the BOM (haven't changed products, just updated the prices). The new bom is more than what was in the review, but I have multiple discounts and coupons (that I have also tested) which bring it back down to what I mentioned in review. Thank you :) Also, in regards to firmware, the entire marlin zip folder (must be a zip) is in the firmware folder, but I have copied all files that have been edited and/or relevant (e.g config and ino files) as well into the firmware folder for the reviewer to view. I was instructed to do it this way by other reviewers in similar projects. Thanks.

I made this project as I had been looking to make a 3d printer. I wanted to be able to print in different colours, without the added cost of AMS systems. It was also a good opportunity to learn about using programs like fusion and Kicad, which I have limited experience with, as well as learning about electronic components. I created this project without a guide, using my own ideas to combat problems, with some inspiration from existing products e.g using linear rods.

Note: The assembly files are too large to upload to Github directly. Instead I have put the assembly .step file and .f3z file into a zipped folder named: Printer assembly.zip 

I have also uploaded the same step file as a zipped folder called printer assembly Step.zip, and an STL file called printer assembly STL.zip, just to be sure.


The printer uses a swappable hotend mechanism to dock tools, removing the need to purge filament as in other multi-material systems. The idle toolheads sit on an aluminium extrusion. The X carriage, supported by a V slot extrusion, moves in and attaches to the toolhead, using kinematic couplings for repeatability. A magnetic pogo connector transfers power for the heter and thermistor.
<img width="386" height="479" alt="image" src="https://github.com/user-attachments/assets/56d7a2ce-660d-4bcc-960f-2b4d483141ab" />


Toolhead:
<img width="587" height="531" alt="image" src="https://github.com/user-attachments/assets/8d0bf8e6-a7aa-4e4d-ba47-985909c1d0bc" />
<img width="633" height="535" alt="image" src="https://github.com/user-attachments/assets/5cbeeb0f-5585-4df4-8152-2cf6aed01155" />


# **Assembly**

The printer assembly is made by aluminium extrusions forming a cube, with corner connectors for mounting.
<img width="832" height="813" alt="image" src="https://github.com/user-attachments/assets/4347bbd8-eae0-4dbe-9538-16369c4790b9" />


To support the Y axis, V slot 2020 aluminium extrusions are used as rails holding a gantry, which in turn supports the X axis.
The Y axis is made up of two carriages, one either side of the X gantry. Each Y carriage uses a gantry plate with wheels to slide along the extrusions, making the Y motion. One carriage is an idler, which the belt loops around a pulley. The other carriage is the stepper motor carriage, which uses a Nema 17 motor to drive the X axis belt. Both carriages hold 90 degree connectors supporting the X extrusion.
Idler:<img width="780" height="571" alt="image" src="https://github.com/user-attachments/assets/6c0c5534-d9d8-4d2f-9483-c314ea633a82" />



Stepper carriage:
<img width="495" height="442" alt="image" src="https://github.com/user-attachments/assets/3f29152c-e13c-4185-9b21-6d38d537004d" />


The X carriage is made of two parts: the main carriage, and the toolhead. The main carriage holds the fan and the extruder stepper motor. When the carriage comes into dock, a fixed arm pushes the extruder idle arm to the side. The filament slides into the extruder,and when docking is complete, the spring loaded, idle arm pushes back into the filament, creating good tension. 
<img width="764" height="604" alt="image" src="https://github.com/user-attachments/assets/5ad904bc-857b-488b-9857-69129a6abaad" />

The fan is a 4010 fan, which sits to the side and blows cool air through the heatsink fins and also onto the part/top layer. 
<img width="422" height="467" alt="image" src="https://github.com/user-attachments/assets/9985ac70-1946-43e4-9276-e3109f47b17f" />



The belt post is located behind the carriage.

<img width="287" height="468" alt="image" src="https://github.com/user-attachments/assets/93a12727-6598-4825-a860-10cf248974ef" />





The carriage sid of the coupling contains the 6mm smooth rods of the kinematic coupling. This is printed in two pieces, so that the rods can be put into grooves before the 'lid' of the coupling closes through screws. The pogo connector is also housed here.
<img width="728" height="532" alt="image" src="https://github.com/user-attachments/assets/0fec19f4-bb58-4467-8d14-0ed86516eca2" />
<img width="737" height="590" alt="image" src="https://github.com/user-attachments/assets/575ff1e0-80c7-42ca-b58a-f8f6172730de" />

The toolhead uses steel balls to push into the kinematic coupling. The male side of the pogo connector is on the toolhead.
<img width="685" height="603" alt="image" src="https://github.com/user-attachments/assets/a49b23d0-b526-4493-a18b-31fe9b0227ed" />

The hotend mounts to the two holes in the middle.


The Z axis involves the motion of the bed up and down. Originally, I had planned to move the hotend throughout all 3 axis, and the bed was fixed. I encountered many issues with reliably and consistently achieving motion of the hotend without the risk of flexing, so I pivoted to a bed Z axis. A leadscrew and two 8mm linear rods are used on each side, connected to an aluminium profile by a nut block and 3d printed clamps.
<img width="600" height="679" alt="image" src="https://github.com/user-attachments/assets/d6711d7c-f21c-45e6-85c4-b537f164d5d2" />


The bed frame is a square made of aluminium extrusions, held together by 90 degree corner connectors. The 6mm aluminium print bed sits on top of that, threaded into T nuts in the profiles.
<img width="617" height="630" alt="image" src="https://github.com/user-attachments/assets/75dc115a-3a3c-4c20-b868-0830292d1216" />
<img width="1004" height="270" alt="image" src="https://github.com/user-attachments/assets/4782ae3d-23fc-4430-9a25-69dddad5791c" />
<img width="657" height="303" alt="image" src="https://github.com/user-attachments/assets/5f6981f7-08a3-4a04-ab67-2ce45387adbb" />
<img width="880" height="356" alt="image" src="https://github.com/user-attachments/assets/f8bb2860-a8e1-437e-bc85-dd8f3af04aad" />

Toolchanging mechanism. Tools are held on the toolchanger rack, installed with T nuts on an aluminium profile. L shaped hooks hold the tools in place, using knobs on the tools.Wwhen the tool slides in sideways, the knob/tool will be separated from the carriage by the hook Then the carriage will move backwards, detaching the magnets in the connectors, and pulling the tool off the rack. To attach, it simply presses the carriage onto the tool, pushes it back and slides out.
<img width="1218" height="755" alt="image" src="https://github.com/user-attachments/assets/aa4679f3-8cc3-4fd2-b12e-470ec22481d3" />
<img width="829" height="574" alt="image" src="https://github.com/user-attachments/assets/d9235e37-5484-43c7-8e78-34b6170f11a6" />
<img width="711" height="576" alt="image" src="https://github.com/user-attachments/assets/905b5d3b-618c-49c9-a6e7-a94856ecbdc0" />





# **Electronics**
<img width="1150" height="734" alt="image" src="https://github.com/user-attachments/assets/768ac75e-59ce-4b11-b38a-0186ca5c3015" />


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

The printer uses the latest version of marlin firmware, which enables the use of G-code. The general firmware of the printer is fairly standard and straightforward, as marlin is just configured to the printer dimensions and layout. The firmware has been edited to match the printer configuration with things like pin usage, limits, dimensions, and rough speeds/acceleration (these will require testing following assembly).

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
| 1            | New X carriage               |<img width="783" height="730" alt="image" src="https://github.com/user-attachments/assets/c879e0f8-5557-4a87-a9da-11e6d7c7c95a" />

| 1 (per tool) | Toolhead                 |<img width="645" height="530" alt="image" src="https://github.com/user-attachments/assets/a53846ff-6eb0-443b-972b-224049141d93" />

| 4            | Z axis bearing clamp     |<img width="815" height="679" alt="image" src="https://github.com/user-attachments/assets/293ec12e-89ed-4642-9345-cbd87039b55d" />
| 2            | Z stepper bracket        |<img width="882" height="596" alt="image" src="https://github.com/user-attachments/assets/4177f87a-acc6-4713-a8a9-84b64c39d4c3" />
| 4            | Z rod holder             |<img width="763" height="627" alt="image" src="https://github.com/user-attachments/assets/a2213d38-e17e-4504-9cd1-95e1a024b09e" />
| 2       | Nema 17 parallel mount| <img width="459" height="632" alt="image" src="https://github.com/user-attachments/assets/acafebbb-9525-4af0-b78a-80282fd7561e" />

|4 | plain limit switch bracket| <img width="547" height="637" alt="image" src="https://github.com/user-attachments/assets/535abee3-f005-48a5-8461-f3b642c4d328" />

|4| z rod top bracket|<img width="683" height="472" alt="image" src="https://github.com/user-attachments/assets/a7e2ab64-90dd-4a99-9ed3-44ca7b5bf581" />
|1| toolchanger rack| <img width="829" height="574" alt="image" src="https://github.com/user-attachments/assets/5888e56c-90b1-47cb-81b0-42fc334f1d6b" />



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




















