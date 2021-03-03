---
description: Latest problems
---

# JohnBot Issues

In this series on the Lulzbot transformation to the JohnBot, I am getting very close to a first print. I have the firmware installed the electronics all wired up and the LCD screen showing the right information. I also have Octoprint running through the Raspberry Pi which is powered by the printer itself. Things are looking up at least I thought!

I am currently having issues with setting up the end stops which are an integral piece in getting the machine to print properly. I know we have a sensorless homing option but I would like to get things working mechanically correct first and then set up sensorless homing. 

The first issue is the actual attachment of the z-axis end stop. I had come up with a tricky and complicated mount which I now realize is not going to work. Usually, the simple method works best and this is no exception. I did some research and now I think I have this working well. After all that I come to find out that the y-axis is homing in the wrong direction. 

Homing definition from [MakerBot](https://support.makerbot.com/s/article/What-is-Homing): The process by which a 3D printer determines its extruder’s location in three-dimensional space. Homing occurs before each print and involves the X, Y, and Z-Axis motors jogging until the axial limit has been reached. The recorded homing data determines how high the printer will position the build plate at the start of a print, and where on the XY plane the extruder will start the print.

I have read much on this topic today and have found out there are a few ways to try and fix this. My first attempt is to change the firmware. changing Y_\__HOME_\__DIR from -1 to 1 is shown on the Marlin site. I changed this and tried to compile but was shown an error. I needed to also comment out line 624 //\#define USE\_YMIN\_PLUG and uncomment line 627 define USE\_YMAX\_PLUG. 

The above has been the solution for the JohnBot. I have read some say this is not the proper solution but I have tried numerous things and this is what's working. My next hurdle will be getting the bed level again and continuing through the TeachingTechs' awesome [calibration site](https://teachingtechyt.github.io/index.html).

 

