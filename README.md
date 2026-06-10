# Adaptive Neuromorphic E-Skin Readout IC (AT-LIF)

Project repository for the IEEE SSCS PICO Chipathon (Track B) edge-native MPW run using the gf180mcu PDK. 

This mixed-signal IC interfaces with multi-modal e-skin sensors, utilizing an Adaptive Threshold Leaky Integrate-and-Fire (AT-LIF) neuromorphic core to convert analog pressure into digital spike trains, featuring biomimetic habituation to save power.

## Dependencies

To manage all dependencies, the project template includes a Nix shell with all the required tools. Install Nix and LibreLane by following the Nix-based installation instructions:
[https://librelane.readthedocs.io/en/latest/installation/nix_installation/index.html](https://librelane.readthedocs.io/en/latest/installation/nix_installation/index.html)

To activate the shell, simply run `nix-shell` in the root directory of this repository. The subsequent steps assume that you are in the Nix shell of the project template.

## Prerequisites

The project template uses the open_pdks gf180mcuD variant of the PDK (leveraging 3.3V analog capabilities for our AFE). To clone the latest PDK version via Ciel, run:
```bash
make clone-pdk
