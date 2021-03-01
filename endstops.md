---
description: This Document was copied directly from Marlin.org Docs
---

# Endstops

Endstops or limit switches are used on every moving axes of a 3D printer. The following chapter will provide information on:

* Purpose of the endstop
* Types of endstops
* Configuring endstops and probes
* Electromagnetic Interference / Electric Noise impact on endstops

## Endstops purpose <a id="endstops-purpose"></a>

Endstops fulfill two important functions in a 3D printer: Reference system for the axes system and safety.   


### Reference for the axes system <a id="reference-for-the-axes-system"></a>

After powering up a 3D printer the printer’s controller board does not know at which position its axes are. Marlin indicates this by blinking question-marks in place of X, Y and Z on the LCD screen \(v1.1.8 and older\) or blinking ‘?’ in place of the coordinates besides X,Y and Z \(Marlin v1.1.9 / v2.0.0 and newer\).

This means the system needs first to establish its starting point of the physical \(machine\) coordinate system, a process called _Homing_. Homing can be initiated either via the [G28 G-code](https://marlinfw.org/docs/gcode/G028.html) or via the LCD controller.

![real](https://marlinfw.org/assets/images/docs/hardware/endstops/not_homed.jpg)

Illustration 1: LCD indication not homed axes \(Marlin &lt;= v1.1.8\)

### Safety <a id="safety"></a>

The other important aspect of an endstop is protecting the hardware from damage. Should any movement try to exceed the physical limits of the machine, the endstop will cut the movement.

## Types of endstops <a id="types-of-endstops"></a>

There are two main types of endstops. Hardware endstops and software endstops.

### Hardware endstops <a id="hardware-endstops"></a>

Hardware endstops are electrically connected to the endstop ports of the printer control board and will provide a signal when the endstop condition is met.

![endstop\_types](https://marlinfw.org/assets/images/docs/hardware/endstops/endstop_types.png)

Illustration 2: Most common endstops \(left to right\): Micro switch, optical endstop \(light barrier\), hall sensor \(magnetic\)

Regardless of the type the basic way of working is the same:

* A typically 5 Volt signal \(High\) drops to 0 Volt \(Low\): Normally closed \(NC\) switch
* A 0 Volt signal \(Low\) rises to 5 Volts \(High\): Normally open \(NO\) switch

**Note**

Since endstops are a safety feature NC switches are recommended as they will halt the machine should the switch be damaged, e.g. by a broken cable etc.

#### Probe as Z-Endstop <a id="probe-as-z-endstop"></a>

Probes can act like an endstop for the minimum Z-axis. While the typical endstop has a fixed position, the probe is mounted on the print-head and can freely move around the bed.

![probes](https://marlinfw.org/assets/images/docs/hardware/endstops/probes.png)

Illustration 3: Common probe types: Inductive \(left\), solenoid touch probe \(right\)

Some aspects of probe configuration are considered in this endstop introduction. Further reading is provided in the Chapter [Probes Configuration](https://marlinfw.org/docs/configuration/probes.html), [Auto Bed Leveling](https://marlinfw.org/docs/features/auto_bed_leveling.html) and [Unified Bed Leveling](https://marlinfw.org/docs/features/unified_bed_leveling.html).

### Software Endstops <a id="software-endstops"></a>

Typically 3D printers are only equipped with hardware endstops on one side of each axis \(Minimum or Maximum of the respective axis\). As discussed above this is used to determine the starting point \(origin\) of the machine coordinate system.

In order to also protect the other side of the axes software endstops should be defined in the firmware via the `#define MAX_SOFTWARE_ENDSTOPS` / `#define MIN_SOFTWARE_ENDSTOPS` directive. This then uses the value from `#define [XYZ]_MAX_POS` / `#define [XYZ]_MIN_POS` to determine the maximum distance between the physical endstop and the software commanded stop of the axis. Software endstops can be \(de-\)activated via the [M211 G-code](https://marlinfw.org/docs/gcode/M211.html).

## Configuring endstops and probes. <a id="configuring-endstops-and-probes"></a>

### Background <a id="background"></a>

By default, slicers generate G-code that places the base of a printed model at z=0 and build upwards from there. The result of homing the z-axis should thus place the build surface at the z=0 plane. After homing in z, the hardware z endstop is deactivated \(unless you have set `ENDSTOPS_ALWAYS_ON_DEFAULT` in configuration\_adv.h, which can be overridden by [M120](https://marlinfw.org/docs/gcode/M120.html), [M121](https://marlinfw.org/docs/gcode/M120.html)\), but to protect the hardware a software endstop is activated \(which in turn can be overridden by [M211](https://marlinfw.org/docs/gcode/M211.html) S0\). This software endstop is located at `Z_MIN_POS` \(defined in configuration.h\) . This is normally at z=0 at the nominal location of the bed. Note that when using bed-leveling, this software endstop is applied to the _uncorrected_ slicer generated z-values. This allows printing into the hollows of the bed, where z &lt; 0.

We now describe some common Cartesian printer configurations, with and without bed-leveling probes.

### Microswitch endstop - no bed leveling probe. <a id="microswitch-endstop---no-bed-leveling-probe"></a>

Here we mechanically adjust the bed and possibly additionally the microswitch trigger point to level the bed surface as close as we can to the z=`Z_MIN_POS` \(normally = 0\) plane. The z location of the hardware \(microswitch\) trigger point defaults to the value of `Z_MIN_POS`. It is possible however to use a microswitch trigger point above the bed by setting `MANUAL_Z_HOME_POS` to the z-coordinate of the trigger point. See [here](https://marlinfw.org/docs/hardware/endstops.html#measure_offsets). Having the trigger point below the bed makes little sense as the nozzle would crash into the bed before the microswitch triggered on homing.

### Probe used for homing and bed-leveling. <a id="probe-used-for-homing-and-bed-leveling"></a>

The probe should be mounted so that its trigger point lies below the extruder nozzle. `Z_PROBE_OFFSET_FROM_EXTRUDER` \(negative!\) is this vertical offset. This offset is applied by the firmware when homing in order to properly reference the coordinate system to the nozzle position. To measure this see [here](https://marlinfw.org/docs/hardware/endstops.html#measure_offsets). For a mechanical probe like a BL-Touch, this offset is geometrically fixed. For a remote sensing probe \(e. g. inductive or capacitive\), the offset might vary with bed material. You can tweak it using [M851](https://marlinfw.org/docs/gcode/M851.html).

![Fig. 1](https://marlinfw.org/assets/images/docs/hardware/endstops/bltouchwithbltouch.png)

Figure 1: Example configuration using BL-Touch for both homing and probing.

The process of bed-leveling generates an array of z-values of the bed heights at the probed points. Marlin interpolates these values to estimate the bed height at any given x/y location. Figure 1 illustrates the situation. While probing, all endstops are turned off so that the probe can reach into the valleys of the bed. To protect the machine in case of the probe failure during probing set `Z_PROBE_LOW_POINT` to limit the probing depth.

### Microswitch used for homing, probe for bed leveling. <a id="microswitch-used-for-homing-probe-for-bed-leveling"></a>

When homing, the printer is not protected against hardware endstop failure. This configuration uses a perhaps more reliable microswitch for homing, reserving the probe for bed leveling, where `Z_PROBE_LOW_POINT` provides failure protection. The configuration is illustrated in Fig. 2, requiring the use of both `MANUAL_Z_HOME_POS` and `Z_PROBE_OFFSET_FROM_EXTRUDER` Ideally, with an uneven bed, `MANUAL_Z_HOME_POS` should be adjusted so that z=0 lies halfway between the highest and lowest parts of the bed. This makes the maximum bed correction as small as possible.

![Fig. 2](https://marlinfw.org/assets/images/docs/hardware/endstops/bltouchwithmicroswitch.png)

Figure 2: Example configuration using a microswitch for homing, BL-Touch for bed-leveling probe.

### Measuring offsets. <a id="measuring-offsets"></a>

To measure an offset between a trigger point and the bed, lower the nozzle to the trigger point \(by homing, if it’s the homing device\), and note the z-value. Now turn off the software endstop temporarily \(with M211 S0\) to enable lowering the nozzle further down to the bed. Note the z again. The difference is the height of the respective trigger point above the bed.

