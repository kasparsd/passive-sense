# Passive Sense

One module that can:

- Transmit and receive sensor data over RFM69 and RS-485.
- Connect RFM69 to Raspberry PI via SPI0.


## Components

- ATTiny84 microcontroller
- RFM69 radio transceiver
- MAX485/MAX1487 RS-485 transceiver


## Connections

RFM69 transceiver to ATTiny84 via USI-SPI since it doesn't have hardware SPI:

- MOSI to PA5 (USI-DO, instead of PA6)
- MISO to PA6 (USI-DI)
- SCK to PA4 (USI-SCK)
- NSS to PB2
- DIO0 to PA7

RFM69 transceiver to Raspberry PI SPI0 header:

- VCC to 3.3V (GPIO9)
- MOSI to MOSI (GPIO10)
- MISO to MISO (GPIO9)
- SCK to CLK (GPIO11)
- NSS to CE (GPIO8)
- DIO0 to GPIO25

MAX485 to ATTiny84 using software serial:

- RO to PA2 as RX
- DI to PA1 as TX
- DE and RE to PA3


## Layout and PCB

- [Schematics (PDF)](docs/assets/schematics.pdf)
- [PCB (PDF)](docs/assets/pcb.pdf)

See [easyeda.com/kasparsd/tiny-sensor-433mhz-rs485](https://easyeda.com/kasparsd/tiny-sensor-433mhz-rs485).
