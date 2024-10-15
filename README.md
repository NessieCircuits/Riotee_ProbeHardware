# Riotee Probe Hardware Design Files

[![Kibot ERC/DRC](https://github.com/NessieCircuits/Riotee_ProbeHardware/actions/workflows/test.yml/badge.svg)](https://github.com/NessieCircuits/Riotee_ProbeHardware/actions/workflows/test.yml)

The Riotee probe lets you program a Riotee module that is soldered onto your PCB or plugged into a breadboard. It has a standard 10-pin 0.1" connector compatible with the popular Tag-Connect cables that allow in-circuit debugging with a very small footprint.

Latest design files:
 - [Schematics](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/schematics.pdf)
 - [Layout](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/pcb.pdf)
 - [Assembly plan](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/assembly.pdf)
 - [3D rendering](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/3drendering.png)
 - [Gerber](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/gerber.zip)
 - [BOM](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/bom.csv)

Specification:
 - Custom debug probe for in-circuit programming/debugging of Riotee modules
 - USB-C connector for connection to a PC
 - Raspberry Pi RP2040 controller handles programming/debugging
 - CMSIS-DAP compatible: Supports programming of the Riotee module via pyOCD/OpenOCD
 - Makes UART output from Riotee module available via USB

![Rendering of Riotee probe](https://www.riotee.nessie-circuits.de/artifacts/probe_hardware/latest/3drendering.png "Riotee probe")

## Firmware

The probe has a dedicated controller (Raspberry Pi RP2040) that manages the upload of new firmware to the Riotee device as well as the communication with a PC. The firmware running on the RP2040 is hosted in [this repository](https://github.com/NessieCircuits/Riotee_ProbeFirmware). To upgrade the firmware on the Riotee probe, connect a wire from one of the ground pins to the test pad labelled 'USB_BOOT' on the bottom of the board, while plugging in the USB cable. A removable storage drive should appear on your PC. Drop a UF2 compatible binary into the drive.