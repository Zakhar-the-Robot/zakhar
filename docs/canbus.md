# ZakharCAN (ver. 0.0.0)

The standard is based on the CAN bus protocol. Base CAN configuration:

- Bitrate: 125 kbits/s
- ID: 11 bits

In the standard there are several common parameters:

- Common timeout: 3 sec
- Dev ID size: 3 bits
- Data ID size: 4 bits

## Addressing

Each device uses 3 highest bits of the 11-bit ID for it's ID (0..7). The last 4 bits are used for different data types (0..15). Bits from 5 to 8 are reserved for future use.

```
 0b   X X X   X X X X   X X X X
    |-------|---------|---------|
     Address  Reserved  Data ID
```

Example of the device id 0x104:

- Device Address: 0x1
- Data ID: 0x4


## Standard Versioning

Note: **Until version 1.0.0 this section can be violated**

The version consists of 3 numbers: `Major`.`Minor`.`Patch` (e.g. 2.3.9)

- All devices using the same `Major` should be able to interact with each other
- All devices using the same `Minor` should be able to interact with each other and have to have the same feature set

## Internal Error Codes

|Code   |Name
|-      |-
|0x0    |OK
|0x1    |TIMEOUT_ERROR
|0xFF   |GENERAL_ERROR

## Data Types

|Data ID    |Name       |Description
|-          |-          |-
|0x0        |DeviceInfo |Used for presence declaration each **Common timeout** (see details bellow). In response for the request should return a data frame with `DATA[0]`:`Major`, `DATA[1]`:`Minor`, `DATA[2]`:`Patch`
|0x1        |           |Reserved for future
|0x2...0x15 |DeviceData |Device specific data defined by each device.

## Operations

### Send data

1. Send a CAN frame:
    - Identifier: `(DevID << 8) | DataID`
    - RTR: 0x0
    - Data length code (DLC): 0x0..0x8
    - Data: 0...8 bytes

### Request data

1. Send a CAN frame:
    - Identifier: `(DevID << 8) | DataID` (ID of the requested data!)
    - RTR: 0x1
    - Data length code (DLC): 0x0
    - Data: 0 bytes

2. Wait for a message with the requested ID during the **Common timeout**

3. If the message has come: `OK`, overwise: `TIMEOUT_ERROR`

### Declare the Presence

A device is online if it declares its presence on the line each **Common timeout**.

To declare being online the device should:

1. Send a CAN frame:
    - Identifier: `DevID << 8` (0xN00)
    - RTR: 0x0
    - Data length code (DLC): 0x0
    - Data: 0 bytes

## Compatible libraries

Libraries bellow are developed inside the Zakhar project and support ZakharCAN.

- Arduino: https://github.com/an-dr/zklib_arduino_canbus
- ESP-IDF: https://github.com/an-dr/zklib_espidf_canbus
- STM32: https://github.com/an-dr/zklib_stm32_canbus
