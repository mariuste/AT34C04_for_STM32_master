# AT34C04_for_STM32_master
This is a simplified driver for the AT34C04 I2C EEPROM. It offers the functionality to safe some data types and retrieve them.

This driver abstracts the Physical EEPROM Registers into virtual registers at the cost of storage efficiency.

 It offers functions to safe the data types
 - unint8_t
 - uint16_t
 - uint32_t
 - floats
 
# Example usage
## USER CODE Includes
```
/* USER CODE BEGIN Includes */

// EEPROM
#include "AT34C04.h"

/* USER CODE END Includes */
```

## USER CODE PV
```
/* USER CODE BEGIN PV */

// EEPROM Object
AT34C04 myAT34C04;

/* USER CODE END PV */
```

## USER CODE 2
```
/* USER CODE BEGIN 2 */

// Initialize EEPROM
AT34C04_Initialize(
		&myAT34C04, // EEPROM object
		0x0,		// Address pin A0 value
		0x0,		// Address pin A1 value
		0x0,		// Address pin A2 value
		&hi2c2		// I2C Handle
);

/* USER CODE END 2 */
```

## USER CODE WHILE
```
/* USER CODE BEGIN WHILE */

// Variables
uint8_t myVirtualRegister = 0x10;

// Read_From EEPROM
uint8_t a8 = 0x00;
uint16_t a16 = 0x0000;
uint32_t a32 = 0x000000;
float f32 = 0.0f;


AT34C04_Read_VReg_unit8(&myAT34C04, myVirtualRegister, &a8);
AT34C04_Read_VReg_unit16(&myAT34C04, myVirtualRegister, &a16);
AT34C04_Read_VReg_unit32(&myAT34C04, myVirtualRegister, &a32);
AT34C04_Read_VReg_float(&myAT34C04, myVirtualRegister, &f32);

// Write to EEPROM
// the exact same except with "Write" instead of "Read" in the function name.
/* USER CODE END WHILE */
```
