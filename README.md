# SLAMS-2.0

**Stochastic, Lagrangian Aggregate Model of Sinking particles, v2.0**

SLAMS-2.0 is a modular, high-performance particle-resolving framework designed to simulate biogenic marine particle attributes and their dynamics within the ocean's biological carbon pump. 

The model combines stochastic process representation and Lagrangian particle tracking with physically grounded aggregation and settling dynamics to investigate how particulate organic carbon is transferred from the surface ocean to depth.

## Key Features

- Stochastic Lagrangian particle-resolving framework
- Super-Droplet Method ([Shima et al., 2009](https://doi.org/10.1002/qj.441)) for efficient resolution of particle interaction dynamics
- Physically grounded particle evolution via fractal scaling and Reynolds-number-dependent settling
- Explicit resolution of aggregation, fragmentation, and zooplankton-mediated repackaging
- Particle fluxes and size spectra emerge diagnostically from explicit depth crossings
- One-dimensional water-column framework scalable to global grids via independent column execution
- Modular Fortran core with Bash workflow control and MATLAB analysis tools

## Computational Design

SLAMS-2.0 adopts a layered architecture separating:
1. Model (**Fortran 90**)
   - Core SLAMS-2.0 simulation engine
   - Reads binary forcing files
   - Scientific parameters configurable via `namelist`
2. Workflow orchestration (**Bash**)
   - Environment initialisation
   - Compilation
   - Forcing management
   - Experiment orchestration
   - SLURM job submission with scalable job arrays (HPC-ready)
3. Pre/post-processing (**MATLAB**)
   - Converts `.mat` forcing datasets into model-ready `.bin` inputs
   - Aggregates model output into `.mat` files
   - Computes derived diagnostics (e.g., biological pump metrics)

## Applications

- Resolving particle-scale controls on carbon transfer efficiency
- Integrating process-based modelling with in situ observations of marine aggregate structure, particle dynamics, size distributions, and biogeochemical fluxes
- Exploring how climate-driven changes in ocean conditions influence carbon transfer efficiency
- Developing quantitative marine carbon cycle diagnostics

## Availability

The full implementation is currently maintained in a private repository while the associated manuscript is under review at the journal *JAMES* (*Journal of Advances in Modeling Earth Systems*). The code will be made publicly available upon publication.

## Development

SLAMS-2.0 was designed and implemented as a primarily independent research effort, reflecting end-to-end responsibility for model architecture, computational implementation, and scientific framework development.

The model originated during my PhD research at the University of Oxford (2016–2022) under the NERC large grant *COMICS* (Controls over Ocean Mesopelagic Interior Carbon Storage; NE/M020835/2) and has continued development with support from the European Space Agency (ESA) Living Planet Fellowship *SLAM DUNK* (Contract No. 4000144464/24/I-DT-lr).

The original model concept was developed by [Dr. Tinna Jokulsdottir and Prof. David Archer](https://doi.org/10.5194/gmd-9-1455-2016) (2016), whose work laid the scientific groundwork for SLAMS-2.0.


**IMPORTANT**: Please do NOT post the SLAMS-2.0 code or any files downloaded from this repository on your own GitHub or other website. See LICENSE for licensing information.
