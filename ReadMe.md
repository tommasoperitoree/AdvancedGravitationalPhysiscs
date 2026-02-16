# Advanced Gravitational Physics - professor Emanuele Castorina
## Project by Tommaso Peritore (67043A) for exam of a.y. 2025-2026
# Advanced Gravitational Physics & Cosmology

## Overview
This repository contains the solutions to the "Advanced Gravitational Physics" coursework (February 2026). The project is divided into two main sections:
1.  **Gravitational Waves:** An analytical study of resonant mass detectors (spring-mass systems).
2.  **Cosmology:** A numerical and theoretical analysis of Gravitational Lensing of the Cosmic Microwave Background (CMB).

## Repository Structure

* **`main.pdf`**
    The comprehensive project report. It contains:
    * **Part 1 (GW):** Full analytical derivation of the equation of motion for a resonant mass detector, solution for the steady state, and energy calculations following the formalism of *Maggiore*.
    * **Part 2 (Cosmology):** Derivation of the lensed CMB power spectra equations (Temperature and Polarization) following the formalism of *Dodelson & Schmidt*.
    
* **`exam.ipynb`**
    The computational implementation of the CMB Lensing exercise.
    * Numerical evaluation of the lensed Temperature spectrum ($C_\ell^{TT}$).
    * Numerical evaluation of the lensed Polarization spectra, specifically the smoothing of $C_\ell^{EE}$ and the generation of $C_\ell^{BB}$ from pure E-modes.
    
* **`AGR_25_26.pdf`**
    The original problem sheet/assignment description.

* **`./data/test_lcdm_cl.dat`** and **`./data/test_lcdm_z0_pk.dat`**
    Input data file containing the unlensed $\Lambda$CDM power spectra and lensing potential used for the numerical integration as well as matter power spectrum for the deflection variance calculation.

---

## Part 1: Gravitational Wave Detection
*Theory Reference: Maggiore, Vol. 1*

This section (detailed in `main.pdf`) explores the physics of a resonant mass detector modeled as two masses connected by a spring. Key derivations include:
* The equation of motion for the system under the influence of a passing GW ($h_+$ polarization).
* The resonant frequency and quality factor analysis.
* Calculation of the system's total energy and the radiated energy.
* A feasibility study for detection using typical parameters ($L=10$m, $Q \sim 10^6$).

## Part 2: CMB Lensing
*Theory Reference: Dodelson & Schmidt, Modern Cosmology (2nd Ed), Chapter 13*

This section combines analytical derivations (`main.pdf`) with numerical results (`exam.ipynb`).

### Physics
We analyze how Large Scale Structure deflects CMB photons.

### Numerical Implementation (`exam.ipynb`)
The Python notebook implements the perturbative approach to compute the lensed power spectra:
1.  **Interpolation:** Cubic spline construction for input spectra ($TT, EE, \phi\phi$).
2.  **Deflection Variance:** Calculation of the damping factor $\sigma^2$ from the integral of the lensing potential.
3.  **Vectorized Integration:** A fast, vectorized 2D integration scheme to solve the mode-coupling integrals:
    * **Temperature:** Smoothing of acoustic peaks.
    * **Polarization:** Explicit calculation of the geometric rotation kernels ($\cos^2 2\beta$ and $\sin^2 2\beta$) to demonstrate the generation of **B-modes** from a pure E-mode source.

## Dependencies
To run `exam.ipynb`, the following Python packages are required:
* `numpy`
* `scipy`
* `matplotlib`


## References
* Dodelson, S., & Schmidt, F. (2020). *Modern Cosmology* (2nd ed.). Academic Press. (Specifically Chapter 13: Lensing).
* Maggiore, M. (2008). *Gravitational Waves: Volume 1: Theory and Experiments*. Oxford University Press.