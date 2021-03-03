---
description: Which Way is Up?
---

# X/Y&Z Direction of 3d Printer

I don't like to admit it axis direction has tripped me up from the beginning. In my opinion, the X/Y&Z direction on a 3d Printer has always seemed backward. 

**The basics of three-dimensional space:** Three coordinates denote a point in space. The linear coordinates are X, Y, and Z. The coordinates supply information about a single direction or axis and are perpendicular to the other two. One single axis can indicate a position along a line. The three axes allow us to situate an object in space.

Every FDM 3D printing system requires at least three different orthogonal axes to create three-dimensional objects. Machine models use other movement systems to maneuver the hot end to deposit the melted filament accordingly. The layer-by-layer deposition process depends on the axes’ movement, which directly influences your prints, including quality and speed.

Current 3D printers use three kinds of systems:

* The print bed: a 3D printer has a  [printing head \(extruder\)](https://www.sculpteo.com/en/glossary/extruder-definition/) and a print bed. In this case, the extruder doesn’t move, but the print bed does. The x and y axes do not move, and the z-axis does. 
* The crane: in this case, the extruder moves, not the print bed. Therefore the x and y axes move while the z-axis remains fixed. 
* Deltabot: the printing head moves by three movable control rods. The x, y, and z-axes are all movable, which requires a complex motor to increase precision and printing speed. 

On most printers \(Cartesian Style\) the x-axis moves left and right. The y-axis moves forward and back and the z-axis moves up and down. The printer stays in sync with the software through the firmware which sets these directions. Wrongly wired stepper motors or incompatible end stop settings will make things travel in the wrong way. We will go through these possibilities in another doc.

