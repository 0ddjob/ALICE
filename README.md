# ALICE MULTI-PORT EXTENSION #

This extension expands the capabilities of MATRA ALICE computers (4K, 32, and 90).  
It adds:  
- two DB9 joystick ports  
- 16KB of RAM  
- two rear extension ports identical to the one on the ALICE  
- A cartridge port on the top  

It is also compatible with the Tandy TRS-80 MC10 (identical to the ALICE 4K).  

![Multi-port extension](./Extension.jpg?raw=true "Optional Title")  

This project was carried out in collaboration with 6502man for the software component.  

![Main board](./EXP_Alice.jpg?raw=true "Optional Title")  

## Joystick Ports  
The joystick ports are compatible with the joystick extension marketed at the time.  
They occupy the addresses $BF30 (48944) for the right joystick and $BF34 (48948) for the left joystick.  

## RAM  
The 16KB of RAM occupies the address range [$5000-8FFF]. It can be disabled using a micro-switch accessible at the back of the box. A modified version of the PLD program allows this RAM to be extended to 24KB [$5000-AFFF], enabling an ALICE 32 to be upgraded to an ALICE 90. However, this modification makes the extension incompatible with the 4K model.  

## Extension Ports  
The box features two rear extension ports, addressing the major limitation of the ALICE, which can only connect one extension at a time.  
The two ports are identical to the one on the ALICE. The SEL signals are connected via diodes to allow the simultaneous use of multiple extensions.  

## Cartridge Port  
A cartridge port is located on the top of the box. It allows the addition of game or language cartridges.  
These cartridges have a 64KB memory, divided into eight 8KB or four 16KB blocks depending on the use.  

### Cartridge Mode  
In this mode, the cartridge is mapped to the address range [$1000-2FFF], i.e. 8KB. It is possible to select the memory from eight blocks (8x8KB). The block selection is done by writing to the address range [$1000-1FFF].  
Block '0' is automatically selected upon power-up.  

### ROM Mode  
In this mode, the cartridge is mapped to the address range [$C000-FFFF], i.e. 16KB. It is possible to select the memory from four blocks (4x16KB). The block selection is done by writing to the address range [$C000-CFFF].  
Block '0' is automatically selected upon power-up.