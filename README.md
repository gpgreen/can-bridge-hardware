# Can-Bridge

Kicad design for a CAN to USB serial bridge. Based on a Nucleo-F103RB development board
with an arduino shield that provides the CAN transceiver for the CAN
controller that resides on the STM32F103RB device on the dev board.

![Can-bridge prototype](20240425_112557.jpg?raw=true "Can-Bridge prototype")

## CAN Hardware

The CAN controller on the Nucleo dev board, is routed to a MCP2551 transceiver on the
arduino daughter board. The two CAN outputs from the transceiver go to the CAN1 connector on
the daughter board. This connector is pinned:

 +---+
 | o | NC
[| o | CANH
[| o | CANL
 | o | NC
 +---+
  CAN1

A 120 ohm terminating resistor is also on the board. To use this resistor, set the DIP switch
position 1 to on.

## Firmware

The firmware is designed to be used with Serial CAN from the canutils project. Rust-based
firmware project is here ![firmware](https://github.com/gpgreen/slcan-bridge.git)

## Schematics

![Schematics](can-bridge.pdf)

## Development Board

![Nucleo F103RB](https://www.st.com/en/evaluation-tools/nucleo-f303re.html)
