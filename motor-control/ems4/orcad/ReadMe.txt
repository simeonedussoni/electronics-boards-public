EMS4 schematics 0 errata/corrige:

1) The interrupt signals from devices U12 e U13 (accelerometer and gyroscope) 
   were not correctly labeled so they are not properly routed:
   - The interrupts from U12 do not reach the microcontroller
   - The interrupts from U13 are not termitated with a pullup-resistor
   This error should be corrected as follows:
   - Schematic page 7: The pins INT1 and INT2 of U12 must be connected to the
     signals ~EXIRQ8 and ~EXIRQ9
   - Schematic page 7: The pins INT and DRDY of U13 must be connected to the
     signals ~EXIRQ11 and ~EXIRQ12
   - Schematic page 2: The inter-sheet reference ~EXTIRQ0 and ~EXTIRQ1
     must be renamed ~EXTIRQ11 and ~EXTIRQ12
   - Schematic page 2: The pullup resistors R139 an R140 must be connected to
     the signals ~EXIRQ8 and ~EXIRQ9

EMS schematics 1 errata/corrige

1) The ethernet reference clock generated by the STM32F407 is affected by an
   excessive long term jitter error. This problem can be minimized with a
   software patch, but a new PCB release should be planned, with a dedicated
   oscillator driving the ETH_REFCLK signal.

2) The ethernet protection networks R49, DZ1, R52, DZ2 may cause an excessive
   signal distortion and should be eliminated


EMS schematics 2 errata/corrige

1) R147 and R148 values are exchanged. The correct values are:
   R147 NM/0402 (not mounted)
   R148 0R/0402 (0 ohm jumper)
