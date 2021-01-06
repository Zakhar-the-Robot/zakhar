# Devices

[Back to README](../README.md)

The main node - it is the node containing main operational program if the robot. Currently it is Raspberry Pi 4.

Zakhar has three devices connected to the main node:

- The Face Module - responsible for expressions and interaction with the user
- The Moving Platform - responsible for movement
- The Sensor Platform - responsible for perception

Each device stores data into registers and interacts with the main node via I2C (i2c conventions used in the project [are here](./i2c.md))

## The Face Module

The module represents a display with a preloaded set of facial expressions.

### FM - Registers

|Address    |Name   |Type       |Commentary |
|-          |-      |-          |-          |
|0x00       |CMD    | R/W       |Command register. The device is reading commands from here|
|0x01       |MODE   | RO        |The Mode register|

### FM - Commands

|Name   |Code  (ASCII)  |Commentary |
|-      |-              |-          |
|CALM   |0x30 (0)       |           |
|BLINK  |0x31 (1)       |           |
|ANGRY  |0x32 (2)       |           |
|HAPPY  |0x33 (3)       |           |
|SAD    |0x34 (4)       |           |

### FM - Source code

[https://github.com/an-dr/zakhar-face-module](https://github.com/an-dr/zakhar-face-module)

## The Moving Platform

It is a platform with two wheels rotating by DC motors. The platform also carries a positional sensor.

### MP - Registers

|Address    |Name           |Type       |Commentary |
|-          |-              |-          |-          |
|0x00       |CMD            | R/W       |Command register. The device is reading commands from here|
|0x01       |ARG            | R/W       |Optional argument of the command|
|0x02       |MODE           | RO        |The Mode register|
|0x03       |SPEED          | RO        |Current speed mode (0-3)|
|0x04       |ANGLE_X_S      | RO        |Sing of the angle for X (0,1)|
|0x05       |ANGLE_X        | RO        |THe value of the X angle (0-180)|
|0x05       |ANGLE_Y_S      | RO        |Sing of the angle for Y (0,1)|
|0x06       |ANGLE_Y        | RO        |THe value of the Y angle (0-180)|
|0x07       |ANGLE_Z_S      | RO        |Sing of the angle for Z (0,1)|
|0x08       |ANGLE_Z        | RO        |THe value of the Z angle (0-180)|

### MP - Commands

|Name           |Code (ASCII)   |Commentary                                 |
|-              |-              |-                                          |
|FORWARD        |0x77 (w)       |move                                       |
|BACKWARD       |0x73 (s)       |move                                       |
|LEFT           |0x61 (a)       |move, accepts an argument in degrees       |
|RIGHT          |0x64 (d)       |move, accepts an argument in degrees       |
|SHIVER         |0x71 (q)       |trembling during a second                  |
|STOP_KB        |0x20 ( )       |stop moving                                |
|STOP           |0xA0           |stop moving                                |
|SPEED0         |0x30 (0)       |set the speed mode                         |
|SPEED1         |0x31 (1)       |set the speed mode                         |
|SPEED2         |0x32 (2)       |set the speed mode                         |
|SPEED3         |0x33 (3)       |set the speed mode                         |
|MPU_CALIBRATE  |0x63 (c)       |recalibrate the positioning sensor         |
|TEST           |0x74 (t)       |used for testing purposes                  |

### MP: Source code

[https://github.com/an-dr/zakhar_platform](https://github.com/an-dr/zakhar_platform)

## The Sensor Platform

The platforms has three distance sensors and a light sensor

### SP - Registers

|Address    |Name           |Type       |Commentary |
|-          |-              |-          |-          |
|0x00       |CMD            | R/W       |Command register. The device is reading commands from here|
|0x01       |ARG            | R/W       |Optional argument of the command|
|0x02       |DIST_L         | RO        |Value of the left distance sensor in cm|
|0x03       |DIST_C         | RO        |Value of the central distance sensor in cm|
|0x04       |DIST_R         | RO        |Value of the right distance sensor in cm|
|0x05       |LIGHT_HI       | RO        |Value of the light sensor, higher part. The less the brighter|
|0x06       |LIGHT_LO       | RO        |Value of the light sensor, lower part. The less the brighter|

### SP - Commands

Not implemented

### SP: Source code

[https://github.com/an-dr/zakhar_sensors](https://github.com/an-dr/zakhar_sensors)
