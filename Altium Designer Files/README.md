# ADACUS Altium designer documentation

## Introduction
Welcome to the Adacus Mixed Signal Analyzer! Designed for precision and versatility, Adacus is a compact yet powerful tool that bridges the gap between oscilloscopes and digital analyzers. With a dual-probe input range of 20Hz to 20kHz, Adacus offers detailed signal analysis across a variety of applications, making it an essential instrument for hobbyists, engineers, and researchers alike.

Adacus is equipped with state-of-the-art peripherals, including SWD for debugging, USB for connectivity, and SPI for high-speed data transfer. This ensures seamless integration with your existing workflows and provides a robust platform for advanced signal analysis.


## Visual description
<p align="center">
  <img src="https://github.com/user-attachments/assets/985bbd4a-43a9-4dfc-9278-16ec77607d84" />
</p>
<p align="center">
Fig. 1 Top view
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/63119bfe-d7c6-4958-98dd-c79cb99341ce" />
</p>
<p align="center">
Fig. 2 Bottom view
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/04fed93b-4685-4203-b5bf-eeb6b8e70949"/>
</p>
<p align="center">
Fig. 3  3D Top view
</p>


<p align="center">
  <img src="https://github.com/user-attachments/assets/ef388c83-13df-41ca-b61c-e2533f18577e" />
</p>
<p align="center">
Fig. 4  3D Bottom view
</p>

## Technical description
This section focuses on the technical side of the board. It discusses the made connections and physical constrainst of the ADACUS. Section also includes the description of the layers used for the projects and general board stack-up. Lastly, EMC results for the board alsoi shared for further detailed analysis.


### Connection & Pin-out:
 SWD connector pin-out:
Only one of suchh connector was used for this PCB it was placed on te top layer with appropritiate pins given as below:

| NO# | PIN_NAME |   PIN_DESCRIPTION    |
| :-: | :------: | :------------------: |
|  1  |   +3V3   |  Power output +3V3   |
|  2  |   GND    |      Ground pin      |
|  3  |   GND    |      Ground pin      |
|  4  |  SWDIO   |   Serial debug I/O   |
|  5  |   GND    |      Ground pin      |
|  6  |  SWCLK   |     Serial clock     |
|  7  |    NC    | Pin is not connected |
|  8  |   SWO    |    Serial wire O     |
|  9  |   NRST   |        Reset         |
| 10  |    NC    | Pin is not connected |


For the MCU "STM32F103CBT6" was used from STM microcontroller family. It is compact and does not need additional connections to operate with 48 pins and fairly small size. One may see the used pins below(1*): 

| NO# | PIN_NAME   | PIN_DESCRIPTION         |
| :-- | ---------- | ----------------------- |
| 1   | VDD/+3V3   | Power input +3V3        |
| 5   | OSC_IN     | Oscillator input        |
| 6   | OSC_OUT    | Oscillator output       |
| 7   | NRST       | Reset                   |
| 8   | GND        | Ground pin              |
| 9   | VDDA/+3V3A | Analog power input      |
| 14  | SPI1/NSS   | Chip select             |
| 15  | SPI1/SCK   | Serial clock            |
| 16  | SPI1/MISO  | Master in slave out     |
| 19  | GPIO/NCLR  |                         |
| 20  | GPIO/NLDAC |                         |
| 23  | GND        | Ground pin              |
| 24  | +3V3       | Power input +3V3        |
| 25  | SPI2/NSS   | Chip select             |
| 26  | SPI2/SCK   | Serial clock            |
| 28  | SPI2/MOSI  | Master out slave in     |
| 32  | D-         | USB data line negative  |
| 33  | D+         | USB data line positive  |
| 34  | SWDIO      | Serial debug wire I/O   |
| 35  | GND        | Ground pin              |
| 36  | +3V3       | Power input +3V3        |
| 37  | SWCLK      | Serial debug wire clock |
| 39  | SWO        | Serial debug wire O     |
| 42  | TIM1       | Timer channel           |
| 43  | TIM2       | Timer channel           |
| 44  | BOOT       | Boot                    |
| 45  | TIM3       | Timer cannel            |
| 47  | GND        | Ground pin              |
| 48  | +3V3       | Power input 3V3         |

NOTE(1*): Only the used pins are marked here and discussed further. Rest of the pins are unconnected and therefore not mentioned hereafter. 

## Schematics
Schematic is devided into 4 internal sheets each containing different components based on the board functionality. Schhematic sheets can be given as below:

* Power_adacus_sch: Contains the power circuitry. Voltage converters for +3V3 and +3V3A(1*) power output as well as the bias generator for op-amp bias. Mechanical components(2*).

* MCU_adacus_sch: Includes main microcontroller schematics and relevant additional components such as oscillator, timer and power LED, SWD connector, USB and relative ESD protection ICs.

* DAC_adacus_sch: This sheet includes the general DAC circuitry. Whic in itself contains DAC circuitry and antialising filter consisting of op-amp. Finally, input connector is also placed in this schematic.

* Analog_adacus_sch: Finally analog front-end is placed on this schematic together with ADC for proper signal analysis. One may also find the output connector on this sheet.


NOTE(1*): +3V3A is generated due to the analog power use. For op-amps used on later stages of project.
NOTE(2*): Mechanical component such as mounting holes are placed on this schematic to avoid creating additional schematic document.


## Board stack-up
As mentioned previously board is designed to be 4 layer PCB. Following stack-up was used to ensure proper board funtionality:

| NO# | BOARD_LAYER  |  SIGNAL   |
| :-: | :----------: | :-------: |
|  1  |  TOP_LAYER   | SIG/POWER |
|  2  | MID_LAYER_1  |    GND    |
|  3  | MID_LAYER_2  |    GND    |
|  4  | BOTTOM_LAYER | SIG/POWER |

Once again such stack-up was implemented to make sure proper return path for top and bottom layer signal and power tracks. Moreover, internal ground planes are further sticked together with stiching vias placed on the top layer.

For the layer specifications JLCPCBs website for board manufacturing since the board is planned to be manufactured via them. One may see the grapical representation of the stack-up below:

<p align="center">
  <img src="https://github.com/user-attachments/assets/6d6013cc-bcba-41b8-89a0-d19c988c0383" />
</p>
<p align="center">
Fig. 5  Layer stack-up
</p>

Material and used layer thicknesses were taken from JLCPBCs. Manufacturer website link can be given as such for furter information: https://jlcpcb.com/impedance.

## Tracks & Vias
For the board designed 3 standard track width used. One may see such specifiations below:

 | NO# |       WIDTH       |               PURPOSE                | USED |
 | :-: | :---------------: | :----------------------------------: | :--: |
 |  1  |  0.3mm/11.811mil  |             Signal lines             | YES  |
 |  2  |  0.5mm/19.685mil  |              Power line              | YES  |
 |  3  | 0.293mm/11.535mil | Impedence matched signal ended track | YES  |

 Furthermore, for the USB data lines impedence matched track was used. Considering the board stack-up and standard impedance for differential pair (90 ohm). Following track width was used for the differential pair:

| NO# |      WIDTH       |                     PURPOSE                     | USED |
| :-: | :--------------: | :---------------------------------------------: | :--: |
|  1  | 0.286mm/11.26mil | Impedance matching track for differential pairs | YES  |
<p align="center">
  <img src="https://github.com/user-attachments/assets/88952e83-4397-4244-b3a5-3c905d8bb83a" />
</p>
<p align="center">
Fig. 5  Differential non-copolar pair impedance matching
</p>

