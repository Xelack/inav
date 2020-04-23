# Board - RACE32F3

The Holybro Race32F3 board (RACE32F3) is very similar of SPRACINGF3 and the board is designed specifically for Cleanfligh.

Full details available on the website, here:

http://www.holybro.com/?s=RACE32


## Hardware Features

* Hybrid plug setup, JST plugs and through holes for pin connectors. No compromise on ports. Full feature support of all modules, all at the same time.
* Black box flight log recorder — high capacity on-board storage for easy tuning optimization, flight replay, and troubleshooting.
* Next-generation STM32 F3 processor with faster ARM-Cortex M4 core with floating point hardware unit for efficient flight calculations. Loop times are up to twice as fast as previous-generation STM32F1 based boards.
* Stackable design - perfect for integrating with OSDs and power distribution boards.
* All plugs are located on the same side of the board for a more space-efficient design.
* 4 PWM 3Pin though-holes connectors, 8 PWM JST Plug for ESCs, Servos and legacy receivers. Full support for OneShot ESCs.
* Supports SBus, SumH, SumD, Spektrum1024/2048, XBus, PPM, PWM receivers. Built-in inverters.
* Dedicated output for programmable LEDs.
* PWR ports for voltage and current.
* Sonar support for precision low-altitude position hold.
* Buzzer port for wamings and notifications.
* Barometer mounted on the bottom of the board for easy wind isolation.
* Configuration of the flight controller via a cross-platform GUI (Windows/OSX/Linux).
* upports a variety of aircraft, tricopters, quadcopters, hexacopters, octocopters, planes and more.
* Micro USB socket.
* 2x6pin JST-SH sockets (PWR,GPS/12C).
* 3x4pin JST-SH sockets (OSD/TELEMTRY,UART3/ SERIAL RX,LED,RSSI)
* 1x8pin JST-SH sockets (PPM,PWM,5V,GND)
* 1x1Opin JST-SH sockets (ESC/Servo connections, 5V, GND).
* 4x3pin though-holes for pin headers for ESC/Servo connections.

## Serial Ports

| Value | Identifier   | RX           | TX           | 5v Tolerant | Notes                                                                                       |
| ----- | ------------ | ------------ | ------------ | ----------- | ------------------------------------------------------------------------------------------- |
| 1     | USART1       | PA10         | PA9          | YES         | Internally connected to USB port via CP2102 IC.  Also available on a USART1 JST connector and on through hole pins. |
| 2     | USART2       | PA15         | PA14         | YES         | Available on USART2 JST port only. |
| 3     | USART3       | PB11 / IO2_3 | PB10 / IO2_4 | NO          | Available on IO_2, USART3 JST port and through hole pins. |

* You cannot use SWD and USART2 at the same time.
* You may encounter flashing problems if you have something connected to the USART1 RX/TX pins.   Power other devices of and/or disconnect them.

## Pinouts

Full pinout details are available in the manual, here:

http://www.holybro.com/manual/Race32%20Manual%20v1.0.pdf

### PWM/PPM RC_IN (Fig. ref3)

The 8 pin IO_1 connector has the following pinouts when used in RX_PARALLEL_PWM mode.

| Pin | Function            | Notes                                        |
| --- | --------------------| -------------------------------------------- |
| 1   | Ground              |                                              |
| 2   | VCC_IN              | Voltage as-supplied by BEC.                  |
| 3   | RC_CH1              | |
| 4   | RC_CH2              | |
| 5   | RC_CH4              | |
| 6   | RC_CH5              | |
| 7   | RC_CH6/HC-SR04_ECHO | Enable `feature RANGEFINDER`                 |
| 8   | RC_CH7/HC-SR04_TRIG | Enable `feature RANGEFINDER`                 |

When RX_PPM/RX_SERIAL is used the IO_1 pinout is as follows.

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | VCC_IN         | Voltage as-supplied by BEC.                  |
| 3   | RX_PPM         | Enable `feature RX_PPM`                      |
| 4   | GPIO           |                                              |
| 5   | SoftSerial1_RX |                                              |
| 6   | SoftSerial1_TX |                                              |
| 7   | RC_CH6/HC-SR04_ECHO | Enable `feature RANGEFINDER`            |
| 8   | RC_CH7/HC-SR04_TRIG | Enable `feature RANGEFINDER`            |


### LED&RSSI Connector

| Pin | Function                  | Notes                                        |
| --- | ------------------------- | -------------------------------------------- |
| 1   | Ground                    |                                              |
| 2   | ADC_2                     | RSSI                                         |
| 3   | LED_STRIP                 | Enable `feature LED_STRIP`                   |
| 4   | VCC                       | +5V                                          |

### PWR Connector

| Pin | Function                  | Notes                                        |
| --- | ------------------------- | -------------------------------------------- |
| 1   | Ground                    | VDC Ground                                   |
| 2   | Ground                    |                                              |
| 3   | VBAT Detect               | Voltage Sensor                               |
| 4   | Current Detect            | Current Sensor                               |
| 5   | VCC_IN                    | VDC +5V                                      |
| 6   | VCC_IN                    | VDC +5V                                      |

### UART1 - OSD (Fig. ref5)

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | RXD1           |                                              |
| 3   | TXD1           |                                              |
| 4   | 5.0v           | Voltage as-supplied by BEC OR USB, always on |

### UART2 / I2C - GPS (Fig. ref8)

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | RXD2           |                                              |
| 3   | TXD2           |                                              |
| 4   | 5.0v           | Voltage as-supplied by BEC OR USB, always on |
| 5   | SDA            | Serial Data                                  |
| 6   | SCL            | Serial Clock                                 |

### UART3 - S.Bus (Fig. ref7)

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | RXD3           |                                              |
| 3   | TXD3           |                                              |
| 4   | 5.0v           | Voltage as-supplied by BEC OR USB, always on |

### SPK/DSM RX (Fig. ref6)

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | RXD3           |                                              |
| 2   | Ground         |                                              |
| 3   | 3.3v           |                                              |
