# AT34C04_for_STM32_master
This is a simplified driver for the AT34C04 I2C EEPROM. It offers the functionality to safe some data types and retrieve them.

This driver abstracts the Physical EEPROM Registers into virtual registers at the cost of storage efficiency.

 It offers functions to safe the data types
 - unint8_t
 - uint16_t
 - uint32_t
 - floats
 
 The header file includes an example on how to inegrate and use the driver
