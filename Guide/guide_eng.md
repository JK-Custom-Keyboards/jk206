<h1 align="Left"> Assembly Guide </h1>

<h2 align="Left"> 1. Base Materials</h2>

To build your own JK206, whether in its macropad version or its 50% keyboard version, you will need the following materials:

|                           | Macropad                                    | Keyboard                                    |
| ------------------------- | ------------------------------------------- | ------------------------------------------- |
| MX switches               | 15 - 20 (depending on the number of encoders) | 57 - 60 (depending on the number of encoders) |
| Kailh hotswap sockets     | 15 - 20 (depending on the number of encoders) | 57 - 60 (depending on the number of encoders) |
| EC11 encoders             | 0 - 5                                       | 0 - 3                                       |
| 1N4148 diodes             | 20                                          | 60                                          |
| JK206 PCB                 | 1                                           | 3                                           |
| Raspberry Pi Pico         | 1                                           | 1                                           |
| OLED SSD1306 Display (0.91 or 0.96 inch) | 1 (optional but recommended) | 1 (optional but recommended) |
| Case                      | User preference                             | User preference                             |
| Keycaps                   | User preference                             | User preference                             |

Later on, we will discuss the different case types and the specific materials required for each one.

In addition to the materials above, you will also need a soldering iron and solder to complete the assembly. Soldering flux is optional, but it is always helpful when soldering.

<h2 align="Left"> 2. Obtaining the PCB </h2>

To obtain the PCBs, simply take the PCB Gerber file (provided as a .zip archive) and send it to a PCB manufacturing service. Just keep in mind that the minimum order quantity is usually 5 PCBs.

<h2 align="Left"> 3. Preparing the PCB </h2>

Once you have all the required materials, it is time to start soldering. Before soldering any components, keep the following considerations in mind depending on whether you are building a macropad or a keyboard.

<h3 align="Left"> For the macropad </h3>

If you are building the macropad, you must "enable" the option to use additional encoders on the PCB. To do this, simply connect the PCB pads shown in the image so that each pad is connected to the one immediately to its left or right.

![guide_01](/assets/images/guide_01.png)

The result should look like this:

![guide_02](/assets/images/guide_02.png)

This can be done using UTP wire, a jumper wire, or simply by bridging both pads directly with solder. As long as there is electrical continuity between the two points, it will work.

<h3 align="Left"> For the keyboard </h3>

If you are building the keyboard, you must connect the 3 PCBs together. To do this, both rows and columns need to be connected. The columns are connected along the top edge of the PCBs as shown below:

![guide_03](/assets/images/guide_03.png)

The rows are connected by bridging the pads located on the sides of each PCB to the adjacent pad on the neighboring PCB. This must be done at both PCB junctions.

![guide_04](/assets/images/guide_04.png)

Do not forget that, to avoid assembly problems later on, all 3 PCBs must be fully joined together and properly aligned.

<h2 align="Left"> 4. Soldering Components </h2>

With all the preparations completed, it is time to solder the components into place. Start with the diodes. They must be installed so that the side with the stripe faces downward, as indicated on the PCB itself.

![guide_05](/assets/images/guide_05.jpg)

Next, solder the hotswap sockets and the encoders. Keep in mind that hotswap sockets should not be installed in locations where encoders will be placed. Depending on whether you are building a keyboard or a macropad, consider the following:

<h3 align="Left"> For the macropad </h3>

Encoders can be placed on the macropad as shown below:

![guide_06](/assets/images/guide_06.png)

The green areas in the diagram indicate the positions where encoders can be installed. It is not recommended to place two encoders in positions sharing the same number, since limitations of both the Raspberry Pi Pico and the PCB design will cause them to be detected as a single encoder. Therefore, the following encoder layouts are recommended:

![guide_07](/assets/images/guide_07.png)
![guide_08](/assets/images/guide_08.png)

<h3 align="Left"> For the keyboard </h3>

Although it is technically possible to install encoders on the left PCB in positions 1, 2, and 3 shown in the previous section, for usability reasons it is recommended to install only one encoder in the upper-left corner.

