# Simulation Files for MMC-Based Solid State Transformer

This folder contains PLECS simulation files for the Modular Multilevel Converter (MMC) based Solid State Transformer (SST) designed for data center applications.

## Folder Structure

### 📁 AC-AC MMC/
Open-loop AC-AC MMC converter simulations.

| File | Description |
|------|-------------|
| `ACAC_MMC_open_loop_nopower.plecs` | Open-loop AC-AC MMC simulation without power transfer, used for basic waveform verification |
| `ACAC_MMC_open_loop_SST.plecs` | Open-loop AC-AC MMC simulation for SST application with power transfer capability |

---

### 📁 Active bridge/
Dual Active Bridge (DAB) converter simulations for DC-DC isolation stage.

| File | Description |
|------|-------------|
| `Active_birdge.plecs` | Basic Dual Active Bridge converter model  controlled by dependent sources |
| `Active_birdge_interface.plecs` | DAB converter with electrical wire interface |
| `DAB_PAC.plecs` | Prototype with Pulse Amplitude Control (PAC) modulation |

---

### 📁 controller/
Controller subsystem models for MMC-SST control.

| File | Description |
|------|-------------|
| `DQ_current_controller.plecs` | DQ-frame current controller for AC-side current regulation |
| `Power_controller.plecs` | Power controller for active and reactive power regulation |

---

### 📁 midware model/
Middleware and utility models used as building blocks in the main simulation.

| File | Description |
|------|-------------|
| `3Phase_grid.plecs` | Three-phase grid voltage source model |
| `DeltaSigma_PSPWM.plecs` | Delta-Sigma modulation with Phase-Shifted PWM (single-phase) |
| `DeltaSigma_PSPWM_3phase.plecs` | Delta-Sigma modulation with Phase-Shifted PWM (three-phase) |
| `DeltaSigma2UpperLower.plecs` | Converter from Delta-Sigma reference to Upper/Lower arm references |
| `UpperLower2DeltaSigma.plecs` | Converter from Upper/Lower arm references to Delta-Sigma reference |
| `PAC_modulation.plecs` | Pulse Amplitude Control modulation block |
| `Power_cal_PAC.plecs` | Power calculation block for Pulse Amplitude Control |
| `Power_cal_PSC.plecs` | Power calculation block for Phase-Shift Control (PSC) |
| `PQ_cal.plecs` | Active (P) and Reactive (Q) power calculation block |

---

### 📁 MMC model/
Modular Multilevel Converter topology models.

| File | Description |
|------|-------------|
| `MMC_3phase_average.plecs` | Three-phase MMC average model (simplified for control design) |
| `MMC_HB_3phase.plecs` | Three-phase MMC with Half-Bridge (HB) submodules |
| `MMC_FB_3phase.plecs` | Three-phase MMC with Full-Bridge (FB) submodules |
| `MMC_FB_single.plecs` | Single-phase MMC with Full-Bridge submodules |

---

### 📁 MMC-SST/
Complete MMC-based Solid State Transformer closed-loop simulations.

| File | Description |
|------|-------------|
| `Close_loop_MMC_SST_average.plecs` | Closed-loop MMC-SST using average model for control verification without power transfer (dependent source )|
| `Close_loop_MMC_SST_average_electrical.plecs` | Closed-loop MMC-SST with average model with electrical connected interface |

---

### 📁 verification/
Verification and test files for individual subsystem validation.

| File | Description |
|------|-------------|
| `3Phase_grid_verify.plecs` | Verification of three-phase grid model |
| `DeltaSigma_PSPWM_verify.plecs` | Verification of Delta-Sigma PSPWM modulation (single-phase) |
| `DeltaSigma_PSPWM_3phase_verify.plecs` | Verification of Delta-Sigma PSPWM modulation (three-phase) |
| `DQ_current_controller_verify.plecs` | Verification of DQ-frame current controller |
| `MMC_3phase_average_verify.plecs` | Verification of three-phase MMC average model |
| `MMC_FB_3phase_verify.plecs` | Verification of three-phase Full-Bridge MMC |
| `MMC_FB_single_verify.plecs` | Verification of single-phase Full-Bridge MMC |
| `PAC_modulation_verify.plecs` | Verification of PAC modulation block |
| `PAC_modulation_verify_copy.plecs` | Copy of PAC modulation verification (for comparison tests) |
| `Power_cal_PAC_verify.plecs` | Verification of power calculation for PAC |
| `PQ_cal_verify.plecs` | Verification of PQ calculation block |
| `PQ_controller_verify.plecs` | Verification of PQ controller |

---

## Simulation Software

All simulation files are created using **PLECS** (Piecewise Linear Electrical Circuit Simulation).

## Usage Guide

1. **Start with verification files**: Use files in the `verification/` folder to understand and validate individual subsystems
2. **Build up complexity**: After understanding subsystems, move to the complete system models in `MMC-SST/`
3. **Average vs Switching models**: Use average models (`*_average.plecs`) for faster simulation and control design; use switching models for detailed analysis

## Abbreviations

| Abbreviation | Full Name |
|--------------|-----------|
| MMC | Modular Multilevel Converter |
| SST | Solid State Transformer |
| DAB | Dual Active Bridge |
| HB | Half-Bridge |
| FB | Full-Bridge |
| DQ | Direct-Quadrature (reference frame) |
| PAC | Pulse Amplitude Control |
| PSC | Phase-Shift Control |
| PSPWM | Phase-Shifted Pulse Width Modulation |
| PQ | Active Power (P) and Reactive Power (Q) |

---

*This simulation package is part of the Master Thesis project: Solid State Transformer for Data Center Applications.*
