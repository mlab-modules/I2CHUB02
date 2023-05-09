<!--- module --->
# I2CHUB02B
<!--- Emodule --->

I2CHUB02 is low voltage I2C multiplexer (hub) which allows you to divide I2C bus into 8 separate buses, where the user can switch and connect individual sub-bus differently. This can connect multiple I2Cs to the device, change the voltage levels, or disconnect a certain part of the bus when it is stuck. 

![I2CHUB02B](/doc/img/I2CHUB02B_top_big.jpg)

#### Parameters
| Parameter | Value | Description |
|-----------|-------|-------------|
| Power input | Max 5V | Can be extended with stabilizator IO |
| Integrated circuit | [TCA9548A](https://www.ti.com/lit/ds/symlink/tca9548a.pdf) | TexasInstruments |
| Buses | 1x master input, 8x slave output | Output can be interconnected by internal matrix |
| Dimensions | 40.13x50.29x16mm | 4x5 MLAB holes |

The number of I2C peripherals is growing and every circuit allows you to change I2C address and connect more component to one bus. This problem can be elegantly solved by this module. Another common problem is the difference in voltage levels. Currently usual voltage levels are 1.8V, 3.3V and 5V. The module is also prepared for this situation, it can work with different voltage levels by the master and slaves units. Furthermore, the module can be taken as a master circuit protection because it isolates master from external (slaves) devices. It is useful, for example, for sensors that are placed in outdoor environment. 

## Usage
Device can be controlled directly from your code. Writing the correct configuration into the switch register, the individual bus are interconnected. This is the simplest way, how to control device. 

### Linux computers
If you have a lack of I2C ports on your Linux computer (for example, on your OBC Raspberry Pi) or on your Linux computer with [USBI2C01A](https://github.com/mlab-modules/USBI2C01) converter, you have two options, how to control I2CHUB02B.

First option is control I2C switch directly from your code. For example from PyMLAB library.

Second, more relailible, option is use kernel multiplexer module. Linux at the kernel level will take care of the correct setting of I2C multiplex. In your Linux you will see 8 separate busses, with which you can communicate as they were a separate I2C bus on your computer.

<!--- description ---><!--- Edescription --->
            