With that in mind, begin soldering the hotswap sockets and any encoders you plan to install. You may encounter some difficulty soldering the sockets, but being generous with the solder should help avoid major issues.

![guide_09](/assets/images/guide_09.jpg)
![guide_10](/assets/images/guide_10.jpg)
![guide_11](/assets/images/guide_11.jpg)

The only remaining components are the Raspberry Pi Pico and the OLED display. The Raspberry Pi Pico must have header pins soldered on in order to be mounted on the PCB. If your Pico does not already have pins installed, you will need to solder a set of header strips to it before mounting it.

![guide_12](/assets/images/guide_12.png)

![guide_13](/assets/images/guide_13.jpg)

As for the OLED display, its placement depends on the specific display you are using. A 0.91-inch rectangular display is mounted above the Raspberry Pi, while a 0.96-inch square display is mounted to the right of it.

![guide_14](/assets/images/guide_14.jpg)
![guide_15](/assets/images/guide_15.jpg)

Note: For the keyboard assembly, both the Raspberry Pi Pico and the OLED display must be installed only on the left PCB. The PCB design is not intended to support them in any other location.

<h2 align="Left"> 5. Assembly </h2>

At this point, the process differs depending on the type of case assembly you want to use.

<h3 align="Left"> For the sandwich-case assembly </h3>

For this relatively simple assembly method, you will need the following materials:

|                                   | Macropad                                    | Keyboard                                    |
| --------------------------------- | ------------------------------------------- | ------------------------------------------- |
| M2 8mm brass standoffs            | 4                                           | 4-12                                        |
| M2 5mm flat-head screws           | 8                                           | 8-24                                        |
| Acrylic plates (preferably 1.5 mm thick, but 2 mm would also work)      | [1 pair](/Cases/Sandwich-Case/Macropad) | [1 pair](/Cases/Sandwich-Case/Keyboard) |
| Anti-slip feet                    | User preference                             | User preference                             |

This assembly guide is primarily focused on the macropad version, but the JK206 keyboard assembly is very similar and this guide should work equally well for it.

To begin assembling either the keyboard or the macropad, take the bottom plate and attach anti-slip feet according to your preference.

![guide_16](/assets/images/guide_16.jpg)

Once that is done, attach the standoffs to the bottom plate.

![guide_17](/assets/images/guide_17.jpg)

![guide_18](/assets/images/guide_18.jpg)

Note: The top and bottom plates of the full keyboard version of the JK206 provide mounting holes for up to 12 standoffs. However, I recommend using only 4 (the positions immediately after the outermost mounting points), although additional standoffs can be installed if a stiffer typing feel is desired.

With the bottom plate prepared, the next step is to secure the PCB to the top plate using the switches. To do this, install a couple of switches into the plate and then insert them into the PCB.

![guide_19](/assets/images/guide_19.jpg)

![guide_20](/assets/images/guide_20.jpg)

After that, install the remaining switches.

![guide_21](/assets/images/guide_21.jpg)

Now that the plate, PCB, and switches are connected together, you can screw the top plate onto the standoffs previously installed on the bottom plate.

![guide_22](/assets/images/guide_22.jpg)

And with that, your keyboard or macropad is ready. All that remains is to install your preferred keycaps and enjoy it.

![guide_23](/assets/images/guide_23.jpg)

<h4 align="Left"> Recommended Mods: </h4>

In general, both the tape mod and PE foam work well with this assembly. Beyond that, there is not much else that can be modified.

<h2 align="Left"> 6. Firmware Installation </h2>

If you want the default configuration for the keyboard or macropad, first download the [corresponding .uf2 file](/assets/uf2%20files/). 

Once you’ve downloaded the .uf2 file, connect your keyboard or macropad to your PC while keeping pressed the button located on the top of the Raspberry Pi Pico. This will make a new storage drive appear in your file manager with a name similar to RPI-RP.

Open the drive and copy/paste the .uf2 file you downloaded there. At that moment, the Raspberry Pi Pico should reboot, and the keyboard or macropad will now be working.

And with that, your JK206 should now be fully functional :D