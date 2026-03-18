# High-Frequency-RF-Signal-Generator-Using-Discrete-Colpitts-Oscillator
This project demonstrates a high-frequency RF signal generator using a BJT-based circuit, validated through LTspice simulation and hardware implementation. The design explores gain, frequency response, and real-world effects, highlighting practical analog design and high-frequency behavior.
# High-Frequency RF Signal Generator Using Discrete Colpitts Oscillator

## Overview

This project demonstrates a high-frequency RF signal generator using a BJT-based circuit, validated through LTspice simulation and hardware implementation.

## Simulation

The circuit was analyzed in LTspice to study frequency response and gain behavior in the MHz range.

## Hardware Implementation

The circuit was built on a breadboard using a BC547 transistor and passive components. Care was taken to reduce noise and parasitic effects.

## Results

* Verified frequency response in simulation
* Stable waveform observed in hardware
* Demonstrates high-frequency operation

## Simulation Netlist

```spice
VCC Vcc 0 DC 9
Vin in 0 AC 1 SIN(0 10m 1Meg)

R1 Vcc base 100k
R2 base 0 10k

Q1 collector base emitter BC547

RC Vcc collector 1k
RE emitter 0 220

Cin in base 10n
Cout collector out 10n

RL out 0 10k
CE emitter 0 10u

.model BC547 NPN(IS=1e-14 BF=200)

.ac dec 100 1k 100Meg
.tran 0 10u

.end
```

## Images

### Simulation

![Simulation](results/frequency_response.png)

### Hardware

![Hardware](hardware/setup.jpg)

## Future Improvements

* Convert to true RF oscillator
* Add buffer stage
* PCB implementation
