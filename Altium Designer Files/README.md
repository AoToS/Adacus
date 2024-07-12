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
 Connector pin-out is as follows:

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

Moreover, following is the pinout of the MCU used for this project. Only the used pins were documented:

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