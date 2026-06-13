# HFSS On-Chip Spiral Inductors

This repository contains the design, simulation and analysis of on-chip spiral inductors using **Ansys HFSS**.
The project was developed for the course **Telecommunication Electronics**.

The main objective is to model different inductor geometries, extract their electromagnetic behavior through S-parameters and compare their performance using the quality factor `Q`.

## Project Overview

The project includes the HFSS design and simulation of the following structures:

* Square spiral inductor with 2.5 turns
* Square inductor with 1 turn
* Octagonal inductor with 1 turn
* Circular inductor with 1 turn

All inductors are implemented on a silicon substrate with a silicon dioxide insulating layer and copper metal layers.

## Design Parameters

The main design parameters used in the project are:

```text
Outer diameter: D = 170 μm
Metal width: w = 11 μm
Spacing: s = 2 μm
Substrate material: Silicon
Insulating layer: SiO₂
Metal material: Copper
```

For the 2.5-turn square spiral inductor, the model also includes:

* Metal 9 spiral inductor
* Metal 8 underpass
* Via connection between Metal 8 and Metal 9
* Two lumped ports for excitation and S-parameter extraction

## Simulation Setup

The simulations were performed in Ansys HFSS using a terminal network setup.

For the 2.5-turn square spiral inductor:

```text
Frequency range: 1 GHz – 160 GHz
Solution frequency: 160 GHz
Sweep type: Interpolating
Maximum number of passes: 10
Maximum Delta S: 0.02
Ports: 2 lumped ports
```

For the comparison between the 1-turn square, octagonal and circular inductors:

```text
Frequency range: 1 GHz – 200 GHz
Solution frequency: 200 GHz
Sweep type: Interpolating
Maximum number of passes: 10
Maximum Delta S: 0.02
```

## Extracted Quantities

The following quantities are extracted from the HFSS simulation results:

* S-parameters
* Reflection coefficient `S11`
* Transmission coefficient `S12`
* Inductance `L`
* Resistance `R`
* Quality factor `Q`

The impedance is calculated from the admittance parameter:

```math
Z = \frac{1}{Y_{11}}
```

The extracted values are then computed as:

```math
L = \frac{\operatorname{Im}(Z)}{2 \pi f}
```

```math
R = \operatorname{Re}(Z)
```

```math
Q = \frac{\operatorname{Im}(Z)}{\operatorname{Re}(Z)}
```

## MATLAB Post-Processing

MATLAB is used to process the exported HFSS data and create common comparison plots.

The quality factor of the different inductor geometries is plotted on the same graph in order to compare their RF performance.

## Results Summary

The simulation results show that the quality factor generally increases with frequency for the examined structures.

The comparison between the geometries shows that the inductor shape affects the quality factor.
The circular inductor provides smoother current distribution because it has no sharp corners.
The octagonal inductor behaves as an intermediate solution, while the square inductor is more affected by its sharp corners.

Overall, the results confirm that geometry plays an important role in the RF behavior and efficiency of on-chip spiral inductors.

## Repository Structure

```text
.
├── si_spiral_ind.aedt      # Ansys HFSS project file
├── report.pdf              # Full project report with designs, simulations and results
└── README.md
```

## Requirements

To open and run the project, the following software is required:

* Ansys Electronics Desktop / HFSS
* MATLAB, for post-processing and comparison plots

## How to Use

1. Open the `.aedt` file in Ansys Electronics Desktop.
2. Select the desired inductor design.
3. Run the HFSS simulation setup.
4. Export the S-parameter or output variable data.
5. Use MATLAB to compare the quality factor curves.

## Topics

* Ansys HFSS
* RF Simulation
* Spiral Inductors
* S-Parameters
* Quality Factor
* On-Chip Passive Components
* Microwave Engineering
* MATLAB Post-Processing
