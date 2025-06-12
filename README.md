# Molecular_Dynamics

## Overview

This project focuses on molecular dynamics (MD) simulations to study the physical properties of germanium (Ge), using empirical interatomic potentials. The work is split into two parts:  
1. Calculating basic material properties such as cohesive energy, lattice constant, and bulk modulus for different crystal structures.  
2. Simulating the melting process of Ge by running MD at increasing temperatures and analyzing the structural changes.

The project was carried out as part of the **Computational Physics** course at the **Physics Department, University of Crete**.

## Goals

- Investigate structural and elastic properties of Ge in various crystal structures (diamond, FCC, BCC, SC) using the Stillinger-Weber potential.
- Estimate the melting temperature of Ge through temperature-dependent MD simulations.
- Study the phase transition using energy plots and the pair correlation function.

## Approach

- The Stillinger-Weber potential was used to model interactions between Ge atoms.
- Supercells were built for each crystal structure, and their total energy was calculated for a range of lattice constants using LAMMPS.
- The Murnaghan equation of state was fitted to the energy-volume data to extract equilibrium properties like cohesive energy and bulk modulus.
- To estimate the melting point, MD simulations were performed at different temperatures, monitoring changes in energy and structure.
- Structural transitions were analyzed using OVITO and the pair correlation function \( g(r) \).

### Implementation Details

- Supercells and simulations were set up using Jupyter notebooks (`crystals.ipynb`) and LAMMPS input files.
- Energy-volume data fitting was done in `murnaghanFit.ipynb`.
- MD simulations were run on 216-atom diamond Ge structures with a time step of 0.001 ps for 200,000 steps using `in.mel.lammps`.
- Data such as kinetic and potential energy were extracted from `energy.dat`.
- Structural visualization and analysis were performed in OVITO.

## Key Results

- The diamond structure had the lowest cohesive energy, confirming it as the most stable phase for Ge.
- Metastable structures like BCC and FCC showed higher energies but surprisingly high bulk modulus values due to dense atomic packing.
- The melting point was estimated around **1650–1660 K**, based on a sharp change in the potential energy and the loss of crystalline order.
- Pair correlation functions clearly showed the disappearance of long-range order above the melting point.

## Conclusions

- The Stillinger-Weber potential gives a good qualitative description of the structural and thermal behavior of Ge.
- The predicted melting point aligns reasonably with expected values, and the phase transition is well captured through both energy plots and structural data.
- Even with classical MD and empirical potentials, meaningful insights into material behavior can be obtained.

## How to Run

All simulations and analysis steps are available in:

- `crystals.ipynb`: builds and simulates the different crystal structures
- `murnaghanFit.ipynb`: fits the energy-volume data
- `in.mel.lammps`: runs MD simulations at different temperatures

Requirements:
- Python with NumPy, Matplotlib, Jupyter
- LAMMPS (must be installed and added to your PATH)
- OVITO (for visualization)

## Acknowledgements

Project by **Giorgos Kritopoulos**, for the Computational Physics course, **Physics Department, University of Crete**.  
Date: May 16, 2025
