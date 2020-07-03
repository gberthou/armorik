# ARMorik

This project proposes a simple platform that interfaces an ARM-based micro-controller (ATSAMS70, Cortex-M7-based) and non-volatile ferroelectric memory,
as an alternative to TI's MSP430FR series.

Industry lacks micro-controllers equipped with non-volatile RAM (NVRAM).
The only existing micro-controllers equipped with NVRAM have small RAM and NVRAM memories, not larger than a few kilobytes.
There is a need for micro-controllers with bigger RAM and NVRAM, implementing other architectures as well, such as ARM.

If such platforms do not exist yet, why not build one ourselves?
Here, the idea is quite simple:
take an ARM-based micro-controller which provides external pins for External Bus Interface (EBI) and which provides a Static Memory Controller (SMC).

## Hardware

- MCU: [ATSAMS70Q19](https://www.microchip.com/wwwproducts/en/ATSAMS70Q19) (ARM Cortex-M7)
- NVRAM: [FM28V202A](https://www.cypress.com/part/fm28v202a-tg) (256kB ferroelectric NVRAM)
- Socket for a [CC2500EMK](https://www.ti.com/tool/CC2500EMK) module
- [ADT7310](https://www.analog.com/en/products/adt7310.html) SPI temperature sensor
- NSL-4962 photoresistor

## Power supply

The platform is powered by a simple USB Micro-B cable.
With the onboard switch, you can choose whether you want to use the 2.2V supply or the variable supply.
The latter can be configured between 2V and 3.3V by using the onboard potentiometer.

## Programming

The platform embeds a socket for the SWD interface.
It was tested with the [Atmel ICE](https://www.microchip.com/DevelopmentTools/ProductDetails/ATATMEL-ICE) programmer.

## Code samples

My other project, [sytARM](https://gitlab.inria.fr/gabertho/sytarm), shows code and the required toolchain to make this code run on the ARMorik platform.
