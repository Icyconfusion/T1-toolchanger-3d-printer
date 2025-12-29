# T1-toolchanger-3d-printer
A toolchanger 3d printer with large format build size and multiple tools for quick, easy multi-material printing.

The printer uses a swappable hotend mechanism to dock tools, removing the need to purge filament as in other multi-material systems. The idle toolheads sit on an aluminium extrusion. The X carriage, supported by linear rods, moves in and attaches to the toolhead, using kinematic couplings for repeatability. A magnetic pogo connector transfers power for the heter and thermistor.
<img width="890" height="646" alt="image" src="https://github.com/user-attachments/assets/f353a81a-1eab-4a17-8c4e-561f42465f79" />

Toolhead:
<img width="543" height="517" alt="image" src="https://github.com/user-attachments/assets/016b33a6-f840-4cb9-86a1-df751536feec" />

Assembly

The printer assembly is made by aluminium extrusions forming a cube, with corner connectors for mounting.
<img width="563" height="509" alt="image" src="https://github.com/user-attachments/assets/e9258c2b-e4d6-4b22-9a8f-e9b41eb924f0" />

To support the Y axis, L brackets and SK8 clamps are used to hold the Y axis rods, which in turn support the X axis.
<img width="285" height="188" alt="image" src="https://github.com/user-attachments/assets/2e80b816-7879-4229-bc31-7378d0a9f980" />

The Y axis is made up of two carriages, one either side of the X gantry. Each Y carriage uses two SCS8UU bearing blocks to slide along the linear rod, making the Y motion. One carriage is an idler, which the belt loops around a pulley. The other carriage is the stepper motor carriage, which uses a Nema 17 motor to drive the X axis belt. Both carriages hold SK8 clamps supporting the X linear rods.
Idler:
<img width="869" height="682" alt="image" src="https://github.com/user-attachments/assets/0a442deb-1370-4e7f-b6a6-48a2bc152c82" />

Stepper carriage:
<img width="845" height="528" alt="image" src="https://github.com/user-attachments/assets/ca6f3948-9639-4b8e-89a0-9c64379931e5" />
<img width="678" height="556" alt="image" src="https://github.com/user-attachments/assets/94e2eb2e-c6c4-4e62-abbd-3f23e7caca79" />

The X carriage is made of two parts: the main carriage, and the toolhead. The main carriage holds the fan and the extruder stepper motor. When the carriage comes into dock, a fixed arm pushes the extruder idle arm to the side. The filament slides into the extruder,and when docking is complete, the spring loaded, idle arm pushes back into the filament, creating good tension. 
<img width="764" height="604" alt="image" src="https://github.com/user-attachments/assets/5ad904bc-857b-488b-9857-69129a6abaad" />
The fan is a 4010 fan, which sits to the side and blows cool air through the heatsink fins. 
<img width="433" height="368" alt="image" src="https://github.com/user-attachments/assets/7eee1bd7-e5d4-4851-8e0e-4429b5385716" />
The belt post is located underneath the carriage.
<img width="570" height="352" alt="image" src="https://github.com/user-attachments/assets/2a602d1f-98de-4862-b642-29f524d01e63" />


The carriage sid of the coupling contains the 6mm smooth rods of the kinematic coupling. This is printed in two pieces, so that the rods can be put into grooves before the 'lid' of the coupling closes through screws. The pogo connector is also housed here.
<img width="609" height="688" alt="image" src="https://github.com/user-attachments/assets/b3a65658-4a6f-4a5e-bf3b-f52c7e877781" />
<img width="703" height="761" alt="image" src="https://github.com/user-attachments/assets/e64d68f9-87fb-452e-851e-f9bc541af3cf" />
<img width="891" height="700" alt="image" src="https://github.com/user-attachments/assets/9d94652b-2f6e-4e3e-a788-707e0d8b9a12" />

The toolhead uses steel balls to push into the kinematic coupling. The male side of the pogo connector is on the toolhead.
<img width="897" height="677" alt="image" src="https://github.com/user-attachments/assets/e1fc08a6-08ca-4877-b842-40cf4f343d8d" />
The hotend mounts to the two holes on the bottom.
<img width="857" height="580" alt="image" src="https://github.com/user-attachments/assets/8d47bb4d-4436-419e-ada4-070ecd14115c" />

The assembled X and Y axis is below:
<img width="813" height="563" alt="image" src="https://github.com/user-attachments/assets/9dbd5a8a-5f42-403c-8045-e1dff4bb9b9a" />

The Z axis involves the motion of the bed up and down. Originally, I had planned to move the hotend throughout all 3 axis, and the bed was fixed. I encountered many issues with reliably and consistently achieving motion of the hotend without the risk of flexing, so I pivoted to a bed Z axis. A leadscrew and two 8mm linear rods are used on each side, connected to an aluminium profile by a nut block and 3d printed clamps.
<img width="569" height="408" alt="image" src="https://github.com/user-attachments/assets/d25802ae-9f6f-48ec-a895-641b2fc667ca" />

WIP


Electronics

The printer uses a PCB motherboard to mount components including the MCU (Mega 2560), stepper drivers, LCD headers, and heater terminals. I decided on a 24v power supply as it was compatible with my heater. To give power to the PCB, I used a meanwell 24v 360W power supply.
<img width="220" height="220" alt="image" src="https://github.com/user-attachments/assets/e40018ba-65bb-4718-b196-dc43032a6b18" />

This connects through wires to screw terminals on the board, which then distribute power across the PCB. Because of the power requirements, I decided to use a 4 layer PCB as I couldn't route signal traces through the power and GND traces. The top and bottom layers of the PCB are the power layers. Power runs from the PSU input to the heater screw terminal, and throughout the board. It is converted to 5v through a buck converter. The Hotend heater is powered through a screw terminal, and controlled by the mosfet next to its terminal. The hotend fan is controlled by a header, it is in an always on state.
<img width="655" height="384" alt="image" src="https://github.com/user-attachments/assets/484874a6-35cf-4dcd-a01a-cc379433830f" />

The signal traces from the drivers, limit switches, thermistor and LCD are on the second and third layers.
<img width="645" height="394" alt="image" src="https://github.com/user-attachments/assets/c286e127-8904-41be-883f-37167d5bf014" />

The MCU is a mega 2560. I chose this because of its large availability of pins, enabling future upgrades and fitting all components. The stepper drivers are A4988s, which have microstepping up to 1/16. All microstep pins are connected to 5v, making the configuration 1/16. The limit switches, thermistor and lcd connect to headers.

The power for the stepper drivers is 24v. To reduce the effect of spikes, a small 100nf capacitor is used between the 24v and gnd supply of each driver. For larger spikes, a 100 uF capacitor is also placed between 24v and gnd of each driver.
<img width="277" height="402" alt="image" src="https://github.com/user-attachments/assets/eb339b2d-3b99-4bf2-b4e5-5e703c932cf7" />

The LCD is the main user interface of the printer.


















