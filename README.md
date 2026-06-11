# Advanced Lab: Mössbauer Spectroscopy ⚛️

> **🚧 Work in Progress (WIP):** The current repository focuses on the preliminary velocity calibration. The evaluation is actively ongoing.

## About the Project
This repository contains the Python-based data analysis pipeline for Mössbauer spectroscopy, conducted as part of the Advanced Physics Lab. 
downloades via https://fs-mcp.pages.desy.de/nuclear-nexus/examples/examples.html#evaluation-of-a-moessbauer-spectrum
* **SciPy (`curve_fit`)** for complex non-linear least squares fitting
* **NumPy & Pandas** for data manipulation, arrays, and export
* **Matplotlib** for scientific data visualization

## Repository Structure
* `/data` - Contains the raw `.ws5` machine data files for both the α-Fe reference and the stainless steel sample.
* `/notebooks` - Jupyter notebooks containing the step-by-step analysis and fitting pipeline.
* `/results` - Exported CSV datasets and plotted spectra.

## Current Status
We are currently fine-tuning the Lorentzian fits for the α-Fe spectrum to finalize the velocity calibration. Once the calibration parameters are solidly established, the code will be applied to the stainless steel measurements.

**Team:** Trinity Hopp & Nelly Patsche  
**Supervisor:** Dr. Sakshath Sadashivaiah  

The experiment is structured in two main phases:
1. **System Calibration (Current Focus):** Processing the raw `.ws5` experimental data of an α-Iron (α-Fe) reference sample. This involves folding the spectrum to establish symmetry and applying a 6-peak Lorentzian fit to analyze the hyperfine splitting and extract the precise velocity calibration parameters.
2. **Sample Analysis (Next Step):** Applying this established calibration pipeline to evaluate the actual target sample, which is a stainless steel (Edelstahl) absorber.

## Tech Stack & Methods
* **Python** for the overall data pipeline, Jupiter Notebooks 
