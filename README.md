# TuchAudio 102
Discrete, _tube-like_ phono preamp.

_**NO LONGER RECOMMENDED, use [TuchAudio 103]() instead.**_

## Purpose
Discrete, non-op-amp classic design phono preamp, made as simple as possible.

## Design quirks
_After_ the original PCB was ordered, overload margin was deemed insufficient; thus a **hack** was made, essentialy _swapping the two first stages_ of the preamp.

DIN and RCA jacks are provided for signal input. Since the _native_ input impedance is around **110 kΩ**, space for suitable load (`Rx` and `Cx`) is provided for perfect adaptation; but for added flexibility, it is possible to use the free input for a suitable RC combo in parallel, to match the appropriate cartridge load.

Originally intended to be connected thru the [501 Input Selector board](), both output pins and power input are at compatible locations within each board. An aditional RCA **output** jack can be installed in order to use the circuit as a _stand-alone preamp_.

### Stability

As any other amplifier with _asymmetrical power supply_, the PSRR is very poor, thus a **well filtered, stable** power supply is essential. Increasing (within reason) `R114/R214` may help a bit.

This circuit has proved to be _quite sensitive to capacitor quality_, especially at `C102/C103/C202/C203` positions which, in some cases, may lead to **instability**. For all these reasons we recommend using the [103 Phono Preamp]() instead, which is a direct replacement in the very **same form factor**.

### Suggested mods

#### Standalone mode

Despite being designed around a 12 Volt power supply, this can be run from a single **9 Volt battery**, with minor changes and similar performance.

- `R114/R214`: use **120 Ω** instead of 180.
- `R111/R211`: use **2.7 kΩ** instead of 3K3.
-  ...

#### IEC1976/Neumann ammendments

The stated values are designed around these _ammendments_ to the **RIAA curve**; but since they're currently _deprecated_, you may get **improved bass response** by turning back to RIAA correction:

- `C105/C205`: do not mount (Neumann ammendment)
- `C107/C207`: use **220 nF** or more instead of 100 nF (which made a _-3 dB point at 20 Hz_ **over 108 kΩ** of the _501 board_ input)

## Specs

- **Power supply:** 9-12 V, asymmetrical, max. 6 mA
- **Input connectors:** 2x RCA plus DIN (in parallel)
- **Gain at 1 kHz:** 50x (+34 dB)
- **Input sensitivity:** 3.6 mV (for 180 mV output)
- **Input impedance:** 108 kΩ; adjusted by `Rx/Cx`, either internal or external.
- **Output level and impedance:** 180 mV / 3.3 KΩ
- **Overload margin:** at least +15 dB
- **Signal-to-noise ratio:** TBD
- **Frequency response:** 32 Hz - 20 kHz _(+1.5/-2 dB deviation from RIAA; -3 dB beyond audible range)_
- **Distortion:** (most notably from **2nd harmonic**, which may resemble **tube sound**)

| Harmonic | nominal output | +15 dB overload |
| -------- | -------------- | --------------- |
| 2nd      | 0.55 %         | **8 %**         |
| 3rd      | 0.16 %         | 0.59 %          |
| 4th      | 0.08 %         | 0.28 %          |
| 5th      | negligible     | 0.08 %          |
